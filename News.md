### Detailed revision history ###
  * [Firmware 1.9.2.7-rtn source changes](https://github.com/wl500g/wl500g/commits/master)
  * [Firmware 1.9.2.7-d source changes](https://github.com/wl500g/wl500g/commits/d)

### RT-N-1.9.2.7-rtn-`r5066` (2013-04-27) ###
  * kernel
    * backports from upstream - MIPS, mm(Slab API change), irq(genirq, softirq), sched(workqueues), fs(epoll), net(ipv4, ipv6, udp, tcp), netfilter, usb(usbnet, cdc\_wdm, cdc\_ether, cdc\_ncm, qmi\_wwan, usbip, serial)
    * fastnat: fix throughput degradation when url filter enabled
    * option: Updates from 3.8 & blacklist fixes, thanks to Vampik
    * Driver core: convert "struct class\_device" to "struct device"

  * 3g/cdma
    * CDC NCM, QMI modems support (EXPERIMENTAL)
    * add ZTE MF190J

  * dnsmasq 2.66

  * dropbear 2013.58

  * misc
    * igmpproxy: eliminate use of second raw socket
    * netfilter/iptables: Add xt\_iface & xt\_condition matches from xtables-addons project
    * tcpdump 4.2.1

  * pppd
    * revert auth-down call to gentoo's auth-fail
    * request/suggest mschapv2 first, also fix unsynced bitmasks/defs

  * bugfixes
    * web-UI fixes, thanks to Vampik
    * busybox (vi)
    * iptables (ipset)
    * iproute2(ip)

### RT-N-1.9.2.7-rtn-`r4923` (2013-03-16) ###
  * kernel
    * backports from upstream - MIPS, core(idr, softirq, genirq, wait, lockdep), fs(writeback, splice, ext2, ext3, ext4, udf, isofs), tty, net(sock, tcp, arp, ipv6), netfilter(nf\_conntrack, xt\_TEE, xt\_CONNMARK), usb(EHCI, usb-storage, usbnet, usb-serial, usbip), scsi/sd
    * cdc\_ncm, cdc\_wdm, qmi\_wwan drivers backport (EXPERIMENTAL)

  * 3g/cdma
    * new ZTE, HUAWEI modems in modems.conf
    * uqmi - utility to manage QMI speaking modems from OpenWRT

  * ntfs-3g 2013.1.13AR.1

  * miniupnpd 1.8.20130207

  * udpxy 1.0.23-7

  * ipset 4.5

  * bugfixes
    * busybox (ntpd, mdev, libbb)

### RT-N-1.9.2.7-rtn-`r4772` (2012-12-23) ###
  * kernel
    * backports from upstream - MIPS, fs(ext4, udf), net(udp, raw), netfilter(rtcp, ACK), usb(usbip)
    * cdc-acm: fix info for /proc/bus/usb/devpath

  * dnsmasq 2.65
    * upstream patches

  * 3g/cdma
    * usb-modeswitch 1.2.5 + usb-modeswitch-data-20121109
    * modem status scripts update
    * new ZTE modems in modems.conf
    * dial scripts update (excluded options: nopcomp, noaccomp due to ZTE MF195 support)

  * busybox
    * bugfixes (ntpd)

  * misc
    * miniupnpd: fix memory & socket leaks
    * rp-pppoe: update to 3.11 & fixes
    * pppd: workaround for negotiated bad peer addresses
    * inadyn: fix HE ipv6

### RT-N-1.9.2.7-rtn-`r4667` (2012-10-08) ###
  * kernel
    * enable LBD (disks > 2Tb)
    * backports from upstream - MIPS, fs(ext3, ext4, udf), net(ipv4{6} raw), netfilter(xt\_limit)

  * pppd MSCHAPv2 fix ([issue 355](https://code.google.com/p/wl500g/issues/detail?id=355))

### RT-N-1.9.2.7-rtn-`r4645` (2012-09-30) ###
  * Broadcom SDK
    * Cleanup unused/dead code

  * kernel
    * backports from upstream - MIPS, softirq(add /proc/softirqs), rcu classic, fs(epoll, nls, fuse, ext2/3/4, udf), net(skb, ipv4, ipv6, connector, tcp), netfilter, usb(ehci), md/raid, uvcvideo
    * l2tp fixes; don't queue incoming packets, if not connected.

  * rc/www
    * httpd cleanup, fixes
    * rc fixes

  * 3g/cdma
    * new modems in modems.conf
    * usb-modeswitch-1.2.4 + usb-modeswitch-data-20120815
    * libusb 1.0 upstream fixes
    * fix usb\_devpath for cdc-acm
    * rc usbnet fixes, thanks to Vampik

  * busybox 1.20.2
    * bugfixes from upstream (sed, wget, mount, awk, lineedit, ash)

  * dnsmasq 2.63
    * upstream patches
    * DHCPv6 improvements
    * tftp enabled

  * udpxy 1.0.23

  * inadyn 1.99.2 from git://github.com/vampik/inadyn.git
    * add asuscomm.com support

  * miniupnpd 1.7.20120824

  * misc
    * radvd: fixes from upstream
    * igmpproxy: add igmpv3 clients support
    * pppd: upstream updates (VJ-comp, crypt, MSCHAP-v2)
    * infosrv: add simple implementation forasus device discovery (set "infosrv\_disable=1" nvram variable to turn it off)

### RT-N-1.9.2.7-rtn-`r4330` (2012-06-12) ###
  * uClibc 0.9.32: Implement tiny /etc/gai.conf - to change default names resolution order to IPv4 first, IPv6 second, create /etc/gai.conf containing single line "precedence ipv4"

  * Broadcom SDK
    * emf/igs backports from 5.110
    * fix igmpv3 snooping
    * minor cleanups

  * kernel
    * backports from upstream - MIPS, mm(slub), softirq, net(tcp, ipv4, ipv6, ppp, netlink), netfilter, fs(writeback, bdi, fuse, fat, ext4, sysfs), vfs, usb(ehci, usbnet, cdc\_ether), tty, debug(softlockup)
    * netfilter backports, fix for [issue 308](https://code.google.com/p/wl500g/issues/detail?id=308)
    * Decrease hardcoded limits - max swapfiles 2, max inet protos 64
    * Disable AIO support
    * usbip fixes
    * fastnat: fix openvpn and other headerless net devices

  * rc/www: bugfixes

  * 3g/cdma
    * usb-modeswitch-data 2012-05-31

  * dnsmasq 2.62
    * enable slaac & dhcpv6, not used yet

  * usbip userspace daemon 1.1.1 (usb.ids should be in /opt/share)

  * miniupnpd 1.7

  * pppd
    * preserve linkname pid file on lcp termination

  * misc
    * busybox: bugfixes from upstream (udhcp, hwclock, busybox, mdev)
    * libusb: bugfixes from upstream
    * rp-pppoe: upstream patches
    * rp-l2tp: fixes
    * pptp/l2tp: peer route improvements

### RT-N-1.9.2.7-rtn-`r4051` (2012-04-02) ###
  * ipkg: Switch to new OpenWRT-based repository http://wl500g-repo.googlecode.com , thanks to ryzhov\_al at wl500g.info

  * kernel
    * backports from upstream - MIPS, mm, sched, net(udp/raw, tcp, af\_unix, arp, ipv4/ipv6, neigh, pptp, tunnel), bridge, fs(ext3/ext4, cifs, ntfs, udf), usb(uvcvideo, gspca, usbnet, rndis\_host, cdc\_ether)
    * netfilter backports:
      * xt\_iprange v1
      * xt\_TOS/xt\_tos v1 merged into xt\_DSCP/xt\_dscp
      * u32 match
      * xt\_mark v1, xt\_MARK v2, merge xt\_MARK into xt\_mark
      * xt\_string v1
      * xt\_connmark v1, merge xt\_CONNMARK into xt\_connmark
      * xt\_owner v1
      * xt\_connlimit v1
      * xt\_addrtype v1 (EXPERIMENTAL)
      * xt\_hashlimit v1 (EXPERIMENTAL)
    * kmemleak: backport memory leak detector support (EXPERIMENTAL)
    * unionfs 2.5.11 - contributed by VA\_DOS at wl500g.info

  * rc
    * bugfixes
    * draft multiwan support(incomplete)
    * basic usbnet support

  * www
    * allow to disable ntfs support at all
    * split WAN and LAN pages

  * 3g/cdma
    * usb-modeswitch 1.2.3 + usb-modeswitch-data 2012-01-20

  * dropbear 2012.55

  * vsftpd 2.3.5

  * dnsmasq 2.60

  * ntfs-3g 2012.1.15AR.1

  * udpxy 1.0.21-2
    * patches by AlexeyS @ wl500g.info:
      * setup TCP\_NODELAY on accept socket
      * call get\_mstream\_type() for F\_CHECK\_FMT case only
      * optimize multicast address internal passing
      * compile out UDPXY\_FILEIO specific parts

  * miniupnpd 1.6.20120320

  * quagga 0.99.20.1

  * misc
    * busybox: bugfixes from upstream (mdev, read, httpd, test)
    * mjpg-streamer: output\_http - redirect to stream automagically if no www folder configured
    * pppd: pppoe - workaround for buggy nas; mppe fixes
    * igmpproxy: support multiple multicast sources
    * iptables: fixes from upstream
    * scsi-idle: switch scsi-start/stop to use SG\_IO

### RT-N-1.9.2.7-rtn-`r3702` (2011-12-25) ###
  * Broadcom SDK 5.60.127
    * RT-N10U, RT-N12B1 support
    * RT-N16 802.1x MD5 authentication support
    * et improvements

  * kernel
    * backports from upstream - mm, net(ip, route, inetpeer, tcp, ipv4/ipv6, vlan), netfilter, vfs, fs(fat, smbfs, isofs, ext2, ext3, ext4), timer/hrtimer, poll/select, splice, usb, hid, usbip
    * CIFS 1.54: backport from 2.6.27.59
    * ext3: backport from 2.6.32.48
    * gspca webcam drivers updates from 3.0.4, contributed by Evgeniy Chilikin aka Almair @ wl500g.info
    * turn off NF\_CONNTRACK\_PROC\_COMPAT (All controls in /proc/sys/net/netfilter/ now)
    * usb-serial: option: prevent adding a new record if device description exists
    * cdc-acm: Updates from 2.6.27.59

  * rc
    * bugfixes
    * use dhcp ip6rd option
    * upnp: send address change notify instead restart, listen loopback too
    * multiple gpio reservation, fixes N12 ses button
    * load pppoe/pptp/l2tp as a modules

  * busybox 1.19.3
    * dhcp6c: optimizations
    * fdisk: fix non-512 sector sizes disk(GPT). Patch from TomatoUSB
    * bugfixes from upstream (getty, modinfo, mount, hexdump, wget)

  * 3g/cdma
    * usb-modeswitch 1.2.0 + usb-modeswitch-data 2011-10-23
    * modems.conf update

  * dropbear 2011.54

  * radvd 1.8.3

  * udpxy 1.0-Chipmunk-21

  * misc
    * miniupnpd: no need to frighten human beings on every wan\_up
    * loader: minor speedup
    * libusb 1.0: fixes from upstream
    * iproute2: fixes from upstream

### RT-N-1.9.2.7-rtn-`r3497` (2011-10-22) ###
  * kernel
    * backports from upstream - arp, blkdev, vfs, net, netfilter, futex, fs/partitions
    * netfilter: h323: Increase max number of RTP ports from 4 to 8
    * ext4 backport from 2.6.30.9 (EXPERIMENTAL)
    * bcmnat: upload speedup

  * 3g/cdma
    * config for ZTE MF-192
    * usb\_modeswitch fixes
    * usb-modeswitch-data 2011-10-12
    * check\_modem only if proto is usbmodem
    * trying to wait ttyUSB if it still absent
    * add Qisda H21 3G modem support. Thanks to macauxdragon ([Issue 246](https://code.google.com/p/wl500g/issues/detail?id=246))

  * rc
    * zeroconfig implementation for no-dhcp networks
    * preliminary ISP Convex authentication support
    * tune max. sizes of /tmp, syslog.log for devices with RAM <= 16MB
    * syslog startup fix

  * dnsmasq 2.59

  * ntfs-3g 2011.4.12AR.7

  * quagga 0.99.20

  * radvd 1.8.2

  * busybox 1.19.2
    * bugfixes from upstream (tail, tftp)

  * bugfixes
    * web-UI
    * e2fsprogs fixes from upstream
    * udpxy Patch-1 build 20
    * miniupnpd: fix infinite loop in SendResp\_upnphttp()
    * bootup of few MIPS32r1 devices ([Issue 259](https://code.google.com/p/wl500g/issues/detail?id=259))
    * igmpproxy: fixes, igmpv3 stub

  * pwrled utility renamed to "gpio"

### RT-N-1.9.2.7-rtn-`r3300` (2011-09-16) ###
  * uClibc 0.9.32 with Native Posix Threads Layer (ATTENTION! possible old binaries incompatibility, especially using libpthreads)

  * kernel
    * backports from upstream - mm(buffered write iterator), raid/md, exportfs, IPv6, vlan, igmp, nfs, pppoe, ehci, usbip, oom
    * bcmnat update
    * usb-serial: use specified endpoint size for bulk\_out too
    * MIPS: Update linux-mips.org patches up to git 2011-08-20
    * UDF backport from 2.6.32.46
    * xfs, FUSE backport from 2.6.27.59
    * sys\_fallocate() implementation (xfs only, no uClibc support yet)
    * disable NFSv4 for now

  * rc
    * add ppp-auth handlers
    * preliminary 802.1x MD5 and KabiNET authentication support
    * ipv6: advertise RDNSS
    * fixed dhcp lease renew after (re)auth
    * TZ: excluding and transferring Russian DST into GMT offsets accordingly to Federal Law
    * wan port link status watchdog

  * rp-l2tp
    * set rws to 8 like in windows client
    * specify 100Mbps connection speed

  * 3g/cdma fixes & updates
    * usb-modeswitch 1.1.9
    * prevent multiple hotplug processing of endpoints from the same device
    * dialing on usb-serial event
    * option driver backports
    * using the driver 'option' only with explicit VID PID. Exclude usb-legacy mode.

  * dnsmasq 2.58

  * miniupnpd 1.6

  * ntfs-3g 2011.4.12AR.6

  * nfs-utils 1.1.6

  * busybox
    * bugfixes from upstream (sed, awk, ping6)
    * udhcpc: allow -O OPT take numeric params, add -N renew timeout option

  * bugfixes
    * accel-pptp fixes and updates
    * wpa\_supplicant fixes and updates
    * Make /linuxrc usable for root fs from external USB drive ([issue 133](https://code.google.com/p/wl500g/issues/detail?id=133))

### RT-N-1.9.2.7-rtn-`r3121` (2011-07-03) ###
  * kernel
    * backports from upstream (IPv6, net, netfilter, UVC, net schedulers, usb, mtd, writeback, bdi)
    * MIPS: Update linux-mips.org patches up to git 2011-06-16

  * busybox 1.18.5
    * dhcp6c compaction

  * e2fsprogs 1.41.14 - replacement for an old one from busybox (1.38)

  * radvd 1.8

  * miniupnpd 1.5.20110309 - replacement for obsolete upnpd

  * udpxy 1.0-Chipmunk-20

  * 3g/cdma fixes
    * usb-modeswitch 1.1.8

  * web-UI + rc
    * control jpeg compression level for webcam in YUV mode
    * improve webcam detection
    * set clamp TCP MSS to PMTU for IPv6 tunnels

  * wireless igmp snooping (WMF)

  * bugfixes
    * libnetconf: fixes caused by iptables upgrade 1.3 -> 1.4 in [r2716](https://code.google.com/p/wl500g/source/detail?r=2716)
    * LPRng: attempt to fix hardcoded by ASUS device paths (untested)

### RT-N-1.9.2.7-rtn-`r2972` (2011-05-15) ###
  * kernel
    * backports from upstream (IPv6, net, netfilter, netlink, usb, USB/IP)
    * netfilter: xt\_conntrack rev.2 , xt\_time from upstream
    * fast-nat module (originally from Broadcom, use 'nvram set misc\_fastnat\_x=0' to disable it)
    * l2tp - speedup

  * rp-l2tp - enhancement & fixes

  * 3g/cdma - enhancement & fixes

  * web-UI + rc
    * flush conntrack on wan address change

  * iptables
    * fixes from upstream
    * use "ctstate" instead of "state" in match rules

  * ntfs-3g 2011.4.12

  * dyndns
    * preliminary dns.he.net support

  * bugfixes
    * dropbear: fix remote connect to forwarded ports
    * libusb: fixes from upstream, enable timerfd.

### RT-N-1.9.2.7-rtn-`r2775` (2011-03-12) ###
  * All changes from trunk (1.9.2.7-d)

  * kernel
    * linux-mips.org updates 2.6.22.git-2010-11-10
    * backports from upstream (IPv6, bridge, mm, net, vfs, netfilter, scsi, netlink)
    * netfilter: xt\_IMQ, xt\_LOG, xt\_webstr, xt\_time
    * USB/IP driver
    * netconsole support(wired only)

  * iproute2 2.6.25
    * fixes from upstream

  * iptables 1.4.3.2
    * fixes from upstream

  * 6rd, DHCPv6 support

  * robocfg - improve BCM53115 support

  * dropbear 0.53.1

  * ntfs-3g 2011.1.15

  * usb\_modeswitch 1.1.7 & usb-modeswitch-data 2011-02-27

  * bugfixes
    * busybox (klogd, ls, mount, more)
    * 3g/cdma
    * lltd

### wl500g-1.9.2.7-d-`r2624` (2011-02-19) ###
  * kernel 2.4.37.11

  * busybox 1.18.3
    * prefer ipv4 addresses from DNS queries
    * dhcpc: fixed huge packets breakage (beeline ISP)
    * bugfixes (wget, modutils24)

  * dnsmasq 2.57

  * pppd
    * Debian patches (dont-exit-pado-timeout, adaptive\_echos, radius\_mtu)
    * pptp/l2tp: force nameserver refresh with pre-0.9.31 uClibc

  * vsftpd 2.3.4

  * udpxy 1.0-Chipmunk-19

  * ipv6: advertise tunnel MTU to avoid large packet issue

  * radvd 1.7

  * usb-modeswitch 1.1.6
    * usb-modeswitch-data 2010-12-22

  * p910nd 0.94

  * www
    * syntax and style enhancements contributed by Anatoly Sotskov

  * 3g/cdma: fix uni/dial script.

  * DynDNS: add easydns and no-ip support

  * iptables bugfixes from TomatoUSB project

### wl500g-1.9.2.7-d-`r2381` (2010-11-27) ###
  * kernel
    * pptp: updated kernel driver, fixed undersized packets without gre demux driver
    * pppoe: Ignore PADT packets whose destination address isn't ours
    * minor net, tcp backports from 2.6
    * ipv6: accept RA and send RS while configured as router

  * web-UI + rc
    * ipv6 support redesign
    * allow suffixes(day,hour,minute) for DHCP lease time field, closes [issue 169](https://code.google.com/p/wl500g/issues/detail?id=169)
    * support edit of ssh(dropbear) public keys from web-UI, contributed by Alexander Panfilov

  * busybox 1.17.4
    * udhcp workarounds for Beeline(Corbina) ISP
    * bugfixes (grep, wc, sendmail, awk, seq, sort, dmesg, klogd, telnet, ls )

  * pwrled utility included

  * bugfixes
    * dropbear fixes from upstream (fake-rfc2553, libtommath)
    * use pool.ntp.org as default clock sync source
    * inadyn: fix socket leak from new inadyn fork

### RT-N-1.9.2.7-rtn-`r2274` (2010-10-17) ###
  * kernel
    * linux-mips.org updates 2.6.22.git-2010-10-15
    * accel-pptp 0.8.5
    * backports from upstream (mm, vfs, tty, net, netlink, netfilter, conntrack, nfs, cifs, hfsplus, usb)
    * disable\_ipv6 sysctl
    * v4l: experimental support for UVC compatible webcams
    * pppoe: ignore PADT packets whose destination address isn't ours

  * efficient multicast forwarding & igmp snooping.

  * wlconf: updated to fix 802.11n issues

  * hub-ctrl utility

  * quagga 0.99.17

  * tcpdump 4.1.1

  * ntfs-3g 2010.10.2

  * mjpg-streamer `r103`

  * all utilities from trunk (1.9.2.7-d)

  * bugfixes

### wl500g-1.9.2.7-d-`r2174` (2010-09-30) ###
  * kernel 2.4.37.10
    * accel-pptp 0.8.5
    * mm/fs/nfs/net/bridge backports
    * nfs/usb fixes from [RedHat](http://rhkernel.org) RHEL3 63.EL
    * RFC 2385 (TCP MD5) patch by Hasso Teppe (EXPERIMENTAL)
    * usb-serial - SiLabs CP210x Driver from [etheus.net](http://www.etheus.net/CP210x_Linux_Driver) (EXPERIMENTAL)
    * CIFS: backports from Tomato project
    * enable appletalk & ipddp external modules
    * MTU change for TUN/TAP interfaces

  * pppd updates from upstream (up to 2010-08-24)

  * efficient multicast forwarding & igmp snooping.

  * 3g/cdma improvements & fixes

  * rc:
    * dhcp - add rfc3442 classless static routes support
    * fix vlans mapping in bridged mode ([issue 136](https://code.google.com/p/wl500g/issues/detail?id=136))

  * busybox 1.17.2
    * bugfixes (ash, sleep, wget)

  * usb\_modeswitch 1.1.4
    * usb-modeswitch-data 20100826

  * inadyn improvements

  * p910nd: IPv6 support

  * samba:
    * handle access flags
    * patch from OpenWRT (fixing enhanced attribute errors on WinXP SP2)

  * ucd-snmp: correct vlan/bridge/wimax/sip connections types

  * vsftpd 2.3.2

  * web-UI
    * added www.tunnelbroker.net service
    * fix symbols escaping ([Issue 51](https://code.google.com/p/wl500g/issues/detail?id=51))
    * added ipv6 tunnel utilization graph
    * allow choose of IPTV STB port
    * restore Operation mode switch for WL320

### alpha RT-N16-1.9.2.7-rtn-`r1943` (2010-08-15) ###
  * kernel
    * linux-mips.org updates 2.6.22.git-20100723
    * backports from upstream (mm, tty, vfs, fat, nfs, usb, usb-serial, scsi, net, bridge, route, netfilter, ppp)
    * ppp: add mppe56 and mppc support
    * usblp fixes
    * netfilter: xt\_recent

  * ntfs-3g 2010.8.8

  * quagga 0.99.16

  * rc
    * updates from RT-N16 1.0.1.2
    * fix RT-N10 support

  * robocfg: Partial support for BCM53115 (vlans mapping)

  * dnsmasq/busybox/radvd/libusb user-space tools updates same as in mainstream trunk

### wl500g-1.9.2.7-d-`r1825` (2010-07-23) ###
  * kernel
    * linux-mips.org fixes
    * minor nfs, hiddev fixes backport
    * bridge backport - allow setting hardware address of bridge pseudo-dev (sticky mac)
    * IPv4/IPv6 backports from 2.6 upstream

  * 3g/cdma modems support, contributed by rss & dlukanidin @ wl500g.info (EXPERIMENTAL)

  * updated toolchain (gcc 4.3.5, binutils 2.20.1)

  * dnsmasq 2.55

  * busybox 1.16.2
    * bugfixes from upstream (ash, udhcpc, sed, wget)
    * which, grep -E utilities added

  * radvd 1.6

  * usb\_modeswitch 1.1.3
    * usb-modeswitch-data 20100707

  * ez-ipupdate ddns updater replaced with inadyn daemon

  * bugfixes
    * web-UI fixes
    * libusb 1.0 fixes from upstream
    * iptables fixes from upstream, "-m time" - allow intervals with timestart > timestop
    * fix pppoe/pptp demand mode, was broken in [r1612](https://code.google.com/p/wl500g/source/detail?r=1612)

### wl500g-1.9.2.7-d-`r1612` (2010-05-27) ###
  * kernel
    * accel-pptp: updated to 2010.05.01-git
    * usb printer driver fixes & cleanup ([Issue 32](https://code.google.com/p/wl500g/issues/detail?id=32))
    * usbdevfs: fix submit\_urb control queries
    * ipset 4.2 modules (requires ipset 4.x userspace!)
    * backports from 2.6
      * more usb EHCI fixes
      * PPPoE/PPP fixes
      * NET/TCP fixes

  * rc
    * ipv6: allow any incoming icmp from 6in4 server

  * web-UI:
    * added bandwidth monitor (OpenWrt sources (originally part of m0n0wall) based, modified by Klim Tatarnikov.
    * ipv6: fixed 6to4 ipv6 address calculation

  * busybox 1.16.1
    * bugfixes from upstream (ash, telnet, swapon, grep, tar, sed, mount, vi, ifconfig)

  * libusb 1.0.8

  * usb-modeswitch 1.1.2

  * udpxy 1.0-Chipmunk-16

### alpha RT-N16-1.9.2.7-rtn-`r1478` (2010-04-27) ###
  * kernel 2.6.22.19
    * [linux-mips 2.6.22.git-20100420](http://www.linux-mips.org/) patches
    * many backports from upstream (mm, sched, vfs, ext3, fat, usb, scsi, net, netfilter, l2tp, pppoe, nfs, cifs)
    * squashfs 3.4

  * Broadcom SDK 5.10.56.46 from ASUS RT-N12 1.0.0.5/RT-N16 1.0.0.6 GPL sources

  * user-space tools mostly the same as in mainstream trunk, except 2.6 specific - udev fs

### wl500g-1.9.2.7-d-`r1445` (2010-04-24) ###
  * kernel
    * backport of ability to disable IPv6 at kernel level (/proc/sys/net/ipv6/conf/all/disable\_ipv6)
    * backport of nf\_conntrack: Don't track locally generated special ICMP error
    * Few patches from Willy Tarreau 2.4.37-wt3 collection (ppoll/epoll jiffies, ipt\_recent memleak)
    * Fix to avoid a flood of zombie cifsd processes, if there are problems connecting to a cifs. By Ray123 @ linksysinfo.org forum.
    * vfat: backport of fix buffer overflow in shortname creation procedure (from Tomato project).

  * rc
    * IPv6 fixes on startup code/rules
    * avoid garbage in vsftpd users' config files, fixes  [issue 94](https://code.google.com/p/wl500g/issues/detail?id=94)
    * fixed huge packets pass in clamp-mss-to-pmtu rule
    * pre-generate directories for built-in cron

  * WiMAX support (madwimax driver for Samsung SWC-U200, web-gui), contributed by artp & rss @ wl500g.info. Ready for Yota, also tested with mezon.lt

  * ez-ipupdate: added wildcard support for zoneedit

  * removed infosvr daemon from ASUS, it functionality of query printer interface moved to httpd.

  * httpd: System command - set 10 second time limit to exclude infinite loops in Web-UI.

  * pppd
    * allow ipv6cp in case of IPv6 enabled.
    * fixes from upstream (git 2010-03-07)

  * nfs-utils 1.0.9

  * usb-modeswitch 1.1.1

  * bugfixes
    * busybox (ash, awk, ping, syslogd, httpd, sed, insmod)
    * upnp: use real web interface port
    * Web-UI: fixed printer info status

### wl500g-1.9.2.7-d-`r1222` (2010-02-21) ###
  * kernel 2.4.37.9
    * update patches from linux-mips.org up to git linux-2.4 2009-12-05
    * netfilter
      * import backport of SIP ALG conntrack by [atens](http://atens.blogspot.com/2008/04/sip-alghelper-for-linux-kernel-24.html) (EXPERIMENTAL, not tested!)
      * backport of IPv6 conntrack (EXPERIMENTAL, not fully tested!)
      * PPTP/GRE helper fixes from 2.6 upstream

  * IPv6 - added IPv6-to-IPv4 tunnel support, redesigned IPv6 setup page

  * Support of obsolete ASUS WaveServer turned off.

  * mini\_sendmail replaced with busybox's sendmail.

  * rc
    * early logger start to avoid kernel messages lost in syslog
    * it was impossible to unset wan MAC-addr, closes [issue 88](https://code.google.com/p/wl500g/issues/detail?id=88)

  * bridge-utils 1.0.6

  * dnsmasq 2.52

  * usb-modeswitch 1.1.0

  * bugfixes
    * busybox (ash, wget, gunzip)
    * libshared - made `_`exec() POSIX.1-2001 compatible
    * madwimax - fix bug in signal handler

### wl500g-1.9.2.7-d-`r1087` (2010-01-24) ###
  * kernel
    * netfilter ipt\_time fix
    * CIFS 1.49 fix for CVE-2009-1439

  * pptp/accel-pptp
    * Add routes to VPN servers exactly as in 1.9.2.7-10.7

  * busybox
    * bugfixes for applets - ash, mkswap
    * blkid applet

  * ucd-snmp
    * Add ability to determine ethernet NIC speed (for bridges port 0 is hardcoded)

  * bugfixes
    * flashfs, dropbearstart, ipkg.sh - restrict PATH(/sbin:/bin:/usr/sbin:/usr/bin) to avoid possible impact with optware
    * rc - fixed ipv6-in-ipv4 tunnel packets drop with DoS protection enabled

### wl500g-1.9.2.7-d-`r1000` (2009-12-21) ###
  * kernel
    * backport of scsi settle by Ray123 from Tomato project
    * several usb storage bugfixes backport from 2.6
    * port trigger (autofw) fix

  * Broadcom SDK updates from GPL source 500gpV2 3.0.4.2

  * updated toolchain (gcc 4.2.4, binutils 2.19.1)

  * busybox 1.15.3
    * bugfixes for applets - wget, crond
    * mkswap volume label support

  * rc
    * dhcp - allow broadcast with wins usage
    * usb-hotplug - perform unmount of specified device only on remove, not all partitions on all discs, closes [issue 43](https://code.google.com/p/wl500g/issues/detail?id=43)

  * bugfixes
    * web-UI - fix validation of number fields & ports range, closes [issue 64](https://code.google.com/p/wl500g/issues/detail?id=64)

### wl500g-1.9.2.7-d-`r893` (2009-12-01) ###
  * kernel 2.4.37.7
    * IPv6: fix BUG of ndisc\_send\_redirect(), backport of ip6t\_TCPMSS netfilter module
    * ext2 module (separate archive)

  * IPv6 - initial support (EXPERIMENTAL! - not included in standard builds)

  * busybox
    * bugfixes for applets - ash, env, ping6, awk
    * traceroute6 applet
    * allow mount by uuid/label ext/swap partitions

  * accel-pptp: don't drop old echo request/reply packets (workaround for Corbina ISP)

  * ez-ipupdate: added support for service autodetected public ip address

  * rc
    * reworked httpd watchdog check, closes [issue 29](https://code.google.com/p/wl500g/issues/detail?id=29)
    * default policies for ip6tables
    * allow append samba config from /usr/local/etc/smb.conf

  * web-UI: minor style fixes

  * pppd 2.4.5

  * vsftpd 2.2.2

  * bugfixes
    * uClibc can't resolv 30 hostnames in DNS answer
    * madwimax driver - TX power must be signed

### wl500g-1.9.2.7-d-`r740` (2009-10-31) ###
  * kernel
    * squashfs 3.0
    * cifs 1.49 (external module)
    * optimize the upload speed for PPP connections

  * busybox 1.15.2

  * dnsmasq 2.51

  * vsftpd 2.2.1

  * igmproxy 1.0

  * rc (startup) procedures changes
    * dnsmasq default cache size increased to 512
    * return back usb\_vfat\_options nvram variable, especially for options NOT related to codepages

  * madwimax
    * statistics & pid files support

  * iputils
    * traceroute6 within IPv6 build

  * bugfixes
    * allow ntpclient to get time from non rfc-4330 servers (win XP)
    * busybox (udhcpc,swaponoff)
    * libshared - disable forwarding of port 0

### wl500g-1.9.2.7-d-`r655` (2009-10-04) ###
  * kernel
    * nfs client patches from http://client.linux-nfs.org
    * cifs module build (separate modules archive)

  * netfilter
    * ESFQ scheduler merged with SFQ, like in kernel 2.6 branch

  * web-interface improvements
    * URL-filter returned back, now it based on webstr iptables module

  * accel-pptp 0.8.4-git

  * bugfixes
    * igmpproxy log level
    * busybox (insmod, ash, find)
    * rc (fix restore of only first 15 upnp's port forwards)

### wl500g-1.9.2.7-d-`r617` (2009-09-23) ###
  * uClibc 0.9.30.1 (ATTENTION! possible old binaries incompatibility)

  * kernel 2.4.37.6
    * khubd daemon can't be killed from user space anymore

  * netfilter
    * added webstr match to help URL filtering

  * busybox 1.15.1
    * bugfixes of applets killall, ash, dd

  * igmpproxy 0.1\_beta5

  * bugfixes
    * ntpclient
    * l2tp

### wl500g-1.9.2.7-d-`r566` (2009-09-12) ###
  * kernel
    * IMQ driver with behavior
    * ESFQ scheduler updated to more recent version
    * pppol2tp backports from 2.6 kernels

  * accel-pptp (PPTP speedup up to 2.5x, used by default)
    * persist connection support
    * bugfixes

  * l2tpd
    * repair kernel mode
    * bugfixes from mainstream

  * pppd
    * minunit option added
    * bugfixes from Alt Linux distribution

  * netfilter/iptables/iproute2
    * "tc qdisc esfq" backport
    * ipset 3.2

  * rc (startup) procedures changes
    * Avoid ntp pseudo daemon, call ntpclient directly

  * dnsmasq 2.50test10 (speedup of DNS queries)

  * libusb 1.0.3 & usb\_modeswitch 1.0.5

  * bugfixes
    * busybox (ash, wget)
    * libusb UHCI transfers

### wl500g-1.9.2.7-d-`r473` (2009-08-22) ###
  * kernel 2.4.37.5
    * accel-pptp driver (EXPERIMENTAL!!!)
      * controlled by wan0\_pptp\_kernel nvram variable, for details see wl500g.info forum ([RUS thread](http://wl500g.info/showpost.php?p=156512&postcount=90) [ENG thread](http://wl500g.info/showpost.php?p=156860&postcount=239))
      * persist connections support
    * include IMQ driver
    * USB: fix infinite loop when unloading khubd
    * USB: fix interrupt transfers for usbdevfs

  * rc (startup) procedures changes
    * set hard limit of open files to 16384

  * busybox 1.14.3

  * vsftpd 2.2.0

  * udpxy 1.0-Chipmunk-14

  * usb\_modeswitch 1.0.2

  * madwimax driver 0.1.1

  * bugfixes
    * busybox (udhcpc, test, sed, tail, ash math operations)
    * iproute2 (tc qdisc statistics, pfifo\_fast)
    * libusb-compat 0.1.3

  * local ipkg repository created (ipkg, ipset, ntfs-3g)

### wl500g-1.9.2.7-d-`r396` (2009-07-17) ###
  * kernel
    * option driver updated

  * iproute2 2.4.7-now-ss020116-try

  * bugfixes
    * modprobe fix
    * ddns fixes

### wl500g-1.9.2.7-d-`r381` (2009-06-21) ###
  * kernel 2.4.37.2
    * FUSE driver included as ext. module
    * option driver updated
    * usbdevfs backports
    * netfilter: ipt\_MASQUERADE - remove redundant rwlock (backport from 2.6)
    * USB 2.0 fixes

  * added libusb 1.0.2, 0.1.2 & usb\_modeswitch tools

  * dnsmasq 2.49

  * vsftpd 2.1.2

  * bugfixes

### wl500g-1.9.2.7-d-`r308` (2009-05-29) ###
  * kernel
    * speedup NFS - increase max block size up to 32kB
    * Option driver updated

  * ppp
    * finally update rp-pppoe plugin from 3.08 to 3.10
    * incorporate external patches
      * Debian - "bogus DNS servers during PPP negotiation"
      * OpenWRT - "compensate time change"

  * netfilter/iptables
    * iplimit match replaced with connlimit (like in 2.6 kernels)
    * CLASSIFY, TOS targets included in firmware
    * layer7 filter enabled (external module)
    * ipset 3.0 modules added (external)
    * multiport match fixed

  * bugfixes
    * upnp daemon will write to nvram not more than 1 per minute

### wl500g-1.9.2.7-d-`r273` (2009-04-30) ###
  * kernel 2.4.37.1
    * fix usbaudio driver work via USB 2.0 hub
    * make pwc webcam driver EHCI compatible
    * USB 2.0 fixes

  * rc (startup) procedures changes
    * improve pre-shutdown before firmware upgrade

  * web-interface improvements
    * add udpxy wan access

  * busybox 1.13.4
    * fix "df -h" command

### wl500g-1.9.2.7-d-`r240` (2009-04-11) ###
  * kernel
    * EHCI driver backport from 2.6.29

  * rc (startup) procedures changes
    * perform pre-shutdown before firmware upgrade
    * timezones improved, ability to manual define TZ

  * pppd chat - support of HEX clause, patch from koppel.cz

  * udpxy 1.0 Chipmunk-11

  * radvd 0.7.3

  * bugfixes
    * busybox fixes (ash, hush, tail, tar, rmmod)
    * iptables "time" rule should work now

### wl500g-1.9.2.7-d-`r191` (2009-03-15) ###
  * kernel
    * EHCI backport - support of split ISO transfers

  * Use tmpfs filesystem for /tmp instead of ramfs

  * bugfixes
    * busybox 1.13.3
    * crash on some USB1.1 devices removal

### wl500g-1.9.2.7-d-`r160` (2009-03-05) ###
  * kernel
    * support spin-up usb hdd drives (scsi allow\_restart from 2.6)
    * backport of IPWireless (3G UMTS TDD) driver
    * backport of Option (GSM modem) driver
    * netfilter:
      * increase size of route & conntrack hash tables (originally Tomato SpeedMOD)

  * web-interface improvements
    * ssh (dropbear) server control
    * ability to disable USB 2.0 controller
    * brute force protection for ssh and ftp servers (ipt\_recent)
    * dnsomatic.com dynamic dns service support

  * rc (startup) procedures changes
    * disable upnp restart after ntp timesync
    * change Read/Write/Erase ftp rights to Write Only.

  * busybox 1.13.2

  * ppp 2.4.5-pre (snapshot 2008-11-26) including rp-pppoe 3.10

  * dnsmasq 2.47

  * udpxy 1.0\_Chipmunk-8

  * p910nd 0.93

  * vsftpd 2.1.0

  * bugfixes

### wl500g-1.9.2.7-d7 (2009-01-24) ###
  * Based on Oleg 1.9.2.7-10

  * kernel 2.4.37
    * [epoll](http://www.xmailserver.org/linux-patches/nio-improve.html) kernel interface
    * drivers/usb/acm.c, ppp\_filter, ip\_conntrack\_clear, /proc/bus/usb/devpath patches from Jiri Engelthaler http://koppel.cz/cdmawifi
    * Workaround for USB 1.1 devices via USB 2.0 hub
    * Backport support of TT transactions into EHCI driver
    * Backport [SigmaTel](http://www.sigmatel.com/) 4200 IRDA/USB driver
    * ftdi FT232R chip support
    * OpenWRT patches:
      * netfilter IMQ target
      * Sierra wireless driver

  * updated toolchain
    * gcc 4.1.2
    * uClibc 0.9.29 fixes

  * wl 4.150.10.29

  * pptp 1.7.1 (New option "--no-host-route")

  * dropbear 0.52

  * dnsmasq 2.46

  * vsftpd 2.0.7

  * udpxy 1.0\_Chipmunk-7

  * p910nd 0.92

  * ntpclient-2007\_365

  * ez-ipupdate fixes by _theMIROn_
    * zoneedit.com fix
    * /etc/ddns.conf support
    * Start ddns as daemon till the first successful update.

  * bugfixes

### wl500g-1.9.2.7-c (2008-06-28) ###
  * uClibc 0.9.29 (new toolchain: gcc-3.4.6, binutils 2.17, uClibc 0.9.29)

  * kernel 2.4.36.6
    * OpenWRT patches:
      * netfilter patches
      * USB serial 3g cards

  * dropbear 0.51

  * dnsmasq 2.42

  * mii-tool updated

  * bugfixes

### wl500g-1.9.2.7-b (2008-03-18) ###

  * Based on Oleg 1.9.2.7-9

  * kernel 2.4.36.2

  * dropbear 0.50


### wl500g-1.9.2.7-a (2008-01-08) ###

  * Based on [Oleg](http://oleg.wl500g.info/) 1.9.2.7-8

  * kernel 2.4.36 (baseline patches from [OpenWRT](http://openwrt.org/) kamikaze 7.09)
    * [Linux-mips](http://www.linux-mips.org/) patches
    * build fixes
    * netfilter patches
    * wl Broadcom operability
    * wireless extensions V18
    * ESFQ scheduler
    * HTB scheduler fixes
    * USB VIA6212 fixes

  * iptables 1.3.8

  * IPv6 turned off