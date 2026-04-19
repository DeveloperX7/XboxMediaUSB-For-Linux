==================================================
🎮 XboxMediaUSB Application
📀 Prepare USB drives for Xbox Series and Xbox One
==================================================

========== 1. 📖 Application Description ==========
This application formats and prepares any USB drive (flash drive or external hard drive) to work fully with modern Xbox consoles (Xbox Series X|S and Xbox One).
✨ Main features:
- 🧱 Create a GPT partition table and a single NTFS partition.
- ⚡ Quick format the partition as NTFS.
- 🔐 Automatically apply Xbox-specific extended ACLs.
- 📁 Create essential folders: Games, Apps, Homebrew, Content, System.
- 📂 Browse USB contents via file manager.
- ⏏️ Safely eject the drive (unmount + power off).

⚠️ Note: The application requires root privileges to run.

========== 2. 🚀 How to Use ==========
1. 📥 Download the file XBOXMEDIAUSB.py.
2. 🖥️ Open a terminal and navigate to the file's folder.
3. 🔑 Run the application with:
   sudo python3 XBOXMEDIAUSB.py
4. 🖱️ After the GUI opens:
   - Select your USB drive from the dropdown (🔍 double‑check – all data will be destroyed).
   - Click the "⚠️ FORMAT-Fix ACLs ▲" button to start formatting and applying ACLs.
   - Once done, you can create folders using the "📁 Create Directory Structure..." button.
   - Browse the drive to copy games via "📂 Browse USB Contents".
   - Finished? Press "⏏️ Eject USB" for safe removal.

💀 Warning: All data on the selected drive will be permanently lost.

========== 3. 📦 Dependency Installation Commands per Distribution ==========

Before first run, install the following packages:
- 💾 ntfs-3g   (NTFS filesystem support)
- 🏷️ attr      (setfattr command for ACLs)
- 🗂️ parted    (partitioning tool)
- 🖼️ PyQt5     (graphical user interface)

Use the appropriate command for your distribution:

-----------------------------------------
| 🐧 Arch Linux                         |
-----------------------------------------
sudo pacman -S ntfs-3g attr parted python-pyqt5

-----------------------------------------
| 🐧 Debian / Ubuntu / Linux Mint       |
-----------------------------------------
sudo apt update
sudo apt install ntfs-3g attr parted python3-pyqt5

-----------------------------------------
| 🪶 Fedora (standard)                  |
-----------------------------------------
sudo dnf install ntfs-3g attr parted python3-qt5

-----------------------------------------
| 🔄 Fedora Atomic / Silverblue         |
| (rpm-ostree system)                   |
-----------------------------------------
rpm-ostree install ntfs-3g attr parted python3-qt5
# Then reboot or run:
rpm-ostree reload

-----------------------------------------
| 🐧 openSUSE (Leap / Tumbleweed)       |
-----------------------------------------
sudo zypper install ntfs-3g attr parted python3-qt5

-----------------------------------------
| 🌿 Other distributions (generic)      |
-----------------------------------------
Install the equivalent packages using your distribution's package manager:
- ntfs-3g
- attr (or any package providing setfattr)
- parted
- pyqt5 (or python3-pyqt5, python-qt5)

========== 4. 📌 Additional Notes ==========
- 🔍 The application automatically detects missing packages and will ask to install them if you run it with root privileges.
- 💾 If no USB drives appear in the list, make sure the drive is properly connected.
- 🔄 On Fedora Atomic, after installing packages via rpm-ostree you may need to reboot the system.
- 🧪 It is recommended to run the application from a terminal to see any error messages.

========== 5. 🏷️ Application Version ==========
Version: 2.1 (supports Atomic and rpm-ostree distributions)
==================================================
