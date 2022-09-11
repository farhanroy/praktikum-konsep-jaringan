Sebelum melakukakn Simulasi packet dari PC0 ke PC1 saya cek di **PC0**, apakah ada tersimpan Destination MAC Adreess dalam hal ini MAC dari PC1, dengan menggunakan perintah:

```
> arp -a
```

![Cek arp cache](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vbhr50c6mzi9qz6j2rf4.png)

Kemudian lakukan ping ke alamat IP dari PC1.


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tdzaksql9y8h6zcf3j1v.png)

Dari situ maka terlihat di animasi packet tracer maka akan ada surat hijau. 

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tp3ob1d3f39jf14l7lwm.png)

Surat hijau itu merupakan packet broadcast (bukan ICMP sendiri) karena pada proses enkapsulasi icmp masih belum mendapat MAC Address destanation nya. 


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/r8dw8bxap6fku7r4v9py.png)

Jika selesai mendapatkan MAC address maka akan dikembalikan ke pc0 atau yang membroadcast tadi,

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/evgxofs88ewhbb9hq9b5.png)

Jika di lihat PDU Information nya maka akan terlihat pada layer 2 (DataLink) akan terlihat physical address dari pc yang dituju, karena sebelumnya sudah melakukan broadcat ke jaringan yang se subnet.


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/q2rgshzp332o1t6b3erw.png)

Kemudian data sudah bisa didistribusikan ke IP tujuan.

## Bagaimana kalau physical address tujuan sudah tersimpan di ARP cache ?

Ini sedikit spekulatif, di beberapa laptop teman saya, walaupun sudah tersimpan. Di laptop saya sendiri tidak perlu broadcast ulang jika sudah tersimpan.


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/piqawkyy2wiwyedom35a.png)

Saya mencoba ping lagi ke alamat IP dari PC1, PC0 langsung melakukakan sending data


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/wliv1mvojfi0yrqw868a.png)

Berikut data detail status packet pada proses ping diatas


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/qxz1z8fm7pfzw1j315m6.png)

## Coba kirim data dari PC2 ke PC0

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rcjdxedtreqiflahlwtj.png)

Saya mencoba untuk mengirim data dari PC2 ke PC0. Yang terjadi adalah PC2 melakukan broadcast seperti yang terjadi pada proses pertama.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/qdigg79ctti2egdhbnc8.png)

Jika sudah mendapatkan physical address destination maka data dari ICMP bisa dikirim ke tujuan


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/obichjftzzmayq6u4e8m.png)


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/cp63ms7govk9hjbe8n00.png)











