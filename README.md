# Jarkom-Modul-5-E05-2021

Nama Kelompok:
1. Muhammad Rafki Mardi 05111940000054
2. Hana Machmudah 05111940000072
3. Achmad Fadillah  05111940000155


## (A) Tugas pertama kalian yaitu membuat topologi jaringan sesuai dengan rancangan yang diberikan Luffy dibawah ini:
   
   Pada praktikum ini dilakukan dengan menggunakan VLSM.
   
   <img width="700" alt="topologi" src="https://user-images.githubusercontent.com/66562311/145678801-a188e02d-87b4-47b4-9c3b-38a91ce40619.PNG">
   
   
## (B) Karena kalian telah belajar subnetting dan routing, Luffy ingin meminta kalian untuk membuat topologi tersebut menggunakan teknik CIDR atau VLSM. setelah melakukan subnetting, 

1. Melakukan pembagian subnet pada topologi.

    <img width="700" alt="" src="https://user-images.githubusercontent.com/66562311/145678981-69b380c9-bdb2-4ac7-b528-af7157830de1.jpg">
   
2. Mentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan lakukan labelling netmask berdasarkan jumlah IP yang dibutuhkan.

    <img width="250" alt="" src="https://user-images.githubusercontent.com/66562311/145678891-bce7649c-43b7-4c8f-93e3-c3274bd238dc.jpg">
    
3. Melakukan perhitungan pembagian IP berdasarkan NID dan netmask tersebut menggunakan pohon. Melakukan subnetting dengan menggunakan pohon tersebut untuk pembagian IP sesuai dengan kebutuhan masing-masing subnet yang ada.

   <img width="700" alt="" src="https://user-images.githubusercontent.com/66562311/145678824-5f30af72-b2b8-4e11-b5bc-3eb6081bfcb6.jpg">

4. Didapatkan pembagian IP dari pohon tersebut sebagai berikut.

    <img width="300" alt="" src="https://user-images.githubusercontent.com/66562311/145679004-70f42a5d-cfa7-4971-b0b8-f6eaff7f82b7.jpg">

    <img width="700" alt="" src="https://user-images.githubusercontent.com/66562311/145678989-4a342254-69ef-4093-af6b-255a48325996.jpg">
    
5. Mengubah Configurasi pada tiap Node.
   - FOOSHA
      ```
      auto lo
      iface lo inet loopback

      auto eth0
      iface eth0 inet dhcp

      auto eth1
      iface eth1 inet static
        address 192.202.0.5
        netmask 255.255.255.252

      auto eth2
      iface eth2 inet static
        address 192.202.0.1
        netmask 255.255.255.252
      ```
      
    - WATER7
        ```
        auto lo
        iface lo inet loopback

        auto eth0
        iface eth0 inet static
        address 192.202.0.2
        netmask 255.255.255.252
        gateway 192.202.0.1

        auto eth1
        iface eth1 inet static
        address 192.202.4.1
        netmask 255.255.252.0

        auto eth2
        iface eth2 inet static
        address 192.202.0.129
        netmask 255.255.255.128

        auto eth3
        iface eth3 inet static
        address 192.202.0.9
        netmask 255.255.255.248
        ```
        
    - GUANHAO
        ```
        auto lo
        iface lo inet loopback

        auto eth 0
        iface eth 0 inet static
        address 192.202.0.6
        netmask 255.255.255.252
        gateway 192.202.0.5

        auto eth 1
        iface eth 1 inet static
        address 192.202.2.1
        netmask 255.255.254.0

        auto eth 2
        iface eth 2 inet static
        address 192.202.1.1
        netmask 255.255.255.0

        auto eth 3
        iface eth 3 inet static
        address 192.202.0.17
        netmask 255.255.255.248
        ```
        
    - BLUENO
        ```
        auto lo
        iface lo inet loopback

        auto eth 0
        iface eth0 inet dhcp
        hwaddress ether
        ```
        
    - CHIPER
        ```
        auto lo
        iface lo inet loopback

        auto eth 0
        iface eth0 inet dhcp
        hwaddress ether
        ```
        
    - ELENA
        ```
        auto lo
        iface lo inet loopback

        auto eth 0
        iface eth0 inet dhcp
        hwaddress ether
        ```
        
    - FUKUROU
        ```
        auto lo
        iface lo inet loopback

        auto eth 0
        iface eth0 inet dhcp
        hwaddress ether
        ```
        
    - MAINGATE
        ```
        auto lo
        iface lo inet loopback

        auto eth 0
        iface eth 0 inet static
        address 192.202.0.19
        netmask 255.255.255.248
        gateway 192.202.0.17
        ```
        
    - JORGE
        ```
        auto lo
        iface lo inet loopback

        auto eth 0
        iface eth 0 inet static
        address 192.202.0.18
        netmask 255.255.255.248
        gateway 192.202.0.17
        ```
        
    - DORIKI
        ```
        auto lo
        iface lo inet loopback

        auto eth 0
        iface eth 0 inet static
        address 192.202.0.10
        netmask 255.255.255.248
        gateway 192.202.0.9
        ```
        
    - JIPANGU
        ```
        auto lo
        iface lo inet loopback

        auto eth 0
        iface eth 0 inet static
        address 192.202.0.11
        netmask 255.255.255.248
        gateway 192.202.0.9
        ```
    
## (C) Kalian juga diharuskan melakukan Routing agar setiap perangkat pada jaringan tersebut dapat terhubung.
    
  - FOOSHA
      ```
      route add -net 192.202.0.128 netmask 255.255.255.128 gw 192.202.0.2
      route add -net 192.202.4.0 netmask 255.255.252.0 gw 192.202.0.2
      route add -net 192.202.0.8 netmask 255.255.255.248 gw 192.202.0.2
      route add -net 192.202.2.0 netmask 255.255.254.0 gw 192.202.0.6
      route add -net 192.202.1.0 netmask 255.255.255.0 gw 192.202.0.6
      route add -net 192.202.0.16 netmask 255.255.255.248 gw 192.202.0.6
      ```

## (D) Tugas berikutnya adalah memberikan ip pada subnet Blueno, Cipher, Fukurou, dan Elena secara dinamis menggunakan bantuan DHCP server. Kemudian kalian ingat bahwa kalian harus setting DHCP Relay pada router yang menghubungkannya.
    
   1. Menginstall `apt-get install isc-dhcp-relay -y` pada  FOOSHA, WATER7, dan GUANHAO dan `apt-get install isc-dhcp-server` pada JIPANGU
   2. Pada Router FOOSHA, WATER7, dan GUANHAO Edit file `/etc/sysctl.conf` dengan command
        ```
        net.ipv4.ip_forward=1
        net.ipv4.conf.all.accept_source_route = 1
        ```
   3. Melakukan `sysctl -p`
   4. Membuka file `/etc/default/isc-dhcp-relay` dan edit server dengan mengarahkan `dchp-relay` menuju Jipangu `192.186.0.19` lalu `service isc-dhcp-relay restart` FOOSHA, WATER7, dan GUANHAO
      ```
      echo '# What servers should the DHCP relay forward requests to?
      SERVERS="192.202.0.10"
      # On what interfaces should the DHCP relay (dhrelay) serve DHCP requests?
      INTERFACES="eth1 eth2"
      # Additional options that are passed to the DHCP relay daemon?
      OPTIONS="" '> /etc/default/isc-dhcp-relay
      ```
   5. Pada JIPANGU edit file `/etc/default/isc-dhcp-server` dengan menambahkan:
      ```
      INTERFACES="eth0"
      ```
   6. Pada `dhcp-server` mengisikan data pada `/etc/dhcp/dhcpd.conf` di JIPANGU, lalu melakukan `service isc-dhcp-server restart`
        ```
        subnet 192.202.0.128 netmask 255.255.255.128{
            range 192.202.0.130 192.202.0.229;
            option routers 192.202.0.129;
            option broadcast-address 192.202.0.255;
            option domain-name-servers 192.202.0.11;
            default-lease-time 600;
            max-lease-time 7200;
        }
        subnet 192.202.4.0 netmask 255.255.252.0{
            range 192.202.4.2 192.202.6.191;
            option routers 192.202.4.1;
            option broadcast-address 192.202.7.255;
            option domain-name-servers 192.202.0.11;
            default-lease-time 600;
            max-lease-time 7200;
        }
        subnet 192.202.2.0 netmask 255.255.254.0{
            range 192.202.2.2 192.202.3.46;
            option routers 192.202.2.1;
            option broadcast-address 192.202.3.255;
            option domain-name-servers 192.202.0.11;
            default-lease-time 600;
            max-lease-time 7200;
        }
        subnet 192.202.1.0 netmask 255.255.255.0{
            range 192.202.1.2 192.202.1.201;
            option routers 192.202.1.1;
            option broadcast-address 192.202.1.255;
            option domain-name-servers 192.202.0.11;
            default-lease-time 600;
            max-lease-time 7200;
        }
       ```
       
   7. Membuka file `/etc/network/interfaces`. Command konfigurasi lama (static) dan ubah ip BLUENO, CHIPER, FUKUROU, dan ELENA dengan command
      ```
      auto eth0
      iface eth0 inet dhcp
      ```
   8. Melakukan restart di node yang dijadikan ip dhcp
      
## 1. Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Foosha menggunakan iptables, tetapi Luffy tidak ingin menggunakan MASQUERADE.
    
   FOOSHA 
   ```
   iptables -t nat -A POSTROUTING -s 192.186.0.0/16 -o eth0 -j SNAT --to-s 192.168.122.1
   ```

   Lalu, pada semua node yang terkait dilakukan echo nameserver `192.168.122.1 > /etc/resolv.conf`

   Keterangan:
    - `-t nat`: Menggunakan tabel NAT karena akan mengubah alamat asal dari paket
    - `-A POSTROUTING`: Menggunakan chain POSTROUTING karena mengubah asal paket setelah routing
    - `-s 192.186.0.0/16`: Mendifinisikan alamat asal dari paket yaitu semua alamat IP dari subnet 192.186.0.0/16
    - `-o eth0`: Paket keluar dari eth0 Foosha
    - `-j SNAT`: Menggunakan target SNAT untuk mengubah source atau alamat asal dari paket
    - `--to-s (ip eth0)`: Mendefinisikan IP source, di mana digunakan eth0 Foosha dengan rentang IP 192.168.122.0 sampai192.168.122.255

   Catatan :
    - ip eth0 akan selalu berganti ketika restart node pada FOOSHA atau restart GNS3 dengan rentang IP yang sudah dijelaskan
    - cara mengetahui eth0, masukan command ip a pada FOOSHA





# pembagian tugas:
- 05111940000054 Muhammad Rafki Mardi : Setup GNS 3 dan semua bash & net conf 
- 05111940000072 Hana Machmudah : Pembagian subnet, Perhitungan IP, Netmask, Netmask ID, Broadcast Address dan lapres
