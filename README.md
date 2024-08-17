# Ubuntu Installation Guide

This guide provides step-by-step instructions for installing Ubuntu, a popular Linux distribution, on a computer with a 256 GB disk.

## Table of Contents

1. [System Requirements](#system-requirements)
2. [Download Ubuntu](#download-ubuntu)
3. [Create a Bootable USB Drive](#create-a-bootable-usb-drive)
4. [Install Ubuntu](#install-ubuntu)
   - [Custom Partitioning (256 GB Disk)](#custom-partitioning-256-gb-disk)
5. [Post-Installation Setup](#post-installation-setup)
6. [Troubleshooting](#troubleshooting)

## System Requirements

Before installing Ubuntu, ensure your system meets the following requirements:

- **Processor:** 2 GHz dual-core processor or better
- **Memory:** 4 GB RAM (8 GB recommended)
- **Storage:** 25 GB of free hard drive space (256 GB disk in this guide)
- **USB Port:** Required for creating a bootable USB drive
- **Internet Access:** Recommended for updates and third-party software

## Download Ubuntu

1. Visit the [official Ubuntu website](https://ubuntu.com/download/desktop).
2. Choose the version of Ubuntu you want to install (e.g., 20.04 LTS).
3. Click on the download button and save the ISO file to your computer.

## Create a Bootable USB Drive

To install Ubuntu, you need to create a bootable USB drive using the downloaded ISO file.

### Using Rufus (Windows)

1. Download and install [Rufus](https://rufus.ie).
2. Insert a USB drive into your computer (at least 4 GB).
3. Open Rufus and select your USB drive.
4. In the "Boot selection" section, choose the Ubuntu ISO file.
5. Click "Start" and wait for the process to complete.

### Using Etcher (Mac/Linux)

1. Download and install [Etcher](https://etcher.io).
2. Insert a USB drive into your computer.
3. Open Etcher, select the Ubuntu ISO file, and choose your USB drive.
4. Click "Flash!" and wait for the process to complete.

## Install Ubuntu

1. Insert the bootable USB drive into your computer.
2. Restart your computer and boot from the USB drive (you may need to change the boot order in your BIOS/UEFI settings).
3. Once Ubuntu loads, you will see a welcome screen.
4. Select your language and click "Install Ubuntu."
5. Choose your installation type:
   - **Erase disk and install Ubuntu:** Installs Ubuntu as the only operating system on your computer.
   - **Install Ubuntu alongside Windows:** Installs Ubuntu alongside your existing Windows installation (dual-boot).
   - **Something else:** Allows for custom partitioning.

### Custom Partitioning (256 GB Disk)

If you choose the "Something else" option, you can manually partition your 256 GB disk. Here’s a recommended partitioning scheme:

1. **EFI Partition (for UEFI systems):**
   - Select the free space and click on the `+` button.
   - **Size:** 300 MB
   - **Type:** Primary
   - **Location for the new partition:** Beginning of this space
   - **Use as:** EFI System Partition

2. **Root Partition (`/`):**
   - Select the remaining free space and click on the `+` button.
   - **Size:** 50 GB
   - **Type:** Primary
   - **Location for the new partition:** Beginning of this space
   - **Use as:** Ext4 journaling file system
   - **Mount point:** `/`
   - This partition will hold your operating system and installed applications.

3. **Home Partition (`/home`):**
   - Select the remaining free space and click on the `+` button.
   - **Size:** 180 GB
   - **Type:** Logical (can also be Primary if needed)
   - **Location for the new partition:** Beginning of this space
   - **Use as:** Ext4 journaling file system
   - **Mount point:** `/home`
   - This partition will store your personal files, documents, and settings.

4. **Swap Partition:**
   - Select the remaining free space and click on the `+` button.
   - **Size:** 4 GB (or equivalent to your RAM size)
   - **Type:** Logical
   - **Location for the new partition:** Beginning of this space
   - **Use as:** swap area
   - This partition acts as virtual memory when your RAM is full.

5. After creating these partitions, verify that the changes are correct, and then click on "Install Now" to begin the installation.

## Post-Installation Setup

After installation, consider the following steps to enhance your Ubuntu experience:

1. **Update your system:** 
   - Open a terminal and run:
     ```bash
     sudo apt update && sudo apt upgrade
     ```
2. **Install additional drivers:** 
   - Go to "Software & Updates" > "Additional Drivers" and install any available proprietary drivers.
3. **Install essential software:**
   - Use the Ubuntu Software Center or the terminal to install software like VLC, GIMP, and more.
   - Example terminal command:
     ```bash
     sudo apt install vlc gimp
     ```
4. **Enable the firewall:** 
   - Open a terminal and run:
     ```bash
     sudo ufw enable
     ```

## Troubleshooting

If you encounter any issues during installation or post-installation, consider the following:

- **No bootable device found:** Ensure the USB drive is properly configured and the boot order is set correctly.
- **Wi-Fi not working:** Check "Additional Drivers" for any proprietary drivers that need to be installed.
- **Display issues:** Try booting with the "nomodeset" option in the GRUB menu.

For additional help, refer to the [Ubuntu Community Forums](https://ubuntuforums.org) or the [Ask Ubuntu](https://askubuntu.com) website.

---

This guide provides a basic overview of the Ubuntu installation process, including custom partitioning for a 256 GB disk. For more detailed instructions, visit the official [Ubuntu Documentation](https://help.ubuntu.com).
