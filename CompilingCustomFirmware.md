## 1. Required software ##

  * Linux with the following packages installed
    * standard compilation software
    * libncurses-dev
    * gawk
    * g++
    * flex
    * bison
    * zlib development
    * git

## 2. Download the additional tools/sources ##
  * Toolchain [hndtools-mipsel-uclibc-4.6.4](http://code.google.com/p/wl500g/downloads/list?can=3&q=hndtools-mipsel-uclibc-4.6.4)
  * Linux kernel [linux-2.6.22.19.tar.bz2](http://wl500g.googlecode.com/files/linux-2.6.22.19.tar.bz2)

## 3. Unpack the archives and prepare the building tree ##

  1. Unpacking (replace the path _/whatever-you-want_ with the one, where your building tree will be located),
```
mkdir -p /opt/brcm
mkdir -p /whatever-you-want/broadcom/src/linux
tar -C /opt/brcm -jxvf hndtools-mipsel-uclibc-4.6.4-K26-r5128.tar.bz2
ln -sf /opt/brcm/hndtools-mipsel-uclibc-4.6.4-K26 /opt/brcm/hndtools-mipsel-uclibc
tar -C /whatever-you-want/broadcom/src/linux -jxvf linux-2.6.22.19.tar.bz2
ln -sf /whatever-you-want/broadcom/src/linux/linux-2.6.22.19 /whatever-you-want/broadcom/src/linux/linux-2.6
```
  1. Checking out firmware sources
```
git clone https://github.com/wl500g/wl500g.git /whatever-you-want/broadcom/src/1.9.2.7-rtn
```

## 4. Building ##

  1. Preparation of the sources
```
$ cd /whatever-you-want/broadcom/src/1.9.2.7-rtn
$ make kernel
$ make
```
  1. Model selection
```
$ cd /whatever-you-want/broadcom/src/gateway
$ make menuconfig
```
    * select one or more models from Router Models menu
    * exit & save new configuraton
  1. Compiling
```
$ cd /whatever-you-want/broadcom/src/gateway
$ make
$ make install
```
  1. Firmware image and extra kernel modules resides under /whatever-you-want/broadcom/src/gateway/mipsel-uclibc/

## 5. Sources update from GIT ##
  * In case of you want to refresh sources GIT, and don't want to rebuild an all tree, update algorithm will be complicated:
    * If kernel patches updated/added, you should
      * unarchive entire kernel sources (see. paragraph 3.1)
      * reapply patches & refresh kernel config
```
$ cd /whatever-you-want/broadcom/src/1.9.2.7-rtn
$ make kernel
$ cd /whatever-you-want/broadcom/src/gateway
$ make koldconf
```
    * If packages only updated, then following is enough
```
$ cd /whatever-you-want/broadcom/src/1.9.2.7-rtn
$ rm -rf /whatever-you-want/broadcom/src/gateway
$ make
```
  * Follow paragraph 4.2 of HowTo.
  * Mostly precision update also possible, but it requires knowledge of development tools such as patch, make etc., and they cannot be described in this HowTo.