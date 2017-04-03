### Creating a bootable usb stick
lsblk # listing information about block devices.
sudo dd if=/path/to/linux/distro/iso/image/file.iso of=/dev/sdb # if: in-file, of: out-file (choose from lsblk command output)
