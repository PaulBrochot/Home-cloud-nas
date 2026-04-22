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

## 📋 Installation & Configuration
### 1. Disk Preparation
Used `wipefs` to clear old partition signatures and avoid mounting conflicts:
`sudo wipefs -a /dev/sda`

### 2. OpenMediaVault Setup
- Created the file system on `/dev/sda` (EXT4).
- Mounted the storage point and created shared folders.
- Configured ACLs (Access Control Lists) for user permission management.

### 3. Network Services
- **SMB:** Enabled sharing for Finder access on macOS.
- **miniDLNA:** Installed and configured the plugin for automatic discovery by the Smart TV.

## 🛡️ Troubleshooting (Challenges Overcome)
- **SMB Permissions:** Resolved an authentication conflict between macOS and Linux by synchronizing user passwords via the OMV Samba database.
- **Hardware:** Managed Raspberry Pi power constraints to support an external 1 TB USB hard drive.

---
*Project developed as part of personal learning in system and network administration.*
