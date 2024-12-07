# Sistem Operasi: Konsep Proses

## 1. Konsep Proses

### 1.1 Definisi Proses
- **Proses** adalah program yang sedang dieksekusi.
- Sebuah proses memerlukan sumber daya seperti CPU, memori, perangkat I/O, dan file untuk menjalankan tugasnya.
- Contoh: Program pengolah kata yang sedang berjalan.

---

### 1.2 Status Proses
Setiap proses memiliki tiga status utama:
1. **New**: Proses baru dibuat.
2. **Ready**: Proses siap dijalankan oleh CPU.
3. **Running**: Proses sedang dieksekusi.
4. **Waiting**: Proses menunggu suatu peristiwa (misalnya, input dari pengguna).
5. **Terminated**: Proses telah selesai.

---

### 1.3 Process Control Block (PCB)
- PCB adalah struktur data yang menyimpan informasi tentang suatu proses.
- Informasi dalam PCB meliputi:
  - **Process ID**: Identitas unik untuk proses.
  - **Program Counter**: Lokasi instruksi berikutnya yang akan dijalankan.
  - **Register**: Menyimpan data sementara selama proses berjalan.
  - **State**: Status proses saat ini (Ready, Running, dll).

---

## 2. Konsep Penjadwalan (Scheduling)

### 2.1 Scheduling Queue
- **Definisi**: Kumpulan proses yang menunggu sumber daya tertentu.
- Jenis antrian penjadwalan:
  - **Ready Queue**: Proses yang siap untuk dijalankan oleh CPU.
  - **Wait Queue**: Proses yang menunggu peristiwa tertentu.

---

### 2.2 Schedulers
- **Long-term Scheduler**: Memilih proses dari memori sekunder untuk dimuat ke memori utama.
- **Short-term Scheduler**: Memilih proses dari ready queue untuk dijalankan oleh CPU.
- **Medium-term Scheduler**: Menunda atau memulihkan proses untuk mengelola memori.

---

### 2.3 Context Switch
- **Definisi**: Proses menyimpan dan memulihkan status proses saat ini untuk memungkinkan CPU berpindah ke proses lain.
- Memerlukan waktu tambahan, disebut **context switch overhead**.

---

## 3. Operasi pada Proses

### 3.1 Pembuatan Proses
- Proses baru dapat dibuat oleh proses induk (parent).
- Operasi ini disebut **fork**.
- Proses baru disebut **child process**.

---

### 3.2 Penghentian Proses
- Proses dihentikan karena:
  - Penyelesaian tugas.
  - Permintaan dari pengguna.
  - Kesalahan atau kegagalan.

---

## 4. Proses yang Saling Bekerjasama (Cooperating Process)

### 4.1 Threads
- **Thread** adalah unit terkecil dari eksekusi dalam sebuah proses.
- Satu proses dapat memiliki banyak thread yang berbagi memori dan sumber daya.

### 4.2 Komunikasi Antar Proses (Inter-Process Communication - IPC)
- Proses yang bekerjasama sering memerlukan komunikasi.
- Metode IPC:
  - **Shared Memory**: Proses berbagi area memori bersama.
  - **Message Passing**: Proses saling bertukar pesan.

### 4.3 Buffering
- **Buffering** adalah penggunaan area penyimpanan sementara untuk menangani komunikasi antar proses.
- Tiga jenis buffering:
  - **Zero Capacity**: Tidak ada buffer; komunikasi sinkron.
  - **Bounded Capacity**: Buffer dengan ukuran terbatas.
  - **Unbounded Capacity**: Buffer tanpa batas.

---

## 5. Kondisi-Kondisi Perkecualian

### 5.1 Proses Dihentikan
- Proses dihentikan jika:
  - CPU atau memori tidak cukup.
  - Sumber daya yang dibutuhkan tidak tersedia.

### 5.2 Kehilangan Pesan
- Pesan antar proses mungkin hilang karena kegagalan jaringan atau sistem.

### 5.3 Proses Terganggu
- **Interrupt** adalah peristiwa yang menyebabkan CPU menghentikan eksekusi proses saat ini untuk menangani peristiwa penting.

---

## Kesimpulan
- **Konsep proses** adalah dasar sistem operasi, mengelola eksekusi program.
- **Penjadwalan proses** memastikan efisiensi pemakaian CPU.
- **Komunikasi antar proses** dan **handling kondisi perkecualian** memastikan sistem berjalan dengan baik.
