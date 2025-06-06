<table>
  <tr>
    <th style="color:#8A2BE2; font-size:20px;">⚠ Important</th>
  </tr>
  <tr>
    <td>This part was made by <strong>Velichko David, Skliarovskyi Danylo, Preobrazhenskyi Danylo</strong>.</td>
  </tr>
</table>

### 1. При роботі з серверними системами або на комп’ютерах, що досить обмежені у ресурсах, досить часто графічну оболонку вимикають або взагалі не встановлюють. Іноді виникають задачі, які здається, що без графічної оболонки виконати не можливо, проте для ОС Linux це не так. Спробуйте через термінал виконати наступні дії та поясніть за допомогою яких команд (пакетів) їх можна виконати.

#### 1.1 Перегляд файлів та папок через файловий менеджер у терміналі.

```
sudo apt update
sudo apt install -y ranger
ranger
```
![image](https://github.com/user-attachments/assets/4ab239aa-2862-4a5f-b65c-f2534df68df9)

#### 1.2 Переглядати веб-сторінки через браузер, що працює у терміналі.

```
sudo apt install -y w3m
w3m https://www.google.com
```
![image](https://github.com/user-attachments/assets/f8bcb576-f4ba-4c6a-b953-92fc0dcc0804)

#### 1.3 Перегляд електронної пошти в терміналі.

```
sudo apt install -y mutt
mutt
```
![image](https://github.com/user-attachments/assets/5621c3f5-3778-42e5-a1fc-16252961d863)

#### 1.4 Слухати музику через термінал.

```
sudo apt install -y cmus
cmus
```

Inside `cmus`:

- `5` — Go to the library
- `Enter` — Play the selected file
- `q` — Exit the program

![image](https://github.com/user-attachments/assets/37337c7e-d6e4-4c36-ae0c-624045ff6256)

#### 1.5 Скачувати торенти через термінал.

```
sudo apt install -y rtorrent
rtorrent
```

Inside `rtorrent`:

- `Enter` on the line with `.torrent` — Add tracker
- `Ctrl`+`q` — Exit the program

![image](https://github.com/user-attachments/assets/d34c8cc2-1568-4ec5-b692-dc73cf9e00f5)

#### 1.6 Планувати дії в календарі та нагадувати про них через термінал.

```
sudo apt install -y calcurse
calcurse
```

Inside `calcurse`:

- `a` — Add appointment
- `C` — Go to calendar view
- `h` — Call help

![image](https://github.com/user-attachments/assets/4d76076d-e235-482e-8ec9-ca2c09779345)

#### 1.7 Переглядати зображення в терміналі

```
sudo apt install -y fim
fim /шлях/до/файлу/картинка.png
```

In `fim`:

- `q` — Exit

![image](https://github.com/user-attachments/assets/5c6bd94a-1af4-491a-9876-780363b1b5d5)

### 2. Існують також дії які є класичними для більшості адміністраторів та мають досить різноманітний функціонал. Опишіть різні програми (команди, пакети) та встановіть по одній на кожну дію у терміналі

#### 2.1 Вводити, редагувати, видаляти текст (редактори файлів).

```
sudo apt update
sudo apt install -y vim
vim /path/to/file.txt
```
Basic keys in `vim`:

- `i` — Insert mode
- `Esc` — Exit to command mode
- `:` `w` — Save changes (write)
- `:` `q` — Exit (quit)
- `:` `wq` — Save and exit

![image](https://github.com/user-attachments/assets/a94a67f9-d15b-4b02-9bd0-92879ceed374)

#### 2.2 Здійснювати моніторинг процесів та ресурсів системи (аналог диспетчера задач або системного монітора в графічній оболонці).

```
sudo apt update
sudo apt install -y htop
htop
```

Main keys in `htop`:

- `F2` — Setup
- `F3` — Search
- `F4` — Filter
- `F6` — Sort by
- `F9` — Kill
- `q` — Exit

![image](https://github.com/user-attachments/assets/fd89feb5-1500-45ad-92a2-f2fa2d4a5da5)

### 3. Задачі, щоб підняти настрій посеред робочого процесу ☺ – так звані «пасхалки» (нажаль підтримуються не всіма дистрибутивами)

#### 3.1 Якщо Ви мрієте про подорож, то термінал може Вам показати зображення парового локомотиву з вагоном (гарний натяк на дорогу).

```
sl
```
![image](https://github.com/user-attachments/assets/dcd112a4-fa53-420b-9b83-12048ed5e76b)

#### 3.2 Якщо Ви фанат зоряних війн, то термінал може їх Вам показати.

```
telnet towel.blinkenlights.nl
```

**Пасхалко вже не підтримується**

#### 3.3 Якщо ви любите тварин, то термінал Вам може організувати діалог з коровою.

```
cowsay "Lets watch deMO"
```
![image](https://github.com/user-attachments/assets/23ce5d88-9741-4a30-b1f3-87572046ff97)

#### 3.4 Інші інтерактиви

- `nyancat` — анімація Nyan Cat

![image](https://github.com/user-attachments/assets/06e79985-a5b1-4a28-9f4d-45930b34024a)

- `oneko` — кішка за курсором

![image](https://github.com/user-attachments/assets/50c5b1aa-d2cc-489d-abbf-e1840dd5d9aa)
