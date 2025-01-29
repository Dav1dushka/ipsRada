---
## Creating a new virtual machine
  **Open VirtualBox**
  **Click Create**
  **Specify the name of the VM and select the type of OS (Windows, Linux, macOS, etc.)**
  **Select the amount of RAM (it is recommended not to exceed 50% of the available memory)**
  **Select “Create a new virtual hard disk” or use an existing one**
  **Select the disk format (VDI, VMDK, VHD) and the storage mode (dynamic or fixed size)**
  **Click Create**
---
## Selecting/adding hardware available for a VM
**Select a VM and click Settings**
**System → Specify the number of processor cores, RAM, and boot order**
**Display → Set the amount of video memory, enable 3D or 2D acceleration**
**Media → Connect an ISO image (for example, to install the OS) or add a virtual hard disk**
**Audio → Enable/disable the audio adapter**
**USB → Select the USB mode (2.0 or 3.0) and add USB devices**
---
## Set up a network and connect to Wi-Fi
**Settings → Network**
**Select the adapter's operating mode:
NAT (access to the Internet, but the VM is isolated)**
**Bridge adapter (the VM receives an IP address from the router and has access to the local network).
-Internal network (communication only between virtual machines)
-Host-only adapter (communication between the VM and the host system without access to the Internet)**
**For Wi-Fi:
-If you are using a Bridge Adapter, select the host machine's Wi-Fi adapter
-If you need to connect to Wi-Fi through a USB adapter, you can transfer it to the VM via USB devices**
---
## Ability to work with external media (flash drives)
**Insert the flash drive into the host computer**
**In VirtualBox, select the VM and go to Settings → USB**
**Turn on the USB controller (2.0 or 3.0)**
**Click Add New USB Filter and select the flash drive from the list**
**Start the VM, the flash drive will appear in the list of devices**
**If the flash drive is not detected:
-On Linux, you may need to add a user to the vboxusers group.
-On Windows, you may need to install the VirtualBox Extension Pack drivers**
