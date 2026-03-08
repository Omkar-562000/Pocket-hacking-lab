![Pocket Cyber Lab](assets/banner.svg)

# 🔐 Pocket Cybersecurity Lab (Portable Kali USB)

A portable cybersecurity learning environment built using **Kali Linux persistence and Ventoy**.

This project allows cybersecurity students to carry a complete **penetration testing lab in a USB drive**.

# 🔐 Pocket Cybersecurity Lab (Portable Kali USB)

![Kali Linux](https://img.shields.io/badge/Kali-Linux-blue)
![Platform](https://img.shields.io/badge/Platform-USB%20Bootable-green)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)

## 📌 Overview

**Pocket Cybersecurity Lab** is a portable penetration-testing learning environment built using a **persistent Kali Linux USB**.

The goal of this project is to create a **lightweight portable cybersecurity lab** that can run on almost any computer **without installing Kali Linux on the host system**.

This project allows cybersecurity learners to **carry a complete practice environment in their pocket** and perform activities such as:

* Network analysis
* Security tool practice
* Linux scripting
* Ethical hacking labs
* System exploration

The environment uses **Kali Linux Live with USB persistence**, allowing tools, scripts, and configurations to remain saved across reboots.

---

# ✨ Features

✔ Portable Kali Linux environment
✔ Persistent storage for tools and files
✔ Structured cybersecurity toolkit workspace
✔ Automation scripts for setup
✔ Organized directories for learning resources
✔ Bootable via **Ventoy**
✔ Designed for **ethical cybersecurity practice**

---

# 📁 Project Architecture

```
Pocket-Cyber-Lab
│
├── docs
│   ├── installation.md
│   ├── usage.md
│   └── architecture.md
│
├── scripts
│   ├── system-setup.sh
│   ├── network-tools.sh
│   └── recon-tools.sh
│
├── toolkit
│   ├── wordlists
│   ├── configs
│   └── notes
│
├── lab-environment
│   └── kali-persistent-usb-guide.md
│
└── README.md
```

---

# 💻 System Requirements

## Hardware

* USB Drive **(minimum 32GB, recommended 64GB)**
* Computer supporting **USB Boot**

## Software

* Kali Linux Live ISO
* Ventoy Bootloader
* Linux utilities
* Git

---

![🏗️ Architecture Diagram]
(assets/diagram.png)

# ⚙️ Installation Guide

## Step 1 — Install Ventoy

1. Download Ventoy from the official website
2. Insert your USB drive
3. Run the Ventoy installer
4. Install Ventoy on the USB device

---

## Step 2 — Add Kali Linux ISO

Create an ISO directory inside the USB:

```
/ISO
```

Copy the Kali Linux ISO file into the folder.

Example:

```
/ISO/kali-linux-live-amd64.iso
```

---

## Step 3 — Create Persistence Partition

Boot Kali Live and create a persistence partition.

```
sudo fdisk /dev/sdb
```

Create a new partition (example: **30GB**).

---

## Step 4 — Format the Partition

```
sudo mkfs.ext4 -L persistence /dev/sdb3
```

---

## Step 5 — Configure Persistence

Mount the partition:

```
sudo mkdir /mnt/persistence
sudo mount /dev/sdb3 /mnt/persistence
```

Create the persistence configuration file:

```
echo "/ union" | sudo tee /mnt/persistence/persistence.conf
```

Unmount the partition:

```
sudo umount /mnt/persistence
```

---

## Step 6 — Boot Kali with Persistence

Restart the computer and boot from the USB drive.

From the Kali boot menu choose:

```
Live system with USB persistence
```

---

# 🧰 Lab Toolkit Setup

Create a structured workspace:

```
mkdir ~/cyber-lab
mkdir ~/cyber-lab/scripts
mkdir ~/cyber-lab/notes
mkdir ~/cyber-lab/wordlists
```

Update the system:

```
sudo apt update
sudo apt upgrade
```

Install useful utilities:

```
sudo apt install git curl python3 python3-pip net-tools
```

---

# ⚡ Example Automation Script

File:

```
scripts/system-setup.sh
```

```
#!/bin/bash

echo "Updating system..."
sudo apt update && sudo apt upgrade -y

echo "Installing essential utilities..."
sudo apt install git curl net-tools -y

echo "Setup completed."
```

Make executable:

```
chmod +x system-setup.sh
```

---

# 🧪 Testing Persistence

Create a test file:

```
touch ~/cyber-lab/test.txt
```

Restart the system.

After reboot, verify:

```
ls ~/cyber-lab
```

If the file remains → **Persistence is working correctly.**

---

# 📚 Learning Outcomes

This project helps learners understand:

* Linux boot environments
* USB persistence systems
* Portable cybersecurity lab creation
* Linux system configuration
* Automation scripting
* Ethical cybersecurity experimentation

---

# 🚀 Future Improvements

* Automated tool installer
* CTF practice environment integration
* Containerized vulnerable targets
* Custom security scripts
* Web-based lab dashboard

---

# ⚠️ Disclaimer

This project is intended **strictly for educational and ethical cybersecurity learning purposes**.

Users must comply with all applicable laws and perform testing **only in authorized environments**.

---

# 👨‍💻 Author

**Omiee**
Cybersecurity Enthusiast | Computer Science Student

---

⭐ If you found this project useful, consider **starring the repository**!
