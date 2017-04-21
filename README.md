# Bash cheatsheet

> Bash commands that have proven to be very useful for me

## Working with the file system

`# find folders and files in the file system`

```bash
# finding all files (-type f) with name starting with 'sidekiq' (-name "sidekiq*")
find /path/to/folder -type f -name "sidekiq*"
```

## Uncategorized

`# making a bootable usb drive by simply mounting an image`

```bash
# listing block devices
lsblk

# if: file to load the image from
# of: partition to mount the image in
sudo dd if=/path/to/linux/distro/iso/image/file.iso of=/dev/sdb1 
```

