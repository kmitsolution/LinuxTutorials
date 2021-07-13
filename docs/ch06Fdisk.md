# fdisk
It is menu driven program for creation and manipulation of partition table
### Partitions
 Hard  disks can be divided into one or more logical disks called partitions.  This division is recorded in the partition table, found in sector 0 of the disk.Linux needs at least one partition, namely for its root file system.  It can use swap files and/or swap partitions,  but the  latter  are  more  efficient. So, usually one will want a second Linux partition dedicated as swap partition.
#### DEVICES
 The device is usually /dev/sda, /dev/sdb or so.  A device name refers to the entire disk. The partition is a device name followed by a partition number.  For example, /dev/sda1 is the  first  partition  on  the first hard disk in the system. 
#### To display the list of partition
```
   $ sudo fdisk -l

# Output will be something like below. In this example there is only one partition /dev/sda1

Disk /dev/sda: 42.9 GB, 42949672960 bytes, 83886080 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0x0009ef1a

   Device Boot      Start         End      Blocks   Id  System
/dev/sda1   *        2048    83886079    41942016   83  Linux

```
#### To display current partition information
```
   $ sudo df -h

#Output will be like below 
Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        489M     0  489M   0% /dev
tmpfs           496M     0  496M   0% /dev/shm
tmpfs           496M  6.8M  489M   2% /run
tmpfs           496M     0  496M   0% /sys/fs/cgroup
/dev/sda1        40G  3.7G   37G  10% /
tmpfs           100M     0  100M   0% /run/user/1000
   
```


       
