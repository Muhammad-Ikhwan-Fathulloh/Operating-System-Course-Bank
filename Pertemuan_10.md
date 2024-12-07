# Konsep Dasar Memori Virtual

## 1. Memori Virtual
Memori virtual adalah teknik yang digunakan untuk memberikan ilusi memori yang lebih besar dari memori fisik yang sebenarnya tersedia dengan memanfaatkan penyimpanan sekunder. Dengan memori virtual, sistem dapat menjalankan program yang lebih besar daripada memori fisik yang tersedia.

### 1.1 Demand Paging
- **Demand Paging** adalah teknik memori virtual di mana halaman-halaman program hanya dimuat ke dalam memori ketika dibutuhkan (on-demand), bukan saat program pertama kali dimulai.
- Halaman-halaman yang tidak aktif tetap berada di penyimpanan sekunder (misalnya disk) hingga proses mencoba mengaksesnya.
  
### 1.2 Unjuk Kerja Demand Paging
- **Unjuk Kerja** pada demand paging dipengaruhi oleh beberapa faktor, termasuk frekuensi akses halaman yang sudah dimuat, ukuran halaman, dan algoritma penggantian halaman yang digunakan.
- Keuntungan utama dari demand paging adalah penggunaan memori yang lebih efisien karena hanya halaman yang digunakan yang dimuat ke dalam memori.

---

## 2. Page Replacement (Penggantian Halaman)
Penggantian halaman adalah proses mengeluarkan halaman yang ada di memori dan menggantinya dengan halaman baru yang diperlukan, terutama ketika memori penuh.

### 2.1 Algoritma Page Replacement
Berikut adalah beberapa algoritma penggantian halaman yang umum digunakan:

#### 2.1.1 Algoritma FIFO (First In, First Out)
- **FIFO** menggantikan halaman yang pertama kali dimuat ke dalam memori. Artinya, halaman yang paling lama berada di memori akan digantikan.
  
#### Keuntungan:
- Implementasi yang sederhana.

#### Kekurangan:
- Tidak efisien dalam beberapa kasus karena bisa menggantikan halaman yang sering digunakan.

#### 2.1.2 Algoritma Optimal
- **Optimal** adalah algoritma penggantian halaman yang menggantikan halaman yang tidak akan digunakan lagi untuk waktu yang paling lama di masa depan.
- Algoritma ini memberikan performa terbaik tetapi tidak dapat diimplementasikan dalam praktek karena memerlukan pengetahuan tentang urutan akses halaman yang akan datang.

#### 2.1.3 Algoritma Least Recently Used (LRU)
- **LRU** menggantikan halaman yang paling lama tidak digunakan, yaitu halaman yang tidak diakses dalam waktu yang lama.
  
#### Keuntungan:
- Lebih efisien daripada FIFO karena mengganti halaman yang jarang digunakan.

#### Kekurangan:
- Memerlukan pengelolaan daftar akses halaman yang lebih kompleks dan lebih mahal dalam hal overhead.

---

## 3. Pengalokasian Frame
Pengalokasian frame adalah teknik yang digunakan untuk memetakan halaman virtual ke frame memori fisik.

### 3.1 Algoritma Pengalokasian
- **Algoritma Pengalokasian** memutuskan bagaimana halaman virtual dipetakan ke dalam frame memori fisik. Beberapa pendekatan yang umum digunakan adalah pengalokasian acak dan pengalokasian berurutan.

### 3.2 Algoritma Global dan Lokal
- **Algoritma Global** mengalokasikan halaman ke semua frame memori yang tersedia, tanpa membedakan antara proses yang berjalan.
- **Algoritma Lokal** membatasi pengalokasian halaman hanya untuk proses tertentu, sehingga setiap proses hanya dapat mengganti halaman dalam frame yang dialokasikan untuknya.

---

## 4. Tracing
- **Tracing** adalah teknik yang digunakan untuk memantau dan mencatat alur eksekusi program, yang dapat membantu dalam analisis performa dan optimisasi algoritma penggantian halaman.
- Dalam konteks manajemen memori, tracing dapat digunakan untuk mengidentifikasi pola akses memori dan menentukan algoritma penggantian yang lebih efisien.

---

## Kesimpulan
Memori virtual memungkinkan sistem untuk menjalankan program yang lebih besar dari memori fisik yang tersedia dengan menggunakan teknik seperti demand paging dan page replacement. Algoritma seperti FIFO, Optimal, dan LRU memberikan cara yang berbeda untuk mengelola penggantian halaman, masing-masing dengan kelebihan dan kekurangannya. Pengalokasian frame dan tracing membantu dalam mengoptimalkan penggunaan memori fisik dan analisis kinerja sistem.
