<table>
  <tr>
    <th style="color:#8A2BE2; font-size:20px;">⚠ Important</th>
  </tr>
  <tr>
    <td>This part was made by <strong>Velichko David, Skliarovskyi Danylo, Preobrazhenskyi Danylo</strong>.</td>
  </tr>
</table>

## 1. В ході роботи досить часто виникає завдання планування задач:
### Охарактеризуйте основні функції які може виконувати планувальник завдань в будь-якій ОС. Порівняйте можливості планування завдань в різних ОС на прикладі Windows та Linux.

**Task scheduler** is a system service that allows you to automatically run scripts, programs, or commands at a specified time or when a specific event occurs. Main functions:

- automation of routine tasks (archiving, log cleaning, backup);

- running programs on a schedule;

- periodic system or program updates;

- scheduling system maintenance (reboots, shutdowns, etc.);

- responding to events (only in some operating systems).

| Feature / Capability             | **Windows Task Scheduler**                                        | **Linux Cron**                                                  |
|----------------------------------|-------------------------------------------------------------------|------------------------------------------------------------------|
| User interface                   | Graphical UI + CLI (`schtasks`, PowerShell)                      | Text-based `crontab` files                                      |
| Schedule flexibility             | High — GUI wizard and full scripting                             | Very high — via time fields and special keywords                |
| Event-based scheduling           | Yes — system boot, login, log event triggers                     | Limited — only `@reboot` supported                              |
| One-time tasks                   | Fully supported (via Task Scheduler or `at`)                     | Not natively (use `at` command or hacks with `cron`)            |
| Logging and monitoring           | Integrated Event Viewer                                           | Requires manual logging (e.g. `>> logfile.log`) or syslog       |
| Default availability             | Built-in                                                         | Built-in in most Linux distributions                            |
| Recovery after missed runs       | Supported (retries and run-on-start options)                     | Not supported by default; use `anacron` or similar              |
| Alternative tools                | PowerShell Scheduled Jobs, Azure Automation                      | `anacron`, `fcron`, `systemd timers`, `at`                      |


### Опишіть основні принципи роботи з планувальником Cron в ОС Linux. Як його налаштовувати? Чи є йому альтернативи (дайте їх характеристику).

- **The Cron daemon** starts when the system boots and periodically (every minute) checks the schedule tables (`crontab`), both system (`/etc/crontab`, `/etc/cron.d/…`) and user (`crontab -e`).

- **The record format** has five time fields and a command:

```
┌───────── minute (0–59)
│ ┌─────── hour (0–23)
│ │ ┌───── day of month (1–31)
│ │ │ ┌─── month (1–12)
│ │ │ │ ┌─ day of week (0–7; 0=Sunday)
│ │ │ │ │
* * * * * /path/to/command arg1 arg2
```

- **Special lines:**

- `@reboot` — run at system startup

- `@daily`, `@hourly`, `@weekly`, `@monthly`, `@yearly` — conditional labels for standard intervals

- **Settings:**

1. `crontab -e` — open the editor for the current user.

2. Add or change entries.

3. `crontab -l` — view the current schedule.

4. `systemctl status cron` — check the status of the daemon (Ubuntu/Debian) or `crond` (CentOS/RHEL).

- **Logs** are usually stored in `/var/log/cron` or `/var/log/syslog` (depending on the distribution); you can also redirect task output to your own files:

`0 2 * * * /usr/local/bin/backup.sh >> /var/log/backup.log 2>&1`

### Alternatives to Cron in Linux

| Tool              | Description                                                                                  |
|-------------------|----------------------------------------------------------------------------------------------|
| **Anacron**        | Runs missed tasks after the system boots. Ideal for systems that are not always on.         |
| **fcron**          | Combines features of `cron` and `anacron`. Supports flexible scheduling and non-root users. |
| **systemd timers** | Modern replacement using `systemd`. Allows calendar-based schedules and persistence.        |
| **at**             | Executes a task once at a specific time. Not suitable for recurring jobs.                   |
| **OpenRC cron**    | A cron-compatible scheduler used in OpenRC-based systems. Lightweight alternative.          |

2. Для вашої віртуальної машини зі встановленою ОС Linux здійсніть планування обраних вами задач (запуск додатків, вмикання/вимикання машини, очистка каталогів, видалення файлів, резервне копіювання, архівування тощо на ваш вибір) через планувальник Cron:
   
- Виконання спланованої задачі в чітко визначений Вами час (наприклад о 8 ранку, 18.30 і т.д.).
  
```
# Створення скрипта backup.sh
cat << 'EOF' > ~/cron-scripts/backup.sh
#!/bin/bash
# Архівування домашньої теки
mkdir -p /home/username/backups

tar czf /home/username/backups/home_$(date +%F).tar.gz /home/username
EOF
chmod +x ~/cron-scripts/backup.sh

# Додавання задачі в crontab
crontab -e
# Додати рядок:
0 8 * * * /home/username/cron-scripts/backup.sh >> /home/username/cron.log 2>&1
```

![image](https://github.com/user-attachments/assets/34b95592-89a0-4edb-a544-55798112923e)

- Виконання однієї й тієї ж задачі двічі в день (час також визначаєте самостійно).

`0 6,18 * * * /home/username/cron-scripts/backup.sh >> /home/username/cron.log 2>&1`

![image](https://github.com/user-attachments/assets/a3524d52-1280-45dc-a8ab-b8353d011333)

- Виконання однієї й тієї ж задачі тільки в будні (або тільки у вихідні дні) у чітко визначений проміжок часу (наприклад з 8 до 18 години).

```
cat << 'EOF' > ~/cron-scripts/cleanup.sh
#!/bin/bash
# Видалення файлів старших за 7 днів у /tmp
find /tmp -type f -mtime +7 -delete
EOF
chmod +x ~/cron-scripts/cleanup.sh
```

`0 8-18 * * 1-5 /home/username/cron-scripts/cleanup.sh >> /home/username/cron.log 2>&1`

![image](https://github.com/user-attachments/assets/d0bf90f2-ab9e-4fe4-9eaf-92032126b0f1)

- Виконання задач тільки раз у рік, раз у місяць, раз у день, щогодини, при вмиканні (після перезавантаження).

```
# Раз у рік — 1 січня о 00:00
0 0 1 1 *   /home/username/cron-scripts/backup.sh >> /home/username/cron.log 2>&1
# Раз на місяць — 1-го числа о 02:00
0 2 1 * *   /home/username/cron-scripts/backup.sh >> /home/username/cron.log 2>&1
# Раз на день — щодня о 03:30
30 3 * * *  /home/username/cron-scripts/cleanup.sh >> /home/username/cron.log 2>&1
# Щогодини — 5 хвилин кожної години
5 * * * *   /home/username/cron-scripts/cleanup.sh >> /home/username/cron.log 2>&1
# При перезавантаженні (reboot)
@reboot     /home/username/cron-scripts/startup.sh >> /home/username/cron.log 2>&1
```

![image](https://github.com/user-attachments/assets/b2f0447f-8d32-497c-826f-508841e842cf)

3. Встановіть альтернативний Cron’у планувальник задач (на Ваш вибір). Виконані у завданні 2 дії продемонструйте через нього.

**3.1. Створення Service Unit**

```
# ~/.config/systemd/user/backup.service
[Unit]
Description=Резервне копіювання домашньої теки

[Service]
Type=oneshot
ExecStart=/home/username/cron-scripts/backup.sh
```

**3.2. Створення Timer Unit**

```
# ~/.config/systemd/user/backup.timer
[Unit]
Description=Таймер: запуск backup.service о 06:00 та 18:00

[Timer]
OnCalendar=*-*-* 06:00:00
OnCalendar=*-*-* 18:00:00
Persistent=true

[Install]
WantedBy=timers.target
```

**3.3. Активація та перевірка**

```
# Перезавантаження конфігурації
systemctl --user daemon-reload
# Увімкнення і старт таймера
systemctl --user enable --now backup.timer

# Перевірка таймера
systemctl --user list-timers
systemctl --user status backup.timer
```

![image](https://github.com/user-attachments/assets/91f3c661-bc85-40f9-bad9-770ab76a86ca)



   

