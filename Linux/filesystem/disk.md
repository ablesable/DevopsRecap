`$ df -T` for seeing info about disk and its filesystems in the system. 

---------

`$ parted -l` for information about partitions.

------

`parted` command support MBR and GPT partitioning. 
In MBR extended partition are marked extended, and additional extensions are marked as logical. 

--------

`mkpart (startnumber) (endnumber)` this is parted command for making partition.

-------
For making filesystem the `$ mkfs` command is used. 

`$ mkfs -t ext4 /dev/sdb2` This will make filesystem ext4 on /dev/sdb2 device.

----

For checking of disk free space `$ df -h`, for disk usage `$ du -h`

----
Before mounting => checking:\
`$ fsck nameofdisk` (the name of disk we know from parted or df -t commands)