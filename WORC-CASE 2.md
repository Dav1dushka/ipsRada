# Git: **Describe a set of basic actions in the hypervisor you have installed:**
>[!IMPORTANT]
> this part made by Davidokt
---
### Creating a new virtual machine
- Open VirtualBox
- Click Create
- Specify the name of the VM and select the type of OS (Windows, Linux, macOS, etc.)
- Select the amount of RAM (it is recommended not to exceed 50% of the available memory)
- Select “Create a new virtual hard disk” or use an existing one
- Select the disk format (VDI, VMDK, VHD) and the storage mode (dynamic or fixed size)
- Click Create
---
### Selecting/adding hardware available for a VM
- Select a VM and click Settings
- System → Specify the number of processor cores, RAM, and boot order
- Display → Set the amount of video memory, enable 3D or 2D acceleration
- Media → Connect an ISO image (for example, to install the OS) or add a virtual hard disk
- Audio → Enable/disable the audio adapter
- USB → Select the USB mode (2.0 or 3.0) and add USB devices
---
### Set up a network and connect to Wi-Fi
 - Settings → Network
 - Select the adapter's operating mode:
 - NAT (access to the Internet, but the VM is isolated)
 - Bridge adapter (the VM receives an IP address from the router and has access to the local network)
    Internal network (communication only between virtual machines)
    Host-only adapter (communication between the VM and the host system without access to the Internet)
 - For Wi-Fi:
    `"If you are using a Bridge Adapter, select the host machine's Wi-Fi adapter"`
    `"If you need to connect to Wi-Fi through a USB adapter, you can transfer it to the VM via USB devices"`
---
### Ability to work with external media (flash drives)
- Insert the flash drive into the host computer
- In VirtualBox, select the VM and go to Settings → USB
- Turn on the USB controller (2.0 or 3.0)
- Click Add New USB Filter and select the flash drive from the list
- Start the VM, the flash drive will appear in the list of devices
- If the flash drive is not detected:
    `"On Linux, you may need to add a user to the vboxusers group"`
    `"On Windows, you may need to install the VirtualBox Extension Pack drivers"`
---

<table>
  <tr>
    <th style="color:#8A2BE2; font-size:20px;">⚠ Important</th>
  </tr>
  <tr>
    <td>This part was made by <strong>Preobrazhensky Danylo</strong>.</td>
  </tr>
</table>

### 3. Встановіть в вашому гіпервізорі операційну систему GNU/Linux (будь-який зручний Вам дистрибутив) у базовій конфігурації з графічною оболонкою.

![image](https://github.com/user-attachments/assets/5858fd38-dec2-4b84-955b-d272d0524358)

### 4.1 Встановіть у мінімальній конфігурації з термінальним вводом-виводом без графічного інтерфейсу операційну систему GNU/Linux;

![image](https://github.com/user-attachments/assets/6c319fbb-1fcc-4d1b-a9b2-7e36d350670c)

### 4.2 Встановіть графічну оболонку GNOME поверх встановленої в попередньому пункті ОС;

![image_2025-02-21_19-39-00](https://github.com/user-attachments/assets/7e24f4f3-6bc4-4dd1-87e4-c50f1671141c)

<table>
  <tr>
    <th style="color:#8A2BE2; font-size:20px;">⚠ Important</th>
  </tr>
  <tr>
    <td>This part was made by <strong>Skliarovskyi Danylo</strong>.</td>
  </tr>
</table>

### 4.3 Встановіть додатково ще другу графічну оболонку

![image](https://github.com/user-attachments/assets/bcac2bfc-f7a0-4291-afdc-12b23174ba83)

## GNOME VS KDE Plasma:

| Feature               | GNOME                                  | KDE Plasma                           |
|-----------------------|--------------------------------------|--------------------------------------|
| **User Interface**    | Minimalistic, focused on simplicity | Highly customizable, feature-rich   |
| **Customization**     | Limited, requires extensions        | Extensive, built-in customization   |
| **Performance**       | Optimized for modern hardware       | More resource-intensive but flexible |
| **Default Apps**      | GNOME-based applications (Nautilus, Gedit) | KDE apps (Dolphin, Kate, Konsole) |
| **Extensions**        | Supports GNOME Shell extensions     | Uses widgets and themes natively    |
| **Settings Manager**  | Simple and streamlined              | Advanced with many options          |
| **Window Management** | Basic tiling and workspace support  | Advanced window management features |
| **Wayland Support**   | More mature and stable              | Improving, but still behind GNOME   |
| **File Manager**      | Nautilus (simple, streamlined)      | Dolphin (feature-rich, dual-pane)   |
| **Resource Usage**    | Generally lower RAM consumption     | Higher RAM usage due to features    |












