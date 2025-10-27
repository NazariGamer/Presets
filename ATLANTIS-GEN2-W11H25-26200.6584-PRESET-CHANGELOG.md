# ATLANTIS-GEN2-W11H25-26200.6584-PRESET Changelog

This document describes the changes between each version of the ATLANTIS-GEN2-W11H25-26200.6584-PRESET NTLite presets.

## Overview

- **Target Image**: Windows 11 Professional 25H2 x64 - 10.0.26200.6584 (en-GB)
- **Image GUID**: {29CB82C7-689A-4C77-B569-15AA20C3D3B8}
- **Host Environment**: Windows 11 Professional 25H2 x64 - 10.0.26200.6901 (en-GB)
- **NTLite Version**: 2025.10.10649

---

## Version 0.0.1 (2025-10-27 15:53:52)

### Initial Release
- **Basic configuration**: Minimal preset with core structure
- **Components**: 
  - Empty RemoveComponents section
  - Empty Compatibility section
  - Empty Tweaks section
- **Image Tasks**:
  - `imageSaveRebuild`
  - `imageFormatWim`

### Features
- Base preset template
- No component removal
- No packages included
- No unattended installation configuration
- Standard WIM format output

---

## Version 0.0.2 (2025-10-27 15:57:49)

### Added Features
- **Packages Integration**: Added comprehensive package management
- **Update Management**: Integrated Windows Update packages

### New Packages (11 total)
1. **Security Updates**:
   - `windows11.0-kb5070762-x64` (CAB)
   - `windows11.0-kb5070773-x64` (MSU)
   - `windows11.0-kb5066683-x64` (CAB)

2. **Framework Updates**:
   - `windows11.0-kb5066128-x64-ndp481` (.NET Framework 4.8.1)

3. **Platform Components**:
   - `updateplatform.amd64fre` (Update Platform)
   - `mpam-fe.exe` (Microsoft Antimalware)

4. **Modern Apps**:
   - `Microsoft.UI.Xaml.2.8_8.2501.31001.0_x64.appx`
   - `Microsoft.WindowsAppRuntime.1.8_8000.616.304.0_x64.appx`
   - `Microsoft.WSL_2.6.2.0_x64_ARM64.msixbundle` (Windows Subsystem for Linux)
   - `Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle` (App Installer)
   - `Microsoft.WindowsTerminal_1.23.12811.0_8wekyb3d8bbwe.msixbundle` (Windows Terminal)

### Package Options
- **CleanHotfixedLeftovers**: Enabled for cleanup optimization

### Changes from 0.0.1
- ✅ Added comprehensive Windows Updates package
- ✅ Included modern Windows applications
- ✅ Added security and framework updates
- ⚡ Enhanced with WSL and development tools

---

## Version 0.0.3 (2025-10-27 16:08:07)

### Major Enhancement: Unattended Installation

### New Features
- **Full Unattended Setup**: Complete automated installation configuration
- **Multi-pass Configuration**: windowsPE, specialize, and oobeSystem passes
- **Enhanced Image Tasks**: Added Windows Recovery Environment processing

### Unattended Configuration Details

#### Windows PE Pass
- **Localization**:
  - Input Locale: `040a:0000040a` (Spanish keyboard layout)
  - System Locale: `en-GB`
  - UI Language: `en-GB`
  - Setup UI Language: `en-GB`

#### Specialize Pass
- **Computer Identity**:
  - Computer Name: `ATLANTIS-G2`
  - Organization: `NazariRigs`
  - Owner: `NazariGamer`
  - Product Key: `PNWKQ-PTH8R-8D6CH-TH42F-TVJXM`
- **Security**: Skip auto-activation enabled

#### OOBE System Pass
- **User Account Setup**:
  - Username: `NazariGamer`
  - Administrator privileges
  - Encrypted password configured
  - Auto-logon enabled (9999999 logons)

- **OOBE Customization**:
  - Hide EULA page
  - Hide local account screen
  - Hide online account screens  
  - Hide wireless setup
  - Network location: Home
  - Privacy settings: Level 3

- **Regional Settings**:
  - Time Zone: `Romance Standard Time`
  - Locale: `en-GB`
  - Input method: Spanish keyboard with English system

### Enhanced Image Tasks
- **Previous Tasks**: 
  - `imageSaveRebuild`
  - `imageFormatWim`
- **New Task**: 
  - `updates_Winre.wim_01__64` (Windows Recovery Environment updates)

### Changes from 0.0.2
- ✅ Added complete unattended installation setup
- ✅ Configured automated user account creation
- ✅ Set up regional and language preferences
- ✅ Enhanced OOBE bypass configuration
- ✅ Added Windows Recovery Environment processing
- ⚡ Full hands-free deployment capability

---

## Version 0.0.4 (2025-10-27 17:26:42)

### Major Update: Target Image & Hardware-Specific Drivers

### Critical Changes
- **Target Image Updated**: Changed from `10.0.26200.6584` to `10.0.26200.6901` (en-GB)
- **Image GUID Updated**: Changed from `{29CB82C7-689A-4C77-B569-15AA20C3D3B8}` to `{EC16321B-BA94-4DF4-9D23-E21BFFB118AE}`
- **Package Reduction**: Reduced from 11 packages to 3 core security updates
- **Driver Integration**: Added comprehensive MSI MPG Edge Ti x870e WiFi motherboard drivers

### Driver Package Details (17 drivers)
1. **AMD RAID Controllers**:
   - `rcbottom.inf` - AMD RAID Bottom Filter
   - `rccfg.inf` - AMD RAID Configuration
   - `rcraid.inf` - AMD RAID Driver

2. **Qualcomm Wireless & Bluetooth**:
   - `BtFilter.inf` - NCM865 Bluetooth Driver v3.1.0.1262
   - `qcwlan64.inf` - NCM865 WiFi Driver v3.1.0.1430

3. **Realtek Audio System** (8 components):
   - `ExtRtXUsb_Msi_AVO_RTK.inf` - MSI AVO Audio Extension
   - `ExtRtXUsb_Msi_AVO_V4_RTK.inf` - MSI AVO V4 Audio Extension
   - `ExtRtXUsb_Msi_RTK.inf` - MSI RTK Audio Extension
   - `RealtekASIO.inf` - ASIO Driver v13
   - `RealtekHSA.inf` - High-Definition Audio v374
   - `RealtekService.inf` - Audio Service v883.7
   - `RealtekUSBAPO.inf` - USB Audio Processing (v13 & v12)
   - `RtDUsbAD_msi.inf` - MSI USB Audio Device

4. **Network Controllers**:
   - `rt640x64.inf` - PCIe Ethernet v10.74.1128.2024
   - `ws640x64.inf` - WinPE Ethernet Support

### Removed Components
- **Modern Apps**: Removed WSL, Windows Terminal, App Installer, UI.Xaml, WindowsAppRuntime
- **Platform Updates**: Removed Update Platform and Antimalware components
- **Framework Updates**: Removed .NET Framework 4.8.1

### Retained Components
- **Core Security Updates**: 3 essential Windows 11 security patches
- **Unattended Configuration**: Complete automated installation setup (unchanged)
- **OOBE Bypass**: All user experience customizations (unchanged)
- **Image Tasks**: Same processing tasks including WinRE updates

### Changes from 0.0.3
- 🔄 **Target Image**: Updated to newer build 26200.6901
- 🔄 **Image GUID**: New unique identifier for updated image
- ✅ **Hardware Drivers**: Added 17 MSI x870e motherboard-specific drivers
- ❌ **Package Reduction**: Removed 8 modern apps and platform updates
- ⚡ **Hardware Optimization**: Focused on specific MSI MPG Edge Ti x870e WiFi platform

---

## Summary of Evolution

| Feature | v0.0.1 | v0.0.2 | v0.0.3 | v0.0.4 |
|---------|--------|--------|--------|--------|
| Basic Structure | ✅ | ✅ | ✅ | ✅ |
| Package Integration | ❌ | ✅ | ✅ | ⚠️ |
| Security Updates | ❌ | ✅ | ✅ | ✅ |
| Modern Apps | ❌ | ✅ | ✅ | ❌ |
| Unattended Install | ❌ | ❌ | ✅ | ✅ |
| User Configuration | ❌ | ❌ | ✅ | ✅ |
| WinRE Processing | ❌ | ❌ | ✅ | ✅ |
| OOBE Bypass | ❌ | ❌ | ✅ | ✅ |
| Hardware Drivers | ❌ | ❌ | ❌ | ✅ |
| Target Image Update | ❌ | ❌ | ❌ | ✅ |

## Usage Recommendations

- **v0.0.1**: Basic testing and minimal deployments
- **v0.0.2**: Updated systems with modern applications
- **v0.0.3**: Full production deployment with complete automation
- **v0.0.4**: Hardware-specific deployment for MSI MPG Edge Ti x870e WiFi systems with updated Windows build

---

*Generated on: 2025-10-27*  
*Preset Family: ATLANTIS-GEN2-W11H25-26200.6584*  
*NTLite Version: 2025.10.10649*