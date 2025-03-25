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

Ubuntu uses the APT (Advanced Package Tool) package manager, which simplifies the process of installing, updating, searching for, and uninstalling packages from official repositories.

### Пошук, скачування та установка необхідних пакетів, яких у Вашій системі немає (зі сховища по замовчуванню, з нового репозиторію тощо).

- Search for a package in the repository:**  
  ```sh
  apt search <package_name>
  ```
  Used to find a package in the available repositories.  

- Get information about a package:**  
  ```sh
  apt show <package_name>
  ```
  Displays detailed information about the package, including its description, dependencies, and version.  

- Installing a package:**  
  ```sh
  sudo apt install <package_name>
  ```
  Downloads and installs the selected package along with any required dependencies.  

- Adding a new repository:** **.  
  ```sh
  sudo add-apt-repository ppa:<repository_name>
  sudo apt update
  ```
  Adds a new package source to the system and updates the list of available software.

### Перегляд інформації про встановлені та доступні пакети.

- **List all installed packages:**  
  ```sh
  dpkg --list
  ```
- **Show details about a specific package:**  
  ```sh
  apt show <package-name>
  ```
- **List available updates:**  
  ```sh
  apt list --upgradable
  ```

### Видалення непотрібних або застарілих пакетів.

- **Remove a package but keep configuration files:**  
  ```sh
  sudo apt remove <package-name>
  ```
- **Remove a package along with its configuration files:**  
  ```sh
  sudo apt purge <package-name>
  ```
- **Remove unnecessary dependencies:**  
  ```sh
  sudo apt autoremove
  ```

### Оновлення менеджера пакетів.

- **Update package lists:**  
  ```sh
  sudo apt update
  ```
- **Upgrade installed packages:**  
  ```sh
  sudo apt upgrade
  ```
- **Perform a full system upgrade (including kernel updates):**  
  ```sh
  sudo apt full-upgrade
  ```
- **Fix broken dependencies if needed:**  
  ```sh
  sudo apt --fix-broken install
  ```

### 3. Встановіть у терміналі через менеджер пакетів на свою систему:

<table>
  <tr>
    <th style="color:#8A2BE2; font-size:20px;">⚠ Important</th>
  </tr>
  <tr>
    <td>This part was made by <strong>Velychko David</strong>.</td>
  </tr>
</table>

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



