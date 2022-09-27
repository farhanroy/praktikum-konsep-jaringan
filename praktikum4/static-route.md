Routing adalah proses dimana pengiriman packet dari satu device ke device lain melalui jaringan yang berbeda. Karena itu diperlukan router karena mengirimkannya di jaringan yang berbeda.

Untuk itu, ada beberapa hal yang perlu di ketahui:
1. IP Tujuan
2.  Router-router tetangga dari mana sebuah router bisa mempelajari tentang network remote
3. Route yang mungkin ke semua network remote
4. Route terbaik untuk setiap network remote

> Router menyimpan routing table, yang bisa menemukan network remote

Routing memiliki 3 jenis:
- Static Route
- Dynamic Route
- Default Route

## Proses Routing IP

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/skoc2ccs4vfzu0v3ilkq.png)

Untuk mengubungkan **Router0** dan **Router1** maka harus membuat routing dengan cara membuat tabel routing terlebih dahulu.

## Konfigurasi Routing Pada Packet Tracer

Karena ini judulnya pake Routing Static maka kita harus set 1 per 1 IP dari masing masing device.

1. Buat desain seperti ini terlebih dahulu

![Desain Topologi Cisco Packet Tracer](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/skoc2ccs4vfzu0v3ilkq.png)

2. Set IP pada PC0 dan PC1

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ypegzu0cw1nndofj64ek.png)

![pc1](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9cwgcl88ksl5uqzqf8nm.png)

3. Kemudian set juga IP untuk Router nya juga


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xeihj68tsvtgzwwo0kvw.png)



![Router0](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/6hsy3maazr5uivvu5nhn.png)

![Router1](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/f0rxtcewsu8jwue75fl2.png)

![Router1](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0oi10xcqwgxvka5jl4rc.png)

5. Buka router 0 ambil tab CLI dan tuliskan perintah untuk membuat routing ( Routing yang dimasukan dalam konfigurasi adalah dengan keterangan indirect )

```
# ip route (dst address) 192.168.2.32 (netmask) 255.255.255.224 (gateway) 192.168.1.2
```

6.  Buka router 1 ambil tab CLI dan tuliskan perintah untuk membuat routing ( Routing yang dimasukan dalam konfigurasi adalah dengan keterangan indirect )

```
# ip route (dst address) 192.168.1.0 (netmask) 255.255.255.224 (gateway) 192.168.1.1
```

7.  Ping ke dari alamat client router pertama ke client router kedua

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1wvykzu6p32x2vn8wyyk.png)

