<table>
  <tr>
    <th style="color:#8A2BE2; font-size:20px;">⚠ Important</th>
  </tr>
  <tr>
    <td>This part was made by <strong>Skliarovskyi Danylo</strong>.</td>
  </tr>
</table>

### 1. В ході роботи досить часто виникає необхідність встановлювати нові програми та додатки. Для цього необхідно в терміналі вміти працювати з менеджерами пакетів:

- Дайте розгорнуте визначення таким поняттям як «пакет» та «репозиторій».

**A package** is an archive file that contains software, its metadata (version, dependencies, author) and scripts for installing, updating or uninstalling it. Packages can be in the form of `.deb', `.rpm', `.tar.gz' and other formats depending on the Linux distribution.  

**A repository** is a software repository that contains a collection of packages that can be downloaded and installed through a package manager. Repositories can be official (supported by the distribution developers) or third-party (with additional or unstable versions of programs).  
 
- Надайте короткий огляд існуючих менеджерів пакетів у Linux. Охарактеризуйте їх основні можливості. 

A package manager is a utility that allows you to install, update, uninstall, and manage programs on Linux. The main managers:  

1. **APT (Advanced Package Tool)**.  
   - Used in Debian and derivatives (Ubuntu, Linux Mint).  
   - The main commands:  
     - `apt update` - update the list of available packages.  
     - `apt install <package>` - install the program.  
     - `apt remove <package>` - remove the program.  

2. **DNF (Dandified YUM)**.  
   - Used in Fedora, RHEL, CentOS.  
   - Supports automatic dependency resolution.  
   - Basic commands:  
     - `dnf install <package>` - install the program.  
     - `dnf remove <package>` - uninstallation.  

3. **Zypper**.  
   - Package manager for openSUSE.  
   - Supports both installation of individual packages and management of repositories.  
   - Basic commands:  
     - `zypper install <package>` - install the package.  
     - `zypper remove <package>` - uninstall.  

4. **Pacman**.  
   - Used in Arch Linux and its derivatives.  
   - Differs in speed and minimalism.  
   - The main commands:  
     - `pacman -S <package>` - installation.  
     - `pacman -R <package>` - uninstall.  

5. **Flatpak and Snap**.  
   - Used for universal installation of programs in different distributions.  
   - Flatpak works through `flatpak install`, and Snap - through `snap install`. 

| Package Manager | Distributions | Package Format | Key Features |
|----------------|--------------|---------------|--------------|
| **APT**  | Debian, Ubuntu, Linux Mint | .deb | Automatic dependency resolution, PPA repository support, system updates. |
| **DNF**  | Fedora, RHEL, CentOS | .rpm | Improved dependency resolution, module support, fast updates. |
| **Zypper** | openSUSE | .rpm | Repository management, transactional updates, package caching. |
| **Pacman** | Arch Linux, Manjaro | .pkg.tar.zst | Fast installation, minimalistic approach, AUR support (via helpers). |
| **Flatpak** | All distributions | .flatpak | Containerized applications, isolated environment, resource access portals. |
| **Snap** | All distributions | .snap | Automatic updates, sandboxed execution, centralized app store. |

### 2. Визначте який менеджер пакетів використовує ваш дистрибутив Linux. Опишіть основні команди для роботи з ним:

<table>
  <tr>
    <th style="color:#8A2BE2; font-size:20px;">⚠ Important</th>
  </tr>
  <tr>
    <td>This part was made by <strong>Preobrazhenskyi Danylo</strong>.</td>
  </tr>
</table>



### 3. Встановіть у терміналі через менеджер пакетів на свою систему:

`sudo apt update`

*Новий відео- чи аудіоплейер.*

![image](https://github.com/user-attachments/assets/a3b212a8-9421-4450-84a0-3de188ae4f4b)

`sudo apt install mpv`

*Середовище для мови програмування, що ви вивчаєте.*

![image](https://github.com/user-attachments/assets/1ca36be9-36b1-4b53-bd47-19d690aceb3b)

`sudo apt install nodejs npm`

![image](https://github.com/user-attachments/assets/f2622bce-0682-47fa-a188-da7f6398f93f)

`mpv -version`
`node -v`
`npm -v`

### 4. Яким чином можна встановити нові програми через магазини додатків та менеджери пакетів у графічному середовищі. Наведіть свої приклади.

**1. Installing apps through the app stores****.

#### **For Ubuntu (Ubuntu Software Center):**
1. Open **Ubuntu Software Center** from the application tray.
2. Use the search to find the application you want (for example, **VLC** or **GIMP**).
3. Click the program, then click the **Install** button.
4. If required, enter your password to confirm.

#### **For Fedora (Software):**
1. Open the **Software** program from the application drawer.
2. Search for the application you want to install.
3. Click the application, and then click **Install**.
4. Confirm the installation by entering a password, if necessary.

#### **For Manjaro (Pamac):**
1. Open **Pamac** (graphical package manager).
2. Find the program you want to install.
3. Click on the program and click **Install**.
4. Enter your password to confirm.

**2. Installing programs through package managers in a graphical environment**

#### **APT (Ubuntu/Debian) through a graphical user interface:**
1. Open the **Synaptic Package Manager** (you need to have the `synaptic` package installed).
2. In the search box, enter the name of the program.
3. Select the program from the search results and click **Mark for Installation**.
4. Click **Apply** to start the installation process.

#### **DNF (Fedora) through the GUI:**
1. Open **GNOME Software** or **KDE Discover** (depending on your environment).
2. Search for the program you want to install.
3. Click on the application and then click **Install**.
4. Confirm the installation with the administrator password.

#### **Pacman (Arch Linux) via graphical user interface:**
1. Open **Pamac**.
2. Search for the program you want to install.
3. Click on it and click **Install**.
4. Enter the password to confirm.

