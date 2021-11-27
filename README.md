# jarkom-modul-4-A01-2021

# Anggota kelompok A1 :
- 05111940000083 Fajar Satria
- 05111940000124 Gerry Sihaj
- 05111940000130 Adrian

# VLSM
Subnet | Jumlah IP | Netmask
--- | --- | --- 
A1  	|721|	/22
A2	|2| 	/30
A3	|2|	/30
A4	|13|	/28
A5	|521|	/22
A6	|1001|	/22
A7	|252|	/24
A8	|701|	/22
A9	|101|	/25
A10	|2|	/30
A11	|2|	/30
A12	|2021|	/21
A13	|2|	/30
A14	|2|	/30
A15	|502|	/23
Total	|5845|	/19

# langkah
1. menggambar grafik dengan root awal subnet 19 dengan ip [prefix].0.0/19
![image](https://user-images.githubusercontent.com/55443217/143681340-58f32995-3adc-4a15-934e-bd2503206874.png)

2. membagi subnet menjadi 16 kiri dan 16 kanan dengan mask 20

3. karena tidak ada yang membutuhkan mask 20 maka lanjut pembagian 
4. node yang kiri dibagi menjadi 8 kiri dan 8 kanan mask 21. setelah itu ambil satu alamat ip untuk di assign ke A12
![image](https://user-images.githubusercontent.com/55443217/143681417-8e77f401-60f3-4d58-9c2d-e7c0506cb7d9.png)

5. ulangi terus sampai semua subnet mendapat ip
![vlsm](https://user-images.githubusercontent.com/55443217/143681439-e8b8eebe-31de-4f4f-8d2a-ad244f3b86e2.png)

6. buat topologi CPT
![image](https://user-images.githubusercontent.com/55443217/143681497-f67456a4-ffe9-4554-ae63-8fa7815a1aa9.png)

7. map ip sesuai tabel berikut
![image](https://user-images.githubusercontent.com/55443217/143681521-ffe4afb1-09e3-43b4-a6e5-237df6030848.png)

8. set routing pada tiap router  
![image](https://user-images.githubusercontent.com/55443217/143681601-c1a65ed5-4f1b-4387-ba96-793122db7e92.png)

9. set interface pada tiap router  
![image](https://user-images.githubusercontent.com/55443217/143681612-478f111c-2229-4904-a1d5-7357d65378c9.png)

10. set alamat ip  
![image](https://user-images.githubusercontent.com/55443217/143681628-0418063a-bea9-43a9-b61d-becd852b06ce.png)

# CIDR
## Subnet :
Subnet | Jumlah IP | Netmask
--- | --- | --- 
A1  |1001|	/22
A2	|2| /30
A3	|701|	/22
A4	|2|	/30
A5	|2021|	/21
A6	|101|	/25
A7	|2|	/30
A8	|521|	/22
A9	|502|	/23
A10	|13|	/28
A11	|2|	/30
A12	|252|	/24
A13	|721|	/22
Total	|5841|	/19

## IP :
Subnet |	Network ID |	Netmask
--- | --- | --- 
A1	|192.169.192.0|	255.255.252.0
A2	|192.169.64.0|	255.255.255.252
A3	|192.169.32.0|	255.255.252.0
A4	|192.169.16.0|	255.255.255.252
A5	|192.169.0.0|	255.255.248.0
A6	|192.169.8.0|	255.255.255.128
A7	|192.169.160.8|	255.255.255.252
A8	|192.169.130.0|	255.255.252.0
A9	|192.169.128.0|	255.255.254.0
A10	|192.169.130.16| 255.255.255.240
A11	|192.169.152.0|	255.255.255.252
A12	|192.169.144.0|	255.255.255.0
A13	|192.169.148.0|	255.255.252.0

## Langkah - langkah:  
1. Menentukan awal subnet

![1](https://user-images.githubusercontent.com/65168221/143670737-4b65c9aa-0aca-49e7-a159-48e2925fe8eb.png)  

2. Gabungkan (A5 dan A6 | A9 dan A10 | A12 dan A13)  

![2](https://user-images.githubusercontent.com/65168221/143670741-d3f52ffd-7519-4371-922e-58963b581dc3.png)  

3. Gabungkan (B1 dan A4 | B2 dan A8 | B3 dan A11)

![3](https://user-images.githubusercontent.com/65168221/143670742-bb1f1c84-805b-4ca5-b997-8909745ba536.png) 

4. Gabungkan (C1 dan A3 | C2 dan C3)

![4](https://user-images.githubusercontent.com/65168221/143670744-ffd98361-708d-492d-b094-05c6f86c1d1f.png)

5. Gabungkan (D1 dan A2 | D2 dan A7)

![5](https://user-images.githubusercontent.com/65168221/143670749-7cf55ea7-3141-44f7-abe2-b3933428f994.png)

6. Gabungkan (E2 dan A1)

![6](https://user-images.githubusercontent.com/65168221/143670750-57a0d4e0-91e8-4b01-94e5-68063806fae7.png)

7. Gabungkan (E1 dan F1)

![7](https://user-images.githubusercontent.com/65168221/143670753-65181d03-131a-4e58-897e-d806a7ad00e7.png)

## Tree :

![tree](https://user-images.githubusercontent.com/65168221/143671427-a8002d99-4f0d-4b68-8705-b686c24f7b3b.png)

## Setting ip pada gns3 :
Pada ```Edit Network Connection``` setting ip seperti berikut : 
Pada Client :
1. Cipher
```
auto eth0
iface eth0 inet static
	address 192.169.32.2
	netmask 255.255.252.0
	gateway 192.169.32.1
```
2. Blueno (A1) :
```
auto eth0
iface eth0 inet static
	address 192.169.192.2
	netmask 255.255.252.0
	gateway 192.169.192.1
```
3. Jipangu
```
auto eth0
iface eth0 inet static
	address 192.169.8.2
	netmask 255.255.255.128
	gateway 192.169.8.1
```
4. Calmbelt
```
auto eth0
iface eth0 inet static
	address 192.169.0.2
	netmask 255.255.248.0
	gateway 192.169.0.1
```
5. Jabra
```
auto eth0
iface eth0 inet static
	address 192.169.132.2
	netmask 255.255.252.0
	gateway 192.169.132.1
```
6. Maingate
```
iface eth0 inet static
	address 192.169.128.3
	netmask 255.255.254.0
	gateway 192.169.128.1
```
7. Jorge
```
auto eth0
iface eth0 inet static
	address 192.169.130.2
	netmask 255.255.255.240
	gateway 192.169.130.1
```
8. Courtyard
```
auto eth0
iface eth0 inet static
	address 192.169.0.3
	netmask 255.255.248.0
	gateway 192.169.0.1
```
9. Enieslobby
```
auto eth0
iface eth0 inet static
	address 192.169.144.3
	netmask 255.255.255.0
	gateway 192.169.144.1
```
10. Elena
```
auto eth0
iface eth0 inet static
	address 192.169.148.2
	netmask 255.255.252.0
	gateway 192.169.148.1
```

Pada Router :
1. Foosha
```
auto eth0
iface eth0 inet dhcp
auto eth1
iface eth1 inet static
	address 192.169.192.1
	netmask 255.255.252.0	
auto eth2
iface eth2 inet static
	address 192.169.64.1
	netmask 255.255.255.252
auto eth3
iface eth3 inet static
	address 10.100.100.105
	netmask 255.255.255.252
auto eth4
iface eth4 inet static
	address 192.169.160.1
	netmask 255.255.255.252
```
2. Water7
```
auto eth0
iface eth0 inet static
	address 192.169.64.2
	netmask 255.255.255.252
	gateway 192.169.64.1
auto eth1
iface eth1 inet static
	address 192.169.32.1
	netmask 255.255.252.0
auto eth2
iface eth2 inet static
	address 192.169.16.1
	netmask 255.255.255.252
```
3. Pucci
```
auto eth0
iface eth0 inet static
	address 192.169.16.2
	netmask 255.255.255.252
	gateway 192.169.16.1
auto eth1
iface eth1 inet static
	address 192.169.0.1
	netmask 255.255.248.0
auto eth2
iface eth2 inet static
	address 192.169.8.1
	netmask 255.255.255.128
```
4. Guanhao
```
auto eth0
iface eth0 inet static
	address 192.169.160.2
	netmask 255.255.255.252
	gateway 192.169.160.1
auto eth1
iface eth1 inet static
	address 192.169.132.1
	netmask 255.255.252.0
auto eth2
iface eth2 inet static
	address 192.169.128.1
	netmask 255.255.254.0
auto eth3
iface eth3 inet static
	address 192.169.152.1
	netmask 255.255.255.252
```
5. Alabasta
```
auto eth0
iface eth0 inet static
	address 192.169.128.2
	netmask 255.255.254.0
	gateway 192.169.128.1
auto eth1
iface eth1 inet static
	address 192.169.130.1
	netmask 255.255.255.240
```
6. OIMO
```
auto eth0
iface eth0 inet static
	address 192.169.152.2
	netmask 255.255.255.252
	gateway 192.169.152.1
auto eth1
iface eth1 inet static
	address 192.169.144.1
	netmask 255.255.255.0
auto eth2
iface eth2 inet static
	address 10.100.100.109
	netmask 255.255.255.252	
```
7. Seastone
```
auto eth0
iface eth0 inet static
	address 192.169.144.2
	netmask 255.255.255.0
	gateway 192.169.144.1
auto eth1
iface eth1 inet static
	address 192.169.148.1
	netmask 255.255.252.0

```

Pada Server :
1. Doriki
```
auto eth0
iface eth0 inet static
	address 10.100.100.106
	netmask 255.255.255.252
	gateway 10.100.100.105
```
2. Fukurou
```
auto eth0
iface eth0 inet static
	address 10.100.100.110
	netmask 255.255.255.252
	gateway 10.100.100.109
```

Routing :
- Foosha
```
route add -net 192.169.0.0 netmask 255.255.192.0 gw 192.169.64.2
route add -net 192.169.128.0 netmask 255.255.224.0 gw 192.169.160.2
route add -net 10.100.100.108 netmask 255.255.255.252 gw 192.169.160.2
```
- Water7
```
route add -net 192.169.0.0 netmask 255.255.240.0 gw 192.169.16.2
```
- Guanhao
```
route add -net 192.169.0.0 netmask 255.255.192.0 gw 192.169.64.2
route add -net 192.169.128.0 netmask 255.255.224.0 gw 192.169.160.2
route add -net 10.100.100.108 netmask 255.255.255.252 gw 192.169.160.2
```
- Oimo
```
route add -net 192.169.148.0 netmask 255.255.252.0 gw 192.169.144.2
```

Pada Foosha :
Jalankan ```iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 192.169.0.0/16```

Pada node selain Foosha :
Jalankan ```echo nameserver 192.168.122.1 > /etc/resolv.conf```

# Kendala
1. pada CPT terkadang harus ping lebih dari 1 kali baru bisa sukses
2. Kesusahan menambahkan route pada CIDR
