<h1 align="center"><img src="https://www.seeklogo.net/wp-content/uploads/2011/05/drupal-logo-vector.png"></h1>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Otomatisasi](#otomatisasi) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:|:---:



# Sekilas Tentang
[`^ kembali ke atas ^`](#)

**Drupal** adalah sebuah perangkat lunak sistem manajemen konten yang bebas dan terbuka yang di distribusikan di bawah lisensi GPL, pengembangan dan perawatannya dilakukan oleh ribuan komunitas pengguna dan pengembang di seluruh dunia. Dibuat dengan bahasa pemrograman PHP, Drupal dapat dipasang pada beberapa jenis database seperti MySQL, PostgreSQL, SQLite,MariaDB dan juga MsSQL. Web server yang mendukung diantaranya Apache, Nginx, IIS yang berjalan pada sistem operasi Cross-platform seperti Microsoft Windows, Mac OS X, Linux dan FreeBSD. Drupal dapat diunduh secara bebas dan dapat digunakan secara bebas, sehingga memungkinkan setiap orang baik secara individu maupun komunitas untuk mempublikasi, mengatur, mengelola dan mengorganisir berbagai jenis dari isi/konten pada website. 



# Instalasi
[`^ kembali ke atas ^`](#)

#### Kebutuhan Sistem :
- Linux
- Windows
- Virtual box

#### Proses Instalasi :
1. Install SSH pada linux menggunakan terminal dengan cara berikut.
    ```
    $ sudo apt update
    $ sudo apt install ssh
    ```

2. Setelah terinstal SSH, kita bisa mengakses VM secara remote. Install semua kebutuhan sistem.
    ```
    $ sudo apt-get install apache2
    $ sudo apt-get install mysql-server
    $ sudo apt-get install php
    $ sudo apt-get install libapache2-mod-php
    $ sudo apt-get install php-mysql
    $ sudo apt install php-gd php-mcrypt php-mbstring php-xml php-ssh2
    $ sudo service apache2 restart
    ```

3. Cek instalasi apache. Buka laman http://localhost:8888

4. Instalasi aplikasi web Drupal. Buat database dan user untuk Drupal.
    ```
    $ mysql -u root -p -v -e "
       > CREATE DATABASE drupal;
       > CREATE USER drupal IDENTIFIED BY 'hehe';
       > GRANT ALL PRIVILEGES ON drupal.* TO drupal;"
    ```

5. Download Drupal ke direktori kita.
    ```
    $ wget "https://ftp.drupal.org/files/projects/drupal-8.5.0.tar.gz"
    ```

6. Ekstrak ke direktori web
    ```
    $ sudo tar -xzf drupal-8.5.0.tar.gz -C /var/www/html
    ```

7. Ubah kepemilikan ke user www-data (webserver)
    ```
    $ sudo chown -R www-data:www-data /var/www/html/drupal-8.5.0

8. Buka laman http://localhost:8888/drupal-8.5.0 untuk meneruskan instalasi.



# Konfigurasi
[`^ kembali ke atas ^`](#)

- Untuk menentukan konfigurasi umum, kuota upload, dan pemberitahuan, kita dapat membuka submenu **Administration** pada menu **Advanced Parameters** dan mengisi field sesuai kebutuhan. 
    
    ![choose language](https://cdn-images-1.medium.com/max/1000/1*WIsfQ6UmXieMQYB9yEim5g.jpeg)

    ![choose profile](https://cdn-images-1.medium.com/max/800/1*l-Y6N52rhrTM_V-hR1AE9A.jpeg)

- Untuk melengkapi aplikasi, kita dapat menambahkan fitur atau modul-modul tertentu pada menu `Modules`.

    ![modul](https://cdn-images-1.medium.com/max/800/1*ifdwJlSaIIfYU7hGnKcWMQ.jpeg)

- Untuk memperindah aplikasi, kita dapat mengganti tema aplikasi pada menu `Design`.

    ![design](https://cdn-images-1.medium.com/max/800/1*QBKmVlDbndLBfNAxJyeYgA.jpeg)
    ![coba](https://cdn-images-1.medium.com/max/880/1*57LPoD2qKTtH4jjjgO72Lw.jpeg)
    ![coba](https://cdn-images-1.medium.com/max/880/1*TKKkEuw1Clbx9-I31zTifQ.jpeg)



# Maintenance
[`^ kembali ke atas ^`](#)

Ketika kita ingin memodifikasi toko yang sudah terinstall, kita mungkin tidak ingin ada orang lain yang membuka aplikasi kita. Pada saat seperti itu, kita dapat mengkonfigurasi aplikasi kita untuk masuk ke dalam *maintenance mode*. Berikut ini adalah langkah-langkah yang harus kita lakukan :
1. Login ke dalam admin toko kita.
2. Klik submenu **General** pada menu **Shop Parameters**.

    ![shop](https://2.bp.blogspot.com/-jD8tqsXFEZU/WNgF9oM9htI/AAAAAAAAGkE/y5imPsRHlC8WE4FWW_4Ypt7B5qldQwGOACLcB/s1600/Screenshot_4.jpg)

3. pilih tab **Maintenance**.

    ![maintenance](https://2.bp.blogspot.com/-nP-fEgmv0Nk/WNgF9liISII/AAAAAAAAGkM/79LNJAoksb0J5dhVSqpo2Q4mZf3G4z-YwCLcB/s1600/Screenshot_5.jpg)

4. Klik tombol `on` atau `off` untuk menjalankan atau mematikan *maintenance mode*.
5. Jika kita ingin agar teman kita dapat membuka aplikasi saat sedang dalam *maintenance mode*, masukkan **IP Adress** miliknya ke dalam field **Maintenance IP**.
6. Tuliskan pesan yang ingin kita sampaikan ketika ada orang yang membuka aplikasi kita saat sedang maintenance ke dalam field **Custom Maintenance Text**
7. Klik tombol **Save** untuk menyimpan perubahan.


# Cara Pemakaian
[`^ kembali ke atas ^`](#)

Cara pemakaian **CMS Drupal** dapat dilihat dengan mengikuti langkah berikut:
1. Extract/copy file/folder CMS Drupal ke C:\xampp\htdocs\

2. Buka web browser dan masukan alamat/path folder drupal pada address bar localhost misal http://localhost/drupal7

3. Maka nanti Anda akan dihadapkan pada jendela instalasi CMS Drupal seperti berikut

    ![instalasi](https://1.bp.blogspot.com/-4A_-Vi6XAb4/Vlk4t1x54LI/AAAAAAAACQE/TSddSAJ91wc/s1600/drupal01.PNG)

4. Pilih Standard. Klik Save and Continue

5. Pada jendela Choose language. Klik Save And continue 

    ![language](https://4.bp.blogspot.com/-YL5rINMIRNQ/Vlk4tt1RJ5I/AAAAAAAACQQ/dna0getcGBE/s1600/drupal02.PNG)

6. Kemudian atur pada jendela “verify requirements” konfigurasi akses ke atabasenya. Misal nama databasenya adalah “drupal”. Untuk database sernamenya secara default adalah “root” dan Database password dikosongkan saja

    ![verify](https://2.bp.blogspot.com/-ut22AJwnxF4/Vlk4tq62ypI/AAAAAAAACQo/HjHTElPNhBk/s1600/drupal03.PNG)

7. Bila sudah selesai. Klik Save and Continue 

8. Selanjutnya tunggu sampai proses instalasi drupal selesai 

    ![install](https://4.bp.blogspot.com/--TsCmmsS1nM/Vlk4uUIrMCI/AAAAAAAACQs/QI8dzswVyw4/s1600/drupal04.PNG)

9. Pada bagian jendela “configure site” Anda mengisi kolom site name dengan nma situs Anda. Silahkan juga atur bagian site maintenance accountnya dengan mengisi username dan password sesuai keinginan Anda. Jangan upa juga sting zona waktunya. Bila sudah selesai Klik Save and continue 

    ![configure](https://2.bp.blogspot.com/-GDQuJPoi2io/Vlk4uX4qqxI/AAAAAAAACQk/PxJht1RXYhk/s1600/drupal05.PNG)
    
10. Proses instalasi selesai. Klik "Visit your new site site" untuk melihat tampilan dari website yang telah Anda buat

    ![visit](https://2.bp.blogspot.com/-WoUdhMrbZkw/Vlk4u8MfxwI/AAAAAAAACQ0/32ChhAKTT4s/s1600/drupal07.PNG)
    
11. Website telah selesai.
    ![done](https://1.bp.blogspot.com/-9O2hBWTto7I/Vlk4vMvikgI/AAAAAAAACQ4/455koz9903I/s1600/drupal08.PNG)



# Pembahasan
[`^ kembali ke atas ^`](#)

**Prestashop** ditulis dalam bahasa pemrograman `PHP` yang support untuk penggunaan MySQL. Sebagai salah satu CMS yang paling banyak digunakan di dunia, aplikasi ini menawarkan berbagai kelebihan, diantaranya :
- Aplikasi memiliki panel administrasinya mudah digunakan dan fleksibel, sehingga dapat disesuaikan dengan kebutuhan.
- Mendukung berbagai layanan pembayaran utama, seperti `PayPal`, `VISA`, `MasterCard`, dan `Maestro`.
- Diterjemahkan dalam banyak bahasa, termasuk Bahasa Indonesia.
- Memiliki desain yang *responsive*, sehingga dapat dibuka menggunakan *device* apapun.
- Memiliki lebih dari tiga ratus fitur untuk memudahkan pengguna.
- Banyak pengguna yang berkontribusi pada *discussion boards* dan sejenisnya, sehingga masalah yang dihadapi pengguna dapat cepat terselesaikan.

Tentu saja, sebuah aplikasi pasti memiliki kekurangan. Kekurangan yang dimiliki **Prestashop** antara lain :
- Penggunaan fitur atau modul yang lengkap menyebakan proses loading dari aplikasi ini menjadi sangat lambat
- Penggunaan *resource* memory aplikasi ini cukup besar, terutama ketika menggunakan fitur atau modul yang lengkap.
- Sebagian besar modul dan tema yang tersedia tidak gratis.

Jika dibandingkan dengan CMS sejenisnya seperti **Microweber**, CMS ini memiliki beberapa keunggulan dan kelemahan. Berikut adalah beberapa perbandingan antara kedua CMS ini :
- **Microweber** menyediakan proses design yang fleksibel dengan fitur *Drag and Drop* tanpa batasan, sehingga pengguna bebas mengkreasikan tampilan websitenya. Sedangkan **Prestashop** hanya menyediakan fitur design berupa penggantian template dan logo, adapun template yang tersedia tidak gratis.
- Modul atau plugin yang tersedia pada **Prestashop** jauh lebih banyak dibandingkan pada **Microweber**.
- **Prestashop** memiliki pengguna yang jauh lebih banyak daripada **Microweber** yang aktif pada forum-forum diskusi untuk membantu pengguna pemula.
- **Microweber** lebih ringan daripada **Prestashop** karena modulnya yang sedikit.
- Proses instalasi **Prestashop** lebih mudah karena berbasis PHP saja, sedangkan **Microweber** menggunakan framework laravel sehingga proses instalasi lebih sulit, terutama dalam hal *dependency*.



# Referensi
[`^ kembali ke atas ^`](#)

1. [About PrestaShop](https://www.prestashop.com/) - PrestaShop
2. [How to Log Into a VPS with PuTTY on Windows](https://www.digitalocean.com/community/tutorials/how-to-log-into-a-vps-with-putty-windows-users) - DigitalOcean
3. [How to Install PrestaShop on Ubuntu 16.04](http://idroot.net/linux/install-prestashop-ubuntu-16-04/) - idroot
4. [One Click Install PrestaShop](https://www.prestashop.com/blog/en/how-to-install-prestashop/) - PrestaShop
5. [Drupal](https://www.root93.co.id/2015/11/cara-mudah-membuat-website-menggunakan-drupal.html) - drupal
