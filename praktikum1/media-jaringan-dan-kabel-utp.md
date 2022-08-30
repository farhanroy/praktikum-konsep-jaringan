# 1. Dasar Teori
Media jaringan menjadi suatu perangkat keras (hardware) yang berada di lapisan pertama dalam struktur OSI, sering disebut dengan Pyshical Layer atau Layer Fisik. Lapisan ini berarti interface untuk meletakan bit bit data ke dalam media seperti kabel, cahaya, atau gelombang radio.

## 1.1 Media Jaringan Komputer
Media yang digunakan untuk men-*trasmit* data secara umum ada 3:
* Gelombang Radio
Media transmit ini sering disebut dengan wireless, karena tidak menggunakan media kabel melainkan udara. Contoh penggunaan nya adalah wifi router di rumah rumah, dan jaringan telpon seluler.
![](https://events.rumah123.com/news-content/img/2022/07/13144353/router-tp-link.jpg)
* Fiber Optik
Fiber Optik adalah kabel yang berisi serat optik. Apa itu serat optik ? Serat kecil yang terbuat dari kaca atau plastik yang dapat mentrasmisikan sinar cahaya. Berikut penampilan di dalamnya:
![](https://kominfo.sulselprov.go.id/upload/post/1513603163.jpg)
* Kabel Tembaga
Yang terakhir yaitu tembaga. Tembaga menjadi logam yang paling tepat untuk dijadikan sebagai penghantar listrik. Kabel tembaga yang digunakan di jaringan ada 2 UTP dan STP. Kedua nya hampir sama bedanya adalah yang utp tanpa shield atau perlindungan, dan begitupun sebaliknya.
![](https://i0.wp.com/4.bp.blogspot.com/-f9P1UL1CofA/Vsq1w6KN59I/AAAAAAAADkM/GE8k5AQCVfA/s1600/kabel%2Blistrik.jpg)

## 1.2 Standar Kabel UTP
Kabel utp menggunakan RJ-45 sebagai konektor atau jacknya. Kemudian menggunakan standar internasional EIA/TIA-568A dan EIA/TIA-568B 
![](https://iebmedia.com/wp-content/uploads/2012/12/ieb4637_3.gif)
## 1.3 Koneksi dengan Kabel UTP
Koneksi kabel UTP ada 2 jenis Crossover dan Straight. Yang disusun berdasarkan urutan warna kabel didalamnyaj, jika Straight susunan di ujung kabel. Jika anda menggunakan susunan standar TIA-568A maka ujung lain kabel juga harus TIA-568A

![](https://www.nesabamedia.com/wp-content/uploads/2018/06/Susunan-Kabel-Straight-Final.jpg)

Dan sebaliknya jika koneksi crossover maka standarisasinya terbalik TIA-568A -> TIA-568B atau sebaliknya.

![](https://www.nesabamedia.com/wp-content/uploads/2018/06/Susunan-Kabel-Cross-Final.jpg)

# 2. Pembuatan Kabel UTP
Cara pembuatan cukup tricky dan harus memperhatikan susunan kabel didalamnya agar pas ketika sudah di clampin (cekrek)
## 2.1 Alat yang perlu disiapkan & kegunaannya
1. Kabel UTP
Kabel utp ini menjadi bahan utama 
![](https://i.ibb.co/rp6mkyb/Whats-App-Image-2022-08-27-at-11-20-05.jpg)
2. Jack RJ-45
Jack RJ-45 konektor lan ke hub, switch, atau router.
![](https://i.ibb.co/yF44Ft3/Whats-App-Image-2022-08-27-at-11-20-08.jpg)
3. Clamping
Biasa digunakan memotong kabel utp, *clamping* (merapatkan utp dengan connector).
![](https://cf.shopee.co.id/file/e738b46e9d37d5c5c83d381b0c4e82ad)
4. Mini Rotary
Memudahkan untuk mengupas kulit kabel UTP.
![](https://i.ibb.co/mtTpdHW/Whats-App-Image-2022-08-27-at-11-20-07.jpg)
## 2.2 Pembuatan kabel tipe Straight
Berikut langkah - langkah pembuatan kabel tipe Straight:
1. Kupas kabel sekitar 3-4 cm.
2. Atur kabel hingga sesuai standar
3. Jika selesai maka masukan ke konektor dan tekan hingga tembaga terlihat dari depan
4. Setelah yakin, maka rapatkan menggunakan alat cramping
5. Untuk yang ujung ulangi langkah 1-5
## 2.3 Pembuatan kabel tipe Crossover 
Berikut langkah - langkah pembuatan kabel tipe Crossover:
1. Kupas kabel sekitar 3-4 cm.
2. Atur kabel hingga sesuai standar
3. Jika selesai maka masukan ke konektor dan tekan hingga tembaga terlihat dari depan
4. Setelah yakin, maka rapatkan menggunakan alat cramping
5. Untuk yang ujung ulangi langkah 1-5 pastikan susunan kabel **berbeda** dengan sebelumnya
# 3. Pengaksesan Kabel UTP
## 3.1 Alat Pengetesan 

Untuk alat pengetesan kabel UTP maka gunakan **LAN Tester**, digunakan untuk testing kecocokan kabel berdasarkan indikator led.

![](https://i.ibb.co/BKC8qHY/Whats-App-Image-2022-08-27-at-11-19-54.jpg)

## Cara Testing UTP
#### - Stright
1. Masukan/colokkan konektor salah satu ujung kabel UTP pada Port Tx induk tester ( yg besar ).
2. Masukan/colokkan konektor ujung kabel UTP lain pada port Rx anak tester (yg kecil).
3. LAN tester dengan menggeser saklar ke posisi auto.
Setelah kedua ujung kabel UTP dihubungkan pada LAN Tester, jika diperoleh data sebagai berikut :
Led 1 : menyala  - Led 1 : menyala
Led 2 : menyala  - Led 2 : menyala
Led 3 : menyala  - Led 3 : menyala
Led 4 : menyala  - Led 4 : menyala
Led 5 : menyala  - Led 5 : menyala
Led 6 : menyala  - Led 6 : menyala
Led 7 : menyala  - Led 7 : menyala
Led 8 : menyala  - Led 8 : menyala

#### - Crossover

1. Masukan/colokkan konektor salah satu ujung kabel UTP pada Port Tx induk tester ( yg besar ).
2. Masukan/colokkan konektor ujung kabel UTP lain pada port Rx anak tester (yg kecil).
3. LAN tester dengan menggeser saklar ke posisi auto.
Setelah kedua ujung kabel UTP dihubungkan pada LAN Tester, jika diperoleh data sebagai berikut :
Led 1 : menyala  - Led 3 : menyala
Led 2 : menyala  - Led 3 : menyala
Led 3 : menyala  - Led 1 : menyala
Led 4 : menyala  - Led 4 : menyala
Led 5 : menyala  - Led 5 : menyala
Led 6 : menyala  - Led 6 : menyala
Led 7 : menyala  - Led 7 : menyala
Led 8 : menyala  - Led 8 : menyala

Contoh pada Kabel UTP Straight
https://www.youtube.com/shorts/lnH3w2Evyqo
![](https://github.com/D4-IT-A-21/PRAKTIKUM-IT-A/blob/PKJ_CABLING/assets/testing.mp4)