# Post‑Install Setup Guide  
_For Ubuntu ARM + XFCE on HP Chromebook 14 G3 (Tegra K1)_

This guide helps you finish setting up your Linux environment after installation. It focuses on development tools, system optimization, and making your Chromebook feel like a proper Linux laptop.

---

# 1. Update and Upgrade the System

Always start by refreshing your package lists and installing updates.

```bash
sudo apt update
sudo apt upgrade
```

Optional but recommended:

```bash
sudo apt install software-properties-common
```

---

# 2. Install Essential Development Tools

These are the basics for coding, compiling, and working with Git.

```bash
sudo apt install git build-essential curl wget
```

---

# 3. Configure Git (Optional but Recommended)

Replace the placeholders with your actual name and email.

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

# 4. Install Python and Tools

Python is usually preinstalled, but ensure you have everything you need.

```bash
sudo apt install python3 python3-pip python3-venv
```

### Create a virtual environment (recommended for projects)

```bash
python3 -m venv ~/envs/myenv
source ~/envs/myenv/bin/activate
```

---

# 5. Install Node.js and npm

Ubuntu ARM supports Node.js directly from the repos.

```bash
sudo apt install nodejs npm
```

Check versions:

```bash
node -v
npm -v
```

---

# 6. Install VS Code (ARM Build)

Ubuntu ARM often includes Code OSS (open‑source VS Code build).

```bash
sudo apt install code-oss
```

If not available, search:

```bash
apt search code
```

---

# 7. Improve XFCE Usability

### Install useful XFCE plugins

```bash
sudo apt install xfce4-whiskermenu-plugin xfce4-taskmanager xfce4-power-manager
```

### Add the Whisker Menu

1. Right‑click the panel  
2. “Panel → Add New Items”  
3. Add **Whisker Menu**  
4. Move it to the left side of the panel

---

# 8. Install Themes and Icons (Optional)

These make XFCE look more modern or Mint‑like.

```bash
sudo apt install arc-theme numix-icon-theme
```

Apply them:

- **Settings → Appearance**
- **Settings → Window Manager**

---

# 9. Enable Firewall (Optional but Recommended)

Ubuntu includes UFW (Uncomplicated Firewall).

```bash
sudo apt install ufw
sudo ufw enable
sudo ufw status
```

---

# 10. Install Useful Everyday Apps

### File archivers

```bash
sudo apt install p7zip-full unzip
```

### Media tools

```bash
sudo apt install vlc gimp
```

### System monitoring

```bash
sudo apt install htop neofetch
```

Run neofetch:

```bash
neofetch
```

---

# 11. Improve Battery Life and Performance

### Install TLP (power management)

```bash
sudo apt install tlp
sudo systemctl enable tlp
```

### Reduce animations in XFCE

- **Settings → Window Manager Tweaks → Compositor**
- Disable or reduce effects

---

# 12. Clean Up the System

Remove unused packages:

```bash
sudo apt autoremove
```

Clear cached packages:

```bash
sudo apt clean
```

---

# 13. Create a Backup Snapshot (Optional)

Since this is a Chromebook running a custom Linux setup, it’s smart to back up your home folder.

```bash
rsync -avh --progress ~/ /media/usbdrive/backup/
```

Replace `/media/usbdrive/backup/` with your actual USB mount point.

---

# 14. Verify Everything Works

Check:

- Wi‑Fi  
- Audio  
- Trackpad  
- Keyboard shortcuts  
- External USB devices  

If something isn’t working, reboot once more — Tegra devices sometimes need a second boot after updates.

---

# 15. You’re Ready to Start Coding

You now have:

- Python + pip + venv  
- Node.js + npm  
- Git  
- VS Code (ARM)  
- XFCE desktop  
- A stable Ubuntu ARM environment  

Your Chromebook is now a fully functional Linux development machine.
