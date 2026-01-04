# Install Linux on HP Chromebook 14 G3 (Tegra K1)  
*Using ChrUbuntu‑Tegra + Ubuntu ARM + XFCE*

> **Device:** HP Chromebook 14 G3 (Tegra K1, codename `nyan_blaze`)  
> **Goal:** Replace ChromeOS in practice with a usable Linux system (Ubuntu ARM + XFCE)  
> **Reality check:** True BIOS‑style full wipe + Arch ARM only is not practically supported on this model.  
> **Reason:** ARM Chromebooks cannot flash a real BIOS and cannot boot standard Linux installers.

---

# 1. Understand the limitations

The HP Chromebook 14 G3 uses:

- **NVIDIA Tegra K1 (ARMv7)** CPU  
- **ChromeOS kernel only** (no custom BIOS possible)  
- **No x86 support** → cannot run Linux Mint, x86 Arch, or `.exe` files  
- **No Crostini (Linux Beta)**  
- **No Play Store**

What *is* possible:

- Full Ubuntu ARM system  
- XFCE desktop  
- Python, Node.js, Git, VS Code (ARM build)  
- A “real Linux laptop” experience for development

---

# 2. Enable Developer Mode

1. Turn off the Chromebook.  
2. Hold **Esc + Refresh**, then tap **Power**.  
3. At the recovery screen, press **Ctrl + D**.  
4. Press **Enter** to confirm.  
5. Wait for the wipe to finish.

From now on, at the white boot screen, press **Ctrl + D** to continue.

---

# 3. Open a VT2 shell

1. Boot into ChromeOS (Developer Mode).  
2. Connect to Wi‑Fi.  
3. Press:

   ```
   Ctrl + Alt + F2
   ```

4. Log in as:

   ```
   chronos
   ```

5. Become root:

   ```bash
   sudo su
   ```

---

# 4. Download the ChrUbuntu‑Tegra installer

ChrUbuntu‑Tegra is the community‑maintained installer for Tegra‑based Chromebooks.

```bash
cd /home/chronos/user
wget https://raw.githubusercontent.com/marcino239/chrubuntu-tegra/master/chrubuntu-tegra.sh
chmod +x chrubuntu-tegra.sh
```

---

# 5. Choose how much storage Linux gets

When running the script, it will ask how much space to allocate.

- If you want Linux to effectively **replace ChromeOS**, give it **most of the internal storage** (e.g., 12–14 GB on a 16 GB device).

---

# 6. Run the ChrUbuntu‑Tegra installer

```bash
cd /home/chronos/user
bash chrubuntu-tegra.sh
```

The script will:

- Resize internal storage  
- Create Linux partitions  
- Download Ubuntu ARM rootfs  
- Install it using the ChromeOS kernel  

If it reboots mid‑process, follow the script’s instructions (usually rerun it to continue).

---

# 7. Boot into Ubuntu ARM

After installation:

1. Reboot.  
2. Press **Ctrl + D** at the white screen.  
3. The system should now boot into Ubuntu ARM.

If it still boots ChromeOS, the script README explains how to switch the default rootfs.

---

# 8. Update Ubuntu ARM

```bash
sudo apt update
sudo apt upgrade
```

---

# 9. Install XFCE desktop

```bash
sudo apt install xfce4 xfce4-goodies lightdm lightdm-gtk-greeter
```

Enable LightDM:

```bash
sudo systemctl enable lightdm
```

Reboot:

```bash
sudo reboot
```

You should now see a graphical login screen.

---

# 10. Install Python and Node.js

### Python

```bash
sudo apt install python3 python3-pip
```

### Node.js

```bash
sudo apt install nodejs npm
```

---

# 11. Install development tools

```bash
sudo apt install git build-essential
```

### VS Code (ARM build)

```bash
sudo apt install code-oss
```

(If not available, search with `apt search code`.)

---

# 12. Optional: Make XFCE look like Linux Mint

```bash
sudo apt install arc-theme numix-icon-theme
```

Then customize:

- **Settings → Appearance**  
- **Settings → Window Manager**  
- **Panel → Add items** (menu, taskbar, system tray)

---

# 13. What your final system can do

You now have:

- Full Ubuntu ARM system  
- XFCE desktop  
- Python 3 + pip  
- Node.js + npm  
- Git + build tools  
- VS Code (ARM)  
- A lightweight Linux dev machine

You **cannot**:

- Run `.exe` files (Wine does not support ARM Windows apps)  
- Install Linux Mint or x86 Arch  
- Flash a traditional BIOS  

But for coding, scripting, and learning Linux, this setup is solid.

---

# 14. Why this isn’t a pure “Arch ARM full wipe” guide

- Arch ARM on Tegra K1 exists, but **not** as a stable, documented full‑wipe installer for this specific model.  
- The HP 14 G3 cannot boot a normal Linux installer because it cannot replace its boot firmware.  
- ChrUbuntu‑Tegra is the **only reliable, repeatable method** for a full Linux environment on this device.

This guide gives you a setup that behaves like a full Linux install while staying within what the hardware supports.

---

# End of Guide
