<table>
  <tr>
    <th style="color:#8A2BE2; font-size:20px;">⚠ Important</th>
  </tr>
  <tr>
    <td>This part was made by <strong>Skliarovskyi Danylo, Preobrazhenskyi Danylo, Velychko David.</strong>.</td>
  </tr>
</table>

1. **При роботі з персональним комп’ютером дуже часто виникає необхідність підключати периферійне обладнання. На прикладі принтера та флешки опишіть який механізм має ОС Linux для роботи з ними.**

 - **Printer**: Linux uses the CUPS (Common UNIX Printing System) system to work with printers. When you connect a printer to your computer, the system usually recognizes it automatically. For configuration, you can use graphical user interfaces (e.g., *System Settings* in Ubuntu) or the command line to add a printer using the `lpadmin` command. To print files, you can use the `lp` command or graphical programs.
   
 - Flash drive**: Linux uses a mount mechanism to connect a flash drive. When a USB flash drive is plugged into the computer, the system can automatically recognize it and mount it, depending on the settings (e.g., using *udev*). In most modern Linux distributions, the flash drive is mounted automatically when connected, and the user can start working with the files right away. If mounting is not automatic, you can run the `mount` command to mount the flash drive manually.

Translated with DeepL.com (free version)

- **В чому суть операції монтування, для чого вона використовується та як?**

  The mount operation involves connecting a file system from a device (e.g., flash drive, hard disk) to the system so that the operating system can access its contents. Without mounting, the device will not be available for use on the system. On Linux, mounting is usually done with the `mount` command, for example:
   
   ```
   sudo mount /dev/sdb1 /mnt/usb
   ```

   This mounts the flash drive (or other device) to the `/mnt/usb` directory. After mounting, the user can work with the files on the device through standard interfaces.

- **В чому різниця при роботі з периферією у ОС Linux та ОС Windows?**

 - **Linux**: In Linux, peripherals typically work through a mount system, and the user must manually or automatically mount devices to access them. Linux also has built-in printer management tools (CUPS) and more open support for a variety of devices through open source drivers. Peripherals are usually detected through interfaces such as `/dev`, and the system may require more configuration to work correctly.
   
 - **Windows:** On Windows, connecting peripherals is usually an automated process. The operating system automatically recognizes the connected devices, installs the necessary drivers, and provides access through a graphical user interface. For example, flash drives and printers are often recognized without the need for additional settings, and the user can simply start using them once connected.

### 2. Підключіть до вашої віртуальної машини зі встановленою ОС Linux флешку та принтер (за можливості) та через графічний інтерфейс скопіюйте один файл з флешки на віртуальну машину та роздрукуйте його (такі ж самі дії повторіть, але з іншим файлом через команди в терміналі).

![image](https://github.com/user-attachments/assets/d7441a50-3168-43fc-a005-41841428de82)

![image](https://github.com/user-attachments/assets/0669cf4c-65ad-4fc2-a1ab-f28db0fe370f)

![image](https://github.com/user-attachments/assets/fca66c23-94a8-4636-adb6-dbe39b70a761)
