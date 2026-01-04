# Linux on HP Chromebook 14 G3 (Tegra K1)
A complete guide for installing and running Linux on the **HP Chromebook 14 G3**, an ARM‑based Chromebook powered by the **NVIDIA Tegra K1 (nyan_blaze)** platform.

This repository documents the **only stable and realistic method** to run a full Linux environment on this device using the **ChrUbuntu‑Tegra** approach, along with post‑install setup instructions and troubleshooting tips.

Because this Chromebook uses an **ARM processor** and **cannot flash a traditional BIOS**, standard Linux distros (like Linux Mint, x86 Arch, or Debian x86) **cannot** be installed. This repo provides the best‑supported path available today.

---

## 📌 Why This Guide Exists
The HP Chromebook 14 G3 is a unique device:

- ARM Tegra K1 CPU (not Intel/AMD)
- No support for BIOS replacement (MrChromebox firmware does **not** support ARM)
- Cannot run x86 Linux installers
- Cannot run `.exe` files (Wine does not support ARM Windows apps)
- No Play Store and no Crostini (Linux Beta)

Despite these limitations, the device **can** run a full Linux environment using the ChromeOS kernel and an ARM root filesystem. This guide explains how.

---

## 🚀 What You Can Install
This guide walks you through installing:

- **Ubuntu ARM** (via ChrUbuntu‑Tegra)
- **XFCE Desktop Environment**
- **Python 3 + pip**
- **Node.js + npm**
- **Git + build tools**
- **VS Code (ARM build)**

This transforms the Chromebook into a lightweight Linux development machine suitable for:

- Web development  
- Python scripting  
- Discord bots  
- General programming  
- Learning Linux  

---

## ❌ What You Cannot Install
Due to hardware and firmware limitations:

- Linux Mint (x86 only)
- Standard Arch Linux (x86 only)
- Wine / `.exe` applications
- BIOS‑based Linux installers
- Steam or x86 games
- ChromeOS Linux (Beta)
- Google Play Store

---

## Documentation
- [Installation Guide](docs/installation.md)
- [Post‑Install Setup](docs/post-install.md)
- [Troubleshooting](docs/troubleshooting.md)
- [FAQ](docs/FAQ.md)
- [Known Issues](docs/known-issues.md)

---

## 📥 Repository Contents

### **1. Installation Guide**
Step‑by‑step instructions for installing Ubuntu ARM using the ChrUbuntu‑Tegra script.

File:  
`installation.md`

### **2. Post‑Install Setup Guide**
Covers installing XFCE, Python, Node.js, VS Code, and essential tools.

File:  
`post-install.md`

### **3. Troubleshooting Guide**
Solutions for common issues such as Wi‑Fi, audio, GUI problems, boot issues, and more.

File:  
`troubleshooting.md`

---

## 🛠️ Requirements

- HP Chromebook 14 G3 (Tegra K1, codename `nyan_blaze`)
- USB drive (optional but recommended)
- Wi‑Fi connection
- Willingness to use Developer Mode
- Basic command‑line comfort

---

## ⚙️ Quick Overview of the Installation Process

1. Enable **Developer Mode**
2. Open a root shell (`Ctrl + Alt + F2`)
3. Download the **ChrUbuntu‑Tegra** installer
4. Allocate storage for Linux
5. Install Ubuntu ARM rootfs
6. Boot into Ubuntu ARM
7. Install XFCE and development tools

Full instructions are in `installation.md`.

---

## 🧩 Supported Features

| Feature | Supported |
|--------|-----------|
| XFCE Desktop | ✔ |
| Python 3 | ✔ |
| Node.js | ✔ |
| VS Code (ARM) | ✔ |
| Wi‑Fi | ✔ (with ChromeOS kernel modules) |
| Audio | ✔ (PulseAudio) |
| USB devices | ✔ |
| GPU acceleration | ✔ (Tegra K1) |
| ChromeOS kernel updates | ✔ (but avoid kernel upgrades inside Ubuntu) |

---

## ⚠️ Unsupported Features

| Feature | Supported |
|--------|-----------|
| BIOS flashing | ❌ |
| x86 Linux distros | ❌ |
| Wine / `.exe` files | ❌ |
| Steam | ❌ |
| Crostini (Linux Beta) | ❌ |
| Google Play Store | ❌ |

---

## 🧪 Development Notes
This device is surprisingly capable for:

- Python development  
- Node.js projects  
- Web servers  
- Lightweight coding tasks  
- Learning Linux internals  

The Tegra K1 GPU even supports OpenGL ES, making it more powerful than many ARM Chromebooks of its era.

---

## 🤝 Contributing
Contributions are welcome!

If you:

- Have fixes  
- Want to improve documentation  
- Have additional troubleshooting tips  
- Want to test other ARM distros  

Feel free to open an issue or submit a pull request.

---

## 📄 License
This project is open‑source and available under the MIT License.

---

## ⭐ Acknowledgements
Special thanks to:

- The **ChrUbuntu‑Tegra** project  
- The ARM Linux community  
- Everyone keeping older Chromebooks alive  

---

## 📬 Contact
If you have questions, suggestions, or improvements, feel free to open an issue on the repository.

---

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Platform: ARM](https://img.shields.io/badge/Platform-ARM-orange)
![Status: Active](https://img.shields.io/badge/Status-Active-blue)
