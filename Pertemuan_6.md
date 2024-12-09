# Pertemuan 6: Konsep Dasar Penjadwalan Prosesor

---

## 1. Penjadwalan Proses
Penjadwalan proses adalah mekanisme dalam sistem operasi yang mengatur urutan eksekusi proses di CPU. Tujuan utama penjadwalan adalah untuk meningkatkan efisiensi penggunaan CPU dan memberikan waktu respons yang baik untuk pengguna.

---

### 1.1 Preemptive Scheduling
- **Preemptive Scheduling** adalah jenis penjadwalan di mana proses yang sedang berjalan dapat dihentikan secara paksa oleh sistem operasi untuk memberi kesempatan kepada proses lain untuk dijalankan.
- Proses yang dihentikan akan dipindahkan kembali ke antrian ready untuk menunggu giliran berikutnya.
- Contoh: **Round Robin Scheduling**.

---

### 1.2 Dispatcher
- **Dispatcher** adalah komponen dalam sistem operasi yang bertanggung jawab untuk memilih dan memindahkan proses dari antrian ready ke CPU.
- Dispatcher juga menangani **context switch**, yaitu menyimpan dan memulihkan status proses yang sedang berjalan.

---

## 2. Kriteria Penjadwalan
Kriteria penjadwalan digunakan untuk menilai efisiensi algoritma penjadwalan. Beberapa kriteria penting dalam penjadwalan proses antara lain:
- **Throughput**: Jumlah proses yang diselesaikan dalam satuan waktu.
- **Turnaround Time**: Waktu yang diperlukan untuk menyelesaikan proses, mulai dari kedatangan hingga selesai.
- **Waiting Time**: Waktu total yang dihabiskan proses dalam antrian ready.
- **Response Time**: Waktu dari pengiriman permintaan hingga respons pertama diterima.

---

## 3. Algoritma Penjadwalan

### 3.1 First Come First Served Scheduling (FCFS)
- **FCFS** adalah algoritma penjadwalan sederhana di mana proses dieksekusi dalam urutan kedatangan.
- Proses pertama yang tiba akan dieksekusi terlebih dahulu, dan seterusnya.
- **Kelebihan**: Mudah diimplementasikan.
- **Kekurangan**: Dapat menyebabkan **long waiting times** untuk proses dengan durasi lebih lama.

---

### 3.2 Shortest Job First Scheduling (SJF)
- **SJF** adalah algoritma penjadwalan yang memilih proses dengan waktu eksekusi (burst time) paling pendek untuk dieksekusi pertama.
- **Preemptive** versi SJF dikenal dengan **Shortest Remaining Time First (SRTF)**.
- **Kelebihan**: Efisien dalam hal **turnaround time**.
- **Kekurangan**: Tidak dapat memprediksi dengan pasti waktu eksekusi proses.

---

### 3.3 Priority Scheduling
- **Priority Scheduling** adalah algoritma penjadwalan yang mengeksekusi proses berdasarkan prioritas yang ditentukan.
- Proses dengan prioritas tertinggi akan dieksekusi terlebih dahulu.
- **Kelebihan**: Fleksibel dan mudah disesuaikan.
- **Kekurangan**: Proses dengan prioritas rendah mungkin tidak pernah dieksekusi jika proses dengan prioritas tinggi selalu datang.

---

### 3.4 Round Robin Scheduling
- **Round Robin (RR)** adalah algoritma preemptive yang memberikan setiap proses waktu eksekusi yang sama, disebut **quantum time**.
- Jika proses tidak selesai dalam waktu yang ditentukan, proses tersebut akan dikembalikan ke antrian ready untuk menunggu giliran berikutnya.
- **Kelebihan**: Memberikan keadilan kepada semua proses.
- **Kekurangan**: Jika quantum time terlalu besar atau kecil, kinerjanya dapat menurun.

---

### 3.5 Multilevel Queue Scheduling
- **Multilevel Queue Scheduling** membagi antrian menjadi beberapa level berdasarkan prioritas.
- Setiap antrian memiliki algoritma penjadwalan yang berbeda, misalnya **FCFS** untuk antrian prioritas rendah dan **Round Robin** untuk antrian prioritas tinggi.
- **Kelebihan**: Memberikan fleksibilitas dalam menangani berbagai jenis proses.
- **Kekurangan**: Proses dengan prioritas rendah mungkin tidak pernah mendapatkan kesempatan untuk dijalankan.

---

### 3.6 Multilevel Feedback Queue Scheduling
- **Multilevel Feedback Queue Scheduling** adalah variasi dari multilevel queue di mana proses dapat dipindahkan antara antrian berdasarkan perilaku dan durasi eksekusinya.
- Proses yang membutuhkan waktu eksekusi lebih lama akan dipindahkan ke antrian dengan prioritas lebih rendah.
- **Kelebihan**: Mengatasi masalah multilevel queue yang tidak adil terhadap proses dengan durasi eksekusi panjang.
- **Kekurangan**: Implementasi yang lebih kompleks.

---

### 3.7 Guaranteed Scheduling
- **Guaranteed Scheduling** adalah algoritma penjadwalan yang bertujuan untuk memberikan jaminan waktu eksekusi untuk proses.
- Biasanya digunakan dalam sistem real-time di mana setiap proses harus diselesaikan dalam waktu tertentu.
- **Kelebihan**: Memberikan jaminan kinerja yang lebih stabil.
- **Kekurangan**: Membutuhkan sumber daya yang cukup untuk memastikan kelancaran.

---

### 3.8 Multiple Processor Scheduling
- **Multiple Processor Scheduling** adalah penjadwalan yang mengelola lebih dari satu CPU.
- Proses dapat dieksekusi secara paralel di berbagai CPU.
- **Kelebihan**: Meningkatkan throughput dan efisiensi sistem.
- **Kekurangan**: Memerlukan sinkronisasi antar CPU dan manajemen sumber daya yang lebih rumit.

---

## 4. Metode Evaluasi Penjadwalan
Metode evaluasi digunakan untuk menilai kinerja algoritma penjadwalan berdasarkan beberapa parameter seperti:
- **Average Waiting Time**: Rata-rata waktu tunggu proses dalam antrian.
- **Average Turnaround Time**: Rata-rata waktu yang diperlukan untuk menyelesaikan proses.
- **CPU Utilization**: Persentase waktu CPU yang digunakan untuk mengeksekusi proses.
- **Throughput**: Jumlah proses yang selesai dalam waktu tertentu.

Evaluasi yang baik membantu memilih algoritma penjadwalan yang paling sesuai dengan kebutuhan sistem.

---

## Kesimpulan
- Pemilihan algoritma penjadwalan yang tepat sangat penting untuk meningkatkan efisiensi dan kinerja sistem operasi.
- Setiap algoritma penjadwalan memiliki kelebihan dan kekurangan yang harus disesuaikan dengan kebutuhan aplikasi dan lingkungan.