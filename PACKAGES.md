# 5G Modem Support Packages

This repository contains OpenWrt packages for comprehensive 5G modem support, integrated from [Siriling/5G-Modem-Support](https://github.com/Siriling/5G-Modem-Support).

## Package Categories

### 5G Drivers (7 packages)
- **quectel_Gobinet** - Quectel GobiNet driver
- **quectel_MHI** - Quectel MHI driver
- **quectel_QMI_WWAN** - Quectel QMI WWAN driver
- **quectel_SRPD_PCIE** - Quectel SRPD PCIe driver
- **fibocom_MHI** - Fibocom MHI driver
- **fibocom_QMI_WWAN** - Fibocom QMI WWAN driver
- **meig_QMI_WWAN** - MEIG QMI WWAN driver

### Dial Utilities (3 packages)
- **quectel_cm_5G** - Quectel Connection Manager for 5G
- **fibocom-dial** - Fibocom dial utility
- **meig-cm** - MEIG Connection Manager

### LuCI Web Interfaces (8 packages)
- **luci-app-modem** - New unified modem management interface
- **luci-app-hypermodem** - Hypermodem management
- **luci-app-usbmodem** - USB modem management
- **luci-app-pcimodem** - PCI modem management
- **luci-app-gobinetmodem** - GobiNet modem management
- **luci-app-spdmodem** - SPD modem management
- **luci-app-cpe** - Simplified CPE information plugin
- **luci-app-sms-tool** - SMS management tool

### Utility Tools (3 packages)
- **sendat** - AT command tool
- **sms-tool** - SMS utility tool
- **ndisc** - IPv6 neighbor discovery tools

### Information Plugin (1 package)
- **rooter** - Comprehensive modem information plugin
  - Contains 41 sub-packages in subdirectories
  - Includes drivers, protocols, basic apps, optional apps, and support utilities

## Building

All packages are automatically detected and built by the GitHub Actions workflow defined in `.github/workflows/build-openwrt-ipk.yml`.

The workflow:
1. Downloads the OpenWrt SDK for the specified target
2. Copies packages with top-level Makefiles into the SDK
3. Builds all packages
4. Uploads the resulting IPK files as artifacts

**Note**: The `rooter` directory structure is different and contains packages in subdirectories. If you need to build specific rooter sub-packages, they should be copied individually to the top level or the build workflow should be modified.

## Usage

After building, install the IPK packages on your OpenWrt router using:
```bash
opkg install <package-name>.ipk
```

## Credits

All packages are sourced from the [Siriling/5G-Modem-Support](https://github.com/Siriling/5G-Modem-Support) repository.

Original sources:
- luci-app-hypermodem: https://github.com/momokind/luci-app-hypermodem
- sendat: https://github.com/ouyangzq/sendat
- luci-app-cpe: https://github.com/ouyangzq/luci-app-cpe
- sms-tool: https://github.com/obsy/sms_tool
