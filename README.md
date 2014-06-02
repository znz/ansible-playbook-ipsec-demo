# IPsec demo

```
% vagrant up
% vagrant halt
% vagrant up
% vagrant ssh vm1
vagrant@vm1:~$ ping -I eth2 192.168.12.12
PING 192.168.12.12 (192.168.12.12) from 192.168.11.11 eth2: 56(84) bytes of data.
ping: sendmsg: Invalid argument
ping: sendmsg: Invalid argument
64 bytes from 192.168.12.12: icmp_seq=3 ttl=64 time=0.401 ms
64 bytes from 192.168.12.12: icmp_seq=4 ttl=64 time=0.377 ms
64 bytes from 192.168.12.12: icmp_seq=5 ttl=64 time=0.402 ms
^C
--- 192.168.12.12 ping statistics ---
5 packets transmitted, 3 received, 40% packet loss, time 4009ms
rtt min/avg/max/mdev = 0.377/0.393/0.402/0.019 ms
vagrant@vm1:~$ sudo racoonctl -l show-sa isakmp
Destination            Cookies                           ST S  V E Created             Phase2
192.168.50.12.500      359f8de96b03a305:5a864a2a495c5835  9 I 10 M 2014-06-02 15:37:52      1
vagrant@vm1:~$
```
