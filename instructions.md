# Install Linux on HP Chromebook 14 G3 (Tegra K1)
Using ChrUbuntu‑Tegra + Ubuntu ARM + XFCE

> **Device:** HP Chromebook 14 G3 (Tegra K1, codename `nyan_blaze`)
> **Goal:** Replace ChromeOS in practice with a usable Linux system (Ubuntu ARM + XFCE)
> **Reality check:** True BIOS‑style full wipe + Arch ARM only is not practically supported on this model.

---

## 1. Understand the limitations
- CPU: NVIDIA Tegra K1 (ARMv7)

- No BIOS replacement: MrChromebox firmware does not support ARM Chromebooks

- No x86 OS: You cannot install Linux Mint, x86 Arch, or run `.exe` via Wine

- Kernel: You must use the ChromeOS kernel or a custom ARM kernel; ChrUbuntu‑Tegra uses the ChromeOS kernel

- Best‑supported path: ChrUbuntu‑style install with Ubuntu ARM

What you can get:

- Full Ubuntu ARM system

- XFCE desktop

- Python, Node.js, Git, etc.

- A “real Linux laptop” feel for coding and projects

---

## 2. Enable Developer Mode
1. **Turn off** the Chromebook.

2. Hold **Esc + Refresh**, then tap **Power**.

3. At the recovery screen, press **Ctrl + D**.

4. Press **Enter** to confirm.

5. Wait for the device to wipe and reboot.

From now on, at the white boot screen, press **Ctrl + D** to continue.

---

## 3. Connect to Wi‑Fi and open a VT2 shell
1. Boot into ChromeOS (Developer Mode).

2. Connect to Wi‑Fi.

3. Press:

```text
Ctrl + Alt + F2
```

4. Log in as:

```text
chronos
```

No password is needed by default.

---

## 4. Download the ChrUbuntu‑Tegra script
The **ChrUbuntu‑Tegra** project provides scripts specifically for Tegra‑based Chromebooks to install Ubuntu ARM using the ChromeOS kernel.

1. In the shell, become root:

```bash
sudo su
```

2. Download the script:

```bash
cd /home/chronos/user
wget https://raw.githubusercontent.com/marcino239/chrubuntu-tegra/master/chrubuntu-tegra.sh
chmod +x chrubuntu-tegra.sh
```

> This script is designed for Tegra Chromebooks and automates partitioning and installing Ubuntu ARM alongside or over ChromeOS.
