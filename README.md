
# PRAKTIKUM 8
# PHP DAN DATABASE MYSQL

## A. Identitas Mahasiswa

- **Nama:** Anggun Kusuma Wardani
- **NIM:** 312510045
- **Kelas:** I253A
- **Mata Kuliah:** Pemrograman Web
- **Dosen Pengampu:** Agung Nugroho, S.Kom., M.Kom.

## B. Tujuan Praktikum

Berdasarkan Modul Praktikum 8, tujuan dari praktikum ini adalah:

1. Mahasiswa mampu memahami konsep dasar Database.
2. Mahasiswa mampu memahami konsep dasar CRUD menggunakan PHP.
3. Mahasiswa mampu membuat program CRUD sederhana menggunakan PHP.

## C. Dasar Teori

### 1. Database

Database merupakan kumpulan data yang disimpan secara terstruktur sehingga dapat dikelola, diakses, dan diperbarui dengan mudah. Pada praktikum ini database digunakan untuk menyimpan informasi barang.

### 2. MySQL

MySQL merupakan sistem manajemen basis data yang digunakan untuk menyimpan dan mengelola data. Pada praktikum ini MySQL digunakan untuk membuat database `latihan1` dan tabel `data_barang`.

### 3. PHP

PHP merupakan bahasa pemrograman sisi server yang digunakan untuk membuat halaman web dinamis. Dalam praktikum ini PHP digunakan untuk menghubungkan aplikasi dengan database dan mengelola data barang.

### 4. CRUD

CRUD merupakan empat operasi utama dalam pengelolaan data, yaitu:

- **Create:** Menambahkan data baru.
- **Read:** Menampilkan data dari database.
- **Update:** Mengubah data yang sudah tersimpan.
- **Delete:** Menghapus data dari database.

### 5. MySQLi

MySQLi merupakan ekstensi PHP yang digunakan untuk menghubungkan dan menjalankan perintah pada database MySQL. Pada praktikum ini MySQLi digunakan melalui fungsi seperti `mysqli_connect()`, `mysqli_query()`, dan `mysqli_fetch_array()`.

## D. Perangkat yang Digunakan

1. Laptop atau komputer.
2. Visual Studio Code sebagai text editor.
3. XAMPP sebagai web server dan database server.
4. MySQL sebagai sistem pengelola database.
5. phpMyAdmin untuk mengelola database.
6. Browser untuk menjalankan dan menguji aplikasi.
7. Git dan GitHub untuk menyimpan hasil praktikum.

## E. Struktur Folder

```text
lab8_php_database/
│
├── koneksi.php
├── index.php
├── tambah.php
├── ubah.php
├── hapus.php
├── style.css
│
├── gambar/
│   ├── hp_oppo.png
│   ├── hp_samsung.png
│   └── hp_xiaomi.png
│
├── Screenshot/
│   ├── 01.png
│   ├── 02.png
│   ├── 03.png
│   ├── 04.png
│   ├── 05.png
│   ├── 06.png
│   ├── 07.png
│   ├── 08.png
│   ├── 09.1.png
│   ├── 09.2.png
│   ├── 10.1.png
│   └── 10.2.png
│
└── README.md
```

## F. Langkah Kerja Praktikum

### 1. Persiapan XAMPP

Menjalankan aplikasi XAMPP, kemudian mengaktifkan Apache dan MySQL agar web server dan database server dapat digunakan.

### 2. Membuat Database

Membuka phpMyAdmin melalui browser dengan alamat:

`http://localhost/phpmyadmin/`

Kemudian membuat database dengan nama `latihan1`.

```sql
CREATE DATABASE latihan1;
```

### 3. Membuat Tabel Data Barang

Setelah database dibuat, selanjutnya membuat tabel `data_barang` dengan struktur berikut:

```sql
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

### 4. Menambahkan Data Awal

Memasukkan tiga data barang ke dalam tabel `data_barang`.

```sql
INSERT INTO data_barang
(kategori, nama, gambar, harga_beli, harga_jual, stok)
VALUES
('Elektronik', 'HP Samsung Android', 'hp_samsung.jpg', 2000000, 2400000, 5),
('Elektronik', 'HP Xiaomi Android', 'hp_xiaomi.jpg', 1000000, 1400000, 5),
('Elektronik', 'HP OPPO Android', 'hp_oppo.jpg', 1800000, 2300000, 5);
```

### 5. Membuat Folder Program

Membuat folder `lab8_php_database` di dalam direktori `htdocs` XAMPP. Folder ini digunakan untuk menyimpan seluruh file program PHP.

Program dapat diakses melalui:

`http://localhost/lab8_php_database/`

### 6. Membuat Koneksi Database (koneksi.php)

Membuat file `koneksi.php` untuk menghubungkan program PHP dengan database `latihan1`.

Koneksi dilakukan menggunakan fungsi `mysqli_connect()` dengan informasi host, username, password, dan nama database.

### 7. Menampilkan Data (Read)

Membuat file `index.php` untuk menampilkan data barang yang tersimpan di dalam database.

Perintah SQL yang digunakan:

```php
$sql = 'SELECT * FROM data_barang';
$result = mysqli_query($conn, $sql);
```

Data ditampilkan dalam bentuk tabel yang berisi gambar, nama barang, kategori, harga jual, harga beli, stok, dan aksi.

### 8. Menambahkan Data (Create)

Membuat file `tambah.php` untuk menambahkan barang baru ke dalam database.

Form tambah barang terdiri dari:
- Nama Barang
- Kategori
- Harga Jual
- Harga Beli
- Stok
- File Gambar

Data yang dimasukkan kemudian disimpan menggunakan perintah SQL `INSERT INTO`.

### 9. Mengubah Data (Update)

Membuat file `ubah.php` untuk mengubah informasi barang yang sudah tersimpan.

Data barang dipilih berdasarkan `id_barang`, kemudian ditampilkan kembali pada form agar dapat diperbarui.

Perintah SQL yang digunakan adalah `UPDATE`.

### 10. Menghapus Data (Delete)

Membuat file `hapus.php` untuk menghapus data barang berdasarkan `id_barang`.

Perintah SQL yang digunakan:

```php
DELETE FROM data_barang WHERE id_barang = '{$id}';
```

Setelah proses penghapusan selesai, halaman diarahkan kembali ke `index.php`.

## G. Latihan Praktikum

Latihan dikerjakan sesuai urutan langkah pada Modul Praktikum 8.

1. Menyiapkan XAMPP dan menjalankan MySQL Server.
2. Mengakses phpMyAdmin.
3. Membuat database `latihan1`.
4. Membuat tabel `data_barang`.
5. Memasukkan tiga data awal barang.
6. Membuat folder `lab8_php_database` pada direktori `htdocs`.
7. Membuat file `koneksi.php` untuk menghubungkan PHP dengan database.
8. Membuat file `index.php` untuk menampilkan data barang.
9. Membuat file `tambah.php` untuk menambahkan data barang.
10. Membuat file `ubah.php` untuk mengubah data barang.
11. Membuat file `hapus.php` untuk menghapus data barang.
12. Menguji seluruh fungsi CRUD melalui browser.

## H. Hasil Praktikum

Berdasarkan latihan yang telah dikerjakan, program pengelolaan data barang memiliki empat fungsi utama:

- **Create:** Program dapat menambahkan data barang baru.
- **Read:** Program dapat menampilkan data barang dari database.
- **Update:** Program dapat mengubah informasi barang.
- **Delete:** Program dapat menghapus data barang.

Dengan demikian, program CRUD sederhana menggunakan PHP dan database MySQL dapat dijalankan melalui web server XAMPP.

#### I. DOKUMENTASI SCREENSHOT HASIL PRAKTIKUM

Dokumentasi berikut merupakan hasil pengerjaan Praktikum 8 mengenai PHP dan Database MySQL. Setiap screenshot menunjukkan proses pengerjaan mulai dari pembuatan database, pembuatan tabel, pengisian data barang, hingga penerapan fungsi CRUD (Create, Read, Update, Delete) menggunakan PHP. Seluruh program dijalankan melalui server lokal XAMPP dan ditampilkan menggunakan browser.

### 1. Latihan 1 – Membuat Database

Pada latihan pertama dilakukan pembuatan database menggunakan phpMyAdmin. Database dibuat dengan nama `latihan1` yang nantinya digunakan sebagai tempat penyimpanan seluruh data barang dalam aplikasi.

**Hasil yang Diperoleh:**

Database `latihan1` berhasil dibuat dan muncul pada daftar database di phpMyAdmin. Database tersebut siap digunakan untuk membuat tabel dan menyimpan informasi barang.

**Screenshot Hasil:**

![01](Screenshot/01.png)

### 2. Latihan 2 – Membuat Tabel Data Barang

Pada latihan kedua dilakukan pembuatan tabel dengan nama `data_barang` di dalam database `latihan1`. Tabel ini memiliki beberapa kolom, yaitu `id_barang`, `kategori`, `nama`, `gambar`, `harga_beli`, `harga_jual`, dan `stok`. Kolom `id_barang` digunakan sebagai primary key dengan fitur auto increment.

**Hasil yang Diperoleh:**

Tabel `data_barang` berhasil dibuat dengan struktur kolom sesuai instruksi modul. Setiap kolom telah disiapkan untuk menyimpan informasi barang yang akan dikelola melalui aplikasi.

**Screenshot Hasil:**

![02](Screenshot/02.png)

### 3. Latihan 3 – Menambahkan Data Awal

Pada latihan ketiga dilakukan pengisian data awal ke dalam tabel `data_barang` menggunakan perintah SQL `INSERT INTO`. Data yang dimasukkan terdiri dari tiga produk elektronik, yaitu HP Samsung Android, HP Xiaomi Android, dan HP OPPO Android.

**Hasil yang Diperoleh:**

Ketiga data barang berhasil dimasukkan ke dalam database. Data tersebut tersimpan dengan informasi kategori, nama barang, gambar, harga beli, harga jual, dan stok sesuai dengan nilai yang telah ditentukan pada perintah SQL.

**Screenshot Hasil:**

![03](Screenshot/03.png)
![04](Screenshot/04.png)

### 4. Latihan 4 – Membuat Koneksi Database

Pada latihan keempat dibuat file `koneksi.php` yang berfungsi menghubungkan program PHP dengan database MySQL. Koneksi dilakukan menggunakan fungsi `mysqli_connect()` dengan konfigurasi host `localhost`, username `root`, password kosong, dan nama database `latihan1`.

**Hasil yang Diperoleh:**

File `koneksi.php` berhasil dibuat dan digunakan sebagai penghubung antara aplikasi PHP dengan database MySQL. Dengan adanya koneksi tersebut, program dapat mengakses database untuk menjalankan proses pengambilan maupun pengelolaan data barang.

**Screenshot Hasil:**

![05](Screenshot/05.png)

### 5. Latihan 5 – Menampilkan Data Barang (Read)

Pada latihan kelima dibuat file `index.php` untuk menampilkan seluruh data barang yang tersimpan di dalam database. Data diambil menggunakan perintah SQL `SELECT * FROM data_barang`, kemudian ditampilkan dalam bentuk tabel pada halaman browser.

**Hasil yang Diperoleh:**

Halaman utama berhasil menampilkan daftar barang yang sebelumnya telah dimasukkan ke dalam database. Tabel menampilkan informasi gambar, nama barang, kategori, harga jual, harga beli, stok, serta bagian aksi untuk pengelolaan data.

**Screenshot Hasil:**

![06](Screenshot/06.png)

### 6. Latihan 6 – Menambahkan Data Barang (Create)

Pada latihan keenam dibuat file `tambah.php` yang digunakan untuk menambahkan data barang baru. Halaman ini menyediakan formulir yang terdiri dari nama barang, kategori, harga jual, harga beli, stok, dan file gambar. Data yang dimasukkan akan diproses menggunakan metode POST dan disimpan ke dalam database melalui perintah SQL `INSERT INTO`.

**Hasil yang Diperoleh:**

Formulir tambah barang berhasil ditampilkan melalui browser. Seluruh kolom input tersedia sehingga pengguna dapat mengisi informasi barang baru sebelum menyimpannya ke dalam database.

**Screenshot Hasil:**

![07](Screenshot/07.png)

### 7. Latihan 7 – Hasil Penambahan Data Barang

Setelah formulir tambah barang diisi, pengguna dapat menekan tombol Simpan untuk memproses data. Program kemudian menjalankan perintah SQL `INSERT INTO` untuk memasukkan informasi barang baru ke dalam tabel `data_barang`.

**Hasil yang Diperoleh:**

Data barang yang baru dimasukkan berhasil tersimpan di dalam database dan ditampilkan pada halaman utama. Hal ini menunjukkan bahwa fungsi Create telah berhasil diterapkan sehingga pengguna dapat menambahkan data barang melalui aplikasi.

**Screenshot Hasil:**

![08](Screenshot/08.png)

### 8. Latihan 8 – Mengubah Data Barang (Update)

Pada latihan kedelapan dibuat file `ubah.php` yang berfungsi untuk memperbarui informasi barang yang sudah tersimpan. Data barang dipanggil berdasarkan `id_barang`, kemudian informasi sebelumnya ditampilkan kembali pada formulir agar pengguna dapat mengubah data sesuai kebutuhan.

**Hasil yang Diperoleh:**

Formulir ubah barang berhasil ditampilkan dengan informasi sesuai data barang yang dipilih. Pengguna dapat memperbarui nama barang, kategori, harga jual, harga beli, stok, maupun gambar barang.

**Screenshot Hasil:**

![09](Screenshot/09.1.png)

### 9. Latihan 9 – Hasil Perubahan Data Barang

Setelah informasi barang diperbarui, pengguna dapat menekan tombol Simpan untuk menyimpan perubahan. Program menjalankan perintah SQL `UPDATE` berdasarkan ID barang yang dipilih sehingga informasi lama dapat diperbarui dengan informasi terbaru.

**Hasil yang Diperoleh:**

Perubahan data barang berhasil disimpan ke dalam database. Informasi pada halaman utama telah menampilkan data terbaru sesuai dengan perubahan yang dilakukan melalui formulir ubah barang.

**Screenshot Hasil:**

![09.2](Screenshot/09.2.png)

### 10. Latihan 10 – Menghapus Data Barang (Delete)

Pada latihan kesepuluh dibuat file `hapus.php` yang digunakan untuk menghapus data barang berdasarkan `id_barang`. Ketika pengguna memilih aksi Hapus pada halaman utama, program akan menjalankan perintah SQL `DELETE` untuk menghapus data yang dipilih dari database.

**Hasil yang Diperoleh:**

Fungsi penghapusan data berhasil diterapkan melalui halaman utama. Program dapat menerima ID barang yang dipilih dan menjalankan proses penghapusan terhadap data tersebut.

**Screenshot Hasil:**

![10.1](Screenshot/10.1.png)

### 11. Latihan 11 – Hasil Penghapusan Data Barang

Setelah proses penghapusan dilakukan, program akan mengarahkan pengguna kembali ke halaman utama. Data barang yang telah dipilih untuk dihapus tidak lagi ditampilkan pada daftar barang karena sudah dihapus dari database.

**Hasil yang Diperoleh:**

Data barang berhasil dihapus dari database dan tidak muncul lagi pada tabel halaman utama. Dengan demikian, fungsi Delete telah berhasil diterapkan dalam program pengelolaan data barang.

**Screenshot Hasil:**

![10.2](Screenshot/10.2.png)
## J. Kesimpulan

Berdasarkan Praktikum 8 tentang PHP dan Database MySQL, dapat disimpulkan bahwa database memiliki peran penting dalam penyimpanan dan pengelolaan data pada aplikasi web. Melalui praktikum ini, mahasiswa mempelajari cara membuat database, membuat tabel, memasukkan data, serta menghubungkan PHP dengan MySQL menggunakan MySQLi.

Selain itu, praktikum ini memberikan pemahaman mengenai penerapan konsep CRUD yang terdiri dari Create, Read, Update, dan Delete. Keempat fungsi tersebut diterapkan dalam program pengelolaan data barang menggunakan file PHP yang berbeda.

Dengan menyelesaikan praktikum ini, mahasiswa diharapkan mampu membuat program CRUD sederhana menggunakan PHP dan database MySQL.
=======
# Lab8Web
>>>>>>> 405bb9aea92bdb698002a91f01c3c33d04c6eedf
