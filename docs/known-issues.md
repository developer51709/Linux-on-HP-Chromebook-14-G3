# Known Issues — HP Chromebook 14 G3 (Tegra K1)

This document lists known limitations and quirks when running Ubuntu ARM on the HP Chromebook 14 G3 using the ChrUbuntu‑Tegra method.

---

# ⚠️ Critical Limitations

## ❌ Cannot flash custom BIOS
ARM Chromebooks cannot use MrChromebox firmware.  
The ChromeOS boot chain must remain intact.

## ❌ Cannot install x86 Linux distros
Linux Mint, x86 Arch, Debian x86, and similar distros will not run.

## ❌ Cannot run `.exe` files
Wine does not support Windows apps on ARM.

## ❌ Kernel updates must NOT be installed
Installing a kernel update inside Ubuntu will break the system.

---

# 🐛 System Issues

## ⚠️ Wi‑Fi may occasionally fail to load
Fix:

```bash
sudo modprobe -r brcmfmac
sudo modprobe brcmfmac
```

A reboot usually resolves it.

---

## ⚠️ Audio may stop working after updates
Restart PulseAudio:

```bash
pulseaudio -k
pulseaudio --start
```

---

## ⚠️ Bluetooth support is incomplete
Bluetooth may:

- Fail to pair  
- Disconnect randomly  
- Not detect some devices  

Installing firmware helps but does not fully fix it:

```bash
sudo apt install bluez bluez-firmware
```

---

## ⚠️ Trackpad may feel laggy
Switch to libinput:

```bash
sudo apt install xserver-xorg-input-libinput
sudo apt remove xserver-xorg-input-synaptics
```

---

## ⚠️ USB devices may not mount automatically
Reload USB subsystem:

```bash
sudo modprobe -r usbcore
sudo modprobe usbcore
```

Or reboot.

---

## ⚠️ Suspend / Resume is unreliable
The device may:

- Freeze  
- Lose Wi‑Fi  
- Fail to wake properly  

Best workaround: disable suspend entirely.

---

# 🖥️ Desktop Environment Issues

## ⚠️ XFCE compositor may cause lag
Disable it:

```
Settings → Window Manager Tweaks → Compositor → Disable
```

---

## ⚠️ XFCE panel may break after updates
Reset it:

```bash
xfce4-panel --quit
rm -rf ~/.config/xfce4/panel
xfce4-panel &
```

---

# 🔧 Boot Issues

## ⚠️ System boots into ChromeOS instead of Ubuntu
Set the Linux partition as highest priority:

```bash
sudo cgpt add -i <partition_number> -P 5 -S 1 /dev/mmcblk0
```

---

## ⚠️ Black screen on boot
LightDM may not be enabled:

```bash
sudo systemctl enable lightdm
sudo systemctl start lightdm
```

---

# 🧹 Storage Issues

## ⚠️ “No space left on device”
Your Linux partition is too small.

Fix:  
Reinstall using ChrUbuntu‑Tegra and allocate more space.

---

# 🧪 Software Issues

## ⚠️ VS Code (ARM) may require extra libraries
Install missing dependencies:

```bash
sudo apt install libasound2 libxkbfile1 libsecret-1-0
```

---

# 📌 Summary

These issues are normal for Tegra‑based Chromebooks.  
Despite them, the HP Chromebook 14 G3 remains a capable lightweight Linux machine for development and learning.
