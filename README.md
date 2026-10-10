# KawanKios — Aplikasi Kasir (POS) Berbasis Web

Dokumentasi resmi **KawanKios**, sistem Point of Sale (POS) berbasis web untuk pemilik usaha ritel, kios, dan toko kelontong di Indonesia.

> **KawanKios — Kawan untuk setiap usaha.**

---

## Daftar Isi

- [Tentang KawanKios](#tentang-kawankios)
- [Filosofi Nama](#filosofi-nama)
- [Fitur Utama](#fitur-utama)
- [Teknologi yang Digunakan](#teknologi-yang-digunakan)
- [Struktur Dokumentasi](#struktur-dokumentasi)
- [Lisensi](#lisensi)
- [Informasi Kontak](CONTACT.md)

---

## Tentang KawanKios

KawanKios adalah sistem *Point of Sale* (POS) berbasis web yang dirancang untuk membantu pemilik usaha ritel, kios, dan toko kelontong dalam mengelola operasional bisnis mereka. KawanKios menyediakan berbagai fitur, mulai dari transaksi kasir, manajemen shift, pengelolaan stok barang, hingga pelaporan keuangan.

---

## Filosofi Nama

Nama **KawanKios** berasal dari gagasan bahwa setiap orang yang menjalankan bisnis adalah kawan dalam perjalanan membangun dan mengembangkan usaha.

- **Kawan** — mencerminkan semangat kebersamaan.
- **Kios** — mewakili usaha dan aktivitas bisnis yang ingin didukung.

KawanKios bukan sekadar nama aplikasi kasir, melainkan representasi dari tujuan untuk menjadi teman bagi para pebisnis dalam mengelola usaha mereka dengan lebih mudah, terstruktur, dan efisien.

**KawanKios — Kawan untuk setiap usaha.**

---

## Fitur Utama

| Fitur | Deskripsi |
|-------|-----------|
| **Terminal Kasir (POS)** | Antarmuka kasir responsif dengan pencarian produk, kalkulasi transaksi otomatis, pengelolaan pajak, dan diskon pesanan. |
| **Manajemen Shift Kasir** | Pengelolaan sesi kerja kasir, mulai dari pembukaan shift dengan modal awal hingga penutupan shift dan pencatatan selisih kas. |
| **Harga Grosir (Tiered Pricing)** | Penyesuaian harga jual otomatis berdasarkan jumlah pembelian yang memenuhi ketentuan grosir. |
| **Manajemen Inventaris dan Stok** | Pemantauan stok barang, pengaturan batas minimum stok, serta perhitungan nilai persediaan berdasarkan HPP. |
| **Retur Penjualan** | Pencatatan pengembalian barang dengan penyesuaian stok dan perhitungan transaksi terkait. |
| **Manajemen Arus Kas (Cashflow)** | Pencatatan arus uang masuk dan keluar, termasuk penjualan, pengeluaran operasional, dan pengembalian dana. |
| **Laporan Keuangan dan Analitik** | Dashboard informatif serta ekspor laporan penjualan, nilai persediaan, dan laba rugi ke PDF atau Excel. |
| **Manajemen Pengguna dan Hak Akses** | Pembagian hak akses berdasarkan peran `owner`, `admin`, dan `kasir`. |

---

## Teknologi yang Digunakan

KawanKios dibangun menggunakan arsitektur aplikasi monolitik dengan antarmuka interaktif.

- **Backend:** [Laravel 12](https://laravel.com/) — framework PHP untuk logika bisnis dan pengelolaan data.
- **Frontend:** [Vue.js 3](https://vuejs.org/) — framework JavaScript untuk antarmuka pengguna yang interaktif.
- **Integrasi:** [Inertia.js](https://inertiajs.com/) — penghubung Laravel dan Vue tanpa API terpisah.
- **Styling:** [Tailwind CSS](https://tailwindcss.com/) — framework CSS untuk antarmuka yang konsisten dan responsif.
- **Database:** [MySQL](https://www.mysql.com/) — sistem basis data relasional.
- **Ekspor Laporan:** DomPDF (PDF) dan Maatwebsite Excel (Excel).

> **Catatan:** Pastikan versi framework, paket, dan teknologi yang tercantum sesuai dengan konfigurasi aktual project.

---

## Struktur Dokumentasi

Repositori ini berisi dokumentasi KawanKios dalam format Markdown:
# Project Structure

```
kawankios-dokumentasi/
├── docs/
│   ├── FEATURES.md
│   └── INSTALLATION.md
├── CONTACT.md
├── LICENSE
└── README.md
```


### Tautan Cepat

- 📦 [Panduan Instalasi](docs/INSTALLATION.md)
- ⚙️ [Penjelasan Fitur](docs/FEATURES.md)
- 📜 [Lisensi](LICENSE)

---

## Lisensi

KawanKios didistribusikan berdasarkan lisensi **proprietari** yang ditetapkan oleh pemegang hak cipta.

Penggunaan, modifikasi, dan distribusi source code harus mengikuti ketentuan yang tercantum dalam berkas [`LICENSE`](LICENSE).

---

## Kontak

- **GitHub:** [@evanCoders](https://github.com/evanCoders)
- **Repositori Dokumentasi:** [evanCoders/kawankios-dokumentasi](https://github.com/evanCoders/kawankios-dokumentasi)

---

**KawanKios — Kawan untuk setiap usaha.**