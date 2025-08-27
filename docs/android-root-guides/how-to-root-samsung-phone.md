---
layout: doc
title: Complete Samsung Galaxy Rooting Guide
description: "Master guide to root Samsung Galaxy devices - S24, S23, A series with bootloader unlock and Magisk installation. Navigate Knox and One UI complexities."
head:
  - - link
    - rel: canonical
      href: https://awesome-android-root.org/android-root-guides/how-to-root-samsung-phone
  - - meta
    - property: og:type
      content: article
  - - meta
    - property: og:title
      content: Complete Samsung Galaxy Rooting Guide - All Models Supported
  - - meta
    - property: og:description
      content: Root any Samsung Galaxy device with our comprehensive guide covering bootloader unlock, Knox bypass and Magisk installation for One UI.
  - - meta
    - property: og:url
      content: https://awesome-android-root.org/android-root-guides/how-to-root-samsung-phone
  - - meta
    - property: og:image
      content: https://awesome-android-root.org/images/og/samsung.png
  - - meta
    - name: twitter:card
      content: summary_large_image
  - - meta
    - name: twitter:title
      content: Complete Samsung Galaxy Rooting Guide - All Models
  - - meta
    - name: twitter:description
      content: Root any Samsung Galaxy device with bootloader unlock and Magisk installation guide.
  - - meta
    - name: keywords
      content: samsung galaxy root guide, samsung rooting, samsung bootloader unlock, samsung magisk guide, one ui root, galaxy s24 root, galaxy s23 root, galaxy a series root, samsung knox, odin samsung
  - - meta
    - name: author
      content: Awesome Android Root Project
  - - meta
    - property: article:author
      content: https://github.com/awesome-android-root/awesome-android-root
  - - meta
    - property: article:section
      content: Device Rooting
  - - meta
    - property: article:tag
      content: Samsung Galaxy Root
  - - meta
    - property: article:tag
      content: One UI
  - - meta
    - property: article:tag
      content: Knox Security
  - - meta
    - property: article:tag
      content: Magisk Installation
  - - meta
    - name: robots
      content: index, follow
---

# Complete Samsung Galaxy Rooting Guide

**Root Samsung's flagship phones** – Galaxy S24, S23, A series, and more – using bootloader unlock and careful Knox management. This updated guide reflects **2025 firmware standards**, **Android 15 (One UI 7)** compatibility, and the latest **Magisk**, **Play Integrity Fix**, and **Heimdall** tooling.

---

## 🔗 Essential Resources
- **[📖 Main Rooting Guide](./index.md)** – Universal rooting principles and safety
- **[🔓 Bootloader Unlocking](./how-to-unlock-bootloader.md)** – General bootloader concepts
- **[🛠️ Custom Recovery](./how-to-install-custom-recovery.md)** – TWRP installation guide
- **[❓ FAQ & Troubleshooting](../faqs.md)** – Solutions for common issues

---

## Samsung Rooting Landscape

**Samsung Unique Challenges:**
- **Knox Security** – Hardware-level security that gets permanently tripped
- **Bootloader restrictions** – Carrier and regional locking still prevalent
- **Complex partitioning** – A/B system partitions with **dual boot images** and **vendor_boot**
- **Odin flashing tool** – Proprietary method for firmware flashing
- **One UI integration** – Deep system-level hooks affect root stability
- **Android 15 (One UI 7)** – Increased security with **Play Integrity Attestation**, **Zygisk mandatory**, and **module signature enforcement**

---

## Critical Warnings

::: danger ⚠️ Samsung-Specific Risks
- **Knox permanently tripped (0x1)** – **Cannot be reversed**, affects Samsung Pay, Health, Secure Folder
- **Warranty completely void** – Samsung will refuse all service once Knox is tripped
- **Carrier restrictions** – US carrier models (Verizon, AT&T) often **cannot unlock bootloader**
- **Banking & financial app detection** – Enhanced root detection via **Play Integrity** and **SafetyNet**
- **OTA updates blocked** – Official updates will fail unless root is temporarily uninstalled
- **Samsung Cloud & Find My Mobile** – May flag device as compromised
:::

---

## Device Compatibility Check

### Supported Devices

**Galaxy S Series (Flagship):**
- **Galaxy S24/S24+/S24 Ultra** – Snapdragon only (Exynos not yet supported by Magisk)  
- **Galaxy S23/S23+/S23 Ultra** – Global, Canadian, and unlocked models supported
- **Galaxy S22/S22+/S22 Ultra** – All regions except carrier-locked US models
- **Galaxy S21/S21+/S21 Ultra** – Excellent support across all variants
- **Older S series (S20 and prior)** – Full root and custom ROM support

**Galaxy A Series (Mid-range):**
- **Galaxy A55/A54/A53** – A55 has full Magisk support
- **Galaxy A35/A34/A33** – A35 supported; older models may require older Magisk
- **Galaxy A25/A24/A23** – A25 works; A23 has limited recovery support
- **Older A series** – Check XDA forums for model-specific status

**Galaxy Z Series (Fold/Flip):**
- **Z Fold 5/6, Z Flip 5/6** – Supported with Magisk and TWRP alternatives
- **Z Fold 4 and older** – Stable root via AP patching

**Galaxy Note Series:**
- **Galaxy Note 20/Note 20 Ultra** – Final Note generation, still actively used
- **Galaxy Note 10/10+** – Legacy support, excellent TWRP availability
- **Older Note devices** – Strong custom ROM community

---

### Unsupported/Restricted Devices

**US Carrier Models:**
- **Verizon (VZW)** – Bootloader locked, **cannot unlock**
- **AT&T** – Most models **bootloader locked**
- **T-Mobile** – Some older models unlockable; newer ones restricted
- **Sprint** – Legacy devices only; mostly locked

**Regional Restrictions:**
- **China variants (e.g., SM-S9180)** – Different firmware, **no official root support**
- **Enterprise models** – Additional Knox policies block modifications
- **Government/secure variants** – Heavily locked down, **not rootable**

---

## Prerequisites & Setup

### Required Tools
1. **[Samsung Odin](https://odindownload.com/)** – Official flashing tool
2. **[Samsung USB Drivers](https://developer.samsung.com/mobile/android-usb-driver.html)** – Critical for ADB/Odin
3. **[Magisk APK](https://github.com/topjohnwu/Magisk/releases)** – Latest stable
4. **[SamFrew](https://samfrew.com/)** – Updated firmware downloader (successor to SamMobile/Frija)
5. **[Heimdall](https://glassechidna.com.au/heimdall/)** – Open-source Odin alternative for Linux/macOS

### Device Preparation
1. **Check bootloader status:**
   - Settings → About Phone → Software Information
   - Look for **OEM Lock: ON/OFF**
   - If "OFF" – bootloader already unlocked

2. **Enable Developer Options:**
   - Settings → About Phone → Tap **Build Number 7 times**
   - Enable **USB Debugging**
   - Enable **OEM Unlocking** (if available)

3. **Backup everything:**
   - **Samsung Cloud** – Sync contacts, messages
   - **Smart Switch PC** – Full device backup
   - **Manual backup** – Photos, downloads, EFS (if possible)

4. **Charge to 70%+** – Flashing requires stable power

### Connection Testing
```bash
# Test ADB connection
adb devices

# Should show device in list
# Accept USB debugging prompt if shown
```

---

## Bootloader Unlocking Process

Samsung bootloader unlocking varies significantly by model and region.

### Step 1: Check Unlock Eligibility
1. **Dial `*#197328640#`** or use **Samsung Members app**
2. Navigate to: **System → Device Security → Knox Status**
3. **Knox Status must show:** Not triggered / Normal
4. **OEM Lock Status:** Must be available to disable

> ⚠️ If Knox is already tripped (0x1), root is still possible, but Samsung Pay and Secure Folder are permanently disabled.

### Step 2: Enable OEM Unlocking
1. **Settings → Developer Options**
2. **Enable "OEM Unlocking"**
3. **May require internet connection** for Samsung server verification
4. **Wait 7 days** if prompted (Samsung’s waiting period for new devices)

### Step 3: Boot to Download Mode
```bash
# Method 1: ADB command
adb reboot download

# Method 2: Hardware keys
# Power off → Hold Volume Up + Volume Down + Power
```

### Step 4: Unlock Bootloader
1. **In Download Mode:**
   - Long press **Volume Up** when prompted
   - Accept bootloader unlock warning
   - Device will factory reset and reboot

2. **Verify unlock:**
   - Should see **"CUSTOM"** in download mode
   - Knox will show **"KNOX WARRANTY VOID: 0x1"**

---

## Root Installation Methods

### Method A: AP Patching (Recommended)

Samsung uses complex firmware files that require specific handling.

#### Step 1: Download Firmware
1. **Find your exact model:**
   - Settings → About Phone → Model Number (e.g., **SM-S918U**, **SM-G998B**)
   - Note **region (CSC)** and **current build number**

2. **Download firmware:**
   - Use **[SamFrew](https://samfrew.com/)** or **Frija**
   - Match **model, region, and build number exactly**
   - Download includes: **AP, BL, CP, CSC** files

#### Step 2: Extract and Patch AP File
1. **Extract AP file** from firmware ZIP
2. **Transfer AP file to device:**
   ```bash
   adb push AP_[model]_[version].tar.md5 /sdcard/Download/
   ```

3. **Install Magisk APK:**
   ```bash
   adb install Magisk-v27.apk
   ```

4. **Patch AP file in Magisk:**
   - Open Magisk app
   - Tap **Install** → **Select and patch a file**
   - Select the AP file from Downloads
   - Wait for patching completion

5. **Retrieve patched AP:**
   ```bash
   adb pull /sdcard/Download/magisk_patched_[hash].tar ./
   ```

#### Step 3: Flash with Odin
1. **Boot to Download Mode:**
   ```bash
   adb reboot download
   ```

2. **Open Odin as Administrator**
3. **Load firmware files:**
   - **BL:** Original BL file
   - **AP:** Magisk-patched AP file  
   - **CP:** Original CP file
   - **CSC:** Original CSC file (⚠️ **NOT HOME_CSC**)

4. **Flash configuration:**
   - **Auto Reboot:** Checked
   - **F. Reset Time:** Checked
   - **Re-Partition:** Unchecked
   - **Options → Auto Reboot:** **UNCHECK** (critical for System-as-Root)

5. **Click START** and wait for completion
6. **Do NOT let device reboot automatically**

---

### Step 4: Factory Reset (MANDATORY!)

> 🔥 **This is the most important step for System-as-Root devices!**

**Enter Recovery Mode:**
1. Unplug USB cable
2. Hold **Power** + **Volume Down** to force shutdown
3. When screen goes black, **immediately** switch to:
4. Hold **Power** + **Volume Up** until recovery appears

**Perform Factory Reset:**
1. Use **Volume buttons** to navigate, **Power** to select
2. Select **Wipe data/factory reset**
3. Confirm the reset
4. After completion, select **Reboot system now**

---

### Step 5: Finalize Root Installation

**Complete Setup:**
1. Device boots to "Welcome" screen again
2. Complete initial setup (connect to Wi-Fi)
3. Copy `Magisk-v27.apk` to device and install again

**Verify Root:**
1. Open **Magisk** app
2. You may see "Additional Setup Required" – tap **OK**
3. App will finish setup and reboot device
4. After reboot, open Magisk again
5. If you see green checkmarks, **congratulations!** 🎉

---

## Alternative Root Methods

### Method B: Custom Recovery Route

Some Samsung devices support custom recovery installation.

#### Step 1: Install TWRP/OrangeFox
1. **Download recovery image** for exact model from [TWRP.me](https://twrp.me) or [OrangeFox](https://orangefox.download)
2. **Flash via Odin:**
   - Load recovery.img in **AP** slot
   - Flash recovery only
   - **Boot to recovery immediately**

#### Step 2: Install Magisk via Recovery
1. **Transfer Magisk ZIP** to device storage
2. **In recovery:** Install → Select Magisk ZIP
3. **Reboot system**

> ✅ **Advantage:** Easier module management, backup/restore, and future updates

---

### Method C: Heimdall (Linux/macOS)

For non-Windows users, **Heimdall** provides Samsung flashing:

1. **Install Heimdall:**
   ```bash
   # Ubuntu/Debian
   sudo apt install heimdall-flash
   
   # macOS
   brew install heimdall
   ```

2. **Flash patched boot:**
   ```bash
   heimdall flash --BOOT magisk_patched.img
   ```

> ⚠️ Heimdall does not support all Samsung models. Check [glassechidna.com.au/heimdall](https://glassechidna.com.au/heimdall/) for compatibility.

---

## Samsung-Specific Troubleshooting

### Knox and Security Issues

#### Knox Status Management
After rooting, Knox security is permanently affected:

**Knox Consequences:**
- **Knox WARRANTY VOID: 0x1** – Cannot be reversed
- **Samsung Pay disabled** – Hardware security compromised
- **Secure Folder broken** – Secure environment unavailable
- **Banking apps detection** – Some may refuse to work

**Mitigation Strategies:**
```bash
# Check current Knox status
adb shell getprop ro.boot.warranty_bit

# Hide root from banking apps using Magisk
# Enable Zygisk → DenyList → Add problematic apps
```

---

### Firmware-Specific Issues

#### AP File Patching Problems
**Invalid AP File Error:**
- Re-download firmware from **SamFrew** or **Frija**
- Verify file integrity using **MD5 checksum**
- Try **Magisk v26** if v27 fails

**Magisk Patching Fails:**
```bash
# Alternative method using manual extraction
tar -xf AP_*.tar.md5
# Locate boot.img.lz4 within extracted files
lz4 -d boot.img.lz4 boot.img
# Patch boot.img directly in Magisk
```

#### Odin Flashing Failures
**FAIL (auth)** Error Solutions:
- Ensure bootloader is **unlocked**
- Use **exact firmware** matching device
- Enable **"OEM Unlocking"** in Developer Options

**Device Not Detected:**
- Install **Samsung USB drivers** properly
- Try **USB 2.0 port**
- Use **high-quality USB cable**

---


## Performance Optimization

---

## Staying Updated

### OTA Update Handling
Samsung OTA updates require careful management:

**Before Update:**
```bash
# Method 1: Magisk uninstall (recommended)
# Open Magisk → Uninstall → Restore Images
```

**After Update:**
1. Download **new firmware** matching updated build
2. Extract new AP file
3. Patch with Magisk and flash via Odin
4. Re-configure modules and DenyList


::: tip 💡 Samsung Root Success Tips
**Best Practices:**
- Samsung devices require patience due to Knox complexity
- Always use **exact firmware** matching your device
- Knox trip is **permanent** – accept this before starting
- Custom ROMs can restore some lost Samsung features
- **Backup EFS partition** for IMEI/baseband recovery
:::

---


## Additional Resources
### Community Resources
- **[Samsung XDA Forums](https://forum.xda-developers.com/c/samsung.12063/)** – Device-specific development
- **[One UI Mods Community](https://t.me/oneuimods)** – Samsung customization
- **[r/GalaxyS24](https://reddit.com/r/GalaxyS24)** – Latest device discussions
- **[Samsung Firmware Database](https://samfrew.com/)** – Firmware downloads

### **Essential Samsung Resources:**

- **[Samsung XDA Forums](https://forum.xda-developers.com/c/samsung.12063/)** – Device-specific development
- **[Samsung Members](https://www.samsung.com/us/support/mobile-devices/)** – Official support
- **[One UI Mods Community](https://t.me/oneuimods)** – Samsung customization
- **[Samsung Smart Switch](https://www.samsung.com/us/support/owners/app/smart-switch)** – Backup tool
- **[SamFrew](https://samfrew.com/)** – Firmware downloads
- **[ODIN Download](https://odindownload.com/)** – Latest Odin (v3.14.4)
- **[Heimdall](https://glassechidna.com.au/heimdall/)** – Open-source alternative

### **Recovery & Backup:**
- **[TWRP](https://twrp.me/)**
- **[OrangeFox](https://orangefox.download/)**
- **[Neo Backup](https://github.com/NeoApplications/Neo-Backup)**

---

**🔗 Related Guides:**
- **[🔓 Bootloader Unlocking Guide](./how-to-unlock-bootloader.md)**
- **[🛠️ Custom Recovery Installation](./how-to-install-custom-recovery.md)**
- **[❓ FAQ & Troubleshooting](../faqs.md)**
- **[📖 Complete Rooting Master Guide](./index.md)**