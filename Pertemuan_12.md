# Pertemuan 12: Pengertian dan Prinsip Kerja Perangkat Keras I/O

---

## 1. I/O Device
- **I/O Device (Input/Output Device)** adalah perangkat yang digunakan untuk komunikasi antara sistem komputer dan dunia luar. Contoh perangkat I/O termasuk keyboard, mouse, monitor, printer, disk drive, dan jaringan.
- I/O devices dapat dibedakan menjadi dua jenis: 
  - **Input Device**: Perangkat yang menerima data dari pengguna, seperti keyboard, mouse, dan scanner.
  - **Output Device**: Perangkat yang mengirimkan data ke pengguna, seperti monitor dan printer.

---

## 2. Device Controller
- **Device Controller** adalah perangkat keras yang mengendalikan operasi dari I/O device. Controller ini bertanggung jawab untuk mengatur komunikasi antara CPU dan perangkat I/O.
- **Peran**:
  - Menyediakan antarmuka antara I/O device dan sistem operasi.
  - Mengirimkan sinyal untuk memulai atau menghentikan operasi perangkat.

---

## 3. Direct Memory Access (DMA)
- **Direct Memory Access (DMA)** adalah metode transfer data yang memungkinkan perangkat I/O untuk mengakses memori utama (RAM) secara langsung tanpa melibatkan CPU.
- Keuntungan dari DMA:
  - Mengurangi beban kerja CPU.
  - Mempercepat proses transfer data.
  
---

# Prinsip Perangkat Lunak I/O

## 1. Tujuan Perangkat Lunak I/O
- **Perangkat Lunak I/O** bertujuan untuk menyediakan antarmuka yang efisien antara perangkat keras I/O dan aplikasi yang berjalan di sistem operasi.
- Tujuan utama perangkat lunak I/O:
  - Mengelola permintaan I/O secara efisien.
  - Mengatur prioritas dan penjadwalan untuk menghindari keterlambatan.
  
---

## 2. Interrupt Handler
- **Interrupt Handler** adalah bagian dari perangkat lunak yang merespons interupsi yang dihasilkan oleh perangkat keras. Interupsi dapat terjadi ketika perangkat I/O membutuhkan perhatian CPU, misalnya saat perangkat selesai mentransfer data.
- Fungsi utama Interrupt Handler:
  - Mencegah CPU terjebak dalam polling yang tidak perlu.
  - Menangani dan merespons interupsi dari perangkat I/O.

---

## 3. Device Drivers
- **Device Drivers** adalah perangkat lunak yang berfungsi sebagai jembatan antara perangkat keras I/O dan sistem operasi.
- Setiap perangkat I/O membutuhkan driver khusus yang mengatur cara komunikasi antara perangkat tersebut dan sistem operasi.

---

## 4. Device-Independent I/O Software
- **Device-Independent I/O Software** menyediakan antarmuka yang tidak tergantung pada perangkat keras, memungkinkan perangkat lunak untuk berinteraksi dengan berbagai perangkat I/O tanpa perlu mengetahui detail perangkat kerasnya.
- Tujuan:
  - Meningkatkan portabilitas perangkat lunak.
  - Mengurangi kompleksitas dalam berinteraksi dengan berbagai perangkat I/O.

---

## 5. User-Space I/O Software
- **User-Space I/O Software** merujuk pada perangkat lunak I/O yang berjalan di ruang pengguna (user space), bukan di ruang kernel. Ini memungkinkan pengembangan perangkat I/O yang lebih fleksibel dan dapat diubah tanpa harus mengubah kode inti kernel.

---

# Disk

## 1. Struktur Disk
- Disk adalah perangkat penyimpanan data yang terbuat dari piringan magnetik atau solid-state drives (SSD) yang menyimpan data dalam blok-blok terorganisir.
- **Bagian utama disk**:
  - **Platter**: Piringan tempat data disimpan.
  - **Head**: Alat pembaca/penulis yang bergerak di atas platter.
  - **Track**: Lingkaran konsentris pada platter yang menyimpan data.
  - **Sector**: Unit terkecil tempat data disimpan di track.

---

## 2. Penjadwalan Disk
- **Penjadwalan Disk** adalah proses menentukan urutan permintaan I/O disk yang akan diproses.
- Tujuannya adalah untuk meminimalkan waktu pencarian (seek time) dan waktu putaran (rotational latency).

---

### 2.1 First Come First Served Scheduling (FCFS)
- **FCFS Scheduling**: Permintaan I/O diproses sesuai urutan kedatangan tanpa mempertimbangkan posisi head disk.
- Kekurangan: Dapat menyebabkan waktu pencarian yang lebih lama jika permintaan terpisah jauh.

---

### 2.2 Shortest Seek Time First Scheduling (SSTF)
- **SSTF Scheduling**: Memilih permintaan yang paling dekat dengan posisi head saat ini.
- Keuntungan: Mengurangi waktu pencarian.
- Kekurangan: Dapat menyebabkan starvation pada permintaan yang jauh.

---

### 2.3 SCAN Scheduling
- **SCAN Scheduling**: Head disk bergerak ke arah satu sisi disk, memproses permintaan di sepanjang jalan, kemudian berbalik arah setelah mencapai ujung disk.
- Keuntungan: Mengurangi waktu pencarian dibandingkan FCFS.

---

### 2.4 C-SCAN Scheduling
- **C-SCAN Scheduling**: Serupa dengan SCAN, tetapi setelah mencapai ujung, head disk kembali ke posisi awal tanpa memproses permintaan.
- Keuntungan: Mengurangi waktu pencarian lebih lanjut dengan menghindari gerakan bolak-balik yang tidak perlu.

---

### 2.5 Look Scheduling
- **Look Scheduling**: Memilih arah yang lebih dekat untuk diproses, tetapi tidak memaksakan head disk untuk bergerak ke ujung disk seperti SCAN.

---

## 3. Disk Management
- **Disk Management** mengacu pada pengelolaan ruang penyimpanan disk, termasuk alokasi ruang, de-alokasi ruang, dan pemeliharaan integritas data.

### 3.1 Swap Space Management
- **Swap Space Management** adalah penggunaan ruang disk sebagai memori virtual untuk menggantikan memori utama (RAM) saat kapasitas RAM penuh.
- Swap space sering digunakan untuk menyimpan proses yang tidak aktif untuk sementara waktu.

### 3.2 Disk Reliability
- **Disk Reliability** berkaitan dengan kemampuan disk untuk beroperasi tanpa gagal dalam jangka waktu tertentu.
- Proses ini mencakup pemantauan kesehatan disk, deteksi kesalahan, dan pemulihan data dari kesalahan atau kegagalan disk.

---
## Kesimpulan
I/O devices dan disk memiliki peran penting dalam sistem komputer. Prinsip perangkat keras dan lunak I/O membantu mengelola komunikasi antara CPU dan perangkat I/O, sementara penjadwalan disk dan manajemen ruang penyimpanan meningkatkan efisiensi penggunaan perangkat penyimpanan. Teknologi seperti DMA, device drivers, dan berbagai algoritma penjadwalan disk berkontribusi pada kinerja sistem yang lebih baik.