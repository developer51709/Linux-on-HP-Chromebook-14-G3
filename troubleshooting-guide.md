# Troubleshooting Guide  
_For Ubuntu ARM + XFCE on HP Chromebook 14 G3 (Tegra K1)_

This guide covers the most common issues you may encounter after installing Linux on your Tegra‑based Chromebook using the ChrUbuntu‑Tegra method.

---

# 1. System Boots Back Into ChromeOS Instead of Ubuntu

### **Cause**
The Chromebook is still using the ChromeOS root filesystem as the default.

### **Fix**
1. Boot into ChromeOS (Developer Mode).
2. Open VT2:

   ```
   Ctrl + Alt + F2
   ```

3. Log in as `chronos` and run:

   ```bash
   sudo su
   cgpt show /dev/mmcblk0
   ```

4. Identify the partition labeled “Linux”.
5. Set it as the highest priority:

   ```bash
   cgpt add -i <partition_number> -P 5 -S 1 /dev/mmcblk0
   ```

6. Reboot.

---

# 2. Black Screen After Boot / No GUI

### **Cause**
LightDM may not be enabled or XFCE didn’t install correctly.

### **Fix**
Switch to a TTY:

```
Ctrl + Alt + F2
```

Log in, then run:

```bash
sudo systemctl enable lightdm
sudo systemctl start lightdm
```

If XFCE is missing:

```bash
sudo apt install xfce4 xfce4-goodies
```

---

# 3. Wi‑Fi Not Working

### **Cause**
Tegra Chromebooks rely on ChromeOS kernel modules. Sometimes they don’t load correctly.

### **Fix**
Reload the Wi‑Fi module:

```bash
sudo modprobe -r brcmfmac
sudo modprobe brcmfmac
```

If that fails, reboot:

```bash
sudo reboot
```

---

# 4. Trackpad Feels Laggy or Unresponsive

### **Cause**
The default Synaptics driver may not behave well on Tegra hardware.

### **Fix**
Install libinput:

```bash
sudo apt install xserver-xorg-input-libinput
```

Then remove Synaptics:

```bash
sudo apt remove xserver-xorg-input-synaptics
```

Reboot.

---

# 5. Audio Not Working

### **Cause**
ChromeOS audio routing doesn’t always transfer cleanly to Ubuntu ARM.

### **Fix**
Restart PulseAudio:

```bash
pulseaudio -k
pulseaudio --start
```

If still broken:

```bash
sudo apt install pavucontrol
```

Open **PulseAudio Volume Control** and ensure the correct output device is selected.

---

# 6. System Feels Slow or Freezes

### **Cause**
The Tegra K1 is powerful for its age, but Ubuntu can still be heavy.

### **Fixes**
- Disable XFCE compositor:

  ```
  Settings → Window Manager Tweaks → Compositor → Disable
  ```

- Install performance tools:

  ```bash
  sudo apt install htop
  ```

- Remove heavy background services:

  ```bash
  sudo systemctl disable bluetooth
  sudo systemctl disable cups
  ```

---

# 7. Node.js or Python Commands Not Found

### **Cause**
PATH may not be set correctly or packages didn’t install.

### **Fix**
Reinstall:

```bash
sudo apt install --reinstall nodejs npm python3 python3-pip
```

Check versions:

```bash
node -v
python3 --version
```

---

# 8. VS Code (Code‑OSS) Won’t Launch

### **Cause**
Some ARM builds require missing libraries.

### **Fix**
Install dependencies:

```bash
sudo apt install libasound2 libxkbfile1 libsecret-1-0
```

Try launching again:

```bash
code-oss
```

---

# 9. USB Devices Not Recognized

### **Cause**
ChromeOS kernel quirks.

### **Fix**
Reload USB subsystem:

```bash
sudo modprobe -r usbcore
sudo modprobe usbcore
```

If that fails, reboot.

---

# 10. Low Storage / “No Space Left on Device”

### **Cause**
Linux partition too small.

### **Fix**
You must resize partitions manually:

1. Boot into ChromeOS.
2. Open VT2.
3. Use `cgpt` to resize partitions.
4. Reinstall Ubuntu ARM using the ChrUbuntu‑Tegra script with a larger allocation.

---

# 11. System Won’t Boot After Update

### **Cause**
Kernel updates don’t apply because the system uses the ChromeOS kernel.

### **Fix**
You must **never** install kernel updates on this device.

If you did:

1. Boot into ChromeOS.
2. Re‑run the ChrUbuntu‑Tegra script to repair the rootfs.
3. Reboot into Ubuntu.

---

# 12. XFCE Panel Missing or Broken

### **Fix**
Reset XFCE panel:

```bash
xfce4-panel --quit
rm -rf ~/.config/xfce4/panel
xfce4-panel &
```

---

# 13. Bluetooth Not Working

### **Cause**
Tegra K1 Bluetooth support is incomplete.

### **Fix**
Install firmware:

```bash
sudo apt install bluez bluez-firmware
```

Restart service:

```bash
sudo systemctl restart bluetooth
```

---

# 14. ChromeOS Warning Screen Appears Every Boot

### **Cause**
Developer Mode is required; this screen cannot be removed.

### **Fix**
Press **Ctrl + D** to skip it faster.

---

# 15. General Recovery Procedure

If the system becomes unbootable:

1. Boot into ChromeOS recovery mode:
   - Hold **Esc + Refresh**, tap **Power**.
2. Reinstall ChromeOS using a recovery USB.
3. Re‑enable Developer Mode.
4. Reinstall Ubuntu ARM using ChrUbuntu‑Tegra.
