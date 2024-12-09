# Pertemuan 9: Pengertian dan Konsep Dasar Memori

---

## 1. Konsep Dasar Memori
Manajemen memori adalah salah satu fungsi utama sistem operasi untuk mengelola penggunaan memori oleh berbagai proses.

### 1.1 Konsep Binding
- **Binding Waktu Kompilasi**: Alamat memori absolut ditentukan saat program dikompilasi.
- **Binding Waktu Pemuatan**: Alamat memori ditentukan saat program dimuat ke memori.
- **Binding Waktu Eksekusi**: Alamat memori dapat berubah selama eksekusi menggunakan mekanisme seperti Relokasi Dinamis.

### 1.2 Dynamic Loading
- Program hanya memuat modul yang dibutuhkan ke dalam memori selama eksekusi, mengurangi penggunaan memori.

### 1.3 Dynamic Linking
- Menghubungkan modul program ke pustaka (library) hanya saat modul tersebut dipanggil, mengurangi kebutuhan ruang penyimpanan.

### 1.4 Overlay
- Teknik untuk menjalankan program yang lebih besar dari memori fisik dengan mengganti bagian memori yang tidak dibutuhkan dengan bagian baru.

---

## 2. Strategi Manajemen Memori

### 2.1 Ruang Alamat Logika dan Fisik
- **Ruang Alamat Logika**: Alamat yang dihasilkan oleh CPU.
- **Ruang Alamat Fisik**: Alamat yang sebenarnya digunakan oleh memori utama.
- **Unit Manajemen Memori (MMU)**: Mengonversi alamat logika ke alamat fisik.

### 2.2 Swapping
- Teknik memindahkan proses yang sedang tidak aktif ke penyimpanan sekunder (disk) dan memuat proses lain ke memori utama.

### 2.3 Pencatatan Pemakaian Memori
#### 2.3.1 Peta Bit
- Menggunakan array bit untuk menunjukkan status setiap blok memori:
  - **1**: Blok memori sedang digunakan.
  - **0**: Blok memori kosong.

#### 2.3.2 Linked List
- Menggunakan daftar tertaut untuk mencatat segmen memori kosong dan terisi.

---

## 3. Monoprogramming

### 3.1 Pengalokasian Berurutan (Contiguous Allocation)
- Setiap proses diberi ruang memori yang berurutan.
- Memori dibagi menjadi dua bagian:
  - **Ruang Sistem Operasi**: Di awal memori.
  - **Ruang Proses Pengguna**: Setelah ruang sistem operasi.

### 3.2 Multiprogramming dengan Partisi Statis
- Memori dibagi menjadi partisi tetap dengan ukuran yang sudah ditentukan sebelumnya.
- Setiap proses dialokasikan ke satu partisi.

### 3.3 Multiprogramming dengan Partisi Dinamis
- Partisi memori dibuat secara dinamis sesuai dengan kebutuhan proses.
- Masalah: **Fragmentasi Eksternal**.

### 3.4 Sistem Buddy
- Teknik pembagian memori menjadi blok dengan ukuran yang merupakan pangkat dua.
- Meminimalkan fragmentasi eksternal.

---

## 4. Pengalokasian Tak Berurutan (Non-Contiguous Allocation)

### 4.1 Paging
- Memori logika dibagi menjadi **halaman (pages)** dengan ukuran tetap.
- Memori fisik dibagi menjadi **kerangka halaman (frames)**.
- **Tabel Halaman (Page Table)** digunakan untuk memetakan halaman logika ke kerangka fisik.

#### Keuntungan:
- Mengurangi fragmentasi eksternal.

#### Kekurangan:
- Overhead manajemen tabel halaman.

### 4.2 Segmentasi
- Memori logika dibagi menjadi segmen berdasarkan fungsi, seperti kode, data, dan stack.
- Setiap segmen memiliki panjang yang berbeda dan tabel segmen digunakan untuk pemosisian.

#### Keuntungan:
- Mendukung struktur data dan modularitas program.

#### Kekurangan:
- Rentan terhadap fragmentasi eksternal.

---

## Kesimpulan
Manajemen memori adalah elemen penting dalam sistem operasi untuk memastikan proses berjalan efisien dengan alokasi memori yang optimal. Strategi seperti paging, segmentasi, dan swapping dirancang untuk mengatasi keterbatasan memori fisik dan fragmentasi memori.
