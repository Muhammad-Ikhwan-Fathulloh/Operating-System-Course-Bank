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

## Aplikasi Sederhana dengan Docker

Proyek ini menunjukkan cara membuat aplikasi HTML dan JavaScript sederhana yang di-deploy menggunakan Docker.

---

### Struktur Proyek

```
simple-docker-app/
├── index.html
├── app.js
├── Dockerfile
```

---

### 1. File HTML: `index.html`
File HTML utama.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Aplikasi Docker Sederhana</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 50px;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <h1>Selamat Datang di Aplikasi Docker Sederhana</h1>
  <button id="clickMe">Klik Saya</button>
  <p id="output"></p>
  <script src="app.js"></script>
</body>
</html>
```

---

### 2. File JavaScript: `app.js`
Script untuk menangani event klik tombol.

```javascript
document.getElementById('clickMe').addEventListener('click', function () {
  document.getElementById('output').textContent = 'Halo dari JavaScript!';
});
```

---

### 3. Dockerfile
Dockerfile untuk mendeploy aplikasi menggunakan Nginx.

```dockerfile
# Gunakan Nginx sebagai base image
FROM nginx:alpine

# Salin file HTML dan JS ke direktori default Nginx
COPY index.html /usr/share/nginx/html/
COPY app.js /usr/share/nginx/html/

# Expose port 80 untuk akses HTTP
EXPOSE 80

# Jalankan Nginx
CMD ["nginx", "-g", "daemon off;"]
```

---

### 4. Build dan Jalankan Docker Container

#### a. Build Docker Image
Jalankan perintah berikut untuk membangun Docker image:

```bash
docker build -t simple-docker-app .
```

#### b. Jalankan Docker Container
Jalankan container dan mapping ke port 8080 di komputer lokal Anda:

```bash
docker run -d -p 8080:80 simple-docker-app
```

#### c. Akses Aplikasi
Buka browser Anda dan akses:

```
http://localhost:8080
```

---

### 5. Opsional: Push ke Docker Hub

#### a. Login ke Docker Hub

```bash
docker login
```

#### b. Tag Docker Image

```bash
docker tag simple-docker-app username-dockerhub/simple-docker-app
```

#### c. Push Image ke Docker Hub

```bash
docker push username-dockerhub/simple-docker-app
```

---

Aplikasi HTML dan JavaScript sederhana Anda sekarang berjalan di dalam Docker container! 🚀

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
