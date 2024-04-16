Disks
=====

- Attached devices
```
    lsblk -f

        -f : output info about filesystems
```

- Check filesystem
```
    sudo e2fsck -fv /dev/sdb1

        -f : force checking even if the file system seems clean
        -v : verbose
```

- Speed test
```
    sudo dd if=/dev/urandom of=/mnt/usb/shared/test1 bs=10M count=100 status=progress
    sudo dd if=/mnt/usb/shared/test1 of=/dev/null bs=10M count=100 status=progress
```

Monitoring
==========

- Nigel's performance Monitor
```
    sudo nmon
```

- I/O monitor
```  
    sudo iotop
```
