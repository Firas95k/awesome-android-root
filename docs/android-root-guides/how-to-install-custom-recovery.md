---
layout: doc
title: Custom Recovery Installation Guide 2025
description: "Complete custom recovery installation guide for 2025. Learn to install TWRP, OrangeFox, and SKYHAWK Recovery with step-by-step instructions for all Android devices. Essential for rooting and ROM flashing."
head:
  - - link
    - rel: canonical
      href: https://awesome-android-root.org/android-root-guides/how-to-install-custom-recovery
  - - meta
    - property: og:type
      content: article
  - - meta
    - property: og:title
      content: Complete Custom Recovery Installation Guide 2025 - TWRP, OrangeFox, SKYHAWK
  - - meta
    - property: og:description
      content: Master custom recovery installation with our comprehensive 2025 guide covering TWRP, OrangeFox, and SKYHAWK Recovery. Step-by-step instructions with troubleshooting for all Android devices.
  - - meta
    - property: og:url
      content: https://awesome-android-root.org/android-root-guides/how-to-install-custom-recovery
  - - meta
    - property: og:image
      content: https://awesome-androidroot.org/images/og/custom-recovery.png
  - - meta
    - name: twitter:card
      content: summary_large_image
  - - meta
    - name: twitter:title
      content: Complete Custom Recovery Installation Guide 2025 - TWRP, OrangeFox, SKYHAWK
  - - meta
    - name: twitter:description
      content: Master custom recovery installation with comprehensive guides for TWRP, OrangeFox, and SKYHAWK Recovery on all Android devices.
  - - meta
    - name: keywords
      content: custom recovery guide 2025, TWRP installation, OrangeFox recovery, SKYHAWK recovery, custom recovery flash, fastboot flash recovery, android custom recovery, twrp 3.7.1, orangefox download, shrp recovery, recovery mode android, flash recovery img, custom recovery tutorial, android recovery installation, twrp guide, recovery flashing guide
  - - meta
    - name: author
      content: Awesome Android Root Project
  - - meta
    - property: article:author
      content: https://github.com/awesome-android-root/awesome-android-root
  - - meta
    - property: article:section
      content: Custom Recovery
  - - meta
    - property: article:tag
      content: Custom Recovery
  - - meta
    - property: article:tag
      content: TWRP
  - - meta
    - property: article:tag
      content: OrangeFox
  - - meta
    - property: article:tag
      content: SKYHAWK Recovery
  - - meta
    - property: article:tag
      content: Recovery Installation
  - - meta
    - property: article:tag
      content: Fastboot Flash
  - - meta
    - property: article:tag
      content: Android Recovery
  - - meta
    - property: article:tag
      content: ROM Flashing
  - - meta
    - property: article:tag
      content: Android Modification
  - - meta
    - name: robots
      content: index, follow
  - - meta
    - name: viewport
      content: width=device-width, initial-scale=1.0
  - - meta
    - property: article:published_time
      content: 2025-01-01T00:00:00Z
  - - meta
    - property: article:modified_time
      content: 2025-06-25T00:00:00Z
---

# Custom Recovery Installation Guide

Complete guide for beginners and advanced users to install custom recovery - your gateway to root access, custom ROMs, and advanced Android modifications.

## Table of Contents
- [Overview](#what-is-custom-recovery)
- [Recovery Options](#recovery-options)
- [Prerequisites](#prerequisites)
- [Installation Process](#installation-process)
- [Post-Installation](#post-installation)
- [Essential Operations](#essential-operations)
- [Troubleshooting](#troubleshooting)

# What is Custom Recovery?
Custom recovery is a specialized environment that replaces your device's stock recovery mode, providing advanced system management capabilities.

### What You Can Do
- **Flash custom ROMs** (LineageOS, Pixel Experience, etc.)
- **Install root solutions** (Magisk, KernelSU, APatch)
- **Create complete system backups** (NANDroid)
- **Manage system files** with root access
- **Install mods and frameworks** (LSPosed, Xposed)

### Stock vs Custom Recovery

| **Stock Recovery** | **Custom Recovery** |
|-------------------|-------------------|
| ✅ Factory reset and cache wipes | ✅ All stock features plus advanced options |
| ✅ Official OTA updates | ✅ Custom ROM and kernel installation |
| ❌ No custom ROM support | ✅ Complete system backups (NANDroid) |
| ❌ Limited file management | ✅ Advanced file manager with root access |
| ❌ No root package installation | ✅ Flash Magisk, KernelSU, and custom packages |
| ❌ Basic interface | ✅ Touch-friendly modern interface |

### Requirements Path
1. 🔓 **[Unlock bootloader](./how-to-unlock-bootloader.md)** ← Start here
2. 🛠️ **Install custom recovery** (this guide)
3. ⚡ **[Install root solution](./index.md)** ← Next step

::: danger ⚠️ ESSENTIAL PREREQUISITE
**Unlocked bootloader required!** Complete [bootloader unlocking](./how-to-unlock-bootloader.md) first.
:::

## Recovery Options

Choose the best recovery for your needs:

### TWRP (Recommended for Beginners)
**[Team Win Recovery Project](https://twrp.me/)** - Most popular and stable

- ✅ **Widest device support** and extensive documentation
- ✅ **Proven stability** with large community
- ✅ **Touch interface** with easy navigation
- ❌ Basic interface design
- **Best for:** First-time users, maximum compatibility

### OrangeFox (Best Interface)
**[OrangeFox Recovery](https://orangefox.download/)** - Modern TWRP-based recovery

- ✅ **Beautiful modern interface** with Material Design
- ✅ **Enhanced features** and improved file manager
- ✅ **TWRP compatible** with regular updates
- ❌ Limited device support vs TWRP
- **Best for:** Users wanting modern UI and extra features

### SKYHAWK/SHRP (Advanced Features)
**[SKYHAWK Recovery](https://skyhawkrecovery.github.io/)** - Feature-rich with dashboard

- ✅ **Unique dashboard interface** with built-in tools
- ✅ **Security features** (password protection)
- ✅ **Integrated Magisk installer** and theming
- ❌ Newest project with smallest device support
- **Best for:** Power users wanting cutting-edge features

::: tip 💡 Quick Decision Guide
- **New to custom recovery?** → Choose TWRP
- **Want modern interface?** → Choose OrangeFox  
- **Need advanced features?** → Choose SKYHAWK
- **Device not supported?** → Check XDA Forums for unofficial builds
:::

## Prerequisites

### Required (Must Complete First)
::: danger ⚠️ ESSENTIAL REQUIREMENTS
1. **[Unlocked bootloader](./how-to-unlock-bootloader.md)** - Absolutely required
2. **ADB/Fastboot tools** - [Setup guide](./how-to-unlock-bootloader.md#step-3-set-up-adb-and-fastboot)
3. **USB debugging enabled** - In Developer Options
4. **Correct recovery image** - For your exact device model
5. **50%+ battery charge** - Prevent interruption during flashing
:::

### Important Warnings
- **Wrong recovery = brick risk** - Double-check device compatibility
- **Warranty voided** - Beyond bootloader unlocking
- **Backup recommended** - Create full backup before proceeding
- **Power interruption** - Can cause serious device issues

## Installation Process

### Step 1: Download Recovery Image

1. **Find your device specs:**
   - Settings → About Phone → Model Number
   - Note Android version and device codename

2. **Download from official sources:**
   - **TWRP:** [twrp.me/Devices](https://twrp.me/Devices/)
   - **OrangeFox:** [orangefox.download](https://orangefox.download/)
   - **SKYHAWK:** [skyhawkrecovery.github.io](https://skyhawkrecovery.github.io/Devices.html)


::: tip 💡 Device Not Listed?
If your device isn't officially supported:
- Check XDA Developers forum for unofficial builds
- Look for Telegram groups for your device
- Consider TWRP first as it has widest support
:::

### Step 2: Prepare for Installation

1. **Place Recovery File:**
   - Move downloaded `.img` file to ADB/Fastboot folder
   - Rename to simple name: `recovery.img`

2. **Enable USB Debugging:**
   - Ensure USB Debugging is still enabled
   - Connect device to computer

3. **Test ADB Connection:**
```bash
adb devices
```
Expected output: `[device_serial] device`

### Step 3: Boot to Fastboot Mode

Choose your method:

**Method 1: ADB Command (Recommended)**
```bash
adb reboot bootloader
```

**Method 2: Hardware Keys**
- Power off device completely
- Hold Volume Down + Power until fastboot screen appears
- (Key combination varies by manufacturer)

**Method 3: Fastboot Command (if in fastboot already)**
```bash
fastboot devices
```
Verify device is detected: `[device_serial] fastboot`

### Step 4: Flash Custom Recovery

::: warning ⚠️ CRITICAL STEP
**Double-check you have the correct recovery image for your exact device model before proceeding!**
:::

**Flash the recovery:**
```bash
fastboot flash recovery recovery.img
```

**Expected output:**
```
Sending 'recovery' (xxxxx KB)...
OKAY [  x.xxxs]
Writing 'recovery'...
OKAY [  x.xxxs]
Finished. Total time: x.xxxs
```

### Step 5: Boot to Recovery (Important!)

**Immediately boot to recovery to prevent stock recovery restoration:**

**Method 1: Fastboot Command**
```bash
fastboot boot recovery.img
```

**Method 2: Hardware Keys**
- Use Volume buttons to navigate to "Recovery Mode"
- Press Power to select
- Device should boot directly to custom recovery

::: tip 💡 Why Boot Immediately?
Some devices automatically restore stock recovery on first normal boot. Booting to custom recovery first prevents this restoration.
:::

## Post-Installation

### 1. Verify Installation
- Boot to recovery using hardware keys (Volume Up + Power)
- Navigate through menus to test touch/button response
- Check if all features load properly

### 2. Create NANDroid Backup (Critical!)
::: tip 💾 CREATE BACKUP FIRST
**Always create a complete backup before making any system changes!**
:::

**In recovery interface:**
1. Go to **Backup** section
2. Select partitions:
   - ✅ **Boot** (essential)
   - ✅ **System** (essential)
   - ✅ **Data** (recommended)
   - ✅ **Recovery** (for safety)
3. Start backup (takes 10-30 minutes)
4. Store backup files safely

### 3. Test Basic Functions
- **File manager** - Browse system folders
- **Flash test** - Try flashing a simple zip
- **Wipe functions** - Test cache wipe (safe)

## Essential Operations

### Installing ZIP Files
1. Download `.zip` file to device storage
2. Boot to recovery
3. **Install** → Navigate to file → **Swipe to confirm**
4. **Reboot System** when complete

### Managing Backups
- **Create:** Backup → Select partitions → Start
- **Restore:** Restore → Select backup → Choose partitions → Confirm
- **Store safely:** Copy backups to computer/cloud storage

### Wiping System
- **Factory Reset:** Wipe → Factory Reset (keeps internal storage) 
- **Advanced Wipe:** Choose specific partitions (System, Data, Cache, etc.)
- **Format Data:** Complete data partition wipe (loses encryption)

::: warning ⚠️ Wipe Warnings
- **System wipe** removes Android OS - have ROM ready to flash
- **Data wipe** removes all user data and apps
- **Format Data** removes encryption - requires password/PIN reset
:::

## Troubleshooting

### Common Issues

#### Recovery Won't Boot
**Problem:** Device stuck on boot screen or bootloop
**Solutions:**
1. **Re-flash recovery:**
   ```bash
   fastboot flash recovery recovery.img
   ```
2. **Try different recovery version** or different recovery project
3. **Emergency: Flash stock recovery** if available

#### "No OS Installed" Warning
**Problem:** Recovery shows system not detected
**Solutions:**
1. **Ignore and reboot** - often boots normally anyway
2. **Flash custom ROM** if this was your intention
3. **Restore system backup** if available

#### Touch Not Working
**Problem:** Cannot navigate recovery with touch
**Solutions:**
1. **Use hardware keys** - Volume keys navigate, Power selects
2. **Try different recovery** - Some have better touch support
3. **Check device compatibility** - May need specific build

#### Recovery Disappears
**Problem:** Custom recovery replaced by stock after reboot
**Solutions:**
1. **Install root solution** (Magisk) to prevent replacement
2. **Boot to recovery immediately** after flashing
3. **Avoid normal boot** until root is installed

### Emergency Recovery

If recovery is completely broken:

1. **Boot to fastboot:**
   ```bash
   fastboot devices
   ```

2. **Flash stock recovery:**
   ```bash
   fastboot flash recovery stock_recovery.img
   ```

3. **Flash stock ROM if needed:**
   - Samsung: Use Odin + stock firmware
   - Xiaomi: Mi Flash Tool + fastboot ROM  
   - OnePlus: MSM Download Tool
   - Google: Factory images

### Advanced Troubleshooting

**Fastboot not working:**
- Check USB drivers (Windows)
- Try different USB port/cable
- Enable OEM unlocking again
- Use different computer

**Recovery crashes:**
- Wrong recovery for device variant
- Corrupted download - re-download
- Hardware incompatibility

---

## Next Steps

**Recovery installed successfully!** Choose your path:

### For Beginners
1. **[Install Magisk](./index.md)** - Most popular root solution
2. **Practice with recovery** - Create backups, flash simple mods
3. **Read FAQ** - Common questions answered

### For Advanced Users  
1. **[Try KernelSU/APatch](./index.md)** - Kernel-based root alternatives
2. **[Install custom ROM](./custom-rom-installation.md)** - Complete Android replacement
3. **[Set up development environment](./index.md)** - For ROM building

### Need Help?
- **[Complete FAQ](../faqs.md)** - Troubleshooting guide
- **[Join community](../about.md)** - Get support from other users
- **XDA Forums** - Device-specific help

::: tip 🎉 Congratulations!
You've successfully installed custom recovery! This unlocks the full potential of Android modification. Take time to explore the interface and always backup before making changes.
:::
