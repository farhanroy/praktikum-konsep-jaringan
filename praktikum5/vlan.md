## Membuat VLAN di Packet Tracer

![topologi](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/s9yry0881ujabgv0nfmy.png)

**Vlan** adalah pengelompokan LAN agar meningkatkan keamanan dan mengurangi latensi jaringan. Vlan ini diprogram menggunakan software di **Switch**.

Kemudian untuk masing-masing PC client harus di konfigurasi IP seperti dibawah ini :

* PC 0 : ip address 192.168.1.2 subnet 255.255.255.0
* PC 1 : ip address 192.168.1.3 subnet 255.255.255.0
* PC 2 : ip address 192.168.1.4 subnet 255.255.255.0
* PC 3 : ip address 192.168.1.5 subnet 255.255.255.0

![setting ip static pc0](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0jcofr1cvbyptn346xxv.png)


![setting ip static pc1](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/axr3zn1mnmsztgeiehf1.png)


![setting ip static pc2](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/zcfm8na4uul06dveg50d.png)

![setting ip static pc3](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/00gl69zzvylljx4eatk2.png)

 
Setelah di setting IP statis dari masing masing PC maka konfigurasi switch dengan menggunakan terminal.

Disini saya membuat 2 vlan dengan nama _lab1_ dan _lab2_

![Membuat vlan di switch](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/c8qo907jnyta1umlrn4i.png)

Kemudian setting juga di ethernet switch nya setiap port dengan vlan sesuai keinginan disini saya port fast ethernet 0 dan 1 di vlan 1 dan sisanya di vlan 2

![config vlan pc0](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/p6xv81lww9b7b1wnmfoc.png)

![config vlan pc1](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xioiebiwey8lha6ksga6.png)


![config vlan pc2 dan pc3](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/53u9m3kihdz5gu8pk22m.png)























