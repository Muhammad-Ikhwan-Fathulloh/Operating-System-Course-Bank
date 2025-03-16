### **Membuat Custom OS Linux dengan Docker: Panduan Lengkap** 🚀  

Membangun **Custom OS Linux** menggunakan **Docker** sangat berguna untuk pengujian, pengembangan, dan lingkungan runtime yang ringan. Dalam panduan ini, kita akan membuat **OS Linux minimal berbasis Debian atau Alpine**, menambahkan **layanan SSH & Web Server**, serta **mendukung penyimpanan data persistent**.

---

## **🛠 1. Memahami Konsep Custom OS dengan Docker**
### **🔹 Apa Itu Custom OS di Docker?**  
Alih-alih membuat OS dari nol, kita akan **membuat lingkungan runtime kustom** berbasis **Debian atau Alpine** yang dapat digunakan sebagai OS virtual dalam container Docker.

### **🔹 Kenapa Menggunakan Docker untuk Custom OS?**  
✅ **Ringan & Cepat** – Tidak memerlukan VM, hanya membutuhkan container.  
✅ **Dapat Disesuaikan** – Bisa menambahkan paket, tools, atau service sesuai kebutuhan.  
✅ **Portabel** – Bisa dijalankan di berbagai sistem (Windows, Linux, Mac).  
✅ **Mudah Dikelola** – Bisa dibuat ulang dengan mudah menggunakan Dockerfile.  

---

## **🛠 2. Membuat OS Linux Kustom dengan Docker**
Kita akan membuat **dua versi Custom OS**:
1. **Berbasis Debian** → Cocok untuk penggunaan umum.
2. **Berbasis Alpine** → Cocok untuk aplikasi ringan.

---

### **📌 2.1 Custom OS Berbasis Debian**
**➡️ Fitur yang Ditambahkan:**
- Paket dasar seperti `vim`, `curl`, `nano`, `htop`, dll.
- Layanan **SSH Server** agar bisa diakses secara remote.
- Layanan **Web Server (NGINX)** untuk hosting halaman sederhana.

**📌 Dockerfile untuk Custom OS Debian:**
```dockerfile
# Menggunakan Debian sebagai base image
FROM debian:latest

# Label metadata
LABEL maintainer="Ikhwan <muhammadikhwanfathulloh17@gmail.com>"
LABEL description="Custom Debian Linux OS with SSH and Web Server"

# Set timezone & install paket dasar
RUN apt-get update && apt-get install -y \
    curl \
    wget \
    vim \
    nano \
    htop \
    sudo \
    systemd \
    openssh-server \
    nginx \
    && rm -rf /var/lib/apt/lists/*

# Buat direktori SSH
RUN mkdir /var/run/sshd

# Tambahkan user baru
RUN useradd -m -s /bin/bash user && \
    echo "user:password" | chpasswd && \
    usermod -aG sudo user

# Expose port untuk SSH & Web Server
EXPOSE 22 80

# Mulai layanan SSH dan Web Server saat container berjalan
CMD service ssh start && service nginx start && bash
```

**📌 Cara Build & Jalankan OS:**
```sh
docker build -t custom-debian-os .
docker run -d -p 2222:22 -p 8080:80 --name debian-os custom-debian-os
```

**📌 Akses SSH ke dalam Container:**
```sh
ssh user@localhost -p 2222
```

**📌 Cek Web Server (Buka Browser):**
```
http://localhost:8080
```
(Anda akan melihat halaman default NGINX)

---

### **📌 2.2 Custom OS Berbasis Alpine (Lebih Ringan)**
Jika ingin sistem yang lebih kecil dan cepat, gunakan **Alpine Linux**.  
Base image **Alpine** hanya **5MB**, sangat cocok untuk **container ringan**.

**📌 Dockerfile untuk Custom OS Alpine:**
```dockerfile
# Menggunakan Alpine sebagai base image
FROM alpine:latest

# Install paket dasar & OpenSSH
RUN apk add --no-cache \
    bash \
    nano \
    htop \
    curl \
    openssh \
    nginx \
    && rc-update add sshd \
    && rc-update add nginx

# Buat direktori SSH
RUN mkdir -p /var/run/sshd

# Buat user baru
RUN adduser -D user && echo "user:password" | chpasswd

# Expose port SSH & Web Server
EXPOSE 22 80

# Jalankan SSH dan NGINX saat container berjalan
CMD service sshd start && service nginx start && sh
```

**📌 Cara Build & Jalankan OS:**
```sh
docker build -t custom-alpine-os .
docker run -d -p 2223:22 -p 8081:80 --name alpine-os custom-alpine-os
```

**📌 Akses SSH ke dalam Container:**
```sh
ssh user@localhost -p 2223
```

**📌 Cek Web Server (Buka Browser):**
```
http://localhost:8081
```

---

## **🛠 3. Menyimpan Konfigurasi Secara Persistent**
**Masalah:**  
Saat container dimatikan, semua perubahan di dalamnya akan hilang.

**Solusi:**  
Gunakan **Volume Docker** agar data tetap tersimpan.

**📌 Jalankan Container dengan Volume Persistent:**
```sh
docker run -d -p 2222:22 -p 8080:80 \
    -v $(pwd)/data:/var/www/html \
    --name debian-os custom-debian-os
```
Sekarang, semua file di dalam **/var/www/html** di container akan tetap ada meskipun container dihentikan.

---

## **🛠 4. Menjalankan Container Sebagai OS Virtual**
Anda bisa **masuk ke dalam container** seolah-olah itu adalah OS Linux biasa.

**📌 Masuk ke Container:**
```sh
docker exec -it debian-os bash
```

**📌 Cek Proses Berjalan di Dalamnya:**
```sh
ps aux
```

**📌 Jalankan Perintah sebagai Superuser:**
```sh
sudo apt update
```

---

## **🔥 Kesimpulan**
✔ **OS Kustom di Docker** = **Distro Linux Minimal + Layanan Tambahan**  
✔ **Debian untuk fitur lengkap, Alpine untuk ringan**  
✔ **Bisa menambahkan SSH, Web Server, dan persistent storage**  
✔ **Portabel & dapat dijalankan di mana saja dengan Docker**  

Dengan metode ini, Anda bisa membuat **sistem operasi Linux kustom berbasis Docker** untuk berbagai kebutuhan pengembangan atau produksi! 🚀💡
