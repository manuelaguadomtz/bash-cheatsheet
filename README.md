# Bash cheatsheet

Bash commands that have proven to be very useful for me

## Working with the file system

#### Find folders and files in the file system

```bash
# finding all files (-type f) with name starting with 'sidekiq' (-name "sidekiq*")
find /path/to/folder -type f -name "sidekiq*"
```

#### Taking each files in a directory and doing something with them

```bash
# Printing all files in a directory
ls . | while read i; do echo $i; done
```

#### Remove files with specific extension in all subdirectories

```bash
# To list all *.pyc files
find . -name "*.pyc" -type f

# To delete all *.pyc files
find . -name "*.pyc" -type f -delete
```

## Installing packages (Ubuntu)

#### Installing subversion

```bash
# Install Apache subversion client and server
sudo apt-get install subversion

# Install RabbitVCS
sudo apt-get install rabbitvcs-cli rabbitvcs-core rabbitvcs-gedit rabbitvcs-nautilus
```

#### Installing temperature monitors

```bash
# Installing sensors
sudo apt install lm-sensors hddtemp
sudo sensors-detect
sensors
sudo apt install psensor
```

## Uncategorized

#### making a bootable usb drive by simply mounting an image

```bash
# listing block devices
lsblk

# if: file to load the image from
# of: partition to mount the image in
sudo dd if=/path/to/linux/distro/iso/image/file.iso of=/dev/sdb1 
```

#### Convert a classic image to an eps image

```bash
convert mainview.png eps2:mainview.eps
```
