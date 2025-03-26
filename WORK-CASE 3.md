<table>
  <tr>
    <th style="color:#8A2BE2; font-size:20px;">⚠ Important</th>
  </tr>
  <tr>
    <td>This part was made by <strong>Skliarovskyi Danylo, Preobrazhenskyi Danylo, Velychko David.</strong>.</td>
  </tr>
</table>

### 1. В робочому середовищі віртуальної машини Virtual Box, VMWare Workstation (або інший на Ваш вибір) необхідно виконати:

- Клонування вашої віртуальної робочої ОС (Work-case 2). Яким чином це можна зробити? Продемонструйте всі етапи;

![1](https://github.com/user-attachments/assets/ad15388c-613e-4bf0-a8c2-d68934b50313)

1: Select your virtual machine.
2. Click Right-click → Clone.
3.Enter a new name, for example: Ubuntu-Clone.
4.Full clone - to create an independent copy.
5.Current state only. 6. Click Next → Clone.

You may need to transfer (clone) the OS to another virtual environment. What steps do you need to take to export your virtual desktop OS? 1. Select a virtual machine → File → Export Appliance.
2.Select the machine to export → Next.
3.Format: OVF 2.0 → Next.
4. Set the path to save the file → Export.

### 2. В ході роботи одна робоча віртуальна машина може взаємодіяти з іншою. Для цього необхідно між ними розгорнути мережу. Опишіть які типи організації мережевих з’єднань підтримуються в середовищі віртуальних машин, в чому особливість кожного з них:

### Трансляція мережевих адрес (NAT);

**Definition.**
This type allows the virtual machine to access the Internet through the host machine's network, but it is not accessible from an external network.

**Features:**

- The virtual machine is assigned a private IP address.

- It can initiate connections to the Internet or the host network.

- Other devices on the network cannot initiate connections to the virtual machine.

- Easy to set up.

- Suitable for secure web surfing, software updates, etc.|

### Мережевий міст (Bridged);

**Definition.**
A virtual machine connects directly to a physical network as if it were a separate physical device.

**Features:**

- A virtual machine gets its IP address from the same DHCP server as the host.

- It is fully available on the network (can ping, receive incoming connections, etc.).

- Provides full network access, just like a physical machine.

- It is required when deploying servers and testing network services.

### Віртуальний адаптер хоста (Host-only);

**Definition.**
Provides connections only between a host (physical machine) and virtual machines.

**Features:**

- Virtual machines do not have access to the Internet.

- They can communicate with each other and with the host.

- An isolated network is created.

- Suitable for testing, development, modeling of internal networks.

### Внутрішня мережа (Internal Network).

**Definition.**
Connections only between virtual machines within the hypervisor, without access to the host or the Internet.

**Features:**

- Completely isolated from the host machine.

- The host does not have access to virtual machines.

- Used to simulate a fully autonomous network.

- Well suited for laboratories, testing without affecting the external environment.

### 3. Розгорніть мережу між вашою робочою ОС та її клоном (завдання 1):

- Продемонструйте базові команди для налаштування мережевих параметрів ОС, поясніть, що вони виконують.

`sudo nano /etc/netplan/01-netcfg.yaml`

![image](https://github.com/user-attachments/assets/df6ccfd9-a0c7-4eb5-945c-ec702a206761)

![image](https://github.com/user-attachments/assets/61888e68-6f30-420c-96f7-9aa30d10c338)

![image](https://github.com/user-attachments/assets/1aef53c1-4ee6-4ae5-aa86-9166d31b94eb)

The `ip a' command on Linux displays information about all network interfaces and their IP addresses.

![image](https://github.com/user-attachments/assets/b821abf9-0cb0-4323-9afe-09cd5c9f4f20)

![image](https://github.com/user-attachments/assets/8ae28a2d-7c97-44eb-b0b2-598cd005a70f)

- Обидві ОС мають мати вихід у мережу Інтернет. Відкрийте браузер та перегляньте будь-яке відео в youtube

![image](https://github.com/user-attachments/assets/35f58ba1-bbee-415d-a5ec-84062cfbbedf)

- Налаштуйте та продемонструйте обмін повідомленнями між двома ОС по локальній мережі. Які команди в терміналі при цьому необхідно ввести?

![image](https://github.com/user-attachments/assets/95130ddd-93a4-4942-97a4-0f626ce3025a)

![image](https://github.com/user-attachments/assets/afbf03be-4b94-4bdb-bf87-43aec4fdea66)

- Налаштуйте спільну мережеву папку для обох ОС. Спробуйте скопіювати файли з цієї директорії в домашній каталог користувача (віртуальна робоча ОС) та на робочій стіл (клон віртуальної робочої ОС).

1: Create a shared folder in Windows:
D:\shared
2: Add this folder as a shared folder in VirtualBox
Select the desired VM → Right-click → Settings.
Go to the Shared Folders section.
Click + (add a new shared folder).

![image](https://github.com/user-attachments/assets/a867211c-b0ae-4be6-b376-2130a7c2976e)

3: Installing Guest Additions in Ubuntu: (You need to install the iso in the IDE controller)

![image](https://github.com/user-attachments/assets/be3768c6-3f72-4ced-b76e-f1529fc02af0)

![image](https://github.com/user-attachments/assets/a19a7bd4-fbc8-4729-b723-e6219cff8ac1)

4: Add a user to the `vboxsf` group
5: After rebooting, the folder will automatically appear in the `/media/sf_Shared directory`
6: Copying files:
To your home directory:
`cp /media/sf_Shared/file_name.txt ~/`

![image](https://github.com/user-attachments/assets/e12282c7-4c63-49fb-a86e-f1f0e2cf7800)

![image](https://github.com/user-attachments/assets/6688e34c-1c93-4c46-9778-e54e53efa42e)

To the desktop:
`cp /media/sf_Shared/file_name.txt ~/Desktop/`

4. Яким чином можна організувати обмін інформацією між вашою основною ОС (наприклад Windows) та віртуальними ОС? Скопіюйте довільний аудіо-файл з вашої основної ОС на робочий стіл віртуальної ОС та її клона. Як зробити зворотну дію, коли треба документ з робочого столу віртуальної ОС скопіювати до вашої основної робочої ОС?
-In VirtualBox, open Settings → Shared Folders.
-Click + (add a new shared folder).
-Folder Path → select a folder on Windows (for example, C:\Shared).
-Folder Name → enter a name, for example, Shared.
-Click OK and start Ubuntu. 4.1 To transfer an audio file:
Copy the audio file to a shared folder in Windows
Move audio.mp3 to C:\Shared.
Move the audio file to the Ubuntu desktop folder
In the Ubuntu terminal, run: `cp /media/sf_Shared/audio.mp3 ~/Desktop/` 4.2 Transfer from the virtual OS to the main OS: Open a terminal in Ubuntu. Copy the document to the shared folder. `cp ~/Desktop/document.pdf /media/sf_Shared/` Switch to Windows and open the C:\Shared folder with the file
