# Panduan Fitur dan Halaman KawanKios

Dokumen ini menjelaskan fitur, halaman, dan fungsi utama yang tersedia dalam aplikasi KawanKios. KawanKios merupakan sistem *Point of Sale* (POS) berbasis web dengan arsitektur **single-tenant**, yang dirancang untuk mendukung operasional usaha ritel, kios, dan UMKM.

## 1. Terminal Kasir (POS)

Terminal kasir merupakan modul utama untuk memproses transaksi penjualan dengan cepat dan efisien.

- **Manajemen Shift Kasir:** Kasir perlu membuka shift sebelum mengakses terminal POS. Saat membuka shift, kasir memasukkan modal awal uang tunai di laci kasir.
- **Pencarian Produk:** Produk dapat dicari berdasarkan nama, SKU, atau menggunakan pemindai barcode jika didukung oleh perangkat dan konfigurasi aplikasi.
- **Harga Grosir (*Tiered Pricing*):** Sistem menerapkan harga grosir secara otomatis ketika jumlah pembelian memenuhi batas minimum yang ditentukan pada produk.
- **Diskon dan Pajak:** Mendukung diskon pesanan serta perhitungan pajak sesuai konfigurasi aplikasi.
- **Validasi Pembayaran:** Sistem memvalidasi nominal pembayaran sebelum transaksi diselesaikan agar pembayaran yang kurang tidak diterima sebagai transaksi lunas.
- **Tutup Shift:** Kasir memasukkan jumlah uang tunai fisik saat menutup shift. Sistem membandingkannya dengan saldo kas yang seharusnya dan menghitung selisihnya.

## 2. Dashboard dan Ringkasan

Dashboard menyajikan ringkasan operasional dan keuangan untuk pengguna yang memiliki izin akses.

- **Metrik Penjualan:** Ringkasan penjualan, laba kotor, pengeluaran, dan laba bersih berdasarkan periode yang tersedia.
- **Ringkasan Arus Kas:** Informasi mengenai pemasukan dan pengeluaran kas.
- **Valuasi Stok:** Perkiraan nilai persediaan berdasarkan harga pokok barang.
- **Peringatan Stok Minimum:** Menampilkan produk yang stoknya mencapai atau berada di bawah batas minimum.
- **Produk Terlaris:** Menampilkan produk dengan jumlah penjualan tertinggi berdasarkan data transaksi.

## 3. Manajemen Produk dan Kategori

Modul ini digunakan untuk mengelola data barang dagangan.

- **Kategori Produk:** Mengelompokkan produk agar mudah dikelola dan dicari.
- **Harga Beli dan Harga Jual:** Menyimpan informasi biaya perolehan produk dan harga jual untuk mendukung perhitungan keuntungan.
- **Harga Grosir:** Mengatur jumlah minimum pembelian dan harga grosir yang berlaku.
- **Stok dan Batas Minimum:** Memantau jumlah stok serta memberikan peringatan ketika persediaan menipis.
- **Penyesuaian Stok:** Menambah atau mengurangi stok secara manual untuk mencatat koreksi inventaris, barang rusak, atau kehilangan sesuai kewenangan pengguna.

## 4. Riwayat Transaksi dan Retur Penjualan

Modul ini digunakan untuk menelusuri transaksi yang telah dilakukan serta menangani pengembalian barang.

- **Riwayat Transaksi:** Menampilkan catatan transaksi penjualan.
- **Cetak Ulang Struk:** Memungkinkan pencetakan ulang struk transaksi jika fitur tersedia pada implementasi.
- **Invoice PDF:** Menyediakan dokumen invoice dalam format PDF jika didukung oleh konfigurasi aplikasi.
- **Retur Penjualan:** Mencatat barang yang dikembalikan pelanggan beserta nilai pengembalian dana.
- **Kondisi Barang Retur:** Barang dapat dicatat dalam kondisi baik atau rusak. Stok disesuaikan berdasarkan kondisi dan aturan retur.
- **Penyesuaian Laporan:** Nilai penjualan dan biaya pokok barang yang diretur perlu diperhitungkan dalam laporan keuangan sesuai logika transaksi yang diterapkan.

## 5. Pembelian Barang dan Pemasok

Modul ini digunakan untuk mencatat pengadaan persediaan dari pemasok atau distributor.

- **Manajemen Pemasok:** Menyimpan informasi pemasok, seperti nama, kontak, dan alamat.
- **Pencatatan Pembelian:** Mencatat barang yang dibeli, kuantitas, harga beli, dan informasi transaksi pembelian.
- **Pembaruan Stok:** Stok diperbarui berdasarkan status dan mekanisme penyelesaian pembelian yang diterapkan oleh aplikasi.

## 6. Arus Kas dan Pengeluaran Operasional

Modul keuangan ini membantu pemilik usaha mencatat pergerakan uang di luar transaksi penjualan biasa.

- **Kategori Pengeluaran:** Mengelompokkan beban operasional, misalnya listrik, gaji, transportasi, dan kebutuhan toko lainnya.
- **Pencatatan Pengeluaran:** Mencatat pengeluaran operasional beserta jumlah dan informasi terkait.
- **Buku Arus Kas:** Menyajikan catatan pemasukan dan pengeluaran secara kronologis, sesuai jenis transaksi yang dicatat oleh sistem.
- **Pengembalian Dana:** Transaksi refund akibat retur dicatat sesuai mekanisme arus kas yang diterapkan.

## 7. Laporan dan Analitik

Modul laporan membantu pemilik usaha mengevaluasi performa penjualan, persediaan, dan keuangan. Format ekspor mengikuti fitur yang tersedia pada aplikasi.

### Laporan Penjualan

- Menampilkan ringkasan penjualan berdasarkan rentang tanggal.
- Menyajikan informasi transaksi, diskon, dan pajak sesuai data yang tersedia.
- Memperhitungkan retur berdasarkan aturan pelaporan yang diterapkan.

### Laporan Laba Rugi (*Profit and Loss*)

- Menampilkan penjualan kotor dan penjualan bersih sesuai definisi perhitungan sistem.
- Menampilkan harga pokok penjualan (HPP) atau *Cost of Goods Sold* (COGS).
- Menghitung laba kotor berdasarkan penjualan bersih dikurangi HPP.
- Menghitung laba bersih setelah memperhitungkan beban operasional yang tercatat.

### Laporan Persediaan (*Stock Report*)

- Menampilkan kuantitas persediaan yang tercatat.
- Menghitung estimasi nilai persediaan berdasarkan biaya perolehan.
- Menyajikan estimasi nilai jual persediaan apabila informasi harga jual tersedia.

### Ekspor Laporan

Laporan dapat diekspor ke format PDF atau Excel apabila didukung oleh modul laporan terkait.

## 8. Pengaturan Sistem dan Manajemen Pengguna

Modul ini digunakan untuk mengatur informasi toko serta hak akses pengguna.

### Pengaturan Toko

Pengaturan yang tersedia dapat mencakup:

- Nama toko.
- Slogan atau tagline.
- Alamat toko.
- Nomor telepon.
- Pesan footer pada struk.
- Persentase pajak default.

Informasi yang ditampilkan pada struk digunakan untuk menyesuaikan identitas toko yang menjalankan KawanKios.

### Manajemen Pengguna

Sistem menggunakan pembagian peran (*role-based access control*) untuk membatasi akses berdasarkan tanggung jawab pengguna.

- **Owner:** Pemilik usaha dengan akses utama sesuai konfigurasi hak akses.
- **Admin:** Pengelola operasional dengan akses sesuai peran yang diberikan.
- **Kasir:** Pengguna yang berfokus pada transaksi penjualan dan aktivitas shift kasir.

Akses aktual terhadap produk, transaksi, laporan, pengaturan, dan data pengguna mengikuti implementasi middleware serta kebijakan otorisasi aplikasi.

### Log Aktivitas (*Activity Logs*)

Log aktivitas digunakan untuk mencatat tindakan pengguna yang didukung oleh sistem, misalnya aktivitas login, transaksi, atau perubahan data. Informasi yang dicatat dapat mencakup pengguna, tindakan, serta waktu aktivitas untuk membantu proses audit operasional.

---

## Catatan

Dokumen ini menjelaskan gambaran fitur KawanKios. Ketersediaan dan perilaku setiap fitur harus mengikuti implementasi aktual pada source code, termasuk aturan validasi, hak akses, perhitungan laporan, dan konfigurasi aplikasi.