---
title: iSCSId
---

This is the server configuration for iSCSI, please refer to [[Linux/iSCSI]] for
the client portion.

## Configuration

Install the package scsi-target-utils.

Example config:

```
default-driver iscsi
initiator-address 10.0.0.100
#ignore-errors yes

<target iqm.2011-09.net.bedroomprogrammers.lab:example-srv.storage>
        backing-store /dev/vdb

        incominguser client1 XXXXXXXXXXXX
        incominguser client2 XXXXXXXXXXXX

        write-cache off
        vendor_id Bedroom Programmers
</target>
```

```
[root@localhost ~]# chkconfig tgtd on
[root@localhost ~]# service tgtd start
```

## References

* http://fedoraproject.org/wiki/Scsi-target-utils_Quickstart_Guide - High Quality
* http://www.ryanuber.com/a-quick-introduction-to-gfs2-over-iscsi.html - Transition from iSCSI to GFS2
* http://www.rainingpackets.com/wiki/doku.php?id=iscsi_cheat_sheet - iSCSI cheat sheet (includes client config)
