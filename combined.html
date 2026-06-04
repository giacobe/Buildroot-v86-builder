# Merged Humphd + Trigerman Buildroot/v86 Build Procedure

This document describes how to create a merged Buildroot + v86 environment that combines:

* The Buildroot/v86 structure used in the `humphd/browser-vm` repository
* The browser VM workflow and configuration concepts from the Trigerman guide
* Additional v86-compatible kernel and userspace features

The result is a reusable Buildroot external tree suitable for producing:

* `bzImage`
* `rootfs.cpio`
* `rootfs.iso9660`

for use with the v86 browser-based virtual machine.

---

# 1. Download and Extract Buildroot

Download a clean Buildroot release:

```bash
wget https://buildroot.org/downloads/buildroot-2024.02.6.tar.gz
tar -xf buildroot-2024.02.6.tar.gz
cd buildroot-2024.02.6
```

---

# 2. Create an External Buildroot Tree

Create a new external tree outside the Buildroot directory:

```bash
mkdir -p merged-v86-buildroot/configs
mkdir -p merged-v86-buildroot/board/v86/rootfs_overlay
```

Create the following file:

```text
merged-v86-buildroot/external.desc
```

Contents:

```text
name: v86
desc: Merged v86 Buildroot configuration
```

Create empty support files:

```bash
touch merged-v86-buildroot/Config.in
touch merged-v86-buildroot/external.mk
```

---

# 3. Create the Buildroot Default Configuration

Create:

```text
merged-v86-buildroot/configs/v86_defconfig
```

Contents:

```text
BR2_x86_i686=y
BR2_CCACHE=y

BR2_TOOLCHAIN_BUILDROOT_WCHAR=y
BR2_PACKAGE_HOST_LINUX_HEADERS_CUSTOM_4_19=y

BR2_ROOTFS_OVERLAY="$(BR2_EXTERNAL_v86_PATH)/board/v86/rootfs_overlay/"
BR2_ROOTFS_POST_IMAGE_SCRIPT="$(BR2_EXTERNAL_v86_PATH)/board/v86/post-image.sh"

BR2_LINUX_KERNEL=y
BR2_LINUX_KERNEL_CUSTOM_VERSION=y
BR2_LINUX_KERNEL_CUSTOM_VERSION_VALUE="4.19.172"
BR2_LINUX_KERNEL_USE_CUSTOM_CONFIG=y
BR2_LINUX_KERNEL_CUSTOM_CONFIG_FILE="$(BR2_EXTERNAL_v86_PATH)/board/v86/linux.config"
BR2_LINUX_KERNEL_BZIMAGE=y

BR2_PACKAGE_BUSYBOX=y
BR2_PACKAGE_NANO=y
BR2_PACKAGE_ED=y
BR2_PACKAGE_LESS=y
BR2_PACKAGE_LUA=y

BR2_PACKAGE_DROPBEAR=y
BR2_PACKAGE_CURL=y
BR2_PACKAGE_IPERF3=y
BR2_PACKAGE_IPROUTE2=y
BR2_PACKAGE_IPUTILS=y
BR2_PACKAGE_TCPDUMP=y
BR2_PACKAGE_SOCAT=y
BR2_PACKAGE_DNSMASQ=y
BR2_PACKAGE_NTP=y
BR2_PACKAGE_LINKS=y

BR2_TARGET_ROOTFS_INITRAMFS=y
BR2_TARGET_ROOTFS_CPIO=y
BR2_TARGET_ROOTFS_CPIO_GZIP=y
BR2_TARGET_ROOTFS_ISO9660=y

BR2_TARGET_SYSLINUX=y
```

---

# 4. Create the Linux Kernel Configuration

Create:

```text
merged-v86-buildroot/board/v86/linux.config
```

Contents:

```text
CONFIG_X86_32=y
CONFIG_M686=y
CONFIG_EXPERT=y

CONFIG_BLK_DEV_INITRD=y
CONFIG_INITRAMFS_SOURCE="${BR_BINARIES_DIR}/rootfs.cpio"

CONFIG_TTY=y
CONFIG_VT=y
CONFIG_VT_CONSOLE=y
CONFIG_SERIAL_8250=y
CONFIG_SERIAL_8250_CONSOLE=y
CONFIG_VIRTIO_CONSOLE=y

CONFIG_NET=y
CONFIG_INET=y
CONFIG_IP_PNP=y
CONFIG_IP_PNP_DHCP=y
CONFIG_IP_PNP_BOOTP=y
CONFIG_IP_PNP_RARP=y

CONFIG_NETDEVICES=y
CONFIG_ETHERNET=y
CONFIG_NET_VENDOR_8390=y
CONFIG_NE2K_PCI=y
CONFIG_VIRTIO_NET=y

CONFIG_PCI=y
CONFIG_VIRTIO=y
CONFIG_VIRTIO_PCI=y
CONFIG_VIRTIO_BLK=y
CONFIG_VIRTIO_MMIO=y

CONFIG_9P_FS=y
CONFIG_NET_9P=y
CONFIG_NET_9P_VIRTIO=y

CONFIG_BLK_DEV=y
CONFIG_BLK_DEV_LOOP=y
CONFIG_BLK_DEV_SD=y
CONFIG_ATA=y
CONFIG_ATA_PIIX=y
CONFIG_BLK_DEV_SR=y

CONFIG_ISO9660_FS=y
CONFIG_EXT2_FS=y
CONFIG_EXT3_FS=y
CONFIG_EXT4_FS=y
CONFIG_FAT_FS=y
CONFIG_VFAT_FS=y
CONFIG_PROC_FS=y
CONFIG_SYSFS=y
CONFIG_TMPFS=y
CONFIG_DEVTMPFS=y
CONFIG_DEVTMPFS_MOUNT=y

CONFIG_INPUT=y
CONFIG_INPUT_KEYBOARD=y
CONFIG_KEYBOARD_ATKBD=y
CONFIG_INPUT_MOUSE=y
CONFIG_MOUSE_PS2=y

CONFIG_DRM=y
CONFIG_DRM_I915=y
CONFIG_FB=y
CONFIG_FRAMEBUFFER_CONSOLE=y

CONFIG_UNIX=y
CONFIG_PACKET=y

CONFIG_MODULES=y
```

---

# 5. Create the Post-Image Script

Create:

```text
merged-v86-buildroot/board/v86/post-image.sh
```

Contents:

```bash
#!/bin/sh
set -e

echo "Post-image step complete."
echo "Kernel and rootfs should be in: ${BINARIES_DIR}"
```

Make the script executable:

```bash
chmod +x merged-v86-buildroot/board/v86/post-image.sh
```

---

# 6. Load the Default Configuration

From inside the Buildroot directory:

```bash
make BR2_EXTERNAL=/path/to/merged-v86-buildroot v86_defconfig
```

This loads:

```text
merged-v86-buildroot/configs/v86_defconfig
```

as the default Buildroot configuration.

---

# 7. Review Buildroot Configuration

Run:

```bash
make menuconfig
```

Verify the following areas:

## Target Options

```text
Target Architecture = i386
Target Architecture Variant = i686
```

## Toolchain

```text
Enable WCHAR support
```

## Kernel

```text
Linux Kernel = enabled
Kernel version = 4.19.172
Kernel configuration = custom config file
Kernel binary format = bzImage
```

## System Configuration

```text
Root filesystem overlay =
$(BR2_EXTERNAL_v86_PATH)/board/v86/rootfs_overlay/
```

## Filesystem Images

Enable:

```text
cpio root filesystem
initial RAM filesystem linked into linux kernel
iso9660 image
```

## Bootloaders

Enable:

```text
Syslinux
```

Save and exit.

---

# 8. Review Linux Kernel Configuration

Run:

```bash
make linux-menuconfig
```

Verify the following:

## Processor Type

```text
32-bit kernel
M686-compatible processor
```

## General Setup

```text
Initial RAM filesystem and RAM disk support
```

## Serial Console

```text
8250/16550 serial support
Console on 8250/16550 serial port
Virtio console
```

## Networking

```text
TCP/IP networking
DHCP support
```

## Network Devices

```text
Virtio network driver
NE2000 PCI support
```

## Filesystems

```text
ISO9660
Ext2/3/4
FAT/VFAT
9P filesystem support
```

Save and exit.

---

# 9. Save the Buildroot Configuration

Save the Buildroot configuration back into the external tree:

```bash
make savedefconfig
cp defconfig /path/to/merged-v86-buildroot/configs/v86_defconfig
```

---

# 10. Save the Linux Kernel Configuration

Update the kernel defconfig:

```bash
make linux-update-defconfig
```

If necessary, manually copy the generated config:

```bash
cp output/build/linux-*/.config \
   /path/to/merged-v86-buildroot/board/v86/linux.config
```

---

# 11. Build the Environment

Run:

```bash
make
```

Outputs will appear in:

```text
output/images/
```

Expected files include:

```text
bzImage
rootfs.cpio
rootfs.cpio.gz
rootfs.iso9660
```

---

# 12. Use with v86

Typical v86 JavaScript configuration:

```javascript
bzimage: { url: "./images/bzImage" },
initrd: { url: "./images/rootfs.cpio" },
cmdline: "console=ttyS0"
```

The critical requirement is:

```text
console=ttyS0
```

because the browser VM normally communicates through the serial console.

---

# 13. Major Enabled Feature Set

The merged configuration enables:

* 32-bit x86 Linux
* Initramfs support
* Serial console support
* VirtIO console
* VirtIO networking
* NE2000 PCI networking
* DHCP autoconfiguration
* 9P filesystem support
* ISO9660 support
* Ext2/3/4 support
* FAT/VFAT support
* Syslinux boot support
* BusyBox userspace
* Networking tools
* SSH support
* Browser-compatible v86 kernel and storage drivers

---

# 14. Important Buildroot Concepts

There are two separate configuration systems:

| Command                 | Purpose                     |
| ----------------------- | --------------------------- |
| `make menuconfig`       | Configures Buildroot itself |
| `make linux-menuconfig` | Configures the Linux kernel |

The connection between them is:

```text
BR2_LINUX_KERNEL_CUSTOM_CONFIG_FILE=
$(BR2_EXTERNAL_v86_PATH)/board/v86/linux.config
```

which tells Buildroot which Linux kernel configuration file to use.
