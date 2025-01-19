# **Tantangan Sistem Operasi - File Server dengan Node.js**

## **Deskripsi Umum**
Mahasiswa diminta untuk memodifikasi kode file server berbasis Node.js agar memiliki fitur tambahan tertentu. Fitur yang dimodifikasi akan berbeda untuk setiap mahasiswa, berdasarkan **NIM**.

Kode awal diberikan di bawah ini, dan mahasiswa harus mengikuti petunjuk sesuai dengan aturan penugasan berdasarkan **NIM** mereka.

---

## **Langkah-Langkah Penugasan**

1. **Gunakan kode awal berikut ini:**
   > [Link Source Code Awal](https://github.com/Muhammad-Ikhwan-Fathulloh/VaultSync)

3. **Petunjuk Modifikasi:**
   - Gunakan dua digit terakhir **NIM** Anda (`XX`) untuk menentukan tantangan spesifik yang harus Anda kerjakan.
   - Lihat daftar tantangan berdasarkan digit NIM di bawah ini.

4. **Hasil Akhir:**
   - File yang dimodifikasi harus mencakup:
     1. Kode sumber dengan fitur tambahan yang berfungsi.
     2. Dokumentasi singkat dalam file `README.md` yang menjelaskan fitur tambahan Anda.

5. **Pengumpulan:**
   - Kompres proyek Anda dalam format ZIP.
   - Beri nama file Anda dengan format: `UAS_<Nama>_<NIM>.zip`.
   - Upload ke sistem LMS atau email sesuai instruksi dosen.

---

## **Tantangan Berdasarkan NIM**

- **Jika dua digit terakhir NIM Anda (`XX`) adalah angka ganjil:**
  1. Tambahkan **fungsi rename file**:
     - Buat endpoint **`POST /rename`** yang menerima parameter `oldName` dan `newName`.
     - Pastikan file lama diganti dengan nama baru.
     - Jika file tidak ditemukan, kembalikan respons error 404.

- **Jika dua digit terakhir NIM Anda (`XX`) adalah angka genap:**
  2. Tambahkan **pencarian file berdasarkan nama**:
     - Buat endpoint **`GET /search`** yang menerima parameter `query`.
     - Kembalikan semua file yang mengandung kata kunci dalam nama file.

- **Jika dua digit terakhir NIM Anda (`XX`) habis dibagi 5:**
  3. Tambahkan **limit file upload berdasarkan ukuran**:
     - Batasi file yang diunggah agar tidak lebih dari **2MB**.
     - Kembalikan error jika file melampaui ukuran ini.

- **Jika dua digit terakhir NIM Anda (`XX`) habis dibagi 3:**
  4. Tambahkan **penomoran otomatis pada nama file yang sama**:
     - Saat file diunggah, jika file dengan nama yang sama sudah ada, tambahkan penomoran otomatis (contoh: `file_123_1`, `file_123_2`).

- **Jika dua digit terakhir NIM Anda adalah kelipatan dari 7:**
  5. Tambahkan **enkripsi nama file**:
     - Buat setiap file yang diunggah menggunakan nama yang dienkripsi (contoh: menggunakan hash MD5 atau SHA256).
     - Pastikan file dapat diunduh kembali dengan nama aslinya.

- **Jika dua digit terakhir NIM Anda adalah angka nol (00):**
  6. Tambahkan **log aktivitas server**:
     - Catat semua aktivitas server (upload, delete, rename) ke file log terpisah, termasuk timestamp dan IP klien.

- **Jika dua digit terakhir NIM Anda adalah 11 atau 22:**
  7. Tambahkan **sistem autentikasi dasar**:
     - Buat middleware untuk memvalidasi token API sederhana.
     - Hanya permintaan dengan token valid yang dapat mengakses endpoint.

---

## **Penilaian**

| Kriteria Penilaian                 | Bobot (%) |
|------------------------------------|-----------|
| Implementasi Fitur Baru            | 40%       |
| Struktur Kode dan Kebersihan       | 20%       |
| Dokumentasi (README.md)            | 20%       |
| Pengujian dan Fungsionalitas       | 20%       |

---
