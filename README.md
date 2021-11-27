# jarkom-modul-4-A01-2021

# Anggota kelompok A1 :
- 05111940000083 Fajar Satria
- 05111940000124 Gerry Sihaj
- 05111940000130 Adrian

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
A1	|192.169.8.0|	255.255.252.0
A2	|192.169.0.0|	255.255.255.252
A3	|192.169.12.0|	255.255.252.0
A4	|192.169.0.4|	255.255.255.252
A5	|192.169.24.0|	255.255.248.0
A6	|192.169.0.128|	255.255.255.128
A7	|192.169.0.8|	255.255.255.252
A8	|192.169.16.0|	255.255.252.0
A9	|192.169.2.0|	255.255.254.0
A10	|192.169.0.16|	255.255.255.240
A11	|192.169.0.12|	255.255.255.252
A12	|192.169.1.0|	255.255.255.0
A13	|192.169.20.0|	255.255.252.0

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
![tree](https://user-images.githubusercontent.com/65168221/143671287-e49230af-1161-43ab-9480-7da015a8ed8a.png)
