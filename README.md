# 🧩 TUGAS AKHIR PRAKTIKUM JARINGAN KOMPUTER

Repositori ini berisi hasil tugas akhir mata kuliah **Praktikum Jaringan Komputer** yang terdiri dari Setiap Judul Percobaan.  
Setiap proyek mencakup file topologi Cisco Packet Tracer, dokumentasi gambar topologi, serta link demonstrasi video di YouTube.

---

## ⚙️ **JUDUL 1 : BASIC SWITCH AND END DEVICE**

### 🎥 Link Demo YouTube
[🔗 Tugas Akhir Judul 1](https://youtu.be/PkrUnFUPkPY)

### 🖼️ Gambar Topologi
<img width="670" height="628" alt="Topologi Judul 1" src="https://github.com/user-attachments/assets/8e4be36e-efc9-42e4-b32b-d06016aeba55" />

### 📂 File
- `PJK_JUDUL1_BASIC SWITCH AND END DEVICE.pkt`
- `Topologi Judul 1.png`

---

## ⚙️ **JUDUL 2 : BUILD A SWITCH AND ROUTER NETWORK**

### 🎥 Link Demo YouTube
[🔗 Tugas Akhir Judul 2](https://youtu.be/scJT19ZU9PA)

### 🖼️ Gambar Topologi
<img width="680" height="458" alt="Topologi Judul 2" src="https://github.com/user-attachments/assets/1e66acf1-1c6e-4961-968b-db4994cedc6b" />

### 🖼️Gambar Hasil Ping 
#### 1. Ping PC-A Ke PC-B
<img width="525" height="388" alt="Cuplikan layar 2025-11-11 224744" src="https://github.com/user-attachments/assets/379be2d6-4c72-4f78-b948-4e3f43442231" />

#### 2. Ping PC-A Ke Switch
<img width="528" height="398" alt="Cuplikan layar 2025-11-11 224853" src="https://github.com/user-attachments/assets/433e886c-f0a3-4272-bb2d-f18aac7ec760" />

#### 3. Ping Switch Ke PC A
<img width="564" height="137" alt="Cuplikan layar 2025-11-11 224921" src="https://github.com/user-attachments/assets/0dfaecf2-96c1-4eab-bac5-e55b210a6940" />

#### 4. Ping Router Ke PC-B, Switch, dan PC-A
<img width="589" height="338" alt="Cuplikan layar 2025-11-11 225017" src="https://github.com/user-attachments/assets/7bb96f2e-329f-49d1-a66a-37b587eeb65e" />

---

### 📂 File
- `PJK2_Build a Switch and Router Network.pkt`
- `Topologi Judul 2.png`

---

## ⚙️ **JUDUL 3 : CONFIGURE VLANs AND TRUNKING - PHYSICAL MODE**

### 🎥 Link Demo YouTube
[🔗 Tugas Akhir Judul 3](https://youtu.be/WOUc_oPExjA)

### 🖼️ Gambar Topologi
<img width="953" height="447" alt="Topologi TA3" src="https://github.com/user-attachments/assets/8589433a-b2b4-4979-a823-f1f50bb38276" />

### **Hasil Pengujian**
#### **Gambar 1 - Ping PC-A ke PC-B, dan Ping PC-A ke S1**
![1](https://github.com/user-attachments/assets/fbfd7fe1-0cd2-4889-a327-abde362837b2)

#### **Gambar 2 - Ping PC-B Ke S2**
![2](https://github.com/user-attachments/assets/bedd5f63-b510-47a8-ae56-64d1f143d2b8)

#### **Gambar 3 - Ping S1 Ke S2**
![3](https://github.com/user-attachments/assets/01ab2e9c-7b29-4bee-842b-94025f124ac5)

### **KESIMPULAN**
Berdasarkan hasil seluruh pengujian konektivitas, dapat disimpulkan bahwa konfigurasi VLAN dan trunking telah berjalan dengan baik. Koneksi antar switch melalui VLAN 99 berfungsi normal sebagai jalur manajemen, dan komunikasi antar PC dalam VLAN 10 berhasil sepenuhnya melalui port trunk antar switch. Sementara itu, koneksi antar VLAN masih tidak memungkinkan karena belum terdapat perangkat Layer 3 yang menjalankan fungsi routing. Hasil ini menunjukkan bahwa VLAN efektif dalam memisahkan domain jaringan untuk meningkatkan keamanan dan efisiensi, sedangkan trunk berperan penting sebagai penghubung VLAN yang sama antar switch.

--

### 📂 File
- `PJK3_Configure VLANs and Trunking - Physical Mode.pkt`
- `Topologi Judul 3.png`

---

## ✍️ **Penyusun**
**Nama:** Tri Septiani  
**NPM:** 2315061036  
**Kelas:** PJK-C

---

> 📌 *Seluruh file dalam repositori ini dibuat menggunakan Cisco Packet Tracer dan disusun untuk memenuhi tugas akhir praktikum Jaringan Komputer.*
> 📌 *Akan di update selama masih menjalani praktikum.*
