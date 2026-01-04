# FAQ — Linux on HP Chromebook 14 G3 (Tegra K1)

This FAQ covers the most common questions about installing and running Linux on the HP Chromebook 14 G3 using the ChrUbuntu‑Tegra method.

---

## ❓ Why can’t I install Linux Mint, Arch Linux (x86), or other standard distros?

Because the HP Chromebook 14 G3 uses an **ARM Tegra K1 processor**, not Intel or AMD.  
Most mainstream Linux distros only provide **x86_64** builds.

ARM Chromebooks also cannot flash a traditional BIOS, so they cannot boot normal Linux installers.

---

## ❓ Why can’t I flash custom firmware (MrChromebox BIOS)?

MrChromebox firmware **does not support ARM Chromebooks**.  
Only Intel/AMD Chromebooks can replace their firmware.

ARM devices must use the ChromeOS boot chain.

---

## ❓ Why can’t I run `.exe` files or Windows apps?

Wine does **not** support Windows applications on ARM Linux.  
There is no x86 emulation layer available for this device.

---

## ❓ Why doesn’t the Play Store show up?

The HP Chromebook 14 G3 is too old to support Android apps.  
Google never enabled Play Store support for Tegra K1 Chromebooks.

---

## ❓ Why doesn’t “Linux (Beta)” (Crostini) appear in settings?

Crostini requires:

- A newer kernel  
- A newer CPU  
- A newer ChromeOS generation  

The 14 G3 does not meet these requirements.

---

## ❓ Can I dual‑boot ChromeOS and Linux?

Yes — the ChrUbuntu‑Tegra script supports dual‑boot‑style setups.  
However, most users choose to allocate most storage to Linux.

---

## ❓ Can I revert back to ChromeOS?

Yes.  
You can always restore ChromeOS using a recovery USB:

1. Turn off the Chromebook  
2. Hold **Esc + Refresh**, then tap **Power**  
3. Insert a ChromeOS recovery USB  
4. Follow the on‑screen instructions  

---

## ❓ Can I install Arch Linux ARM instead of Ubuntu ARM?

Not cleanly.  
Arch ARM on Tegra K1 requires:

- Custom kernels  
- Manual boot configuration  
- Hardware‑specific patches  

There is no stable, repeatable full‑wipe Arch ARM installer for this model.

Ubuntu ARM via ChrUbuntu‑Tegra is the most reliable method.

---

## ❓ Does GPU acceleration work?

Yes — the Tegra K1 GPU supports OpenGL ES.  
Performance is surprisingly good for an older ARM device.

---

## ❓ Can I update the kernel inside Ubuntu?

**No.**  
Never install kernel updates inside Ubuntu ARM.

The system must continue using the ChromeOS kernel.

---

## ❓ Is this setup good for development?

Yes — it works well for:

- Python  
- Node.js  
- Web development  
- Lightweight coding  
- Learning Linux  

It is not suitable for:

- Heavy workloads  
- x86‑only software  
- Gaming  

---

## ❓ Does this work on other Tegra Chromebooks?

Yes — the ChrUbuntu‑Tegra method also works on:

- Acer Chromebook 13 (nyan_big)  
- Acer Chromebook 13 touchscreen (nyan_blaze variant)  

But instructions may vary slightly.
