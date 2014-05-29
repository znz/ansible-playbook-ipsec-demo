# IPsec demo

```
% vagrant up
% vagrant ssh vm1
vagrant@vm1:~$ ping -I eth1 192.168.12.12
PING 192.168.12.12 (192.168.12.12) from 192.168.50.11 eth1: 56(84) bytes of data.
^C
--- 192.168.12.12 ping statistics ---
2 packets transmitted, 0 received, 100% packet loss, time 1008ms

vagrant@vm1:~$ sudo racoonctl -l show-sa isakmp
Destination            Cookies                           ST S  V E Created             Phase2
192.168.50.12.500      3b4f2ea82cd21d53:8cb804e1767c867b  9 I 10 M 2014-05-29 20:02:23      1
vagrant@vm1:~$
```
