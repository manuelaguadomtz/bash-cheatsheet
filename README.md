# Bash cheatsheet

> Bash commands that have proven to be very useful for me

## Uncategorized

`# making a bootable usb drive by simply mounting an image`

```bash
# listing block devices
lsblk

# **if:** in-file
# **of:** out-file
sudo dd if=/path/to/linux/distro/iso/image/file.iso of=/dev/sdb 
```

