# **Process Scheduling**

## **1. First Come First Serve (FCFS)**

### **Data Proses:**
| Proses | Waktu Kedatangan (Arrival Time) | Waktu Burst (Burst Time) |
|--------|--------------------------------|--------------------------|
| P1     | 0                              | 5                        |
| P2     | 1                              | 3                        |
| P3     | 2                              | 8                        |

### **Langkah Penyelesaian:**
1. Atur proses berdasarkan **Arrival Time**.
2. Eksekusi proses satu per satu berdasarkan urutan kedatangan.

### **Gantt Chart:**  
| P1 | P2 | P3 | 
0 5 8 16


### **Perhitungan:**
- **Turnaround Time (TAT):**  
  `TAT = Waktu Selesai - Waktu Kedatangan`  
  - TAT P1 = 5 - 0 = 5  
  - TAT P2 = 8 - 1 = 7  
  - TAT P3 = 16 - 2 = 14  

- **Waktu Tunggu (WT):**  
  `WT = TAT - Waktu Burst`  
  - WT P1 = 5 - 5 = 0  
  - WT P2 = 7 - 3 = 4  
  - WT P3 = 14 - 8 = 6  

### **Rata-rata TAT dan WT:**
- Rata-rata TAT = `(5 + 7 + 14) / 3 = 8.67`  
- Rata-rata WT = `(0 + 4 + 6) / 3 = 3.33`

---

## **2. Shortest Job First (SJF)**

### **Data Proses:**
| Proses | Waktu Kedatangan | Waktu Burst |
|--------|------------------|-------------|
| P1     | 0                | 6           |
| P2     | 2                | 4           |
| P3     | 4                | 9           |

### **Langkah Penyelesaian:**
1. Urutkan berdasarkan waktu burst terkecil.
2. Eksekusi proses.

### **Gantt Chart:**  
| P1 | P2 | P3 | 0 6 10 19


---

# **Banker's Algorithm**

## **Data:**
- **Jumlah Sumber Daya Tersedia (Available):**  
  A = 3, B = 3, C = 2  

- **Matriks Maksimum:**  
  | Proses | A | B | C |
  |--------|---|---|---|
  | P1     | 7 | 5 | 3 |
  | P2     | 3 | 2 | 2 |
  | P3     | 9 | 0 | 2 |

- **Matriks Alokasi:**  
  | Proses | A | B | C |
  |--------|---|---|---|
  | P1     | 0 | 1 | 0 |
  | P2     | 2 | 0 | 0 |
  | P3     | 3 | 0 | 2 |

## **Langkah Penyelesaian:**
1. Hitung **Need** = Maksimum - Alokasi.  
   Contoh untuk P1:  
   `Need(P1) = [7 - 0, 5 - 1, 3 - 0] = [7, 4, 3]`  

   Matriks Need:  
   | Proses | A | B | C |
   |--------|---|---|---|
   | P1     | 7 | 4 | 3 |
   | P2     | 1 | 2 | 2 |
   | P3     | 6 | 0 | 0 |

2. Cek apakah sumber daya yang tersedia cukup untuk memenuhi **Need** proses.  
   Jika ya, alokasikan sumber daya, tambahkan ke **Available**, lalu tandai proses sebagai selesai.

---

# **Memory Management**

## **1. First Fit**

### **Partisi Memori:**
| Partisi | Ukuran (KB) |
|---------|-------------|
| P1      | 100         |
| P2      | 500         |
| P3      | 200         |
| P4      | 300         |

### **Proses:**
| Proses | Ukuran (KB) |
|--------|-------------|
| P1     | 212         |
| P2     | 417         |
| P3     | 112         |

### **Langkah Penyelesaian:**
1. **P1 (212 KB):** Masuk ke Partisi 500 KB (partisi pertama yang cukup besar).  
   - Sisa memori: `500 - 212 = 288 KB`.

2. **P2 (417 KB):** Masuk ke Partisi 500 KB (yang tersisa cukup besar).  

3. **P3 (112 KB):** Masuk ke Partisi 200 KB.  

---

# **File System**

## **Single-Level Directory**

### **Contoh:**
- **Root Directory:**  
/root


- **File:**  
/root/file1.txt /root/file2.txt


Jika pengguna mencoba membuat file dengan nama yang sama (`file1.txt`), file lama akan ditimpa oleh file baru.


