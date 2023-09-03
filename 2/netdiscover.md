Should be `10.128.0.0/20`, but netdiscover apparently only supports a subset of CIDR notation. See man page for further detail.

```sh
$ sudo netdiscover -r 10.128.0.0/24
Currently scanning: Finished!   |   Screen View: Unique Hosts                                                                                                   
                                                                                                                                                                 
 1 Captured ARP Req/Rep packets, from 1 hosts.   Total size: 42                                                                                                  
 _____________________________________________________________________________
   IP            At MAC Address     Count     Len  MAC Vendor / Hostname      
 -----------------------------------------------------------------------------
 10.128.0.1      42:01:0a:80:00:01      1      42  Unknown vendor                                                                                                

```
