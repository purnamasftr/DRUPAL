<h1 align="center"><img src="https://www.seeklogo.net/wp-content/uploads/2011/05/drupal-logo-vector.png"></h1>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:


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
   - Pilih Bahasa yang akan digunakan
   
     ![1](https://github.com/purnamasftr/KOMDAT-JARKOM-DRUPAL/blob/master/album1.jpg)
     
   
   - Pilih jenis profil yang ingin digunakan

      ![2](https://github.com/purnamasftr/KOMDAT-JARKOM-DRUPAL/blob/master/album2.jpg)
      

   - Lihat requirements review yang ditampilkan

      ![3](https://github.com/purnamasftr/KOMDAT-JARKOM-DRUPAL/blob/master/album3.jpg)
      

   - Atur konfigurasi database yang akan dipakai saat menggunakan drupal

      ![4](https://github.com/purnamasftr/KOMDAT-JARKOM-DRUPAL/blob/master/album4.jpg)
      

   - Lanjutkan proses instalasi
      ![5](https://github.com/purnamasftr/KOMDAT-JARKOM-DRUPAL/blob/master/album5.jpg)



# Konfigurasi
[`^ kembali ke atas ^`](#)

![adm menu](https://cdn-images-1.medium.com/max/880/1*aQY10wBwqRk-z8fD7Mx0Yg.png)

Pada halaman Drupal terdapat **Administrative Menu**, di menu tersebut kita dapat melakukan konfigurasi umum seperti : 

- Meng *edit* informasi dasar situs pada menu `Configuration`.

    ![edit](https://raw.githubusercontent.com/purnamasftr/KOMDAT-JARKOM-DRUPAL/master/10.png)

- Meng *install* atau *uninstall* sebuah module pada menu `Extends`.

    Pada menu **Extends**, ditampilkan semua module yang tersedia di situs tersebut. Install module dilakukan dengan cara mengisi *check box* terhadap module yang ingin di install. Sama halnya dengan meng-uninstall module.
    
    ![modul](https://raw.githubusercontent.com/purnamasftr/KOMDAT-JARKOM-DRUPAL/master/9.PNG)

- Mengkonfigurasi pengaturan akun *User* pada menu `Configuration`.
    
    Dilakukan dengan cari pilih menu **Configuration** di *Administrative Menu*, lalu pilih **People** - **Account Setting**.

    ![setting](https://raw.githubusercontent.com/purnamasftr/KOMDAT-JARKOM-DRUPAL/master/21.png)

- Mengubah tampilan pada menu `Appearance`.
    
    ![theme](https://raw.githubusercontent.com/purnamasftr/KOMDAT-JARKOM-DRUPAL/master/8.png)
    
    
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

Pertama-tama kita memasuki laman dengan login dengan akun **Administrator** yang sebelumnya kita buat di laman konfigurasi saat instalasi Drupal pertama kali. Jika ingin Create User, akun baru harus diverifikasi oleh Administrator dan terdaftar sebagai pengguna **Authenticated User**

Berikut adalah ragam fitur yang dapat digunakan di **CMS Drupal**:

#### Menambahkan Konten
1. Setelah login, kita dapat menambahkan konten yang nantinya akan muncul di laman utama Drupal. Fitur ini bernama **Add content** dan  terletak di kotak **Tools** di pojok kiri bawah.
2. Kita akan dialihkan ke menu utama Content. Disini kita dapat memilih tombol **Add content** untuk menambahkan konten.
3. Kita akan diminta untuk memilih jenis konten yang akan kita buat.
4. Selanjutnya, kita bisa menuliskan konten yang ingin kita buat. Sesudahnya pilih tombol **Save** untuk menyimpan konten. Jika ingin melihat tampilan konten di laman utama sebelum disimpan, kita dapat memilih tombol **Preview**. Di sebelah kanan laman ada beberapa peraturan yang dapat kita tentukan untuk konten kita.
5. Konten terunggah dan ditampilkan di laman utama Drupal.

#### Mengedit daftar pengguna (User)

Sebagai Administrator, kita dapat mengedit daftar pengguna yang terdaftar di database akun Drupal kita. 
1. Terdapat tombol **Add user** untuk menambahkan user secara manual. Kita juga dapat mencari user berdasarkan username dan email.
2. Di bawah tombol tersebut terdapat dropdown **Action**, yang merupakan daftar tindakan yang dapat kita lakukan terhadap user. Terdapat 5 opsi: 
    - **Add the Administrator role to the selected user(s)** : Kita dapat menambahkan peran sebagai Administrator untuk user yang               dipilih
    - **Block the selected user(s)** : Blokir user yang dipilih
    - **Cancel the selected user account(s)** : Membatalkan akun user yang dipilih
    - **Remove the Administrator role to the selected user(s)** : Menghapus peran Administrator dari user yg dipilih
    - **Unblock the selected user(s)** : Btalkan blokir user yang dipilih
2. Setelah memilih Action yang akan diterapkan, pilih user, lalu klik tombol **Apply to selected items**. Sebagai contoh, kita akan hapus akun user melatiapw. Pilih Action **Cancel the selected user account(s)**.
3. Dalam Action tersebut, ada beberapa opsi yang bisa kita pilih terkait pembatalan akun. Pilih opsi **Delete the account and its content** untuk menghapus akun lalu klik **Cancel accounts**
4. Akun tersebut pun terhapus dari database kita.
5. Kita juga dapat merubah data-data user yang kita pilih dengan mengklik opsi **Edit** di kolom user

#### Melihat Report
Di menu **Reports**, kita dapat melihat laporan-laporan terkait operasional website kita

#### Help
Berisi langkah-langkah penggunaan Drupal beserta overview modul-modul yang terdapat dalam Drupal

# Pembahasan
[`^ kembali ke atas ^`](#)

Drupal merupakan website CMS (Content Management Software) yang sering dipakai untuk digunakan membuat aplikasi dan website. Drupal menggunakan bahasa pemrograman PHP dan opensource dengan lisensi software GPL 2.0. Beberapa aplikasi yang menggunakan drupal dapat dilihat di tautan [ini](https://www.drupal.org/case-studies). 

Sebagai CMS yang cukup populer digunakan, tentu memiliki kelebihan. Beberapa kelebihan CMS Drupal yaitu:
- Mempunyai banyak fungsi, seperti advanced menu management, polls management, graphics modification tool, users management dll.
- Mendukung banyak tipe konten, seperti videos, polls, user management, text, blogs, podcasts, statistics, dll
- Advanced User Management: administrator dapat membuat akun user dan menentukan permission rights.
- Graphics management: Tersedia templates dan theme, dan juga dapat membuat konfigurasi halaman sendiri. 
- Page content management: Dapat mengkategorikan konten dengan alamat URL, paths, dan membuat list.
- Tersedia banyak plugins, dan dapat membuat plugins sendiri
- Tersedia documentation, boards, dan chat yang dapat membantu user mencari informasi seputar manajemen dan konfigurasi script

Namun, tetap saja aplikasi ini memiliki beberapa kekurangan, yaitu:
- Instalasi sulit dan tidak user-friendly
- Masalah kompatibilitas dengan sistem lama
- Masalah efisiensi pada website besar (big server load).

Jika dibandingkan dengan CMS sejenisnya seperti **Microweber**, CMS ini memiliki beberapa keunggulan dan kelemahan. Berikut adalah beberapa perbandingan antara kedua CMS ini :
- **Microweber** menyediakan proses design yang fleksibel dengan fitur *Drag and Drop* tanpa batasan, sehingga pengguna bebas mengkreasikan tampilan websitenya. Sedangkan **Prestashop** hanya menyediakan fitur design berupa penggantian template dan logo, adapun template yang tersedia tidak gratis.
- Modul atau plugin yang tersedia pada **Prestashop** jauh lebih banyak dibandingkan pada **Microweber**.
- **Prestashop** memiliki pengguna yang jauh lebih banyak daripada **Microweber** yang aktif pada forum-forum diskusi untuk membantu pengguna pemula.
- **Microweber** lebih ringan daripada **Prestashop** karena modulnya yang sedikit.
- Proses instalasi **Prestashop** lebih mudah karena berbasis PHP saja, sedangkan **Microweber** menggunakan framework laravel sehingga proses instalasi lebih sulit, terutama dalam hal *dependency*.



# Referensi
[`^ kembali ke atas ^`](#)

1. [Drupal](https://www.drupal.org/) - Drupal
2. [Instalasi Web Server Virtual](https://github.com/auriza/komdat-lab/blob/master/p01.md) - github
3. [Awesome Self-hosted](https://github.com/Kickball/awesome-selfhosted) - github
4. [Cara Mudah Membuat Website Menggunakan Drupal](https://www.root93.co.id/2015/11/cara-mudah-membuat-website-menggunakan-drupal.html) - root93
5. [Drupal - CMS review, advantages and disadvantages](http://whichcmstochoose.com/drupal.html) - whichcmstochoose
