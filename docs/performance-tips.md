# Performance Tips — HP Chromebook 14 G3 (Tegra K1)

This guide provides practical optimizations to improve performance on the HP Chromebook 14 G3 when running Ubuntu ARM with XFCE.  
The Tegra K1 is capable hardware for its age, but benefits greatly from lightweight tuning.

---

# ⚡ 1. Disable XFCE Compositor (Major Speed Boost)

The built‑in compositor can cause lag, tearing, and slow window movement.

Disable it:

```
Settings → Window Manager Tweaks → Compositor → Disable
```

This is the single biggest improvement you can make.

---

# 🧹 2. Remove Unnecessary Background Services

Some services are not needed on this device and consume RAM/CPU.

Disable Bluetooth if you don’t use it:

```bash
sudo systemctl disable bluetooth
```

Disable printing services:

```bash
sudo systemctl disable cups
```

Disable ModemManager (Chromebooks don’t have cellular modems):

```bash
sudo systemctl disable ModemManager
```

---

# 🔋 3. Install TLP for Better Battery Life and Efficiency

TLP optimizes power usage and reduces heat.

```bash
sudo apt install tlp
sudo systemctl enable tlp
```

TLP runs automatically in the background.

---

# 🧠 4. Reduce Swappiness (Less Swap, More RAM)

By default, Linux swaps too aggressively on low‑RAM systems.

Check current value:

```bash
cat /proc/sys/vm/swappiness
```

Set swappiness to 10:

```bash
echo 'vm.swappiness=10' | sudo tee /etc/sysctl.d/99-swappiness.conf
```

Apply immediately:

```bash
sudo sysctl -p /etc/sysctl.d/99-swappiness.conf
```

This reduces lag when multitasking.

---

# 🧽 5. Clean Up Unused Packages

Remove leftover dependencies:

```bash
sudo apt autoremove
```

Clear cached packages:

```bash
sudo apt clean
```

---

# 🖥️ 6. Use Lightweight Applications

Prefer lightweight alternatives:

| Task | Heavy App | Lightweight Alternative |
|------|-----------|-------------------------|
| Text editing | VS Code | Mousepad / FeatherPad |
| Image editing | GIMP | Pinta |
| File browsing | Nautilus | Thunar (already in XFCE) |
| Terminal | GNOME Terminal | XFCE Terminal |

VS Code (ARM) works fine, but keep other apps light.

---

# 🧩 7. Disable Unneeded Autostart Programs

Open:

```
Settings → Session and Startup → Application Autostart
```

Disable anything you don’t need.

---

# 🧊 8. Reduce Animations and Effects

In XFCE:

```
Settings → Appearance → Settings → Enable/Disable animations
```

Turn off:

- Window animations  
- Tooltips fade  
- Menu fade  

---

# 🧰 9. Install Performance Tools

### htop — better system monitor

```bash
sudo apt install htop
```

Run it:

```bash
htop
```

### neofetch — system info

```bash
sudo apt install neofetch
```

Run it:

```bash
neofetch
```

---

# 🧼 10. Keep the System Lean

Avoid installing:

- GNOME  
- KDE Plasma  
- Heavy browsers  
- Electron apps (unless necessary)

XFCE is ideal for this hardware.

---

# 🌐 11. Use a Lightweight Browser

Firefox works, but alternatives may be faster:

- **Midori**
- **Falkon**
- **GNOME Web (Epiphany)**

Install example:

```bash
sudo apt install midori
```

---

# 🔧 12. Reboot After Major Updates

Tegra devices sometimes need a reboot to reload kernel modules correctly.

---

# 🏁 Summary

With these optimizations, your HP Chromebook 14 G3 becomes:

- Faster  
- More responsive  
- More stable  
- Better on battery  
- Less prone to freezing  

Despite its age, the Tegra K1 remains a surprisingly capable ARM chip when paired with a lightweight Linux environment.
