# Recovery Guide — Restoring ChromeOS on HP Chromebook 14 G3 (Tegra K1)

This guide explains how to fully restore ChromeOS on the **HP Chromebook 14 G3** after installing Linux using the ChrUbuntu‑Tegra method.  
Restoring ChromeOS will **erase all data** on the device and return it to factory condition.

---

# 📌 When You Should Use This Guide

Use this recovery guide if:

- You want to return the Chromebook to stock ChromeOS  
- Your Linux installation is broken or unbootable  
- The device no longer boots correctly  
- You want to sell or repurpose the Chromebook  
- You want to start over with a clean installation  

This process is safe and officially supported by Google.

---

# 🧰 What You Need

- A separate computer (Windows, macOS, or Linux)  
- A USB flash drive or SD card (4 GB or larger)  
- Internet connection  
- Your HP Chromebook 14 G3  

---

# 🛠️ Step 1 — Identify Your Chromebook Model

Your device is:

**HP Chromebook 14 G3 (Tegra K1, codename: `nyan_blaze`)**

You will need this when creating the recovery media.

---

# 💾 Step 2 — Create ChromeOS Recovery Media

1. On another computer, install the **Chromebook Recovery Utility**:

   Chrome Web Store link:  
   https://chrome.google.com/webstore/detail/chromebook-recovery-utility

2. Open the Recovery Utility.

3. Click the gear icon → **“Erase recovery media”** (optional if reusing a drive).

4. Click **“Get started”**.

5. When asked for your Chromebook model, choose:

   **HP Chromebook 14 G3**  
   or enter the model number printed on the bottom of the device.

6. Insert your USB drive or SD card.

7. Follow the prompts to create the recovery image.

This process takes a few minutes.

---

# 🔄 Step 3 — Enter ChromeOS Recovery Mode

On the Chromebook:

1. Turn the device off.  
2. Hold **Esc + Refresh (⟳)**.  
3. While holding them, tap the **Power** button.  
4. Release all keys when you see the recovery screen.

You should see:

> “ChromeOS is missing or damaged.”

This is normal.

---

# 💽 Step 4 — Restore ChromeOS

1. Insert the USB recovery drive you created.  
2. The Chromebook will automatically detect it.  
3. Follow the on‑screen instructions to reinstall ChromeOS.  
4. Wait for the process to complete (usually 5–10 minutes).  
5. When prompted, remove the USB drive.  
6. The Chromebook will reboot into a fresh ChromeOS installation.

---

# 🔧 Step 5 — Disable Developer Mode (Optional but Recommended)

If you previously enabled Developer Mode, ChromeOS will warn you on every boot.

To disable it:

1. At the white “OS verification is OFF” screen, press **Space**.  
2. Press **Enter** to confirm.  
3. The Chromebook will reset again and return to Verified Mode.

This removes the Developer Mode boot screen.

---

# 🧹 Step 6 — Optional: Securely Wipe User Data

If you want a completely clean system:

1. Boot into ChromeOS.  
2. Press **Ctrl + Alt + Shift + R**.  
3. Select **Powerwash**.  
4. Confirm.

This resets ChromeOS to factory defaults.

---

# 🧭 Troubleshooting Recovery Problems

### ❗ The Chromebook doesn’t detect the USB drive
- Try a different USB port  
- Try a different USB drive  
- Recreate the recovery media  
- Ensure the drive is at least 4 GB  

### ❗ “Invalid recovery image”
- Make sure you selected the correct model  
- Recreate the recovery USB  
- Try a different USB drive  

### ❗ Device keeps booting into Developer Mode
Disable it by pressing **Space** at the white warning screen.

### ❗ Recovery utility fails to write the image
On Windows, run Chrome as Administrator.  
On macOS, ensure the USB drive is not write‑protected.

---

# 🏁 Final Notes

After completing this guide:

- ChromeOS is fully restored  
- All Linux partitions are removed  
- The device is safe to sell, give away, or reuse  
- You can re‑enable Developer Mode later if you want to reinstall Linux  

This process is completely reversible and safe.
