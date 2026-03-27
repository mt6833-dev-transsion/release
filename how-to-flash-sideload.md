# 📦 ROM Installation Guide

A step-by-step guide to flashing a custom ROM using ADB sideload

---

## Prerequisites

- ADB & Fastboot installed on your PC (or use the [Bugjaeger](https://play.google.com/store/apps/details?id=eu.sisik.hackendebug) app)
- USB cable
- Downloaded ROM files and OSS recovery (vendor_boot.img)

---

## Downloaded Files

After downloading the ROM, you should have:

- A `.zip` file (the ROM file)
- `vendor_boot.img` from the rom

---

## Installation Steps

### 1. Enter Fastboot Mode

Boot your device into fastboot mode (USB screen), then run:

```bash
adb reboot bootloader
```

---

### 2. Flash Vendor Boot

```bash
fastboot flash vendor_boot vendor_boot.img
```

---

### 3. Reboot to Recovery

```bash
fastboot reboot recovery
```

---

### 4. Format Data

In recovery:

1. Use **Volume Down** to navigate to **"Format Data"** (or use your finger to navigate because oss recovery support touch feature)
2. Confirm the format
3. Reboot back into **recovery**

> ⚠️ **Warning:** This will wipe all data on your device make sure to backup your data.

---

### 5. Flash the ROM via ADB Sideload

In recovery, select **"Apply Update"**, then select **"Apply rom adb"**,from your PC run:

```bash
adb sideload rom.zip
```

> Replace `rom.zip` with the actual filename of your ROM package.

---

### 6. Wait for Sideload to Complete

> ⏳ **Note:** The process may appear to freeze at **47%** in your terminal. This is normal — do **not** disconnect your device. Be patient and wait for it to finish.

---

### 7. Finish Up

Once sideloading is complete:

1. Recovery may ask if you want to flash another package — select **"No"**
2. Select **"Reboot to system"**

---

## ✅ Done!

Your device should now boot into the new ROM. If it's your first boot, it may take a few minutes — this is normal.

---

## Troubleshooting

| Issue | Solution |
|---|---|
| Stuck at 47% | Wait — do not disconnect. This is expected behavior. |
| Device not detected | Make sure USB debugging is enabled and drivers are installed. |
| Sideload fails | Re-download the ROM zip and verify the file isn't corrupted. |

---
