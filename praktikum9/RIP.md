Routing Information Protocol (RIP) adalah protokol routing yang menggunakan algoritma routing distance vector. RIP tidak memiliki peta yang lengkap tentang jaringan yang ada.  RIP menggunakan hop count sebagai metric dan link dengan hop count terkecil yang akan menjadi link terbaik (best path).

Berikut langkah langkah untuk menkonfigurasi RIP pada jaringan:

1. Buat topologi jaringannya 

![topologi](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/2qkynoer2lsc1vuvuwhe.png)

saya menggunakan topologi yang sama dengan praktikum sebelumnya.

2. Konfigurasi IP

Karena memang topologi sama, maka saya juga tidak merubah konfigurasi dari IP nya.

|  Devices 	| Interface 	|      IP     	|
|:--------:	|:---------:	|:-----------:	|
| Router 0 	|   Fa0/0   	| 192.168.2.2 	|
|          	|   Fa1/0   	| 192.168.1.2 	|
| Router 1 	|   Fa0/0   	| 192.168.1.1 	|
|          	|   Fa1/0   	| 192.168.3.2 	|
|           |   Fa2/0   	| 192.168.5.1   |
| Router 2 	|   Fa0/0   	| 192.168.2.1 	|
|          	|   Fa1/0   	| 192.168.3.1 	|
|           |   Fa2/0   	| 192.168.4.1   |


3. Atur RIP
Untuk mengkonfigurasi, yang dimasukan hanya jaringan yang direct langsung ke router yang dikonfigurasi.

* Route 0
![Route0](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/yshevm353kfjuc0nn2r7.png)

* Route 1
![Route1](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8kc0jsjk1kfmk9dzwxfh.png)


* Route 2
![Route2](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gev0pweq2ntgpspf86e1.png)

