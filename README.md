# Perpustakaan MPPL

Repository ini berisi database untuk keperluan tugas akhir Manajemen Proyek Perangkat Lunak. Database ini dirancang untuk sistem perpustakaan sederhana yang mendukung pengelolaan data pengguna, buku, dan aktivitas membaca.

## Deskripsi Proyek

Database ini bertujuan untuk:
- Menyimpan data akun pengguna.
- Mengelola informasi buku yang tersedia.
- Melacak aktivitas membaca pengguna.

## Prasyarat

Sebelum menggunakan database ini, pastikan Anda memiliki:
- **XAMPP**: Untuk menjalankan server Apache dan MySQL.
- **phpMyAdmin**: Untuk mengelola database dengan antarmuka grafis (biasanya sudah termasuk dalam XAMPP).

## Cara Instalasi

1. **Unduh dan Instal XAMPP**
   - Unduh XAMPP dari [https://www.apachefriends.org/index.html](https://www.apachefriends.org/index.html).
   - Instal dan jalankan Apache serta MySQL melalui XAMPP Control Panel.

2. **Impor Database**
   - Buka phpMyAdmin di browser Anda melalui `http://localhost/phpmyadmin`.
   - Klik tab **Database** dan buat database baru dengan nama `perpustakaan_mppl`.
   - Pilih database tersebut, lalu klik tab **Import**.
   - Unggah file `perpustakaan_mppl.sql` dari repository ini.
   - Klik **Go** untuk menyelesaikan proses impor.

## Struktur Database

### Tabel `akun`
- **id_akun**: ID unik untuk setiap akun.
- **username**: Nama pengguna.
- **password**: Kata sandi pengguna.
- **role**: Peran pengguna (misalnya, admin atau anggota).

### Tabel `baca`
- **id_baca**: ID unik untuk aktivitas membaca.
- **total_selesai**: Total buku yang selesai dibaca.
- **genre_fav**: Genre favorit pengguna.
- **tgl_selesai_baca**: Tanggal selesai membaca.
- **id_buku**: ID buku yang dibaca.

### Tabel `buku`
- **id_buku**: ID unik untuk setiap buku.
- **judul**: Judul buku.
- **penulis**: Penulis buku.
- **deskripsi**: Deskripsi buku.
- **urlFoto**: URL foto sampul buku.
- **total_baca**: Total kali buku dibaca.
- **rate_baca**: Rating dari pembaca.
- **id_rak**: ID rak tempat buku disimpan.

### Tabel `pinjaman_buku`
- **id_pinjam**: ID unik untuk transaksi peminjaman.
- **tgl_pinjam**: Tanggal peminjaman buku.
- **tgl_kembali**: Tanggal pengembalian buku.
- **status**: Status peminjaman (misalnya, "dipinjam" atau "dikembalikan").
- **id_user**: ID pengguna yang meminjam buku.
- **id_buku**: ID buku yang dipinjam.

### Tabel `tabel`
- **id_rak**: ID unik untuk setiap rak.
- **posisi**: Lokasi atau posisi rak di perpustakaan.

### Tabel `user`
- **id_user**: ID unik untuk setiap pengguna.
- **nama**: Nama lengkap pengguna.
- **foto_profile**: URL foto profil pengguna.
- **id_baca**: ID aktivitas membaca yang terkait dengan pengguna.
- **id_akun**: ID akun pengguna.

## Penggunaan

Setelah database berhasil diimpor, Anda dapat:
1. Menghubungkan aplikasi Anda ke database menggunakan kredensial berikut:
   - **Host**: `localhost`
   - **User**: `root`
   - **Password**: *(kosongkan jika default)*
   - **Database**: `perpustakaan_mppl`

2. Menjalankan query SQL untuk mengelola data.
   Contoh:
   ```sql
   SELECT * FROM akun;
   ```

3. Mengintegrasikan database ini dengan aplikasi berbasis web atau desktop untuk sistem perpustakaan.

## Catatan

- Pastikan server MySQL berjalan sebelum mengakses database.
- Ubah kredensial default MySQL jika diperlukan untuk keamanan.

---

Jika ada pertanyaan atau masalah, silakan hubungi
