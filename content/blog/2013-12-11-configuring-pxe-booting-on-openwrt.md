---
date: 2013-12-11 08:40:44 -0500
slug: configuring-pxe-booting-on-openwrt
tags:
- linux
title: Configuring PXE Booting on OpenWRT
---

I needed to support PXE booting on my home network. I use OpenWRT as my main
router and DHCP server and it took me a bit of searching how to configure the
BOOTP next server to redirect local clients to my Arch TFTP/NFS server for
booting, so I'm placing the configuration here to help others who might be
looking to do the same thing.

It's worth noting that this isn't a guide on setting up PXE booting completely
on an OpenWRT, you'll need another system that is running a configured TFTP
server. I'll write up how I setup my Arch box as a TFTP server at a later date.

The configuration itself was very simple; You just need to add a couple lines
to `/etc/config/dhcp`. You'll want to replace 10.0.0.45 with whatever your
local TFTP server is.

```
config boot linux
  option filename      'pxelinux.0'
  option serveraddress '10.0.0.45'
  option servername    'Arch-Pixie'
```

The filename `pxelinux.0` is from Syslinux, and the `servername` has no
technical meaning, but it provides nice information to the clients. In this
case I've used the name of my Arch linux server that I'll be booting off of.

Hope this helps someone out. Cheers!
