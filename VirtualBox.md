# Latihan VirtualBox dan Sistem Operasi

## Pendahuluan
VirtualBox adalah perangkat lunak virtualisasi yang memungkinkan kita untuk menjalankan sistem operasi secara virtual di dalam komputer. Dalam latihan ini, kita akan membuat sebuah lab sederhana untuk memahami dasar-dasar sistem operasi, manajemen resource, dan konsep jaringan.

---

## Tujuan Pembelajaran
1. Memahami cara instalasi dan konfigurasi VirtualBox.
2. Belajar menginstal sistem operasi di VirtualBox.
3. Mengeksplorasi fitur-fitur sistem operasi seperti manajemen proses, sistem file, dan jaringan.

---

## Persiapan
- **Perangkat keras**: Minimal 4 GB RAM, prosesor dual-core, dan 20 GB ruang kosong di hard drive.
- **Perangkat lunak**:
  - VirtualBox: Unduh di [https://www.virtualbox.org](https://www.virtualbox.org)
  - ISO sistem operasi: Misalnya Ubuntu Server atau Windows 10.

---

## Langkah-Langkah Latihan

### 1. Instalasi VirtualBox
1. Unduh installer VirtualBox dari situs resmi.
2. Jalankan installer dan ikuti petunjuk instalasi.
3. Pastikan Anda juga menginstal "VirtualBox Extension Pack" untuk fitur tambahan seperti USB 3.0 dan RDP.

### 2. Membuat Virtual Machine
1. Buka VirtualBox dan klik tombol **New**.
2. Masukkan nama VM, misalnya `Latihan_OS`.
3. Pilih jenis dan versi sistem operasi (contoh: Linux - Ubuntu 64-bit).
4. Atur alokasi RAM (minimal 1 GB untuk Ubuntu Server).
5. Buat hard disk virtual baru (tipe **VDI**, **dynamically allocated**, dan kapasitas 20 GB).

### 3. Instalasi Sistem Operasi
1. Pilih VM yang baru dibuat dan klik **Start**.
2. Pilih file ISO sistem operasi sebagai boot disk.
3. Ikuti proses instalasi sistem operasi hingga selesai.
4. Setelah selesai, restart VM dan eject file ISO dari pengaturan storage.

### 4. Eksperimen Sistem Operasi
#### a. Manajemen Proses
- Jalankan perintah `top` atau `htop` untuk memonitor proses yang berjalan di Linux.
- Di Windows, gunakan **Task Manager**.

#### b. Sistem File
- Buat, salin, dan hapus file menggunakan terminal (Linux) atau File Explorer (Windows).
- Eksperimen dengan perintah:
  - `mkdir` untuk membuat folder.
  - `cp` untuk menyalin file.
  - `rm` untuk menghapus file.

#### c. Konfigurasi Jaringan
- Pastikan jaringan NAT diaktifkan di pengaturan VirtualBox.
- Periksa koneksi internet di dalam VM:
  - Linux: Jalankan `ping google.com`.
  - Windows: Gunakan `cmd` dan jalankan `ping google.com`.

### 5. Snapshot dan Pemulihan VM
1. Ambil snapshot VM sebelum melakukan perubahan besar.
2. Lakukan eksperimen seperti instalasi software tambahan.
3. Jika terjadi kesalahan, kembalikan VM ke snapshot sebelumnya.

---

## Tugas Tambahan
1. **Install Web Server**:
   - Linux: Instal Apache menggunakan perintah `sudo apt install apache2`.
   - Windows: Instal XAMPP.
2. **Simulasi Jaringan**:
   - Buat dua VM dan atur jaringan internal agar dapat saling berkomunikasi.
   - Gunakan perintah `ping` untuk menguji konektivitas antara kedua VM.
3. **Eksperimen Sistem File**:
   - Mount disk baru ke VM dan format disk tersebut.
   - Gunakan perintah seperti `mkfs.ext4` (Linux).

---

## Evaluasi
1. Apakah Anda berhasil menginstal sistem operasi di VirtualBox?
2. Apakah Anda dapat melakukan konfigurasi dasar sistem operasi (jaringan, sistem file)?
3. Apakah Anda berhasil mengambil dan memulihkan snapshot?

---

## Referensi
- [Panduan Resmi VirtualBox](https://www.virtualbox.org/manual/)
- [Panduan Ubuntu Server](https://ubuntu.com/download/server)
- [Dokumentasi XAMPP](https://www.apachefriends.org/index.html)

---

## Penutup
Latihan ini memberikan pemahaman dasar tentang virtualisasi dan sistem operasi. Selanjutnya eksplorasi lebih lanjut seperti instalasi Docker, Kubernetes, atau server aplikasi di VM yang sudah dibuat.
