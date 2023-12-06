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
