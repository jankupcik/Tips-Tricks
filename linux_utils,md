Disks
=====

lsblk -f
	-f : output info about filesystems

sudo e2fsck -fv /dev/sdb1
    -f : force checking even if the file system seems clean
    -v : verbose

sudo dd if=/dev/urandom of=/mnt/usb/shared/test1 bs=10M count=100 status=progress
sudo dd if=/mnt/usb/shared/test1 of=/dev/null bs=10M count=100 status=progress

sudo iotop -Po
