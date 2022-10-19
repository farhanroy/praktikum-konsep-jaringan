**Metrik **adalah suatu nilai yang digunakan untuk mencapai suatu jaringan. Semakin nilai metrik maka akan memiliki jalur terbaik.

1. Langkah pertama saya membuat topologi seperti ini

![Topologi jaringan](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/u0bzpj7mj2lmtb0wb1jk.png)

Topologi diatas terdiri dari 3 router, 2 switch, dan 2 host. Nantinya host akan terhubung melalui jaringan dengan metric terkecil.

2. Atur ip pada masing masing device 


**Konfigurasi IP Route**

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

**Konfigurasi IP PC**

|  Devices 	| Interface 	|      IP     	|
|:--------:	|:---------:	|:-----------:	|
|    PC0   	|   Fa0/0   	| 192.168.4.2 	|
|    PC1   	|   Fa0/0   	| 192.168.5.2 	|

**Konfigurasi Static Routing Pada Komputer**

|  Devices 	| Destination Network 	|    Netmask    	|     Via     	|    Metric    	|
|:--------:	|:-------------------:	|:-------------:	|:-----------:	|:------------:	|
| Router 0 	|     192.168.4.0     	| 255.255.255.0 	| 192.168.2.1 	| 10 (Default) 	|
|          	|     192.168.5.0     	| 255.255.255.0 	| 192.168.1.1 	| 10 (Default) 	|
| Router 1 	|     192.168.4.0     	| 255.255.255.0 	| 192.168.3.1 	| 10 (Default) 	|
|          	|     192.168.2.0     	| 255.255.255.0 	| 192.168.1.2 	| 10 (Default) 	|
| Router 2 	|     192.168.5.0     	| 255.255.255.0 	| 192.168.3.1 	| 10 (Default) 	|
|          	|     192.168.1.0     	| 255.255.255.0 	| 192.168.2.2 	| 10 (Default) 	|

Setelah konfigurasi ip selesai maka di testing dengan menggunakan traceroute

3. Menggunakan traceroute
Untuk menggunakan tracerout saya menggunakan command dibawah ini

```
tracecert 192.168.4.2
```

![traceroute](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/mf3eu7zus0q4tx9seql4.png)

saat saya coba tracert 3 kali pada pc1 (192.168.5.2) melakukan tracert ke pc0 (192.168.4.2) melalui router 1 (192.168.5.1) lalu ke router 2 (192.168.3.1) dan akhirnya ke pc0 (192.168.4.2).

4. Membuat metric

Jika ingin mengatur jalannya packet di static route maka menggunakan metric. Cara menambah metric ialah pada saat mendefinisikan ip route



|  Devices 	| Destination Network 	|    Netmask    	|     Via     	|    Metric    	|
|:--------:	|:-------------------:	|:-------------:	|:-----------:	|:------------:	|
| Router 0 	|     192.168.4.0     	| 255.255.255.0 	| 192.168.2.1 	| 10 (Default) 	|
|          	|     192.168.5.0     	| 255.255.255.0 	| 192.168.1.1 	| 10 (Default) 	|
| Router 1 	|     192.168.4.0     	| 255.255.255.0 	| 192.168.3.1 	| 10 (Default) 	|
|          	|     192.168.4.0     	| 255.255.255.0 	| 192.168.1.2 	|       1      	|
| Router 2 	|     192.168.5.0     	| 255.255.255.0 	| 192.168.3.1 	| 10 (Default) 	|
|          	|     192.168.5.0     	| 255.255.255.0 	| 192.168.2.2 	|       1      	|

Setelah di set dengan tabel routing diatas, saya mencoba lagi inspect jalur routing pada network 192.168.5.2

![Traceroute](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/iihk7t099801o3aoj4wy.png)

