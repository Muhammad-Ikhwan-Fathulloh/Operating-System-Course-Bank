# Masalah Critical Section dan Deadlock

## 1. Masalah Critical Section
Critical Section adalah bagian dari kode dalam suatu proses di mana proses tersebut mengakses sumber daya bersama (shared resource) yang tidak boleh diakses secara bersamaan oleh proses lain. 

### 1.1 Masalah yang Muncul
- **Race Condition**: Terjadi ketika hasil akhir dari program bergantung pada urutan eksekusi proses.
- **Mutual Exclusion**: Hanya satu proses yang dapat berada di critical section dalam waktu tertentu.

---

## 2. Sinkronisasi
Sinkronisasi adalah mekanisme untuk mengatur eksekusi proses agar dapat berjalan secara aman ketika mengakses sumber daya bersama.

### 2.1 Sinkronisasi Software
- Menggunakan algoritma seperti **Peterson’s Algorithm** atau **Dekker’s Algorithm** untuk memastikan mutual exclusion.
- Solusi berbasis software memerlukan pengujian dan pengaturan variabel secara manual.

### 2.2 Sinkronisasi Hardware
- Memanfaatkan dukungan hardware seperti **Test-and-Set Instruction** atau **Compare-and-Swap** untuk menjaga mutual exclusion.
- Lebih cepat dan andal dibandingkan sinkronisasi software.

---

## 3. Semaphore
**Semaphore** adalah alat sinkronisasi yang digunakan untuk mengatur akses ke sumber daya bersama.

### 3.1 Jenis Semaphore
- **Counting Semaphore**: Mengelola sejumlah sumber daya tertentu.
- **Binary Semaphore**: Sama seperti mutex, hanya memiliki nilai 0 atau 1.

### 3.2 Operasi Semaphore
- **Wait (P)**: Menurunkan nilai semaphore dan menunggu jika nilainya negatif.
- **Signal (V)**: Meningkatkan nilai semaphore.

---

## 4. Masalah-Masalah Klasik dalam Sinkronisasi
1. **Producer-Consumer Problem**: Produsen menghasilkan data, konsumen mengambil data, keduanya harus disinkronkan.
2. **Readers-Writers Problem**: Beberapa pembaca dapat membaca data secara bersamaan, tetapi hanya satu penulis yang dapat menulis.
3. **Dining Philosophers Problem**: Masalah sinkronisasi pada sejumlah proses yang membutuhkan sumber daya terbatas secara bersamaan.

---

## 5. Deadlock
**Deadlock** terjadi ketika sekelompok proses saling menunggu sumber daya yang sedang digunakan oleh proses lain, sehingga tidak ada yang bisa melanjutkan.

### 5.1 Model Sistem
- Proses menggunakan sumber daya dengan cara:
  1. Meminta (Request)
  2. Menggunakan (Use)
  3. Melepaskan (Release)

### 5.2 Karakteristik Deadlock
Deadlock terjadi jika keempat kondisi berikut terpenuhi:
1. **Mutual Exclusion**: Sumber daya tidak dapat dibagikan.
2. **Hold and Wait**: Proses memegang satu sumber daya dan menunggu sumber daya lain.
3. **No Preemption**: Sumber daya tidak dapat diambil secara paksa.
4. **Circular Wait**: Ada rantai proses yang saling menunggu.

---

## 6. Metode Penanganan Deadlock

### 6.1 Pencegahan Deadlock
Menghilangkan salah satu dari keempat kondisi deadlock:
- **Mutual Exclusion**: Gunakan sumber daya yang dapat dibagikan.
- **Hold and Wait**: Wajibkan proses meminta semua sumber daya sekaligus.
- **No Preemption**: Izinkan pengambilan sumber daya dari proses.
- **Circular Wait**: Tetapkan urutan total untuk permintaan sumber daya.

### 6.2 Penghindaran Deadlock
- Menggunakan algoritma seperti **Banker’s Algorithm**.
- Analisis alokasi sumber daya sebelum diberikan untuk memastikan tidak terjadi deadlock.

### 6.3 Pendeteksian Deadlock
- Sistem secara rutin memeriksa apakah deadlock terjadi menggunakan grafik tunggu (Wait-For Graph).
- Jika ditemukan siklus, deadlock sedang terjadi.

### 6.4 Recovery Deadlock
Jika deadlock terdeteksi, langkah-langkah berikut dapat diambil:
1. **Terminating Processes**: Hentikan satu atau lebih proses untuk memutus siklus deadlock.
2. **Preemption**: Ambil kembali sumber daya dari proses tertentu.

### 6.5 Pendekatan Kombinasi
Menggabungkan beberapa metode di atas untuk:
- Mencegah deadlock sebanyak mungkin.
- Meminimalkan dampak jika deadlock terjadi.

---

## Kesimpulan
Masalah critical section dan deadlock adalah tantangan utama dalam sinkronisasi proses pada sistem operasi. Dengan memahami konsep seperti sinkronisasi, semaphore, dan metode penanganan deadlock, sistem operasi dapat mengelola proses dengan lebih efisien dan aman.
