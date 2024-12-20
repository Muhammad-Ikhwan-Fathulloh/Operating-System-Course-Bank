# Belajar Docker untuk Sistem Operasi

## Pendahuluan
Docker adalah platform open-source yang dirancang untuk mengotomatisasi proses penyebaran aplikasi dalam container. Container ini memungkinkan aplikasi berjalan dengan dependensi yang dibutuhkan dalam lingkungan yang terisolasi. Dalam konteks sistem operasi, Docker mempermudah pengelolaan aplikasi multi-platform dan integrasi pengembangan serta penyebaran aplikasi.

---

## Apa Itu Docker?
Docker adalah alat yang memungkinkan developer untuk:

- **Membuat container**: Unit independen untuk menjalankan aplikasi.
- **Menyebarkan container**: Menyediakan aplikasi di lingkungan apa pun, baik itu lokal, server, atau cloud.
- **Mengelola container**: Melakukan scaling, pembaruan, atau pemantauan container.

Docker mendukung banyak sistem operasi seperti Linux, Windows, dan macOS.

---

## Komponen Utama Docker

1. **Docker Engine**: Mesin inti untuk membuat dan menjalankan container.
2. **Docker Image**: File template yang berisi semua komponen yang diperlukan untuk menjalankan aplikasi.
3. **Docker Container**: Lingkungan runtime yang menjalankan aplikasi berdasarkan image.
4. **Docker Hub**: Repositori untuk menyimpan dan berbagi image Docker.
5. **Docker Compose**: Alat untuk mendefinisikan dan menjalankan aplikasi multi-container.

---

## Instalasi Docker

### Langkah Instalasi Docker
1. **Windows**:
   - Unduh Docker Desktop dari [situs resmi Docker](https://www.docker.com/products/docker-desktop).
   - Instal dan ikuti petunjuk konfigurasi.
   - Aktifkan fitur WSL2 untuk integrasi Linux.

2. **Linux**:
   - Jalankan perintah berikut:
     ```bash
     sudo apt update
     sudo apt install docker.io
     sudo systemctl start docker
     sudo systemctl enable docker
     ```

3. **macOS**:
   - Unduh Docker Desktop dari [situs resmi Docker](https://www.docker.com/products/docker-desktop).
   - Instal seperti aplikasi biasa di macOS.

---

## Perintah Dasar Docker

### Perintah Umum Docker
| Perintah                          | Deskripsi                                    |
|-----------------------------------|----------------------------------------------|
| `docker --version`                | Mengecek versi Docker                        |
| `docker images`                   | Melihat daftar image yang tersedia           |
| `docker ps`                       | Melihat container yang sedang berjalan       |
| `docker ps -a`                    | Melihat semua container, termasuk yang mati  |
| `docker run`                      | Menjalankan container baru                  |
| `docker stop [container_id]`      | Menghentikan container yang berjalan         |
| `docker rm [container_id]`        | Menghapus container                         |
| `docker rmi [image_id]`           | Menghapus image                              |

---

## Membuat Aplikasi Sederhana dengan Docker

### Langkah 1: Membuat Dockerfile
Buat file bernama `Dockerfile`:
```dockerfile
# Menggunakan base image
FROM python:3.9-slim

# Menyalin file aplikasi ke container
COPY app.py /app/app.py

# Menetapkan direktori kerja
WORKDIR /app

# Menjalankan aplikasi saat container dijalankan
CMD ["python", "app.py"]
```

### Langkah 2: Menyusun Aplikasi Python
Buat file `app.py`:
```python
print("Halo, Docker!")
```

### Langkah 3: Build dan Jalankan Docker Container
1. **Build Image**:
   ```bash
   docker build -t my-python-app .
   ```

2. **Jalankan Container**:
   ```bash
   docker run my-python-app
   ```

---

## Docker Compose untuk Aplikasi Multi-Container

Docker Compose mempermudah pengelolaan aplikasi dengan banyak container. Misalnya, aplikasi web dengan database.

### Contoh: Aplikasi Web dengan Database

1. Buat file `docker-compose.yml`:
   ```yaml
   version: '3.8'
   services:
     web:
       image: nginx:latest
       ports:
         - "8080:80"

     db:
       image: postgres:latest
       environment:
         POSTGRES_USER: user
         POSTGRES_PASSWORD: password
         POSTGRES_DB: mydb
   ```

2. Jalankan aplikasi:
   ```bash
   docker-compose up
   ```

3. Akses aplikasi di `http://localhost:8080`.

---

## Latihan Praktis

### 1. Membuat Container dengan Web Server
- Gunakan image `nginx`.
- Jalankan perintah berikut:
  ```bash
  docker run -d -p 8080:80 nginx
  ```
- Akses web server di `http://localhost:8080`.

### 2. Menjalankan PostgreSQL dengan Docker
- Gunakan image `postgres`.
- Jalankan perintah:
  ```bash
  docker run -d --name my-postgres -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 postgres
  ```

---

## Manfaat Docker dalam Sistem Operasi
1. **Portabilitas**: Aplikasi berjalan di lingkungan yang sama, terlepas dari sistem operasi host.
2. **Efisiensi**: Lebih ringan dibandingkan virtual machine.
3. **Pengelolaan Versi**: Mudah untuk rollback ke versi sebelumnya.
4. **Otomasi**: Mendukung CI/CD pipeline dengan mudah.

---

## Kesimpulan
Docker adalah alat penting yang membantu pengembang dan admin sistem untuk mengelola aplikasi secara efisien. Dengan memahami dasar dan praktiknya, Anda dapat meningkatkan kemampuan dalam manajemen sistem operasi modern.

---

## Referensi Tambahan
1. [Dokumentasi Resmi Docker](https://docs.docker.com)
2. [Docker Hub](https://hub.docker.com)
