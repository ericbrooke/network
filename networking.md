Discover IP
```
ifconfig

lo0: flags=8049<UP,LOOPBACK,RUNNING,MULTICAST> mtu 16384
	options=3<RXCSUM,TXCSUM>
	inet6 ::1 prefixlen 128
	inet 127.0.0.1 netmask 0xff000000
	inet6 fe80::1%lo0 prefixlen 64 scopeid 0x1
	nd6 options=1<PERFORMNUD>
gif0: flags=8010<POINTOPOINT,MULTICAST> mtu 1280
stf0: flags=0<> mtu 1280
en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	ether b8:e8:56:49:02:92
	inet6 fe80::bae8:56ff:fe49:292%en0 prefixlen 64 scopeid 0x4
	inet 192.168.1.182 netmask 0xffffff00 broadcast 192.168.1.255
	nd6 options=1<PERFORMNUD>
	media: autoselect
	status: active
en1: flags=8963<UP,BROADCAST,SMART,RUNNING,PROMISC,SIMPLEX,MULTICAST> mtu 1500
	options=60<TSO4,TSO6>
	ether 72:00:01:2d:ec:c0
	media: autoselect <full-duplex>
	status: inactive
en2: flags=8963<UP,BROADCAST,SMART,RUNNING,PROMISC,SIMPLEX,MULTICAST> mtu 1500
	options=60<TSO4,TSO6>
	ether 72:00:01:2d:ec:c1
	media: autoselect <full-duplex>
	status: inactive
p2p0: flags=8843<UP,BROADCAST,RUNNING,SIMPLEX,MULTICAST> mtu 2304
	ether 0a:e8:56:49:02:92
	media: autoselect
	status: inactive
awdl0: flags=8843<UP,BROADCAST,RUNNING,SIMPLEX,MULTICAST> mtu 1452
	ether 16:50:8e:a7:43:ae
	inet6 fe80::1450:8eff:fea7:43ae%awdl0 prefixlen 64 scopeid 0x8
	nd6 options=1<PERFORMNUD>
	media: autoselect
	status: active
bridge0: flags=8822<BROADCAST,SMART,SIMPLEX,MULTICAST> mtu 1500
	options=63<RXCSUM,TXCSUM,TSO4,TSO6>
	ether ba:e8:56:94:b2:00
	Configuration:
		id 0:0:0:0:0:0 priority 0 hellotime 0 fwddelay 0
		maxage 0 holdcnt 0 proto stp maxaddr 100 timeout 1200
		root id 0:0:0:0:0:0 priority 0 ifcost 0 port 0
		ipfilter disabled flags 0x2
	member: en1 flags=3<LEARNING,DISCOVER>
	        ifmaxaddr 0 port 5 priority 0 path cost 0
	member: en2 flags=3<LEARNING,DISCOVER>
	        ifmaxaddr 0 port 6 priority 0 path cost 0
	media: <unknown type>
	status: inactive
utun0: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 1380
	inet6 fe80::5573:bffb:a8a3:2483%utun0 prefixlen 64 scopeid 0xa
	inet6 fdd7:da51:30ea:2752:5573:bffb:a8a3:2483 prefixlen 64
	nd6 options=1<PERFORMNUD>
```
Gateway
```
netstat -nr

Routing tables

Internet:
Destination        Gateway            Flags        Refs      Use   Netif Expire
default            192.168.1.1        UGSc           10        0     en0
127                127.0.0.1          UCS             0        0     lo0
127.0.0.1          127.0.0.1          UH              1 10058453     lo0
169.254            link#4             UCS             0        0     en0
192.168.1          link#4             UCS             0        0     en0
192.168.1.1/32     link#4             UCS             1        0     en0
192.168.1.1        44:2b:3:7e:8d:7c   UHLWIir        25      367     en0   1156
192.168.1.182/32   link#4             UCS             0        0     en0

Internet6:
Destination                             Gateway                         Flags         Netif Expire
::1                                     ::1                             UHL             lo0
fdd7:da51:30ea:2752::/64                fe80::5573:bffb:a8a3:2483%utun0 Uc            utun0
fdd7:da51:30ea:2752:5573:bffb:a8a3:2483 link#10                         UHL             lo0
fe80::%lo0/64                           fe80::1%lo0                     UcI             lo0
fe80::1%lo0                             link#1                          UHLI            lo0
fe80::%en0/64                           link#4                          UCI             en0
fe80::18ea:606b:4e0d:5431%en0           7c:d1:c3:4:de:da                UHLWI           en0
fe80::9272:40ff:fe0c:62c%en0            90:72:40:c:6:2c                 UHLWI           en0
fe80::bae8:56ff:fe49:292%en0            b8:e8:56:49:2:92                UHLI            lo0
fe80::%awdl0/64                         link#8                          UCI           awdl0
fe80::1450:8eff:fea7:43ae%awdl0         16:50:8e:a7:43:ae               UHLI            lo0
fe80::%utun0/64                         fe80::5573:bffb:a8a3:2483%utun0 UcI           utun0
fe80::5573:bffb:a8a3:2483%utun0         link#10                         UHLI            lo0
ff01::%lo0/32                           ::1                             UmCI            lo0
ff01::%en0/32                           link#4                          UmCI            en0
ff01::%awdl0/32                         link#8                          UmCI          awdl0
ff01::%utun0/32                         fe80::5573:bffb:a8a3:2483%utun0 UmCI          utun0
ff02::%lo0/32                           ::1                             UmCI            lo0
ff02::%en0/32                           link#4                          UmCI            en0
ff02::%awdl0/32                         link#8                          UmCI          awdl0
ff02::%utun0/32                         fe80::5573:bffb:a8a3:2483%utun0 UmCI          utun0

ping
```
Beyond the router
```
traceroute -q 1 -n www.professionalyou.com

traceroute to professionalyou.com (66.147.244.223), 64 hops max, 52 byte packets
 1  66.147.244.223  3.453 ms
 2  64.46.12.1  5.298 ms
 3  216.243.24.2  3.906 ms
 4  206.81.80.40  9.272 ms
 5  72.52.92.10  20.760 ms
 6  184.105.80.30  42.151 ms
 7  66.160.133.118  98.387 ms
 8  199.58.199.118  65.543 ms
 9  66.147.244.223  64.131 ms
```
-q 1 try each router once
-n only look at IP not DNS

###Local DNS server
```
cat /etc/resolv.conf

#
# Mac OS X Notice
#
# This file is not used by the host name and address resolution
# or the DNS query routing mechanisms used by most processes on
# this Mac OS X system.
#
# This file is automatically generated.
#
domain Terram
nameserver 192.168.1.1
```
###Name server lookup
```
nslookup www.professionalyou.com

Server:		192.168.1.1
Address:	192.168.1.1#53

Non-authoritative answer:
www.professionalyou.com	canonical name = professionalyou.com.
Name:	professionalyou.com
Address: 66.147.244.223
```
###Domain information Groper
```
dig www.professionalyou.com

; <<>> DiG 9.8.3-P1 <<>> www.professionalyou.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 60398
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 0

;; QUESTION SECTION:
;www.professionalyou.com.	IN	A

;; ANSWER SECTION:
www.professionalyou.com. 3541	IN	CNAME	professionalyou.com.
professionalyou.com.	3541	IN	A	66.147.244.223

;; Query time: 7 msec
;; SERVER: 192.168.1.1#53(192.168.1.1)
;; WHEN: Mon Dec  8 21:20:40 2014
;; MSG SIZE  rcvd: 90
```
###Public IP
```
curl ipinfo.io/ip
64.46.30.250
```

