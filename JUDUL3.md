## **JUDUL 3 : CONFIGURE VLANs AND TRUNKING - PHYSICAL MODE**

### **Link Demo YouTube**
[🔗 Tugas Akhir Judul 3](https://youtu.be/jbyunV39VjE)

---

### **Deskripsi Singkat**
Laporan ini merupakan dokumentasi hasil uji konektivitas dari konfigurasi VLAN dan Trunking (Physical Mode) di Cisco Packet Tracer.  
Tujuan dari percobaan ini adalah untuk memahami bagaimana VLAN memisahkan jaringan, serta bagaimana trunk memungkinkan perangkat dalam VLAN yang sama tetapi berbeda switch dapat berkomunikasi.

---

### **Gambar Topologi**
<img width="953" height="447" alt="Topologi TA3" src="https://github.com/user-attachments/assets/8589433a-b2b4-4979-a823-f1f50bb38276" />

---

### **Hasil Pengujian**
#### **Gambar 1 - Ping PC-A ke PC-B, dan Ping PC-A ke S1**
![1](https://github.com/user-attachments/assets/fbfd7fe1-0cd2-4889-a327-abde362837b2)

**1. Ping PC-A ke PC-B (192.168.10.4)**
- **Hasil:**  
  Semua paket ICMP berhasil diterima tanpa kehilangan data (0% loss). Waktu respons antara 1–3 ms.  
- **Analisis:**  
  PC-A dan PC-B berada dalam **VLAN 10**, sehingga komunikasi dapat berlangsung langsung melalui port-port access yang terhubung ke switch dengan trunk aktif.  
  Hasil ini menunjukkan bahwa **konfigurasi VLAN 10 dan trunk antar-switch sudah benar** serta konektivitas antar-host di VLAN yang sama berjalan normal.
- **Kesimpulan:**  
  Koneksi antar PC di VLAN 10 **berhasil sepenuhnya**, menandakan konfigurasi VLAN 10 dan trunk port sudah berjalan sesuai harapan.

**2. Ping PC-A ke S1 (192.168.1.11)**
- **Hasil:**  
  Semua percobaan ping gagal dengan pesan *Request timed out* (100% loss).  
- **Analisis:**  
  PC-A berada di **VLAN 10** (subnet 192.168.10.0/24), sedangkan **S1 menggunakan VLAN 99** (subnet 192.168.1.0/24).  
  Karena tidak ada perangkat Layer 3 (router/multilayer switch) yang melakukan routing antar VLAN, maka paket ICMP tidak bisa melewati batas VLAN.  
  Kondisi ini juga menunjukkan bahwa mekanisme isolasi antar VLAN bekerja dengan baik.
- **Kesimpulan:**  
  Komunikasi antara VLAN 10 dan VLAN 99 **tidak dapat dilakukan**, sehingga fungsi pemisahan jaringan berbasis VLAN sudah diterapkan dengan benar.
