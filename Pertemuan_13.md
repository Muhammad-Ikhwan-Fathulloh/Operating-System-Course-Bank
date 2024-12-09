# Pertemuan 13: Mekanisme Proteksi dalam Sistem Komputer

---

## 1. Tujuan dari Proteksi
- **Proteksi** dalam sistem komputer adalah mekanisme yang bertujuan untuk memastikan bahwa akses terhadap sumber daya sistem (seperti memori, file, perangkat keras) dikendalikan dengan cara yang tepat.
- Tujuan utama dari proteksi adalah:
  - **Melindungi sumber daya** dari akses yang tidak sah.
  - **Mencegah kerusakan atau modifikasi** yang tidak diinginkan pada data atau perangkat.
  - **Menjamin bahwa hanya entitas yang berwenang** yang dapat mengakses atau mengubah data atau sumber daya.
  
---

## 2. Domain Proteksi
- **Domain Proteksi** adalah rentang hak akses yang diberikan kepada entitas dalam sistem, seperti pengguna atau proses, terhadap objek dalam sistem.
- Domain proteksi mengatur siapa yang dapat mengakses objek dan apa yang dapat dilakukan pada objek tersebut (misalnya, membaca, menulis, mengeksekusi).

---

## 3. Matriks Akses
- **Matriks Akses** adalah struktur data yang digunakan untuk mendefinisikan hak akses antara entitas dan objek dalam sistem. Matriks ini menggambarkan akses yang diberikan kepada setiap pengguna terhadap objek yang ada dalam sistem.
- Contoh:
  - Baris mewakili **entitas** (pengguna atau proses).
  - Kolom mewakili **objek** (file, perangkat, dll).
  - Nilai dalam matriks mewakili hak akses (misalnya, `read`, `write`, `execute`).

---

## 4. Revokasi Hak Akses
- **Revokasi Hak Akses** adalah proses pencabutan hak akses yang sebelumnya diberikan kepada entitas atau pengguna dalam sistem.
- Ada beberapa metode revokasi:
  - **Revokasi langsung**: Mencabut akses dari entitas tertentu secara langsung.
  - **Revokasi tidak langsung**: Menghapus atau mengubah hak akses dalam matriks akses.

---

## 5. Sistem Berdasarkan Kapabilitas
- **Sistem Berdasarkan Kapabilitas** menggunakan "kapabilitas" (capabilities) yang merupakan token atau referensi yang menunjukkan hak akses tertentu ke objek dalam sistem.
- Setiap entitas (seperti pengguna atau proses) memiliki kapabilitas yang memberikan akses ke objek atau sumber daya tertentu, dan dapat memindahkan atau berbagi kapabilitas ini dengan entitas lain.

---

## 6. Proteksi Berdasarkan Bahasa
- **Proteksi Berdasarkan Bahasa** adalah mekanisme yang melibatkan penggunaan bahasa pemrograman untuk memastikan bahwa akses ke objek hanya dilakukan melalui cara yang sah.
- Bahasa pemrograman ini dapat menyediakan fasilitas untuk mengatur hak akses dan membatasi operasi yang tidak sah.

---

# Sekuriti

## 1. Masalah Sekuriti
- **Masalah Sekuriti** adalah ancaman yang dihadapi oleh sistem komputer dan jaringan untuk memastikan kerahasiaan, integritas, dan ketersediaan data.
- Tujuan sekuriti adalah melindungi sistem dari akses yang tidak sah, gangguan, dan kerusakan yang dapat memengaruhi operasi atau data.

---

## 2. Autentikasi
- **Autentikasi** adalah proses verifikasi identitas pengguna atau entitas lainnya dalam sistem.
- Metode autentikasi meliputi:
  - **Password**: Kata sandi yang hanya diketahui oleh pengguna yang sah.
  - **Biometrik**: Penggunaan fitur fisik seperti sidik jari atau pengenalan wajah.
  - **Token**: Penggunaan perangkat atau aplikasi yang menghasilkan kode sementara.

---

## 3. Ancaman Program
- **Ancaman Program** adalah risiko yang berasal dari program atau perangkat lunak yang berpotensi membahayakan sistem.
- Contoh ancaman program:
  - **Virus**: Program yang dapat menyebar dan merusak sistem.
  - **Worm**: Program yang dapat menyebar dan menambah salinan dirinya tanpa perlu interaksi pengguna.
  - **Trojan Horse**: Program yang menyamar sebagai program yang sah tetapi memiliki fungsi berbahaya.

---

## 4. Ancaman Sistem
- **Ancaman Sistem** adalah risiko yang dapat merusak atau mengganggu operasi sistem secara keseluruhan, baik yang berasal dari perangkat keras maupun perangkat lunak.
- Contoh ancaman sistem:
  - **Serangan DDoS** (Distributed Denial of Service) yang mengganggu layanan dengan membanjiri server dengan lalu lintas berlebihan.
  - **Eksploitasi Kerentanannya**: Menggunakan kelemahan dalam perangkat lunak untuk mendapatkan akses yang tidak sah.

---

## 5. Monitoring Ancaman
- **Monitoring Ancaman** adalah proses memantau dan mengidentifikasi potensi ancaman yang dapat mengganggu keamanan sistem.
- Metode monitoring ancaman termasuk:
  - **Intrusion Detection Systems (IDS)**: Sistem yang mendeteksi potensi serangan berdasarkan pola atau perilaku yang mencurigakan.
  - **Log Monitoring**: Menganalisis log sistem untuk mendeteksi aktivitas yang tidak biasa.

---

## 6. Enkripsi
- **Enkripsi** adalah proses mengubah data asli menjadi bentuk yang tidak dapat dibaca tanpa kunci dekripsi. Ini digunakan untuk melindungi data selama transmisi atau penyimpanan.
- Enkripsi berfungsi untuk:
  - **Melindungi kerahasiaan**: Memastikan bahwa hanya pihak yang berwenang yang dapat membaca data.
  - **Integritas data**: Memastikan bahwa data tidak diubah tanpa izin.
  - **Otentikasi**: Memastikan bahwa data berasal dari sumber yang sah.

---

# Kesimpulan
Proteksi dan sekuriti adalah dua komponen yang sangat penting dalam menjaga keamanan sistem komputer. Proteksi memastikan akses yang sah ke sumber daya, sedangkan sekuriti melindungi sistem dari ancaman yang dapat merusak kerahasiaan, integritas, dan ketersediaan data. Implementasi yang tepat dari mekanisme seperti autentikasi, enkripsi, dan monitoring ancaman adalah kunci untuk menjaga keamanan dan integritas sistem.
