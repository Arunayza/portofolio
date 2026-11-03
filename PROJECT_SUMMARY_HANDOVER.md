# 📘 Rangkuman Arsitektur & Dokumentasi Handover Proyek Portofolio
**Pemilik Portofolio:** Armand Maulana, S.Tr.T.  
**Domain Keahlian:** IT Support, Network & Infrastructure, Software & Digital Solutions  
**Tanggal Update Terakhir:** 3 November 2026  
**Status Repositori:** Git Branch `main` (Up-to-date)  
**File Utama Proyek:**
- [index.html](file:///f:/Portfolio/index.html) — Aplikasi Utama Frontend (Bento Grid + Tailwind CSS + Dark Mode)
- [admin.html](file:///f:/Portfolio/admin.html) — Admin Studio & Client-Side CMS dengan Split View Live Preview
- [data.json](file:///f:/Portfolio/data.json) — Basis Data Tunggal (Single Source of Truth)
- [design.md](file:///f:/Portfolio/design.md) — Acuan Profil, Transkrip Prestasi, & Spesifikasi CV

---

## 🧭 Ikhtisar & Tujuan Proyek
Aplikasi portofolio ini dibangun tanpa framework backend (Client-Side Jamstack murni) dengan performa instan, dukungan penuh tema gelap (*Dark Mode*), animasi transisi halus, dan kemampuan manajemen data mandiri melalui [admin.html](file:///f:/Portfolio/admin.html) yang langsung terhubung ke [data.json](file:///f:/Portfolio/data.json) serta penyimpanan browser (*LocalStorage*).

---

## 🛠️ Ringkasan Pembaruan Utama yang Telah Diterapkan

### 1. Section 01: Pendidikan & Prestasi Ilmiah (`#pendidikan`)
- **Struktur Layout 2-Card Bento:**
  - **Card Kiri (lg:col-span-7): Pendidikan Formal & Riset:**
    - Gelar: `Sarjana Terapan Teknik (S.Tr.T.)`.
    - Perguruan Tinggi: Politeknik Negeri Samarinda (POLNES) dengan logo institusi resmi di sebelah kiri teks.
    - Jurusan & Prodi: Jurusan Teknologi Informasi — D4 Teknologi Rekayasa Komputer.
    - Periode & IPK: `2022 — 2026`, Badge IPK `3.91 / 4.00` dengan predikat `Cum Laude`.
    - Mata Kuliah Relevan: 6 tag badge (Infrastruktur Jaringan, Otomasi IoT, Administrasi Server, Web, AI Citra Digital, Keamanan Sistem).
    - Sub-Card Tugas Akhir / Skripsi: Judul dinamis (dapat diubah di Admin).
    - Sub-Card Publikasi Jurnal: Jurnal JAIEA, status *Published*, dan link tautan resmi DOI.
  - **Card Kanan (lg:col-span-5): Khusus Hak Cipta (HAKI) Kemenkumham RI:**
    - Format **Carousel Slider Interaktif**: Tombol navigasi prev/next (`‹` `›`), indikator halaman (`1 / 2`), dan titik *dot indicator*.
    - Bingkai Pratinjau Sertifikat: Tinggi vertikal proporsional (`h-64 sm:h-80 lg:h-[360px]`) yang memenuhi kartu dan mengeliminasi ruang kosong canggung di bawahnya.
    - Nomor Dokumen Resmi yang Valid:
      - **HAKI 1:** No. Ciptaan `EC002026098202`, No. Pencatatan `001304461`, Tanggal `26 Juni 2026`, Jenis Karya `Program Komputer`.
      - **HAKI 2:** No. Ciptaan `EC00202448914`, No. Pencatatan `000624268`, Tanggal `12 Juni 2024`, Jenis Karya `Program Komputer`.
    - Tombol Aksi: *"Pratinjau Surat"* (Lightbox Zoom) & *"Unduh PDF"*.

### 2. Section 02: Pengalaman Kerja & Profesional (`#pengalaman`)
- **Struktur Layout Vertical Timeline Minimalis:**
  - Garis vertikal timeline ramping di sebelah kiri (`border-l-2 border-slate-200 dark:border-slate-800`).
  - Titik penanda (*node dot*) bercincin biru di setiap kartu pengalaman.
  - Disusun secara **kronologis terbalik** (pengalaman terbaru di posisi teratas):
    1. **Pengalaman Mengajar / Ruangguru** (September 2024 – Sekarang)
    2. **Pengadilan Tata Usaha Negara (PTUN) Samarinda** (Januari 2026 – Mei 2026)
  - Setiap kartu memuat:
    - Logo perusahaan/instansi di sebelah kiri atas teks (frame rounded modern).
    - **Dukungan Otomatis Link Google Drive pada Logo:** Mengonversi link berbagi Google Drive (`drive.google.com/file/d/...` atau `drive.google.com/open?id=...`) secara otomatis menjadi URL CDN gambar langsung (`https://lh3.googleusercontent.com/d/...`).
    - Nama instansi, peran/jabatan, dan divisi.
    - Badge rentang waktu / periode di pojok kanan atas.
    - **Deskripsi singkat dalam satu paragraf narasi mengalir** (tanpa *bullet points*).
    - Tombol interaktif rounded bernuansa biru muda elegan: **"Lihat detail dan Dokumentasi →"**.
- **Modal Pop-up Terpisah Dinamis & Terisolasi (`#experience-modal`):**
  - **Header Interaktif:** Menampilkan logo institusi (dengan converter Google Drive), nama instansi, jabatan, divisi, dan periode pengalaman yang bersangkutan.
  - **Highlight / Spotlight Metrik Dinamis per Pengalaman:**
    - Jika metrik diisi, tampil bento card metrik.
    - Jika metrik dikosongkan, bagian ini otomatis disembunyikan agar pop-up langsung fokus pada narasi dan dokumentasi tanpa menampilkan kotak angka 0 semu.
  - **Tugas & Lingkup Teknis Dinamis:**
    - Khusus untuk item yang memiliki daftar tugas. Tidak lagi mengalami *fallback* ke tanggung jawab IT Support instansi lain.
  - **Isolasi Galeri Dokumentasi Foto & Sistem:** Setiap pengalaman memiliki koleksi dokumentasinya sendiri (`item.web_systems`). Pengalaman baru yang belum memiliki foto akan menampilkan *empty-state* bersih tanpa membocorkan dokumentasi dari instansi lain.

### 3. Admin Studio & Live Editor (`admin.html`)
- **Tab Pengalaman Kerja (Multi-Experience Manager Lengkap):**
  - Tombol **`+ Tambah Pengalaman Baru`** untuk menyisipkan pengalaman baru di posisi teratas (#1).
  - Input field: Nama Perusahaan/Instansi, Divisi, Peran/Jabatan, Periode, Logo URL, dan Paragraf Narasi.
  - **Auto Converter & Preview Logo Google Drive:** Input logo langsung mengonversi link Google Drive dan menampilkan thumbnail pratinjau di samping kolom input.
  - **Editor Metrik Spotlight:** Tombol `+ Tambah Metrik` dan `Hapus` dengan field Nilai/Angka, Label Utama, dan Keterangan Sublabel per item pengalaman.
  - **Editor Tugas & Ruang Lingkup:** Tombol `+ Tambah Tugas` dan `Hapus` dengan field Judul Tugas dan Uraian Tugas per item pengalaman.
  - **Editor Dokumentasi & Foto Khusus (2 Metode Penambahan Foto):**
    1. **Upload File Lokal:** Tombol `📁 Upload File Lokal` untuk memilih file langsung dari komputer.
    2. **Paste Link URL / Google Drive:** Kolom teks input link + tombol `+ Tambah Link Foto` yang mengonversi Google Drive link otomatis ke direct image URL.
    - Caption foto dan tombol hapus per foto.
    - Tombol `+ Tambah Dokumentasi` menambahkan kegiatan khusus ke array `item.web_systems` milik item pengalaman yang bersangkutan (tanpa bug hoisting/timpa fungsi legacy).
- **Tab Pendidikan & Sertifikasi (HAKI Editor):**
  - Form input No. Ciptaan, No. Pencatatan, Tanggal Dokumen, dan Jenis Karya tersinkronisasi otomatis via `syncHakiWithEducation()`.
- **Seluruh 8 Tab Editor Berfungsi Normal:**
  - *Profile, Metrics, Education, Experience, Projects, Certifications, Skills, Raw JSON*.

---

## 📌 Panduan untuk AI / Pengembang Berikutnya
1. **Google Drive URL Parsing:**
   - Gunakan selalu fungsi `convertGoogleDriveImageUrl(url)` ketika merender gambar atau logo yang berpotensi berasal dari link Google Drive publik.
2. **Penanganan Array Pengalaman:**
   - Setiap item dalam `currentData.experience.items` memiliki array `web_systems: []` sendiri.
   - Fungsi `addExperienceProjectLink(expIdx)` dan `addExperienceSystemImageUrl(expIdx, sysIdx)` menerima indeks pengalaman `expIdx` untuk menjamin isolasi data antar instansi.
