## Color rule di Wireshark
Color rule ini merupakan aturan pemberian warna pada list yang ada di software Wireshark untuk memudahkan dalam mengidentifikasi jenis paket berdasarkan kode warna. adapun ada banyak kode warna kode warna yang mewakili jenis packet tertentu. Berikut klasifikasi kode warna nya:

| Warna      | Jenis Paket |
| ----------- | ----------- |
| Ungu Muda      | TCP       |
| Biru Muda   | UDP        |
| Hitam   | Paket dengan kesalahan        |
| Hijau Muda   | Trafic HTTP        |
| Kuning Muda   | Lalu lintas khusus Windows, termasuk Server Message Blocks (SMB) dan NetBIOS       |
| Kuning Gelap   | Rute        |
| Abu-abu Gelap   | TCP SYN, FIN dan ACK lalu lintas        |

![](https://i.ibb.co/rHzSS7B/Screenshot-2022-09-01-161125.png)

## Penjelasan masing masing packet
### TCP
![](https://i.ibb.co/kSLB4GZ/Screenshot-2022-09-01-172839.png)

|     |     |     |
| --- | --- | --- |
| Nama field | Ukuran | Keterangan |
| Source Port | 2 byte (16 bit) | Mengindikasikan sumber protokol lapisan aplikasi yang mengirimkan segmen TCP yang bersangkutan. Gabungan antara \_field\_ \*\*Source IP Address\*\* dalam \_header IP\_ dan \_field\_ \*\*Source Port\*\* dalam \_field\_ \_header TCP\_ disebut juga sebagai \*\*\_socket\_ sumber\*\*, yang berarti sebuah alamat global dari mana segmen dikirimkan. Lihat juga port TCP. |
| Destination Port | 2 byte (16 bit) | Mengindikasikan tujuan protokol lapisan aplikasi yang menerima segmen TCP yang bersangkutan. Gabungan antara field Destination IP Address dalam header IP dan field Destination Port dalam field header TCP disebut juga sebagai \*\*\_socket\_ tujuan\*\*, yang berarti sebuah alamat global ke mana segmen akan dikirimkan. |
| Sequence Number | 4 byte (32 bit) | Mengindikasikan nomor urut dari oktet pertama dari data di dalam sebuah segmen TCP yang hendak dikirimkan. Field ini harus selalu diset, meskipun tidak ada data (payload) dalam segmen. Ketika memulai sebuah sesi koneksi TCP, segmen dengan flag SYN (Synchronization) diset ke nilai 1, field ini akan berisi nilai Initial Sequence Number (ISN). Hal ini berarti, oktet pertama dalam aliran byte (byte stream) dalam koneksi adalah ISN+1. |
| Acknowledgment Number | 4 byte (32 bit) | Mengindikasikan nomor urut dari oktet selanjutnya dalam aliran byte yang diharapkan oleh untuk diterima oleh pengirim dari si penerima pada pengiriman selanjutnya. Acknowledgment number sangat dipentingkan bagi segmen-segmen TCP dengan flag ACK diset ke nilai 1. |
| Data Offset | 4 bit | Mengindikasikan di mana data dalam segmen TCP dimulai. Field ini juga dapat berarti ukuran dari header TCP. Seperti halnya field \*\*Header Length\*\* dalam header IP, field ini merupakan angka dari word 32-bit dalam header TCP. Untuk sebuah segmen TCP terkecil (di mana tidak ada opsi TCP tambahan), field ini diatur ke nilai 0x5, yang berarti data dalam segmen TCP dimulai dari oktet ke 20 dilihat dari permulaan segmen TCP. Jika field Data Offset diset ke nilai maksimumnya (24=16) yakni 15, header TCP dengan ukuran terbesar dapat memiliki panjang hingga 60 byte. |
| Reserved | 6 bit | Direservasikan untuk digunakan pada masa depan. Pengirim segmen TCP akan mengeset bit-bit ini ke dalam nilai 0. |
| Flags | 6 bit | Mengindikasikan flag-flag TCP yang memang ada enam jumlahnya, yang terdiri atas: URG (Urgent), ACK (Acknowledgment), PSH (Push), RST (Reset), SYN (Synchronize), dan FIN (Finish). |
| Window | 2 byte (16 bit) | Mengindikasikan jumlah byte yang tersedia yang dimiliki oleh buffer host penerima segmen yang bersangkutan. Buffer ini disebut sebagai Receive Buffer, digunakan untuk menyimpan byte stream yang datang. Dengan mengimbuhkan ukuran window ke setiap segmen, penerima segmen TCP memberitahukan kepada pengirim segmen berapa banyak data yang dapat dikirimkan dan disangga dengan sukses. Hal ini dilakukan agar si pengirim segmen tidak mengirimkan data lebih banyak dibandingkan ukuran Receive Buffer. Jika tidak ada tempat lagi di dalam Receive buffer, nilai dari field ini adalah 0\\. Dengan nilai 0, maka si pengirim tidak akan dapat mengirimkan segmen lagi ke penerima hingga nilai field ini berubah (bukan 0). Tujuan hal ini adalah untuk mengatur lalu lintas data atau \_flow control\_. |
| Checksum | 2 byte (16 bit) | Mampu melakukan pengecekan integritas segmen TCP (\_header\_-nya dan \_payload\_-nya). Nilai field Checksum akan diatur ke nilai 0 selama proses kalkulasi checksum. |
| Urgent Pointer | 2 byte (16 bit) | Menandakan lokasi data yang dianggap “urgent” dalam segmen. |
| Options | 4 byte (32 bit) | Berfungsi sebagai penampung beberapa opsi tambahan TCP. Setiap opsi TCP akan memakan ruangan 32 bit, sehingga ukuran header TCP dapat diindikasikan dengan menggunakan field Data offset. |

### ICMP
![](https://i.ibb.co/SmYfmLq/Screenshot-2022-09-01-172918.png)
1. Version (4 bit). Menunjukkan format dari internet header. Versi saat ini sebagaimana dijelaskan pada RFC 791 adalah versi 4.
2. Internet header length (IHL: 4 bit). Menjelaskan panjang dari header menggunakan 32-bit word. Ukuran minimum header yang diijinkan adalah 5 word.
3. Type of service / jenis servis (8 bit). Data pada field ini menunjukkan kualitas layanan yang diinginkan.
4. Total Length/panjang keseluruhan (16 bit). Panjang keseluruhan ICMP dalam oktet, termasuk header dan data IP. Field ini memungkinkan datagram berisi sampai 66535 oktet. Standar yang ada menganjurkan tiap host bersiap siap untuk menerima datagram dengan panjang paling tidak 576 oktet.
5. Identification (16 bit). Field identifikasi digunakan untuk membantu proses penggabungan kembali pecahan-pecahan dari sebuah datagram.
6. Flag (3 bit). Field ini berisi tiga control flag.
7. Bit 0. Dicadangkan , harus 0.
8. Bit 1 (DF). 0 = bisa dipecah menjadi fragmen; 1 = tidak boleh dipecah
9. Bit 2 (MF). 0 = fragmen terakhir; 1 = masih ada fragmen lagi.
10. Bila sebuah datagram dipecah, MF bit untuk tiap fragmen kecuali yang terakhir bernilai 1.
11. Fragment Offset / posisi fragmen (13 bit). Untuk datagram yang dipecah, menunjukkan posisi fragmen ini dalam datagram.
12. Time To Live / waktu hidup (8 bit). Menunjukkan waktu maksimum bagi sebuah datagram untuk berada dalam suatu jaringan. Bila field ini memberi nilai 0, datagram akan dibuang. Field ini di modifikasi selama tahap pemrosesan header IP dan umum nya dihitung dalam detik. Namun tiap modul IP yang menangani datagram harus mengurangi Time To Live ini dengan 1. mekanisme ini memastikan bahwa datagram yang tak terkirim suatu saat akan dibuang.
13. Protokol (8 bit). Protokol lapisan atas yang berhubungan dengan bagian data dari datagram.
14. Header checksum (16 bit) Sebuah nilai checksum untuk header saja. Nilai ini harus dihitung ulang tiap kali header dimodifikasi.
15. Source Address (32 bit). Alamat IP dari host yang mengirimkan datagram.
16. Destination Address (32 bit). Alamat IP dari host yang merupakan tujuan akhir datagram.
17. Option (0 sampai 11 32-bit word). Dapat berisi 0 atau lebih pilihan.

### Ethernet II
![](https://i.ibb.co/Jy49hjc/Screenshot-2022-09-01-173003.png)
* Prembule – Bingkai Ethernet dimulai dengan Pembukaan 7-Bytes. Ini adalah pola alternatif 0 dan 1 yang menunjukkan awal dari frame dan memungkinkan pengirim dan penerima untuk membuat sinkronisasi bit. Awalnya, PRE (Pembukaan) diperkenalkan untuk memungkinkan hilangnya beberapa bit karena penundaan sinyal. Tetapi Ethernet berkecepatan tinggi saat ini tidak memerlukan Pembukaan untuk melindungi bit frame.
PRE (Pembukaan) menunjukkan penerima bahwa frame akan datang dan memungkinkan penerima untuk mengunci ke aliran data sebelum frame yang sebenarnya dimulai.
* Start of frame delimiter (SFD) – Ini adalah bidang 1-Byte yang selalu disetel ke 10101011. SFD menunjukkan bahwa bit yang akan datang memulai dari frame, yang merupakan alamat tujuan. Terkadang SFD dianggap sebagai bagian dari PRE, inilah alasan Pembukaan digambarkan sebagai 8 Bytes di banyak tempat. SFD memperingatkan stasiun atau stasiun bahwa ini adalah kesempatan terakhir untuk sinkronisasi.
* Destination Address – Ini adalah bidang 6-Byte yang berisi alamat MAC mesin tempat data ditujukan.
* Source Address – Ini adalah bidang 6-Byte yang berisi alamat MAC mesin sumber. Karena Alamat Sumber selalu merupakan alamat individu (Unicast), bit paling tidak signifikan dari byte pertama selalu 0.
Panjang – Panjang adalah bidang 2-Byte, yang menunjukkan panjang seluruh bingkai Ethernet. Bidang 16-bit ini dapat menampung nilai panjang antara 0 hingga 65534, tetapi panjangnya tidak boleh lebih besar dari 1500 karena beberapa keterbatasan Ethernet sendiri.
* Data – Ini adalah tempat di mana data aktual dimasukkan, juga dikenal sebagai Payload . Baik header IP dan data akan disisipkan di sini jika Internet Protocol digunakan melalui Ethernet. Data maksimum yang ada mungkin selama 1500 Bytes. Jika panjang data kurang dari panjang minimum yaitu 46 byte, maka padding 0 ditambahkan untuk memenuhi panjang minimum yang mungkin.
* Cyclic Redundancy Check (CRC) – CRC adalah bidang 4 Byte. Bidang ini berisi kode hash data 32-bit, yang dihasilkan melalui bidang Alamat Tujuan, Alamat Sumber, Panjang, dan Data. Jika checksum yang dihitung oleh tujuan tidak sama dengan nilai checksum yang dikirim, data yang diterima rusak.