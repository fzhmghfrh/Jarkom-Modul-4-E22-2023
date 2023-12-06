# Jarkom-Modul-4-E22-2023

| Nama                       | NRP        |
| ---------------------------| -----------|
| Anggara Saputra            | 5025211241 |
| Faizah Nurdianti Maghfirah | 5025211134 |

## VLSM - GNS3

### Subnet
![image](https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/blob/main/img/subnet.jpg)

### Rute
| Nama Subnet | Rute                                            | Jumlah IP | Netmask |
| ------------| ------------------------------------------------| ----------| ------- |
| A1          | Aura-Frieren                                    | 2    | /30 |
| A2          | Frieren-Switch3-LakeKorridor                    | 25   | /27 |
| A3          | Frieren-Flamme                                  | 2    | /30 |
| A4          | Flamme-Fern                                     | 2    | /30 |
| A5          | Fern-Switch4-LaubHills-Switch4-AppetitRegion    | 1023 | /21 |
| A6          | Flamme-Switch5-RohrRoad                         | 1001 | /22 |
| A7          | Flamme-Himmel                                   | 2    | /30 |
| A8          | Himmel-Switch6-SchwerMountains                  | 6    | /29 |
| A9          | Aura-Eisen                                      | 2    | /30 |
| A10         | Eisen-Switch1-Richter-Switch1-Revolte           | 3    | /29 |
| A11         | Eisen-Linie                                     | 2    | /30 |
| A12         | Linie-Lawine                                    | 2    | /30 |
| A13         | Lawine-Switch7-BredtRegion-Switch7-Heiter       | 31   | /26 |
| A14         | Heiter-Switch8-Sein-Switch8-RiegelCanyon        | 512  | /22 |
| A15         | Linie-Switch11-GranzChannel                     | 255  | /23 |
| A16         | Eisen-Lugner                                    | 2    | /30 |
| A17         | Lugner-Switch9-GrobeForest                      | 251  | /24 |
| A18         | Lugner-Switch10-TurkRegion                      | 1001 | /22 |
| A19         | Eisen-Switch0-Stark                             | 2    | /30 |
| A20         | Aura-Denken                                     | 2    | /30 |
| A21         | Denken-Switch2-RoyalCapital-Switch2-WilleRegion | 127  | /25 |
| Total       |                                                 | 4255 | /19 |

### Tree
![image](https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/blob/main/img/vlsmtree.jpg)

### Pembagian IP
| Subnet | Rute          | Netmask         | Broadcast      |
| -------| --------------| ----------------| -------------- |
| A1     | 192.217.0.0   | 255.255.255.252 | 192.217.0.3    |
| A2     | 192.217.0.64  | 255.255.255.224 | 192.217.0.95   |
| A3     | 192.217.0.4   | 255.255.255.252 | 192.217.0.7    |
| A4     | 192.217.0.8   | 255.255.255.252 | 192.217.0.11   |
| A5     | 192.217.32.0  | 255.255.248.0   | 192.217.32.255 |
| A6     | 192.217.12.0  | 255.255.252.0   | 192.217.12.255 |
| A7     | 192.217.0.12  | 255.255.255.252 | 192.217.0.15   |
| A8     | 192.217.0.48  | 255.255.255.248 | 192.217.0.55   |
| A9     | 192.217.0.16  | 255.255.255.252 | 192.217.0.19   |
| A10    | 192.217.0.40  | 255.255.255.248 | 192.217.0.47   |
| A11    | 192.217.0.20  | 255.255.255.252 | 192.217.0.23   |
| A12    | 192.217.0.24  | 255.255.255.252 | 192.217.0.27   |
| A13    | 192.217.0.128 | 255.255.255.192 | 192.217.0.192  |
| A14    | 192.217.8.0   | 255.255.252.0   | 192.217.8.255  |
| A15    | 192.217.4.0   | 255.255.254.0   | 192.217.4.255  |
| A16    | 192.217.0.28  | 255.255.255.252 | 192.217.0.31   |
| A17    | 192.217.2.0   | 255.255.255.0   | 192.217.2.255  |
| A18    | 192.217.16.0  | 255.255.252.0   | 192.217.16.255 |
| A19    | 192.217.0.32  | 255.255.255.252 | 192.217.0.35   |
| A20    | 192.217.0.36  | 255.255.255.252 | 192.217.0.39   |
| A21    | 192.217.1.0   | 255.255.255.0   | 192.217.1.255  |

### Topologi
![image](https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/blob/main/img/toplogi.jpg)

### Node Config
#### Aura
```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 192.217.0.1
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 192.217.0.17
	netmask 255.255.255.252

auto eth3
iface eth3 inet static
	address 192.217.0.37
	netmask 255.255.255.252
```

#### Frieren
```
auto eth0
iface eth0 inet static
address 192.217.0.2
	netmask 255.255.255.252
	gateway 192.217.0.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.217.0.65
	netmask 255.255.255.224

auto eth2
iface eth2 inet static
	address 192.217.0.5
	netmask 255.255.255.252
```

#### LakeKorridor
```
auto eth0
iface eth0 inet static
	address 192.217.0.66
	netmask 255.255.255.224
	gateway 192.217.0.65
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### Flamme
```
auto eth0
iface eth0 inet static
address 192.217.0.6
	netmask 255.255.255.252
	gateway 192.217.0.5
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.217.0.9
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 192.217.12.1
	netmask 255.255.252.0

auto eth3
iface eth3 inet static
	address 192.217.0.13
	netmask 255.255.255.252
```

#### Fern
```
auto eth0
iface eth0 inet static
	address 192.217.0.10
	netmask 255.255.255.252
	gateway 192.217.0.9
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.217.32.1
	netmask 255.255.248.0
```

#### LaubHills
```
auto eth0
iface eth0 inet static
	address 192.217.32.2
	netmask 255.255.248.0
	gateway 192.217.32.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### AppetitRegion
```
auto eth0
iface eth0 inet static
	address 192.217.32.3
	netmask 255.255.248.0
	gateway 192.217.32.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### RohrRoad
```
auto eth0
iface eth0 inet static
	address 192.217.12.2
	netmask 255.255.252.0
	gateway 192.217.12.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### Himmel
```
auto eth0
iface eth0 inet static
	address 192.217.0.14
	netmask 255.255.255.252
	gateway 192.217.0.13
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.217.0.48
	netmask 255.255.255.248
```

#### SchwerMountains
```
auto eth0
iface eth0 inet static
address 192.217.0.49
	netmask 255.255.255.248
	gateway 192.217.0.48
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### Eisen
```
auto eth0
iface eth0 inet static
	address 192.217.0.18
	netmask 255.255.255.252
	gateway 192.217.0.17
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.217.0.41
	netmask 255.255.255.248

auto eth2
iface eth2 inet static
	address 192.217.0.21
	netmask 255.255.255.252

auto eth3
iface eth3 inet static
	address 192.217.0.29
	netmask 255.255.255.252

auto eth4
iface eth4 inet static
	address 192.217.0.33
	netmask 255.255.255.252
```

#### Richter
```
auto eth0
iface eth0 inet static
	address 192.217.0.42
	netmask 255.255.255.248
	gateway 192.217.0.41
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### Revolte
```
auto eth0
iface eth0 inet static
	address 192.217.0.43
	netmask 255.255.255.248
	gateway 192.217.0.41
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### Linie
```
auto eth0
iface eth0 inet static
	address 192.217.0.22
	netmask 255.255.255.252
	gateway 192.217.0.21
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.217.0.25
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 192.217.4.1
	netmask 255.255.254.0
```

#### Lawine
```
auto eth0
iface eth0 inet static
	address 192.217.0.26
	netmask 255.255.255.252
	gateway 192.217.0.25
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.217.0.129
	netmask 255.255.255.192
```

#### BredtRegion
```
auto eth0
iface eth0 inet static
	address 192.217.0.130
	netmask 255.255.255.192
	gateaway 192.217.0.129
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### Heiter
```
auto eth0
iface eth0 inet static
	address 192.217.0.131
	netmask 255.255.255.192
	gateaway 192.217.0.129
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.217.8.1
	netmask 255.255.252.0
```

#### Sein
```
auto eth0
iface eth0 inet static
	address 192.217.8.2
	netmask 255.255.252.0
	gateaway 192.217.8.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### RiegelCanyon
```
auto eth0
iface eth0 inet static
	address 192.217.8.2
	netmask 255.255.252.0
	gateaway 192.217.8.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### GranzChannel
```
auto eth0
iface eth0 inet static
	address 192.217.4.2
	netmask 255.255.254.0
	gateaway 192.217.4.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### Lugner
```
auto eth0
iface eth0 inet static
	address 192.217.0.30
	netmask 255.255.255.252
	gateway 192.217.0.29
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.217.16.1
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 192.217.2.1
	netmask 255.255.252.0
```

#### GrobeForest
```
auto eth0
iface eth0 inet static
	address 192.217.2.2
	netmask 255.255.252.0
	gateaway 192.217.2.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### TurkRegion
```
auto eth0
iface eth0 inet static
	address 192.217.16.2
	netmask 255.255.255.0
	gateaway 192.217.16.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### Stark
```
auto eth0
iface eth0 inet static
	address 192.217.0.34
	netmask 255.255.252.0
	gateaway 192.217.0.33
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### Denken
```
auto eth0
iface eth0 inet static
	address 192.217.0.38
	netmask 255.255.255.252
	gateway 192.217.0.37
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.217.1.1
	netmask 255.255.255.0
```

#### RoyalCapital
```
auto eth0
iface eth0 inet static
	address 192.217.1.2
	netmask 255.255.255.0
	gateway 192.217.1.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

#### WilleRegion
```
auto eth0
iface eth0 inet static
	address 192.217.1.3
	netmask 255.255.255.0
	gateway 192.217.1.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

### Routing
#### Aura
```
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 192.217.0.0/16

route add -net 192.217.0.64 netmask 255.255.255.224 gw 192.217.0.2
route add -net 192.217.0.4 netmask 255.255.252.252 gw 192.217.0.2
route add -net 192.217.0.8 netmask 255.255.255.252 gw 192.217.0.2
route add -net 192.217.32.0 netmask 255.255.248.0 gw 192.217.0.2
route add -net 192.217.12.0 netmask 255.255.252.0 gw 192.191.0.2
route add -net 192.217.0.12 netmask 255.255.255.252 gw 192.217.0.2
route add -net 192.217.0.48 netmask 255.255.255.248 gw 192.191.0.2

route add -net 192.217.0.40 netmask 255.255.255.248 gw 192.217.0.18
route add -net 192.217.0.20 netmask 255.255.255.252 gw 192.217.0.18
route add -net 192.217.0.24 netmask 255.255.255.252 gw 192.217.0.18
route add -net 192.217.0.128 netmask 255.255.255.192 gw 192.217.0.18
route add -net 192.217.8.0 netmask 255.255.252.0 gw 192.217.0.18
route add -net 192.217.4.0 netmask 255.255.254.0 gw 192.217.0.18
route add -net 192.217.0.28 netmask 255.255.255.252 gw 192.217.0.18
route add -net 192.217.2.0 netmask 255.255.255.0 gw 192.217.0.18
route add -net 192.217.16.0 netmask 255.255.252.0 gw 192.217.0.18
route add -net 192.217.0.32 netmask 255.255.255.252 gw 192.217.0.18

route add -net 192.217.1.0 netmask 255.255.255.0 gw 192.217.0.38
```

#### Frieren
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.0.1

route add -net 192.217.0.8 netmask 255.255.255.252 gw 192.217.0.6
route add -net 192.217.32.0 netmask 255.255.248.0 gw 192.217.0.6
route add -net 192.217.12.0 netmask 255.255.252.0 gw 192.191.0.6
route add -net 192.217.0.12 netmask 255.255.255.252 gw 192.217.0.6
route add -net 192.217.0.48 netmask 255.255.255.248 gw 192.191.0.6
```

#### Flamme
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.0.5

route add -net 192.217.0.8 netmask 255.255.255.252 gw 192.217.0.10
route add -net 192.217.32.0 netmask 255.255.248.0 gw 192.217.0.10

route add -net 192.217.0.12 netmask 255.255.255.252 gw 192.217.0.14
route add -net 192.217.0.48 netmask 255.255.255.248 gw 192.191.0.14
```

#### Fern
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.0.9
```

#### Himmel
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.0.13
```

#### Eisen
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.0.17

route add -net 192.217.0.24 netmask 255.255.255.252 gw 192.217.0.22
route add -net 192.217.0.128 netmask 255.255.255.192 gw 192.217.0.22
route add -net 192.217.8.0 netmask 255.255.252.0 gw 192.217.0.22
route add -net 192.217.4.0 netmask 255.255.254.0 gw 192.217.0.22
route add -net 192.217.0.28 netmask 255.255.255.252 gw 192.217.0.22
route add -net 192.217.2.0 netmask 255.255.255.0 gw 192.217.0.22
route add -net 192.217.16.0 netmask 255.255.252.0 gw 192.217.0.22
```

#### Linie
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.0.21

route add -net 192.217.0.128 netmask 255.255.255.192 gw 192.217.0.26
route add -net 192.217.8.0 netmask 255.255.252.0 gw 192.217.0.26
```

#### Lawine
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.0.25

route add -net 192.217.8.0 netmask 255.255.252.0 gw 192.217.0.131
```

#### Heiter
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.0.129
```

#### Lugner
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.0.29
```

#### Denken
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.0.37
```

### Contoh ping
![image](https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/blob/main/img/ping.png)

## CIDR - Cisco

### Topologi

<img width="660" alt="Jepretan Layar 2023-12-06 pukul 19 52 49" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/d68de4ba-1b19-476b-af23-639dc1db3e4c">

### Pembagian Subnet
<img width="696" alt="Jepretan Layar 2023-12-06 pukul 19 32 37" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/8520ce4c-9c32-4502-98ee-aa817ad2a5c3">

### Penggabungan-CIDR
<img width="1028" alt="Jepretan Layar 2023-12-06 pukul 19 33 24" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/b90b82b0-8a00-4a35-bf82-d8ae12112d67">

<img width="1028" alt="Jepretan Layar 2023-12-06 pukul 19 33 02" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/a3a3ecb7-64b2-42c5-a4cb-889202365115">

### Tree-CIDR
<img width="1028" alt="Jepretan Layar 2023-12-06 pukul 19 36 15" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/6aa049d4-0a74-4afb-ab2f-4adadc05cd70">

### Pembagian IP-CIDR
<img width="1028" alt="Jepretan Layar 2023-12-06 pukul 19 36 32" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/1c8ac85f-f8f1-4613-b800-ef6bbc381697">

### Subnetting
| Subnet | Rute               		| IPv4            | Netmask           |
|--------|------------------------------|-----------------|-------------------|
| A1     | Router Eisen       		| 192.217.80.9    | 255.255.255.252   |
|        | Server-PT Stark    		| 192.217.80.10   | 255.255.255.252   |
| A2     | Router Eisen       		| 192.217.72.1    | 255.255.255.252   |
|        | Router Lugner      		| 192.217.72.2    | 255.255.255.252   |
| A3     | Router Lugner      		| 192.217.64.1    | 255.255.252.0     |
|        | PC-PT Region     		| 192.217.64.2    | 255.255.252.0     |
| A4     | Router Lugner      		| 192.217.68.1    | 255.255.255.0     |
|        | PC-PT GrobeForest      	| 192.217.68.2    | 255.255.255.0     |
| A5     | Router Eisen       		| 192.217.32.1    | 255.255.255.252   |
|        | Router Linie        		| 192.217.32.2    | 255.255.255.252   |
| A6     | Router Linie        		| 192.217.8.1     | 255.255.255.252   |
|        | Router Lawine       		| 192.217.8.2     | 255.255.255.252   |
| A7     | Router Linie        		| 192.217.16.1    | 255.255.254.0     |
|        | PC-PT GranzChannel     	| 192.217.16.2    | 255.255.254.0     |
| A8     | Router Lawine       		| 192.217.4.1     | 255.255.255.192   |
|        | PC-PT BredtRegion      	| 192.217.4.3     | 255.255.255.192   |
|        | Router Heiter       		| 192.217.4.2     | 255.255.255.192   |
| A9     | Router Heiter       		| 192.217.0.1     | 255.255.252.0     |
|        | Server-PT Sein         	| 192.217.0.3     | 255.255.252.0     |
|        | PC-PT ReigelCanyon     	| 192.217.0.2     | 255.255.252.0     |
| A10    | Router Eisen       		| 192.217.80.1    | 255.255.255.248   |
|        | Server-PT Ritcher      	| 192.217.80.2    | 255.255.255.248   |
|        | Server-PT Revolte      	| 192.217.80.3    | 255.255.255.248   |
| A11    | Router Aura         		| 192.217.128.1   | 255.255.255.252   |
|        | Router Eisen       		| 192.217.128.2   | 255.255.255.252   |
| A12    | Router Aura         		| 192.219.1.1     | 255.255.255.252   |
|        | Router Denken       		| 192.219.1.2     | 255.255.255.252   |
| A13    | Router Denken       		| 192.219.0.1     | 255.255.255.0     |
|        | PC-PT RoyalCapital     	| 192.219.0.2     | 255.255.255.0     |
|        | PC-PT WilleRegion      	| 192.219.0.3     | 255.255.255.0     |
| A14    | Router Aura         		| 192.218.128.1   | 255.255.255.252   |
|        | Router Freiern     		| 192.218.128.2   | 255.255.255.252   |
| A15    | Router Frieren      		| 192.218.64.1    | 255.255.255.224   |
|        | PC-PT LakeCorridor     	| 192.218.64.2    | 255.255.255.224   |
| A16    | Router Frieren      		| 192.218.32.1    | 255.255.255.252   |
|        | Router Flamme       		| 192.218.32.2    | 255.255.255.252   |
| A17    | Router Flamme       		| 192.218.8.1     | 255.255.255.252   |
|        | Router Fern         		| 192.218.8.2     | 255.255.255.252   |
| A18    | Router Fern         		| 192.218.0.1     | 255.255.248.0     |
|        | PC-PT LaubHills        	| 192.218.0.2     | 255.255.248.0     |
|        | PC-PT AppetiteRegion    	| 192.218.0.3     | 255.255.248.0     |
| A19    | Router Flamme       		| 192.218.16.1    | 255.255.252.0     |
|        | PC-PT RohrRoad         	| 192.218.16.2    | 255.255.252.0     |
| A20    | Router Flamme       		| 192.218.20.9    | 255.255.255.252   |
|        | Router Himmel       		| 192.218.20.10   | 255.255.255.252   |
| A21    | Router Himmel       		| 192.218.20.1    | 255.255.255.248   |
|        | PC-PT SchewerMountains  	| 192.218.20.2    | 255.255.255.248   |


### Routing

- Router Aura
  
  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 39 38" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/2af38fe2-b108-4efa-8c0c-509d48adc2e0">

  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 40 09" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/7f08f06a-e5a9-4aed-9c6f-15f2f39a0dcd">

- Router Denken

  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 41 04" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/27cad1e7-fdf2-44be-8c63-59fe47b916ec">

- Router Frieren

  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 41 46" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/e9c54d47-8419-4979-be0a-469c8bdf61d6">

- Router Flame
  
  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 49 48" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/5aaef3cf-82e5-4d59-aaa9-ef1d04d79697">

- Router Fern
  
  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 49 28" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/4e0d4e35-68e3-482c-bff1-a9e3876335fe">

- Router Himmel
  
  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 50 11" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/331f4909-0840-4e6e-b192-fb05272f5fbf">

- Router Eisen
  
  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 45 53" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/64bb0111-0780-4793-a4a5-b53e1e825429">

- Router Lugner
  
  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 47 45" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/a48c945e-66ef-40bb-a3f9-0b4e5deae38a">

- Router Linie
  
  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 48 08" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/bc9b8d0b-23b6-40e3-bdff-70a06fe1e5b1">

- Router Lawine
  
  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 48 31" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/26f09e1e-2bb3-46b0-9069-d03907b5d4a0">

- Router Heiter

  <img width="501" alt="Jepretan Layar 2023-12-06 pukul 19 49 00" src="https://github.com/fzhmghfrh/Jarkom-Modul-4-E22-2023/assets/116636265/92013a8d-48f3-4948-b529-6d8b5d40104c">
