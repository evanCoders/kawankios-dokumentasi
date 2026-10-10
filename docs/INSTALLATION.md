# Panduan Instalasi KawanKios

Dokumen ini menjelaskan langkah-langkah instalasi dan konfigurasi KawanKios pada lingkungan lokal (localhost). Panduan deployment produksi dibahas secara terpisah.

## 1. Persyaratan Sistem

Pastikan perangkat sudah memiliki perangkat lunak berikut:

- PHP dengan versi yang kompatibel dengan project KawanKios.
- Composer.
- Node.js dan NPM dengan versi yang kompatibel dengan project.
- MySQL atau MariaDB.
- Git (opsional, jika source code diperoleh melalui repository).

Untuk lingkungan Windows, kamu dapat menggunakan XAMPP atau Laragon untuk menjalankan layanan PHP dan database.

## 2. Menyiapkan Project

Ekstrak source code KawanKios ke direktori server lokal.

Contoh direktori XAMPP:

`C:\xampp\htdocs\KawanKios`

Contoh direktori Laragon:

`C:\laragon\www\KawanKios`

Buka terminal, lalu masuk ke direktori project sesuai lokasi instalasi.

Contoh untuk XAMPP:

```bash
cd C:\xampp\htdocs\KawanKios
```

## 3. Instalasi Dependensi Backend

Jalankan perintah berikut untuk memasang dependensi PHP:

```bash
composer install
```

Tunggu hingga proses instalasi selesai. Jika muncul pesan error, periksa versi PHP, Composer, dan ekstensi PHP yang dibutuhkan oleh project.

## 4. Konfigurasi Environment

Buat file `.env` berdasarkan file contoh yang disediakan.

Linux, macOS, atau terminal yang mendukung `cp`:

```bash
cp .env.example .env
```

Windows Command Prompt:

```bat
copy .env.example .env
```

Buka file `.env`, lalu sesuaikan konfigurasi database:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=kawankios_db
DB_USERNAME=root
DB_PASSWORD=
```

Nilai di atas hanya contoh untuk lingkungan lokal. Sesuaikan nama database, username, dan password dengan konfigurasi perangkat masing-masing.

Selanjutnya, buat application key:

```bash
php artisan key:generate
```

Jangan membagikan file `.env` yang berisi kredensial atau informasi rahasia kepada pihak lain.

## 5. Menyiapkan Database

1. Jalankan layanan MySQL atau MariaDB melalui XAMPP Control Panel atau Laragon.
2. Buka phpMyAdmin atau database client yang digunakan.
3. Buat database baru, misalnya `kawankios_db`.
4. Pastikan nama database sesuai dengan konfigurasi `DB_DATABASE` di file `.env`.

### Menjalankan migrasi

Untuk instalasi baru, jalankan:

```bash
php artisan migrate --seed
```

Perintah tersebut menjalankan migrasi yang belum diterapkan dan seeder yang dikonfigurasi oleh project.

Jika memang ingin menghapus dan membangun ulang seluruh tabel, perintah berikut dapat digunakan:

```bash
php artisan migrate:fresh --seed
```

**Peringatan:** `migrate:fresh` menghapus seluruh tabel pada database yang sedang digunakan. Jangan menjalankannya pada database yang berisi data penting atau data bisnis pengguna.

## 6. Instalasi Dependensi Frontend

Pasang dependensi JavaScript menggunakan NPM:

```bash
npm install
```

Jika project menyediakan `package-lock.json` yang sesuai, `npm ci` dapat digunakan untuk instalasi yang mengikuti lockfile tersebut.

## 7. Menjalankan KawanKios

Untuk menjalankan aplikasi dalam lingkungan pengembangan, buka dua terminal pada direktori project.

**Terminal pertama — Laravel**

```bash
php artisan serve
```

Secara default, aplikasi dapat diakses melalui:

`http://127.0.0.1:8000`

**Terminal kedua — Vite**

```bash
npm run dev
```

Vite akan menjalankan server aset frontend selama proses pengembangan.

Biarkan kedua proses tetap berjalan selama aplikasi digunakan dalam mode pengembangan.

## 8. Login Awal

Jika project menyediakan akun demo melalui seeder, gunakan kredensial yang tercantum pada konfigurasi atau dokumentasi resmi project.

Pastikan email dan password yang dicantumkan sesuai dengan seeder aktual. Jika tidak tersedia akun demo, buat akun melalui mekanisme pembuatan pengguna yang disediakan aplikasi.

Setelah berhasil masuk, periksa fitur dan hak akses sesuai peran pengguna.

## 9. Troubleshooting

### Database tidak dapat terhubung

- Pastikan MySQL atau MariaDB sudah berjalan.
- Periksa `DB_HOST`, `DB_PORT`, `DB_DATABASE`, `DB_USERNAME`, dan `DB_PASSWORD` pada file `.env`.
- Pastikan database sudah dibuat dan pengguna database memiliki izin yang sesuai.

### Aset frontend tidak muncul

Dalam mode pengembangan, pastikan perintah berikut masih berjalan:

```bash
npm run dev
```

Jika menyiapkan aset untuk deployment, jalankan:

```bash
npm run build
```

Pastikan proses build berhasil dan direktori aset hasil build tersedia.

### Dependensi gagal dipasang

- Periksa versi PHP dan Node.js yang digunakan.
- Pastikan Composer dan NPM dapat dijalankan melalui terminal.
- Periksa pesan error untuk mengetahui paket atau ekstensi yang bermasalah.

### Aplikasi mengalami error setelah konfigurasi

Periksa log Laravel pada direktori `storage/logs` dan pastikan konfigurasi environment sudah benar.

## 10. Catatan Keamanan

- Jangan membagikan file `.env` yang berisi kredensial.
- Gunakan password yang kuat untuk akun dan database.
- Jangan menggunakan akun demo atau kredensial default untuk lingkungan produksi.
- Lakukan backup database secara berkala.
- Untuk deployment produksi, gunakan konfigurasi server yang sesuai dan jangan menjalankan server pengembangan Laravel atau Vite sebagai layanan produksi.

---

Untuk panduan deployment, backup dan pemulihan database, serta konfigurasi server produksi, lihat dokumentasi terkait apabila tersedia di repository KawanKios.