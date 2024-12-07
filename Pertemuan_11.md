# Interface Sistem File

## 1. Konsep File
- **File** adalah kumpulan data yang disimpan di perangkat penyimpanan (seperti hard disk atau SSD) yang dapat diakses, diubah, dan dikelola oleh pengguna atau program.
- File memiliki atribut seperti nama, ukuran, tipe, dan lokasi penyimpanan di disk.
- File dapat berisi data dalam berbagai format seperti teks, gambar, video, atau program eksekusi.

### 1.1 Jenis-jenis File
- **File Teks**: Menyimpan data dalam bentuk teks yang dapat dibaca oleh manusia.
- **File Biner**: Menyimpan data dalam bentuk yang tidak langsung dapat dibaca oleh manusia, biasanya digunakan untuk program atau file multimedia.

---

## 2. Metode Akses
Metode akses mengacu pada cara data dalam file dapat diakses atau dibaca oleh sistem operasi.

### 2.1 Akses Secara Urut (Sequential Access)
- Data dalam file dibaca secara berurutan, dari awal hingga akhir. Akses hanya dapat dilakukan dalam urutan yang telah ditentukan.
- Contoh: File teks, log file.

### 2.2 Akses Langsung (Direct Access)
- Sistem dapat mengakses data di file dalam urutan acak. Akses dapat dilakukan ke lokasi tertentu dalam file tanpa perlu membaca dari awal.
- Contoh: Database atau sistem penyimpanan lainnya.

### 2.3 Akses Indeks (Indexed Access)
- Sistem menggunakan indeks untuk menemukan data yang diperlukan dalam file, memungkinkan akses cepat ke bagian tertentu dari file.
- Contoh: Sistem file berbasis indeks seperti NTFS.

---

## 3. Struktur Direktori
- **Direktori** adalah tempat untuk menyimpan informasi tentang file-file yang ada di sistem file, termasuk nama file, lokasi, dan atribut lainnya.
- Struktur direktori bisa berupa hierarkis, di mana direktori dapat berisi sub-direktori dan file.
  
### 3.1 Jenis Struktur Direktori
- **Struktur Flat**: Semua file disimpan dalam satu direktori tanpa pembagian lebih lanjut.
- **Struktur Hierarkis**: Direktori disusun dalam bentuk pohon, dengan sub-direktori yang bisa berisi file dan sub-direktori lainnya.
- **Struktur Acyclic Graph (DAG)**: Menggabungkan struktur pohon dengan referensi bersama antar direktori, memungkinkan file memiliki beberapa induk.

---

## 4. Proteksi
Proteksi sistem file berfungsi untuk mengatur hak akses pengguna terhadap file dan direktori.

### 4.1 Sistem Hak Akses
- **Hak baca (read)**: Pengguna dapat melihat isi file.
- **Hak tulis (write)**: Pengguna dapat mengubah isi file.
- **Hak eksekusi (execute)**: Pengguna dapat menjalankan file sebagai program.
  
### 4.2 Model Keamanan
- **Model Keamanan Diskret**: Menggunakan model seperti kontrol akses berbasis peran (Role-Based Access Control/RBAC) atau kontrol akses berbasis atribut.
- **Enkripsi**: Teknik pengamanan data dengan mengacak informasi dalam file agar hanya dapat dibaca oleh pengguna yang memiliki kunci dekripsi.

---

# Implementasi Sistem File

## 1. Struktur Sistem File
Struktur sistem file adalah cara data disusun di dalam perangkat penyimpanan sehingga dapat dengan mudah diakses oleh sistem operasi.

### 1.1 Tabel Alokasi File
- Sistem file biasanya menggunakan tabel alokasi untuk melacak lokasi blok disk yang menyimpan bagian-bagian file.
- Contoh: Tabel alokasi file (FAT) atau indeks blok dalam sistem file seperti ext4.

---

## 2. Metode Pengalokasian
Ada beberapa metode yang digunakan untuk mengalokasikan ruang di dalam sistem file:

### 2.1 Pengalokasian Berurutan (Contiguous Allocation)
- Semua bagian file disimpan secara berurutan di disk, sehingga akses file menjadi cepat.
- Kekurangan: Ketika file diperbesar, ruang kosong yang tersisa di disk bisa menjadi terfragmentasi.

### 2.2 Pengalokasian Terindeks (Indexed Allocation)
- Setiap file memiliki struktur indeks yang menunjuk ke blok-blok yang tidak terhubung secara berurutan.
- Keuntungan: Mengurangi masalah fragmentasi dan memungkinkan alokasi dinamis.
- Kekurangan: Memerlukan overhead untuk menyimpan indeks.

### 2.3 Pengalokasian Pemetaan (Linked Allocation)
- Setiap blok file menyimpan alamat dari blok berikutnya, sehingga file dapat disusun tidak berurutan.
- Kekurangan: Akses menjadi lebih lambat karena sistem harus mengikuti rantai blok yang berantai.

---

## 3. Manajemen Ruang Kosong
- Manajemen ruang kosong bertujuan untuk melacak ruang kosong pada disk yang dapat digunakan untuk menyimpan file baru atau bagian file yang diperbesar.

### 3.1 Peta Bit (Bitmap)
- **Bitmap** adalah struktur data yang digunakan untuk melacak ruang kosong dengan cara menggunakan bit untuk menunjukkan apakah blok tertentu kosong atau terisi.

### 3.2 Linked List
- **Linked List** adalah struktur data yang digunakan untuk melacak ruang kosong dengan menyusun daftar blok kosong dalam bentuk list.

---

## 4. Implementasi Direktori
- Direktori digunakan untuk menyimpan informasi tentang file dan sub-direktori yang ada di dalam sistem file.

### 4.1 Penyimpanan Data Direktori
- Direktori bisa disimpan sebagai tabel atau struktur data lainnya yang menyimpan informasi file seperti nama file, atribut, dan lokasi blok disk.

### 4.2 Pengelolaan Direktori
- Beberapa sistem file mengelola direktori secara efisien dengan membagi direktori besar menjadi beberapa bagian atau menggunakan struktur indeks untuk mempercepat pencarian.

---

## 5. Efisiensi, Unjuk Kerja, dan Recovery
- **Efisiensi**: Sistem file harus efisien dalam mengalokasikan ruang dan meminimalkan fragmentasi disk untuk meningkatkan kinerja.
- **Unjuk Kerja**: Melibatkan kecepatan dalam akses file dan pengelolaan ruang, serta kecepatan pencarian file dalam struktur direktori.
- **Recovery**: Sistem file harus mampu pulih dari kegagalan atau crash, dengan cara menggunakan teknik seperti logging, journaling, atau pembuatan salinan cadangan (backup).

---
## Kesimpulan
Sistem file adalah komponen penting dalam sistem operasi yang mengelola penyimpanan dan akses file. Pengelolaan yang efisien terhadap ruang penyimpanan, proteksi file, serta metode alokasi ruang dan pengelolaan direktori sangat mempengaruhi kinerja dan keandalan sistem. Berbagai teknik seperti pengalokasian berurutan, terindeks, dan pemetaan membantu mengatasi masalah fragmentasi dan efisiensi penyimpanan.
