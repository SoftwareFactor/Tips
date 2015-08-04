# View mounted disks
sudo lsblk

# View all disks and where they are mounted, format them, etc
sudo gparted

# Write ISO to drive
http://askubuntu.com/a/60430

# Write bootable Windows installation disk to USB drive  
1. Rewrite the partition table as msdos and format your USB drive as NTFS using GParted (also add the boot flag)
2. In GParted, right click the USB partition and select Information. Copy the UUID somewhere as you will need it.
3. Copy all files from Windows ISO to USB drive using your favorite file manager
