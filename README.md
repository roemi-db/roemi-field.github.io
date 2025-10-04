# 📋 Notulen Final – Entry Data & Sistem Database ROEMI

Dokumen ini berisi hasil rapat final mengenai rancangan **Entry Data Individu, Event, Panitia, Lembaga/Komunitas, Dashboard, dan Report** dalam sistem **ROEMI**.  


---

## 🧑 Entry Data Individu

### 🔑 Identitas Dasar
- **Nama** → dipisahkan menjadi **Nama Depan** dan **Nama Belakang**.  
  - Nama belakang menjadi key pencarian.  
  - Cukup 1 kata untuk nama belakang.  
- **Title / Gelar** → opsional, ditampilkan jika peserta ingin.  
- **Gender** → digunakan, **Pronoun tidak ditampilkan**.  
- **Foto** → upload maksimal **5 MB**.  

### 📝 Profil
- Mendeskripsikan **unique selling point** & **spesialisasi menarik**.  
- Mencakup:  
  - Kapabilitas / Skills  
  - Capacity  
  - Interest  

### 🏢 Organisasi & Komunitas
- **Istilah diganti:** Organisasi → **Lembaga**.  
- Bisa diisi otomatis maupun manual.  
- Ada **fitur tambah** lembaga baru.  

### ☎️ Kontak
- Nomor telepon rigid, format **(kode negara)**.  

### 🌍 Lokasi
- **Wilayah** → kolom: Kota/Kabupaten + **Negara**.  
- Field **Alamat** ditambahkan (tidak mandatory).  
- **Provinsi** → fixed 38 provinsi.  

### 🗂️ Kategorisasi
- Field kategori → **admin Roemi** dapat menambah.  

### ♿ Kebutuhan Khusus
- **Kapabilitas** → dihapus.  
- **Kebutuhan Khusus** → tetap, tetapi:  
  - Opsi *“tidak ingin menyebutkan”* **dihapus**.  
  - Tambah field **Keterangan**.  

### 🤝 Kolaboraya
- Centang untuk opsi **WAG** dan **Aplikasi Pasar Kolaboraya**.  
- Checklist **consent to publish**.  
- Aktivitas → lookup dari **Event**, ditampilkan sebagai list.  
- **Import CSV** absensi kegiatan → format:  
- Field **Engagement dengan Roemi sejak kapan** → input tahun.  

---

## 🎟️ Entry Data Event

### 📌 Struktur
- **Penanggung Jawab & Kolaborator**  
- Tambah **peran** di samping field.  
- Istilah *Sponsor* → diganti **Kolaborator**.  
- Terminologi Kolaborator = *speaker, inspirator, pembicara live streaming*.  

### 👥 Peserta
- Tambah kategori peserta → checkbox **Tamu**.  
- **Field Peserta** → dipindahkan ke level **Session**.  
- **Field Pendukung** → dipindahkan ke level **Session**.  
- Input individu **tidak masuk langsung ke Event**, tapi bulk melalui **Entry Data Individu**.  

### 📂 Metadata
- Event dipahami juga sebagai metadata.  
- Section Session → ada tombol **Download CSV**.  

---

## 👨‍💼 Entry Data Crew/Staff

### 🔄 Terminologi
- Istilah **Crew/Staff** diganti → **Panitia**.  

### 👤 Identitas
- **Nama** → dipisahkan depan & belakang.  
- **Posisi & Peran**  
- Lookup ke Event.  
- Ditampilkan terkait Event.  
- Field **Divisi/Departemen** dihapus.  
- Tambah fitur **Tambah peran baru**.  

### 📥 Data Masuk
- CSV Panitia & Relawan → diinput bulk.  
- Format ditambah kolom **Peran**.  

### 📊 Rangkuman
- Di bagian akhir → rangkuman **Aktivitas Pasar Kolaboraya** (mirip individu).  
- Back-end → ada fitur **Import to Individu**.  

---

## 🏛️ Entry Data Organisasi / Komunitas

### 🔄 Terminologi
- **Organisasi → Lembaga**.  

### 📝 Deskripsi
- Menjelaskan **kekuatan lembaga/komunitas**.  

### 📍 Alamat & Kontak
- Field alamat disatukan dengan wilayah.  
- Nomor kontak & email = **milik lembaga**.  
- Jika tidak ada, field bisa dikosongkan.  

### 👤 Narahubung
- Lookup ke data individu (tampilkan: **Nama / Nomor HP / Email**).  
- Ada fitur **Tambah narahubung**.  

### 📂 Aktivitas
- Event yang pernah dihadiri → ditampilkan di bawah.  
- Engagement dengan Roemi sejak kapan → input tahun.  
- Checklist **consent to publish**.  

### ⚠️ Reset Button
- Reset → ada **pop-up konfirmasi**.  
- Diberi jarak cukup jauh dari tombol **Simpan**.  

---

## 📊 Dashboard

### Statistik Utama
- Jumlah **Komunitas, Individu, Lembaga**.  
- Statistik **Gender**.  
- Statistik **Sebaran Wilayah**.  
- Statistik **Top 10 fokus isu dan kegiatan inti**.  
- Statistik **Persentase Berkebutuhan Khusus** → ditampilkan dalam **pie chart**.  
- Bisa dipilih tampilan **persen (%)** atau **jumlah (n)**.  

### Time Series Database Kolaboraya
- **Per semester**: pertumbuhan data dihitung di akhir Juni & Desember.  
- **Cut off time**: diambil dari event berdasarkan **tahun engagement**.  
- Model grafik: **bar chart** per tahun/semester.  
- Menghitung **total individu/lembaga yang bergabung**.  

---

## 📑 Report

### Fitur Utama
- **Search dengan checklist filter**, misalnya:  
- Tahun  
- Lokasi  
- Gender  
- Peserta  
- Tamu  
- dll.  

### Output Data
- Data yang dihasilkan = **list individu/lembaga**, bukan summarize.  
- Tetap akan muncul **total jumlah** di akhir.  

### Format Export
- Report dapat diunduh dalam format:  
- **PDF**  
- **DOC**  
- **Excel**  

---

✨ Dokumentasi ini menjadi dasar implementasi **Entry Data Roemi**.  
💡 Format sudah disiapkan agar fleksibel untuk kebutuhan sistem backend maupun frontend.  
