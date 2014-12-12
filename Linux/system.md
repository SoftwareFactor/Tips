# System

#### Numeric permissions
http://www.cyberciti.biz/faq/unix-linux-bsd-chmod-numeric-permissions-notation-command/

#### Adding a new partition

1. List all drives:

		sudo fdisk -l

2. Then I see the new drive in a list

		Disk /dev/xvdb: 85.9 GB, 85899345920 bytes
		255 heads, 63 sectors/track, 10443 cylinders, total 167772160 sectors
		Units = sectors of 1 * 512 = 512 bytes
		Sector size (logical/physical): 512 bytes / 512 bytes
		I/O size (minimum/optimal): 512 bytes / 512 bytes
		Disk identifier: 0x00000000

		Disk /dev/xvdb doesn't contain a valid partition table

2. Create a new partition in /dev/xvdb1. Use "n" for new partition, "p" for primary, "w" to write the changes:

		sudo fdisk /dev/xvdb

3. Format the device:

		sudo mkfs /dev/xvdb1

4. Create a new directory:

		mkdir /new-disk

5. Mount the partition to this new directory:

		mount /dev/xvdb1 /new-disk