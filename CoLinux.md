## Introduction ##

If you want to compile packages under windows without rebooting you need instal CoLinux.
CoLinux is a port of the Linux kernel that allows it to run cooperatively alongside another operating system on a single machine, and work as service on Microsoft Windows.
For instance, it allows one to freely run Linux on Windows 2000/XP, without using a commercial PC virtualization software such as VMware, in a way which is much more optimal than using any general purpose PC virtualization software.

## Installing Cooperative Linux ##

First step - get colinux installation.
Download colinux-x.y.z.exe from sourceforge onto the Windows machine.
http://sourceforge.net/projects/colinux/files
or develop snapshot
http://colinux.org/snapshots/
Next step run colinux-x.y.z.exe on the Windows machine
Switch off flag **Root Filesystem image (Download)**, leter you neen download image manual.
colinux prefer it to be installed in c:\coLinux.
Next download image of Linux Slackware 12.2 from (http://slackware.com/getslack/), it's dvd image, after download move this into c:\colinux\linux\ as **slack12.iso**

## Prepare local files ##

```
c:\>fsutil.exe file createnew c:\colinux\linux\root_fs.img 3000000000
c:\>fsutil.exe file createnew c:\colinux\linux\hdb.img 3000000000
c:\>fsutil.exe file createnew c:\colinux\linux\hdc.img 2000000000
c:\>fsutil.exe file createnew c:\colinux\linux\swap.img 300000000
```

configure colinux installation
**install.conf**
```
kernel=vmlinux
hda=c:\coLinux\linux\root_fs.img
hdd=c:\coLinux\linux\slack12.iso
hdе=c:\coLinux\linux\swap.img
root=/dev/ram load_ramdisk=1 prompt_ramdisk=0 ramdisk_size=10000
initrd=initrd.img
mem=256
cocon=120x40
```

For Slackware installation, for colinux first run you need initrd.img file, it resides on distribution disk. For it extraction from dvd image you should use appropriate program, alcohol or ISObuster for example, I used Total Commander plugin.

Installing linux
```
c:\> cd c:\colinux
c:\> colinux-daemon.exe -t nt @install.conf
```

появится предложение выбрать раскладку клавиатуры и ввести имя пользователя, можно нажать 2 раза enter.
mount linux boot dist image as /cdrom
```
mount /dev/hdd /cdrom
```
formating hda
```
mkfs.ext2 -j /dev/hda
```
on qustion **Proceed anyway? (y,n)** say **y**

mount main
```
mount /dev/hda /mnt
```

creating swap
```
mkswap /dev/hde
swapon /dev/hde
```

installing packages
```
cd /cdrom/slackware/a
installpkg -root /mnt *.tgz
cd /cdrom/slackware/ap
installpkg -root /mnt *.tgz
cd /cdrom/slackware/d
installpkg -root /mnt *.tgz
cd /cdrom/slackware/f
installpkg -root /mnt *.tgz
cd /cdrom/slackware/l
installpkg -root /mnt *.tgz
cd /cdrom/slackware/n
installpkg -root /mnt *.tgz
```

After packets install, you have to edit /mnt/etc/fstab to achieve successful next reboot.
You can edit file like:

nano /mnt/etc/fstab

```
/dev/hda        /               ext2      noatime         2     2
/dev/hdb        /home           ext3      noatime         2     2
/dev/hdc        /wl500g         ext3      noatime         2     2
/dev/hdd        /dvd            iso9660   defaults        0     0
/dev/hde        swap            swap      defaults        0     0
proc            /proc           proc      defaults        0     0
devpts          /dev/pts        devpts    gid=5,mode=620  0     0
```

rebooting after installation.
```
poweroff
```

configure colinux service

**slack.conf**
```
kernel=vmlinux
hda=c:\coLinux\linux\root_fs.img
hdb=c:\coLinux\linux\hdb.img
hdc=c:\coLinux\linux\hdc.img
hdd=c:\coLinux\linux\slack12.iso
hde=c:\coLinux\linux\swap.img
root=/dev/hda ro
initrd=initrd.gz
mem=128
cocon=120x40
eth0=tuntap
```

run Slackware

```
c:\> cd c:\colinux
c:\> colinux-daemon.exe --install-service colinux @slack.conf
```

## Configure linux for compilling firmware ##

configure enviroment

After that it is necessary to add environment variables set into profile
add following lines into **/etc/profile**
```
export OPTWARE_TARGET="oleg"
export LANG="ru_RU.UTF-8" (or your locale)
```

swich off daemons
```
cd /etc/rc.d
chmod -x rc.bluetooth.conf rc.httpd rc.local rc.nfsd rc.sendmail rc.udev rc.acpid 
chmod -x rc.cups rc.messagebus rc.ntpd rc.serial rc.wireless rc.alsa rc.dnsmasq rc.pcmcia
chmod -x rc.snmpd rc.wireless.conf rc.atalk rc.modules-2.6.27.7 rc.rpc rc.sshd rc.yp 
chmod -x rc.bind rc.fuse rc.inetd rc.modules-2.6.27.7-smp rc.samba rc.syslog rc.bluetooth 
chmod -x rc.hald rc.ip_forward rc.mysqld rc.saslauthd rc.sysvinit
```

в файле **/etc/rc.d/rc.inet1.conf** необходимо настроить IP адрес, маску и шлюз по умолчанию.
```
IPADDR[0]="192.168.0.2"
NETMASK[0]="255.255.255.0"
GATEWAY="192.168.0.1"
```

Reboot and check.

```
reboot
```

If all work correct add colinux as service
```
c:\> colinux-daemon.exe --install-service "colinux" @slack.conf
```

after you can start/stop colinux in commant line.
```
net start colinux
net stop colinux
```

## Compilling firmware ##

See [CompilingCustomFirmware](CompilingCustomFirmware.md) for details

Sample install.sh

**install.sh**
```
#!/bin/sh
inst=`pwd -P`
mkdir $inst/broadcom/src/linux -p
mkdir /opt/brcm -p
git clone https://github.com/wl500g/wl500g.git $inst/broadcom/src/1.9.2.7-rtn
tar -C /opt/brcm -jxvf hndtools-mipsel-uclibc-4.6.3-K26-r4755.tar.bz2
ln -sf /opt/brcm/hndtools-mipsel-uclibc-4.6.3-K26 /opt/brcm/hndtools-mipsel-uclibc
rm -rf $inst/broadcom/src/linux/linux-2.6
tar -C $inst/broadcom/src/linux -jxvf linux-2.6.22.19.tar.bz2
ln -sf linux-2.6.22.19 $inst/broadcom/src/linux/linux-2.6
```