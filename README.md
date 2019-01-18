# configsys
A raspberry pi configuration system that is controlled from the /boot partition

## Installation

* Copy `configsys` to any location such as `/usr/local/bin` on your pi. Make sure that it is executable (`chmod a+x configsys`).
* Copy the `crontab` file to `/etc/cron.d/` and name it `configsys`. Edit the file and change the path to the location where you installed the executable.
* Reboot

## Usage

*configsys* uses 2 special files and one directory on the FAT32 *boot* partition of any raspbian SD card.
```
/boot/autoexec/always.sh
/boot/autoexec/once.sh
/boot/autoexec/bin/
```

The `bin/` directory is added to the path environment to be used by the autoexec scripts.  Place any helper scripts or other config stuff here.

After booting the system the `once.sh` is executed if present. This file gets deleted once it has been run.

Finally the `always.sh` is executed each time the system reboots.

All output is logged to `/tmp//configsys.log`.
 

