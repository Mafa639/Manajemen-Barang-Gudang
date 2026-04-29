# 📦 Manajemen Barang Gudang

## Anggota Kelompok :
- Muhammad Azka Fadillah Abqary
- Athir Athaya Alghifari
- Virna Isnaya
[Usage](#usage)
---

## 📖 Deskripsi
Sistem Manajemen Barang Gudang adalah aplikasi berbasis **C#** dengan integrasi **database relasional** yang digunakan untuk mencatat transaksi barang masuk dan keluar secara real-time. Sistem ini mendukung **multi-user login** dengan hak akses berbeda (Admin, Staff, Supervisor) serta menyediakan laporan stok yang akurat untuk membantu pengelolaan inventaris gudang.

---

## 🎯 Tujuan
- Mencatat transaksi **barang masuk** dan **barang keluar** secara terstruktur.
- Menyediakan fitur **role-based access control** (Admin, Staff, Supervisor).
- Mengintegrasikan database dengan relasi antar tabel menggunakan **foreign key**.
- Menyediakan laporan stok akhir secara otomatis.
- Mempermudah monitoring dan pengendalian inventaris gudang.

---

## 🌟 Manfaat
- **Efisiensi kerja**: Mengurangi pencatatan manual.
- **Akurasi data**: Stok barang tercatat dengan benar.
- **Transparansi**: Setiap transaksi tercatat dengan jelas.
- **Keamanan sistem**: Hak akses berbeda mencegah penyalahgunaan.
- **Pengambilan keputusan**: Laporan stok membantu strategi distribusi dan pembelian.

---

## ⚖️ Batasan Masalah
1. Sistem hanya mencatat transaksi **barang masuk** dan **barang keluar**, tidak mencakup jual-beli langsung ke pelanggan.
2. Difokuskan pada **pengelolaan stok gudang internal**, belum terintegrasi dengan sistem eksternal.
3. Laporan terbatas pada stok akhir, riwayat transaksi, dan data pengguna.
4. Sistem berbasis **desktop/web sederhana**, belum mendukung integrasi cloud atau mobile apps.
5. Data barang hanya mencakup informasi dasar (nama, jumlah, kategori).

---

## 🗂️ Struktur Database
- **User**: Data pengguna dengan role (Admin, Staff, Supervisor).
- **Barang**: Data barang (nama, jumlah, kategori).
- **Transaksi**: Catatan barang masuk/keluar.
- **KategoriBarang**: Kategori untuk pengelompokan barang.
- **Supplier** *(opsional)*: Data pemasok barang.
- **LogAktivitas** *(opsional)*: Catatan aktivitas pengguna.

---

## ⚙️ Trigger Database
Untuk menjaga konsistensi data, sistem menggunakan beberapa **trigger** pada tabel:

1. **Trigger Update Stok Barang**
   - Aktif saat terjadi transaksi barang masuk/keluar.
   - Secara otomatis menambah/mengurangi jumlah stok di tabel **Barang**.

2. **Trigger Audit Trail**
   - Aktif saat ada perubahan data pada tabel **Barang** atau **Transaksi**.
   - Menyimpan catatan perubahan ke tabel **AuditTrail**.

3. **Trigger Validasi Transaksi**
   - Aktif saat insert transaksi baru.
   - Memastikan jumlah barang keluar tidak melebihi stok yang tersedia.

4. **Trigger Log Aktivitas**
   - Aktif saat user melakukan operasi CRUD.
   - Mencatat aktivitas ke tabel **LogAktivitas**.

---

## 🚀 Teknologi yang Digunakan
- **C# .NET** (WinForms / ASP.NET)
- **SQL Server / MySQL**
- **Entity Framework** (opsional)
- **GitHub** untuk version control
