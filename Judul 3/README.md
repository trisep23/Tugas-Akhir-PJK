## **JUDUL 3 : CONFIGURE VLANs AND TRUNKING - PHYSICAL MODE**

### **Link Demo YouTube**
[🔗 (youtube.com/watch?v=WOUc_oPExjA&feature=youtu.be)

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

**A. Ping PC-A ke PC-B (192.168.10.4)**
- **Hasil:**  
  Semua paket ICMP berhasil diterima tanpa kehilangan data (0% loss). Waktu respons antara 1–3 ms.  
- **Analisis:**  
  PC-A dan PC-B berada dalam **VLAN 10**, sehingga komunikasi dapat berlangsung langsung melalui port-port access yang terhubung ke switch dengan trunk aktif.  
  Hasil ini menunjukkan bahwa **konfigurasi VLAN 10 dan trunk antar-switch sudah benar** serta konektivitas antar-host di VLAN yang sama berjalan normal.
- **Kesimpulan:**  
  Koneksi antar PC di VLAN 10 **berhasil sepenuhnya**, menandakan konfigurasi VLAN 10 dan trunk port sudah berjalan sesuai harapan.

**B. Ping PC-A ke S1 (192.168.1.11)**
- **Hasil:**  
  Semua percobaan ping gagal dengan pesan *Request timed out* (100% loss).  
- **Analisis:**  
  PC-A berada di **VLAN 10** (subnet 192.168.10.0/24), sedangkan **S1 menggunakan VLAN 99** (subnet 192.168.1.0/24).  
  Karena tidak ada perangkat Layer 3 (router/multilayer switch) yang melakukan routing antar VLAN, maka paket ICMP tidak bisa melewati batas VLAN.  
  Kondisi ini juga menunjukkan bahwa mekanisme isolasi antar VLAN bekerja dengan baik.
- **Kesimpulan:**  
  Komunikasi antara VLAN 10 dan VLAN 99 **tidak dapat dilakukan**, sehingga fungsi pemisahan jaringan berbasis VLAN sudah diterapkan dengan benar.

  ---

#### **Gambar 2 - Ping PC-B Ke S2**
![2](https://github.com/user-attachments/assets/bedd5f63-b510-47a8-ae56-64d1f143d2b8)

Nilai statistik menunjukkan **100% packet loss**, artinya tidak ada paket ICMP yang berhasil mencapai tujuan.
**Analisis**
PC-B berada di jaringan **VLAN 10** dengan subnet `192.168.10.0/24`, sedangkan alamat tujuan `192.168.1.12` dimiliki oleh **VLAN 99** dengan subnet `192.168.1.0/24`.  
Kedua VLAN tersebut terpisah secara logis, sehingga perangkat pada VLAN 10 tidak dapat langsung mengakses perangkat di VLAN 99.  
Karena belum ada perangkat Layer 3 seperti **router** atau **multilayer switch** yang menjalankan fungsi *inter-VLAN routing*, maka paket ICMP yang dikirim PC-B tidak dapat diteruskan ke jaringan VLAN 99.
**Kesimpulan**
- **Ping PC-B ke S2 gagal (100% loss).**  
- Kegagalan ini menunjukkan bahwa segmentasi antar VLAN bekerja sebagaimana mestinya.  
- VLAN 10 dan VLAN 99 berhasil terisolasi, sehingga komunikasi antar jaringan hanya bisa dilakukan jika nanti ditambahkan perangkat Layer 3 untuk proses routing.

---

#### **Gambar 3 - Ping S1 Ke S2**
![3](https://github.com/user-attachments/assets/01ab2e9c-7b29-4bee-842b-94025f124ac5)

**A. Percobaan pertama:**  
  `Success rate is 60 percent (3/5)` → tiga paket berhasil, dua gagal.  
**B. Percobaan kedua:**  
  `Success rate is 100 percent (5/5)` → seluruh paket ICMP berhasil dikirim dan diterima.
**Analisis**
Hasil pengujian menunjukkan bahwa koneksi antara **S1 (192.168.1.11)** dan **S2 (192.168.1.12)** berhasil setelah beberapa kali percobaan.  
Kegagalan sebagian pada percobaan pertama (ditandai pola `..!!!`) disebabkan oleh proses **ARP (Address Resolution Protocol)** — di mana S1 harus terlebih dahulu mencari alamat MAC dari S2 sebelum dapat mengirimkan paket ICMP.  
Setelah entri ARP berhasil dibuat, semua ping berikutnya berhasil 100%.  
Hal ini menandakan bahwa **VLAN 99** sebagai VLAN manajemen sudah berfungsi dengan benar dan **trunk antar switch aktif**, memungkinkan komunikasi antar VLAN yang sama di dua switch berbeda.
**Kesimpulan**
1. Komunikasi antar switch S1 dan S2 **berhasil 100%** setelah proses ARP awal.  
2. **VLAN 99** telah dikonfigurasi dengan baik untuk fungsi manajemen jaringan.  
3. **Trunk antar switch** berjalan stabil dan dapat mengirimkan data antar VLAN manajemen dengan sempurna.

---

### **KESIMPULAN**
Berdasarkan hasil seluruh pengujian konektivitas, dapat disimpulkan bahwa konfigurasi VLAN dan trunking telah berjalan dengan baik.
Koneksi antar switch melalui VLAN 99 berfungsi normal sebagai jalur manajemen, dan komunikasi antar PC dalam VLAN 10 berhasil sepenuhnya melalui port trunk antar switch.
Sementara itu, koneksi antar VLAN masih tidak memungkinkan karena belum terdapat perangkat Layer 3 yang menjalankan fungsi routing.
Hasil ini menunjukkan bahwa VLAN efektif dalam memisahkan domain jaringan untuk meningkatkan keamanan dan efisiensi, sedangkan trunk berperan penting sebagai penghubung VLAN yang sama antar switch.

