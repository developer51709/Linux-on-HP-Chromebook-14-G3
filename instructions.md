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
