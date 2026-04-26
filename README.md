# 🏠 Personal Home Cloud & Media Server (NAS)

This project involves setting up a high-performance domestic Network Attached Storage (NAS) using a **Raspberry Pi 3** and **OpenMediaVault (OMV)**. The goal is to centralize 1 TB of data and make it accessible across all local network devices (MacBook, iPhone, Android, Smart TV).

## 🚀 Features
- **Centralized Storage:** 1 TB hard drive configured with the **EXT4** file system.
- **Cross-platform (SMB/CIFS):** Smooth file sharing with secure access for macOS and mobile devices.
- **Media Server (DLNA):** Native video/photo streaming to an LG Smart TV via the `miniDLNA` plugin.
- **Headless Management:** Full administration via web interface and SSH terminal.

## 🛠️ Technical Stack
- **Hardware:** Raspberry Pi 3 B+ | 1 TB Western Digital HDD | 32 GB SD Card (OS).
- **OS:** Debian 12 (Bookworm) with OpenMediaVault 7.
- **Protocols:** SMB/CIFS, DLNA, SSH.

<img width="1468" height="880" alt="Capture d’écran 2026-04-26 à 13 37 02" src="https://github.com/user-attachments/assets/249bc8fc-3fc5-4c6b-b6f4-e71ef6cd6f3f" />


## 📋 Installation & Configuration
### 1. Disk Preparation & SSH Access
Used `wipefs` to clear old partition signatures and avoid mounting conflicts. Managed the system via SSH to monitor disk status.

`sudo wipefs -a /dev/sda`

<img width="1470" height="956" alt="Capture d’écran 2026-04-26 à 13 37 34" src="https://github.com/user-attachments/assets/d45a2a48-9c2d-4a2f-b3c5-0594ff7c0817" />


### 2. OpenMediaVault Setup
- Created the file system on `/dev/sda` (EXT4).
- Mounted the storage point and created shared folders.
- Configured ACLs (Access Control Lists) for user permission management.

### 3. Network Services
- **SMB:** Enabled sharing for Finder access on macOS.
- **miniDLNA:** Installed and configured the plugin for automatic discovery by the Smart TV.

<img width="1470" height="956" alt="Capture d’écran 2026-04-26 à 13 37 25" src="https://github.com/user-attachments/assets/8f89f667-f0d1-4dc1-981c-c6184e519d75" />


## 🛡️ Troubleshooting (Challenges Overcome)
- **SMB Permissions:** Resolved an authentication conflict between macOS and Linux by synchronizing user passwords via the OMV Samba database.
- **Hardware:** Managed Raspberry Pi power constraints to support an external 1 TB USB hard drive.

---
*Project developed as part of personal learning in system and network administration.*
