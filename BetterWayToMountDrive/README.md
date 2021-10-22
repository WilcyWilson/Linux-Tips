# Warning: Please use with caution since any changes in UUID value or the fstab configuration file can cause your system to not boot.
## What is blkid?
The blkid program is the command-line interface to working with libblkid(3) library. It can determine the type of content (e.g. filesystem, swap) a block device holds, and also attributes (tokens, NAME=value pairs) from the content metadata (e.g. LABEL or UUID fields).

## What is fstab?
The fstab file is a system configuration file commonly found at /etc/fstab on Unix and Unix-like computer systems. In Linux, it is part of the util-linux package.

## Information provided by the blkid
```bash
[wilcy@wilcy-pc ~]$ sudo blkid
[sudo] password for wilcy:
/dev/sdb1: UUID="f2409bf8-e166-4a79-9a40-682fcb674a87" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="da5b24aa-01"
/dev/sdc1: LABEL="Local Disk" BLOCK_SIZE="512" UUID="6812209C1220716C" TYPE="ntfs" PARTLABEL="Basic data partition" PARTUUID="71daa08a-0cc1-4d3a-ae94-53a1fd49d634"
/dev/sda2: LABEL="swap" UUID="f9ae5c46-0e7d-4215-9e23-065fe92f9a08" TYPE="swap" PARTUUID="2b2d842b-02"
/dev/sda1: UUID="c3830078-bb60-4fc3-bcae-a5b7931bb3d2" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="2b2d842b-01"
```

## Creating folders for each drive in /mnt and changing their read and write permission of the folder
```bash
[wilcy@wilcy-pc mnt]$ sudo mkdir D_Drive
[wilcy@wilcy-pc mnt]$ sudo chmod 777 -R D_Drive/
```
## Adding the drive and its UUID and type info in fstab using blkid info
```bash
[wilcy@wilcy-pc mnt]$ sudo nano /etc/fstab
# /etc/fstab: static file system information.
#
# Use 'blkid' to print the universally unique identifier for a device; this may
# be used with UUID= as a more robust way to name devices that works even if
# disks are added and removed. See fstab(5).
#
# <file system>             <mount point>  <type>  <options>  <dump>  <pass>
UUID=c3830078-bb60-4fc3-bcae-a5b7931bb3d2 /              ext4    defaults,noatime 0 1
UUID=f9ae5c46-0e7d-4215-9e23-065fe92f9a08 swap           swap    defaults,noatime 0 0
UUID=6812209C1220716C                     /mnt/D_Drive   ntfs    defaults 0 0
UUID=f2409bf8-e166-4a79-9a40-682fcb674a87 /mnt/E_Drive   ext4    defaults 0 0
```




