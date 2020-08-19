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

#### Find and replace text within a file

```bash
# To update the input file
sed -i 's/text_to_find/replace_text/g' input_file.txt

# To create a new file  with the changes
sed 's/text_to_find/replace_text/g' input_file.txt > output_file.txt

# case-insensitive
sed -i 's/text_to_find/replace_text/gI' input_file.txt

# Replacing commas by dots in floats
sed -i -r 's/([0-9]),([0-9])/\1.\2/g' input_file.txt
```

#### Find text in files

```bash
# Find files containing specific text
grep -iRl 'text_to_find' directory

# -i - ignore text case
# -R - recursively search files in subdirectories.
# -l - show file names instead of file contents portions.
# -n - prints the line numbers

# Find sepcific text within a file
grep -i 'text_to_find' input_file.txt
grep 'text_to_find' input_file.txt  # Case sensitive
```

#### Print n lines of a file

```bash
# Print the first 20 line of a file
sed -n 1,10p input_file.txt
```

#### Displaying path of the current directory

```bash
pwd
```

#### Transfer files (scp)

```bash
# Copy single file from local to remote
scp myfile.txt remoteuser@remoteserver:/remote/directory/

# Copy single file from remote to local
scp remoteuser@remoteserver:/remote/directory/myfile.txt  myfile.txt
```

#### Downloading files

## Download a file

```bash
wget http://example.com/file
```

## Knowing the file lenght before download it

```bash
wget http://example.com/file --spider --server-response -O - 2>&1 | sed -ne '/Content-Length/{s/.*: //;p}'
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

#### Convert EPUB to PDF

```bash
# Installing calibre
sudo apt-get -y install calibre

# Converting
ebook-convert <file>.epub <file>.pdf
```
