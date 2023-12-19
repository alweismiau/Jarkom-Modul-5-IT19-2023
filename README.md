# Jarkom-Modul-5-IT19-2023
## Kelompok IT19
- Fina Keiza Arismana       5027211028
- Rifqi Akhmad Maulana      502721035

# Topologi
![](https://cdn.discordapp.com/attachments/1025213238763327683/1186618332087070740/image.png?ex=6593e770&is=65817270&hm=7a5165f420126dde6555da1b2c49e4ee9c3ec5d3d20d2a695145f78208fb5e09&)

# Rute
![](https://cdn.discordapp.com/attachments/1025213238763327683/1186618675546034196/image.png?ex=6593e7c2&is=658172c2&hm=04bc055ad3d29f0e5140ca88ec2c93c220b4df92afab6b80d2c8800be142b6b9&)

## Pengelompokan 
![](https://cdn.discordapp.com/attachments/1025213238763327683/1186620729458966558/Frame_21.png?ex=6593e9ac&is=658174ac&hm=ab367569f46bb23f6dc4c6e2b3c5e63f9608dde386aad58be3df55eadd96eaa0&)

## Tree
![](https://cdn.discordapp.com/attachments/1025213238763327683/1181584753376374824/WhatsApp_Image_2023-12-02_at_21.44.36_5013cef4.jpg?ex=6581978d&is=656f228d&hm=dd48ac0a257c59cc313e276caebbfc0c230bc15e12f00aa22f0e65a5ed88c802&)

## Konfigurasi Network
- Aura
```
# DHCP config for eth0
auto eth0
iface eth0 inet dhcp

# 1 Heiter
auto eth1
iface eth1 inet static
    address 10.73.14.133
    netmask 255.255.255.252

# 2 Frieren
auto eth2
iface eth2 inet static
    address 10.73.14.137
    netmask 255.255.255.252
```
- Fern
```
# Himmel
auto eth0
iface eth0 inet static
    address 10.73.14.3
    netmask 255.255.255.128
    gateway 10.73.14.1

# 1 Richter
auto eth1
iface eth1 inet static
    address 10.73.14.149
    netmask 255.255.255.252

# 2 Revolte
auto eth2
iface eth2 inet static
    address 10.73.14.129
    netmask 255.255.255.252

```
- Frieren
```
# Aura
auto eth0
iface eth0 inet static
    address 10.73.14.138
    netmask 255.255.255.252
    gateway 10.73.14.137

# 1  Stark
auto eth1
iface eth1 inet static
    address 10.73.14.141
    netmask 255.255.255.252

# 2 Himmel
auto eth2
iface eth2 inet static
    address 10.73.14.145
    netmask 255.255.255.252
```
- GrobeForest
```
# Heiter
auto eth0
iface eth0 inet static
    address 10.73.8.3
    netmask 255.255.252.0
    gateway 10.73.8.1
```
- Heiter
```
# Aura
auto eth0
iface eth0 inet static
    address 10.73.14.134
    netmask 255.255.255.252
    gateway 10.73.14.133

# 1 TurkRegion
auto eth1
iface eth1 inet static
    address 10.73.0.1
    netmask 255.255.248.0

# 2 Sein 
auto eth2
iface eth2 inet static
    address 10.73.8.1
    netmask 255.255.252.0
```
- Himmel
```
# Frieren
auto eth0
iface eth0 inet static
    address 10.73.14.146
    netmask 255.255.255.252
    gateway 10.73.14.145

# 1 LaubHills
auto eth1
iface eth1 inet static
    address 10.73.12.1
    netmask 255.255.254.0

# 2 Fern - Schwer
auto eth2
iface eth2 inet static
    address 10.73.14.1
    netmask 255.255.255.128
```
- LaubHills
```
# Himmel
auto eth0
iface eth0 inet static
    address 10.73.12.2
    netmask 255.255.254.0
    gateway 10.73.12.1
```
- Revolte
```
# Fern
auto eth0
iface eth0 inet static
    address 10.73.14.130
    netmask 255.255.255.252
    gateway 10.73.14.129
```
- Richter
```
# 1 Richter
auto eth0
iface eth0 inet static
    address 10.73.14.150
    netmask 255.255.255.252
    gateway 10.73.14.149
```
- SchwerMountains
```
# Himmel
auto eth0
iface eth0 inet static
    address 10.73.14.2
    netmask 255.255.255.128
    gateway 10.73.14.1
```
- Sein
```
# Heiter
auto eth0
iface eth0 inet static
    address 10.73.8.2
    netmask 255.255.252.0
    gateway 10.73.8.1
```
- Stark
```
# Frieren
auto eth0
iface eth0 inet static
    address 10.73.14.142
    netmask 255.255.255.252
    gateway 10.73.14.141
```
- TurkRegion
```
# heiter
auto eth0
iface eth0 inet static
    address 10.73.0.2
    netmask 255.255.248.0
    gateway 10.73.0.1
```

##  Routing
- Aura
```
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 192.173.0.0/16

# Heiter
route add -net 10.73.14.132 netmask 255.255.255.252 gw 10.73.14.134

# Frieren
route add -net 10.73.14.136 netmask 255.255.255.252 gw 10.73.14.138

# Heiter - Turk
route add -net 10.73.0.0 netmask 255.255.248.0 gw 10.73.14.134

# Heiter - Sein - GrobeForest
route add -net 10.73.8.0 netmask 255.255.252.0 gw 10.73.14.134

# Frieren - Stark
route add -net 10.73.14.140 netmask 255.255.255.252 gw 10.73.14.138

# Frieren - Himmel
route add -net 10.73.14.144 netmask 255.255.255.252 gw 10.73.14.138

# Frieren - Himmel - LaubHills
route add -net 10.73.12.0 netmask 255.255.254.0 gw 10.73.14.138

# Frieren - Himmel - Schwer - Fern
route add -net 10.73.14.0 netmask 255.255.255.128 gw 10.73.14.138

# Frieren - Himmel - Fern - Richter
route add -net 10.73.14.148 netmask 255.255.255.252 gw 10.73.14.138

# Frieren - Himmel - Fern - Revolte
route add -net 10.73.14.128 netmask 255.255.255.252 gw 10.73.14.138
```
- Fern
```
# Himmel
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.73.14.1
```
- Frieren
```
# Aura
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.73.14.137

# LaubHills
route add -net 10.73.12.0 netmask 255.255.254.0 gw 10.73.14.146

# Schwer & Fern
route add -net 10.73.14.0 netmask 255.255.255.128 gw 10.73.14.146

#  Richter
route add -net 10.73.14.148 netmask 255.255.255.252 gw 10.73.14.146

#  Revolte
route add -net 10.73.14.128 netmask 255.255.255.252 gw 10.73.14.146
```
- Heiter
```
# Aura
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.73.14.133
```
- Himmel
```
# Frieren
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.73.14.145

# Fern - Richter
route add -net 10.73.14.148 netmask 255.255.255.252 gw 10.73.14.3

# Fern - Revolte
route add -net 10.73.14.128 netmask 255.255.255.252 gw 10.73.14.3
```

## Nomor 1

