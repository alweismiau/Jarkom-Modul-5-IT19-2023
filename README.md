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

### Soal-No-1
Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.

#### Penyelesaian 
Didalam Node Aura kita menambahkan script dibawah ini 
```
ETH0_IP=$(ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')

iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP
```
Lalu pada setiap node di tambahkan ``` nameserver 192.168.122.1 ``` pada ``` /etc/resolv.conf ```

#### Hasil Testing
- **AURA**
![No 1 Aura](https://github.com/faizfernanda/Jarkom-Modul-5-B25-2023/assets/101172294/1d0449d5-0cfd-4822-8dd9-dd19da1bb48b)
- **Client**
![no 1 client](https://github.com/faizfernanda/Jarkom-Modul-5-B25-2023/assets/101172294/beb68d5c-6e5b-4011-814d-176ec10777e6)
### Soal-No-2
Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.

#### Penyelesaian 
Untuk menyelesaikan problem di atas maka di perlukan sytax seperti di bawah ini :
```
# Drop semua koneksi UDP
iptables -A INPUT -p udp -j DROP

# Drop semua koneksi TCP kecuali port 8080
iptables -A INPUT -p tcp ! --dport 8080 -j DROP
iptables -A INPUT -p tcp -j DROP
```
#### Hasil Testing
- Dari Sender

![No 2 sender](https://github.com/faizfernanda/Jarkom-Modul-5-B25-2023/assets/101172294/6144a21b-6eb7-4eac-9b83-a0d86e324410)


- Dari Receiver

![no 2 receiver](https://github.com/faizfernanda/Jarkom-Modul-5-B25-2023/assets/101172294/6564d017-0702-480e-b022-1d73bc297ce9)

### Soal-No-3
Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop

#### Penyelesaian 
Untuk menyelesaikan problem di atas maka di perlukan sytax seperti di bawah ini :
```
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP

```
#### Hasil Testing
Bisa di lihat pada client ```TurkRegion``` ping tidak dapat di lakukan karena ada nya pembatasan maximal 3 client

![3](https://github.com/alweismiau/Jarkom-Modul-5-IT19-2023/assets/112788819/90de6211-7d68-4bbf-a49b-7f7b88a070b6)

### Soal-No-4
Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.

#### Penyelesaian 
Untuk menyelesaikan problem di atas maka di perlukan sytax seperti di bawah ini :
```
#pada Sein
# Allow SSH from a specific IP range
iptables -A INPUT -p tcp --dport 22 -m iprange --src-range 10.73.8.3-10.73.10.5 -j ACCEPT

# Drop SSH from all other sources
iptables -A INPUT -p tcp --dport 22 -j DROP

```

#### Hasil Testing
Terlihat dari Hasil Testing bahwa yang muncul hanya yang berada di GrobForest sedangkan client lainnya tidak menerima pesan

![4](https://github.com/alweismiau/Jarkom-Modul-5-IT19-2023/assets/112788819/c5f7d4aa-b5fe-418d-8699-269724d1ef0c)

### Soal-No-5
Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.

#### Penyelesaian 
Untuk menyelesaikan problem di atas maka di perlukan sytax seperti di bawah ini :
```
# Allow HTTP access only during working hours (Monday-Friday, 08:00-16:00)
iptables -A INPUT -p tcp --dport 80 -m time --timestart 08:00 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT

# Drop other HTTP traffic
iptables -A INPUT -p tcp --dport 80 -j DROP

```
#### Hasil Testing
Terlihat hasil testing bahwa saat waktu server bukan berada di antara 08:00-16:00 walau di hari yang kita tentukan, maka client tidak menerima pesan yang di kirim web server (Sein)

![5-gagal](https://github.com/alweismiau/Jarkom-Modul-5-IT19-2023/assets/112788819/e88d8fff-3878-4000-8bfa-ad6c4a4e4d65)

![No5 hasil](https://github.com/faizfernanda/Jarkom-Modul-5-B25-2023/assets/101172294/13736ce7-5dfb-4b25-b6b1-79776844de53)


### Soal-No-6
Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).

#### Penyelesaian 
Tambahkan script pada `Sein` dan `Stark` sebagai Web Server :
```
# Drop akses pada hari Senin-Kamis jam 12:00 - 13:00
iptables -A INPUT -p tcp --dport 80 -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j DROP

# Drop akses pada hari Jum'at pada 11:00 - 13:00
iptables -A INPUT -p tcp --dport 80 -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j DROP
```

#### Hasil Testing
https://github.com/faizfernanda/Jarkom-Modul-5-B25-2023/assets/88433109/1eb5c451-a4f5-4d13-a309-0fd416708a39

### Soal-No-7
Karena terdapat 2 Web Server, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.

#### Penyelesaian 
Tambahkan script pada `Sein` dan `Stark` sebagai Web Server :
- Sein
  ```
  iptables -A PREROUTING -t nat -p tcp -d 10.73.8.2 --dport 80 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.73.8.2:80

  iptables -A PREROUTING -t nat -p tcp -d 10.73.8.2 --dport 80 -j DNAT --to-destination 10.73.14.138:80
  ```

- Stark
  ```
  iptables -A PREROUTING -t nat -p tcp -d 10.73.8.2 --dport 443 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.73.8.2:443

  iptables -A PREROUTING -t nat tcp -d 10.73.8.2 --dport 443 -j DNAT --to-destination 10.73.14.138:443
  ```

#### Hasil Testing


### Soal-No-8
Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.

#### Penyelesaian 
Tambahkan script pada `Sein` dan `Stark` sebagai Web Server :
- Sein
  ```
  iptables -A INPUT -s 10.73.14.130 -m time --datestart 2023-10-19T00:00 --datestop 2024-02-15T00:00 -j DROP
  ```
  
- Stark
  ```
  iptables -A INPUT -s 10.73.14.130 -m time --datestart 2023-10-19T00:00 --datestop 2024-02-15T00:00 -j DROP
  ```

#### Hasil Testing


### Soal-No-9
Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir  alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. 
(clue: test dengan nmap)

#### Penyelesaian 
Tambahkan script pada `Sein` dan `Stark` sebagai Web Server :
- Sein dan Stark
  ```
  iptables -N portscan

  iptables -A INPUT -m recent --name portscan --update --seconds 600 --hitcount 20 -j DROP
  iptables -A FORWARD -m recent --name portscan --update --seconds 600 --hitcount 20 -j DROP

  iptables -A INPUT -m recent --name portscan --set -j ACCEPT
  iptables -A FORWARD -m recent --name portscan --set -j ACCEPT
  ```

#### Hasil Testing


### Soal-No-10
Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level. 

#### Penyelesaian 
Tambahkan script pada setiap node server dan router :
 ```
 iptables -A INPUT -j LOG --log-level debug --log-prefix "Dropped Packet" -m limit --limit 1/second --limit-burst 10
 ```
