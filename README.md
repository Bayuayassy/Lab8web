# Lab8web

Nama &nbsp; &nbsp;: Bayu Maulana Ayassy<br>
NIM&nbsp; &nbsp; &nbsp; : 312210166<br>
Kelas&ensp; &nbsp; : TI.22.A.1<br>

## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|Instruksi Praktikum|[Click Here](#instruksi-praktikum)|
|2|Langkah-langkah Praktikum|[Click Here](#langkah-langkah-praktikum)|
|3|Result|[Click Here](#result)|

## Instruksi Praktikum
1. Persiapkan text editor misalnya VSCode.
2. Buat folder baru dengan nama lab8_php_database pada docroot webserver (htdocs)
3. Ikuti langkah-langkah praktikum yang akan dijelaskan berikutnya.

## Langkah-langkah Praktikum
1. Persiapan Untuk memulai membuat aplikasi CRUD sederhana, yang perlu disiapkan adalah database server menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan melalui XAMPP.

2. Menjalankan MySQL Server Untuk menjalankan MySQL Server dari menu XAMPP Control.

3. Membuat Database: Studi Kasus Data Barang
```
CREATE DATABASE latihan1;
```
```
CREATE TABLE data_barang (
    id_barang int(10) auto_increment Primary Key,
    kategori varchar(30),
    nama varchar(30),
    gambar varchar(100),
    harga_beli decimal(10,0),
    harga_jual decimal(10,0),
    stok int(4)
);
```

![1](https://github.com/Bayuayassy/Lab8web/assets/115678251/92894b44-ee8c-4f39-931a-ea17d7fe47f5)

4. Menambah Data
```
INSERT INTO data_barang (kategori, nama, gambar, harga_beli, harga_jual, stok)
VALUES ('Elektronik', 'HP Samsung Android', 'hp_samsung.jpg', 2000000, 2400000, 5),
('Elektronik', 'HP Xiaomi Android', 'hp_xiaomi.jpg', 1000000, 1400000, 5),
('Elektronik', 'HP OPPO Android', 'hp_oppo.jpg', 1800000, 2300000, 5);
```

![2](https://github.com/Bayuayassy/Lab8web/assets/115678251/df994f74-eed1-4899-8d98-197797ba5147)

5. Membuat Program CRUD, Buat folder lab8_php_database pada root directory web server (d:\xampp\htdocs)

6. Membuat file koneksi database, Buat file baru dengan nama `koneksi.php`
```
<?php
$host = "localhost";
$user = "root";
$pass = "";
$db = "latihan1";
$conn = mysqli_connect($host, $user, $pass, $db);
if ($conn == false)
{
    echo "Koneksi ke server gagal.";
    die();
} #else echo "Koneksi berhasil";
?>
```

> Buka melalui browser untuk menguji koneksi database untuk menyampilkan pesan koneksi berhasil, ***uncomment*** pada perintah echo “koneksi berhasil”;

![3](https://github.com/Bayuayassy/Lab8web/assets/115678251/df303ad7-7950-4d08-95fb-bed21147db30)

7. Membuat file index untuk menampilkan data (Read), buat file baru dengan nama `index.php`

> **Akses File-->>**[index.php](index.php)

![4](https://github.com/Bayuayassy/Lab8web/assets/115678251/968219d9-af2d-4ff8-9701-c6106f8f60ab)

8. Menambah Data (Create), buat file baru dengan nama `tambah.php`

> **Akses File-->>**[tambah.php](tambah.php)

![5](https://github.com/Bayuayassy/Lab8web/assets/115678251/cc456951-1168-422d-8637-4ff61297bd1b)

9. Mengubah Data (Update), buat file baru dengan nama `ubah.php`

> **Akses File-->>**[ubah.php](ubah.php)

![6](https://github.com/Bayuayassy/Lab8web/assets/115678251/d7c40ad2-3370-4d10-944b-1a0cf46e2a95)

10. Menghapus Data (Delete), buat file baru dengan nama `hapus.php`
```
<?php
include_once 'koneksi.php';
$id = $_GET['id'];
$sql = "DELETE FROM data_barang WHERE id_barang = '{$id}'";
$result = mysqli_query($conn, $sql);
header('location: index.php');
>
```

https://github.com/Bayuayassy/Lab8web/assets/115678251/627139ed-48b4-46ce-ac00-afae4a8421ab

## Terima kasih
