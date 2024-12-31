

# Linux File Commands

This guide covers essential Linux file commands for managing, viewing, and manipulating files and directories.

---

## Basic File Management

- **`ls`**  
List files and directories.  
  Examples:  
  ```bash
  ls                # List files in the current directory
  ls -l             # List with detailed information
  ls -a             # Include hidden files
- **`cd`**  
  Change the current directory.  
  Examples:
  ```bash
  cd /path/to/directory  # Navigate to a specific directory
  cd ..                  # Move up one level
  cd ~                   # Navigate to the home directory
  ```
- `pwd`  
Print the current working directory.  
Example:  
``` bash
pwd
```
- `mkdir`  
Create a new directory.
Examples:
``` bash
mkdir new_directory
mkdir -p parent/child   # Create parent and child directories
```
- `rmdir`  
Remove an empty directory.
Example:
``` bash
rmdir empty_directory
```
#### File Viewing
- `cat`
Concatenate and display file contents.
Examples:
``` bash
cat file.txt
cat file1.txt file2.txt > combined.txt
```
- `less`  
View file content one screen at a time.  
Example:
```bash
less largefile.txt
```
- `more`  
View file content, similar to less.  
Example:
```bash
more file.txt
```
- `head`  
Display the first lines of a file.  
Example:
``` bash
head -n 10 file.txt  # Show the first 10 lines
```
- `tail`  
Display the last lines of a file.  
Examples:

``` bash
tail -n 10 file.txt   # Show the last 10 lines
tail -f log.txt       # Continuously monitor the file
```
### File Manipulation
- `cp`  
Copy files and directories.  
Examples:
``` bash
Copy code
cp file1.txt file2.txt         # Copy file1.txt to file2.txt
cp -r dir1 dir2                # Copy directory and its contents
```
- `mv`  
Move or rename files and directories.  
Examples
``` bash
Copy code
mv old_name.txt new_name.txt   # Rename a file
mv file.txt /new/location/     # Move a file
```
- `rm`  
Remove files or directories.  
Examples:
``` bash
rm file.txt                  # Delete a file
rm -r directory              # Delete a directory and its contents
rm -i file.txt               # Prompt before deletion
``` 
- `touch`  
Create an empty file or update the timestamp of a file.  
Examples
``` bash
touch newfile.txt
touch -c existingfile.txt    # Update the timestamp
```
#### File Search and Metadata
- ```find```  
Search for files and directories.  
Examples:
``` bash
find /path -name "file.txt"       # Search by name
find /path -type d               # Search for directories
find /path -size +1M             # Search for files larger than 1MB
``` 
- `locate`  
Quickly find a file using a prebuilt index.  
Example:
``` bash
locate filename
```
- ```stat```  
Display detailed file information.  
Example:
``` bash
stat file.txt
```
- `file`
Determine the file type.  
Example:
``` bash
Copy code
file file.txt
```
### File Permissions and Ownership
- ```chmod```  
Change file permissions.  
Examples:

``` bash
chmod 644 file.txt        # Read/write for owner, read for others
chmod +x script.sh        # Add execute permission
```
- `chown`  
Change file ownership.  
Examples:
``` bash
chown user file.txt
chown user:group file.txt
```
- `umask`
Set default permissions for new files.
Example:
```bash
umask 022
```
#### File Compression and Archiving
- `tar`  
Archive files.  
Examples:
``` bash
tar -cvf archive.tar file1 file2  # Create an archive
tar -xvf archive.tar              # Extract an archive
tar -czvf archive.tar.gz dir      # Create a compressed archive
tar -xzvf archive.tar.gz          # Extract a compressed archive
```
- `gzip`  
Compress files.    
Examples:
``` bash
gzip file.txt
gunzip file.txt.gz
```
- `zip` and `unzip`  
Compress and extract files in ZIP format.  
Examples:
``` bash
zip archive.zip file1 file2
unzip archive.zip
```
### Advanced Commands
- `ln`  
Create links (symbolic or hard).  
Examples:
``` bash
ln file.txt hardlink.txt
ln -s /path/to/original symlink
```
- `du`
Estimate disk usage.
Examples:
``` bash
du -h file.txt             # Human-readable size
du -sh /path/to/directory  # Summary for a directory
```
- `df`  
Display available disk space.  
Example:
``` bash
df -h
``` 
- `mount` and `umount`  
Mount and unmount file systems.
Examples:
``` bash
mount /dev/sda1 /mnt
umount /mnt
```
#### File Backup and Recovery

- ```cpio```  
Backup files to or restore from an archive.  
Examples:

``` bash
find /path | cpio -o > backup.cpio
cpio -i < backup.cpio
```