# Linux File System Overview

The **Linux file system** (FS) organizes files and directories in a hierarchical structure. It follows the **Filesystem Hierarchy Standard (FHS)** and supports multiple file system types.

---

## 1. Key Linux File System Concepts
### 1.1 Files and Directories
- **Everything in Linux is a file**, including directories, devices, and processes.
- Files are stored in a hierarchical structure starting from the root directory `/`.

### 1.2 File System Types
- **ext4** (Fourth Extended File System) – Default in most Linux distros.
- **xfs** – High-performance journaling FS.
- **btrfs** – Advanced FS with snapshots and RAID support.
- **zfs** – Scalable FS with built-in compression and snapshots.
- **NFS** (Network File System) – Allows remote access to files.
- **FAT32, NTFS, exFAT** – Used for Windows compatibility.

---

## 2. Linux File System Structure

Linux follows a hierarchical directory structure:

| Directory | Purpose |
|-----------|---------|
| `/` | Root directory (starting point of FS). |
| `/bin` | Essential binaries (commands like `ls`, `cp`, `mv`). |
| `/boot` | Boot-related files (kernel, GRUB). |
| `/dev` | Device files (e.g., `/dev/sda` for disks). |
| `/etc` | System configuration files. |
| `/home` | User home directories (`/home/user`). |
| `/lib` | Essential shared libraries. |
| `/media` | Auto-mounted removable media (USB, CD-ROM). |
| `/mnt` | Temporary mount points. |
| `/opt` | Optional software packages. |
| `/proc` | Virtual filesystem for system and process info. |
| `/root` | Root user’s home directory. |
| `/sbin` | System binaries (for system administration). |
| `/srv` | Data for services (e.g., web servers). |
| `/sys` | Virtual FS with system-related info. |
| `/tmp` | Temporary files (cleared on reboot). |
| `/usr` | User applications, libraries, documentation. |
| `/var` | Variable files (logs, cache, databases). |

---

## 3. File System Operations
### 3.1 Viewing File System Information
- Check mounted file systems:
  ```bash
  df -h
  ```
- View file system type:
  ```bash
  lsblk -f
  ```
- Check disk usage:
  ```bash
  du -sh /directory
  ```

### 3.2 Mounting and Unmounting
- Mount a partition:
  ```bash
  mount /dev/sdb1 /mnt
  ```
- Unmount:
  ```bash
  umount /mnt
  ```

### 3.3 Creating and Formatting File Systems
- Format a partition as `ext4`:
  ```bash
  mkfs.ext4 /dev/sdb1
  ```
- Check file system for errors:
  ```bash
  fsck /dev/sdb1
  ```

---

## 4. Advanced File System Features
### 4.1 Journaling
- Ensures file system integrity in case of crashes (ext3, ext4, xfs).

### 4.2 LVM (Logical Volume Manager)
- Allows flexible disk management:
  ```bash
  lvcreate -L 20G -n myvolume myvg
  ```

### 4.3 RAID (Redundant Array of Independent Disks)
- Used for redundancy and performance.

### 4.4 File System Permissions
- View permissions:
  ```bash
  ls -l
  ```
- Change permissions:
  ```bash
  chmod 755 file
  ```
- Change ownership:
  ```bash
  chown user:group file
  ```

---

## 5. Common File Systems in Linux

| File System | Features |
|------------|---------|
| `ext4` | Journaling, large file support, default in Linux. |
| `xfs` | High-performance, used in RHEL/CentOS. |
| `btrfs` | Snapshots, checksums, RAID support. |
| `zfs` | Advanced FS with self-healing and deduplication. |
| `vfat/exFAT` | Used for USB drives (Windows-compatible). |
| `NFS` | Remote file sharing. |

---

## 6. Automounting File Systems
To automatically mount a disk at boot, add an entry in `/etc/fstab`:
```bash
/dev/sdb1  /mnt/data  ext4  defaults  0  2
```
Apply changes:
```bash
mount -a
```

---

## Conclusion
The Linux file system is powerful and flexible, supporting various file systems, permission management, logical volume management, and advanced features like RAID and snapshots.

Let me know if you need more details on a specific aspect! 🚀

