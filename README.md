# 🛡️ CBT Aman (UjianAman) — Portal Ujian Anti Nyontek & Zero-Error

> **Platform Ujian Sekolah Bebas Nyontek, Semudah Google Form untuk Guru + Kiosk Pengunci Layar + Kebal Gangguan Jaringan (*Zero-Error*).**

![Status](https://img.shields.io/badge/Status-Siap%20Pakai%20v1.0-blue?style=flat-square)
![Arsitektur](https://img.shields.io/badge/Arsitektur-Zero--Dependency%20%26%20Offline--First-emerald?style=flat-square)
![Target](https://img.shields.io/badge/Sasaran-Sekolah%20%26%20Madrasah%20Indonesia-black?style=flat-square)
![Lisensi](https://img.shields.io/badge/Biaya-100%25%20Gratis%20untuk%20Guru-yellow?style=flat-square)

---

## 📌 1. Visi & Filosofi Sistem

Sistem ini dibangun berdasarkan dokumen spesifikasi produk **"Portal Ujian Anti Nyontek (CBT Aman) — Product & System Spec"** dengan prinsip utama:

1. **Membuat Kecurangan Menjadi Sulit & Terlihat Nyata, Bukan Mengklaim "Mustahil Dicurangi":**
   Peramban web tidak bisa melihat seluruh isi perangkat fisik siswa (misal: jika ada HP kedua di pangkuan). Oleh karena itu, sistem melakukan 3 hal:
   - Menghilangkan celah mudah (kunci layar penuh, blokir ganti tab, blokir copy-paste & devtools).
   - Merekam bukti objektif detik demi detik saat terjadi anomali.
   - Menyerahkan keputusan vonis akhir kepada guru/pengawas manusia (*Human-in-the-loop*).
2. **Ringan (*Light*):** Berjalan lancar di laptop spesifikasi rendah dan ponsel murah; siswa tidak perlu menginstal aplikasi (*zero-install*).
3. **Bukti, Bukan Tuduhan (*Evidence, not accusation*):** Sistem tidak pernah mendiskualifikasi siswa secara sepihak.
4. **Adil (*Fair & Zero-Error*):** Internet mati atau sinyal tersendat **tidak pernah** menghilangkan jawaban atau mengunci siswa. Jawaban tersimpan di memori perangkat lokal dalam waktu `<0.01 detik`.
5. **Transparan & Minim Data:** Siswa melihat protokol aturan sebelum mulai; tidak merekam audio/video berat yang membebani kuota atau privasi.

---

## ✨ 2. Modul & Fitur Utama

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       MODUL UTAMA PLATFORM CBT AMAN                         │
├─────────────────────┬──────────────────────────┬────────────────────────────┤
│   👨‍🏫 SISI GURU      │    🛡️ LIVE MONITOR       │       🎓 SISI SISWA        │
├─────────────────────┼──────────────────────────┼────────────────────────────┤
│ 1. Editor Soal      │ 1. Grid Meja Siswa       │ 1. Verifikasi & DND        │
│    ala Google Form  │    Real-time (12 Peserta)│ 2. Kiosk Layar Penuh       │
│ 2. Rumus KaTeX Math │ 2. Live Incident Stream  │ 3. Rumus LaTeX & Gambar    │
│ 3. Bank Soal Mapel  │ 3. Tombol 1-Klik Unlock  │ 4. Zero-Error Autosave     │
│ 4. Aturan Strike    │ 4. Peringatan Interaktif │ 5. Toleransi Kartu Kuning  │
│ 5. Ekspor CSV/Print │ 5. Triage Status Siswa   │ 6. Layar Lockout 10 Menit  │
└─────────────────────┴──────────────────────────┴────────────────────────────┘
```

### 🧭 Navigasi Sidebar Kiri "Timbul Tenggelam"
- **Layar Bebas & Bersih:** Seluruh menu peran dan kontrol dipindahkan ke **Sidebar sebelah kiri** yang dapat **timbul tenggelam** (*collapsible drawer*).
- **Tombol Pemicu (*Trigger*):** Klik tombol **`[ ☰ Menu CBT ]`** di bilah atas untuk memunculkan sidebar, atau klik tombol **`[ Sembunyikan ]` / area luar** untuk menenggelamkannya.
- **Pintasan Keyboard (*Shortcuts*):** Tekan tombol **`Ctrl + M`** (atau `Cmd + M`) untuk membuka/menutup menu, atau tekan tombol **`Escape`** untuk menutup.
- **Otomatis Tenggelam Saat Ujian:** Ketika siswa menekan *Mulai Ujian*, sidebar dan seluruh bilah navigasi otomatis disembunyikan 100% demi integritas *Kiosk Mode* yang fokus tanpa distraksi.

### A. Ruang Ujian Siswa (Student Kiosk Room)
- **Onboarding Transparansi:** Edukasi mengaktifkan mode *Jangan Ganggu* (Do Not Disturb), persetujuan layar penuh, dan penjelasan jaminan *zero-error*.
- **Proteksi Layar Penuh & Anti-Alt-Tab:** Mendeteksi `visibilityState`, pelepasan layar penuh, upaya copy/paste, dan tombol pintasan inspect element.
- **Watermark Rahasia Anti-Bocor:** Teks samar Nama Siswa, NISN, dan Token melayang di latar belakang, membuat foto layar langsung terlacak jika disebarkan di grup chat.
- **Zero-Error Offline Resilience:** Auto-save instan ke penyimpanan lokal. Saat koneksi internet mati, siswa tetap dapat membaca dan menjawab soal seperti biasa.
- **Aturan Strike & Layar Lockout 10 Menit:**
  - *Toleransi 1x:* Kartu kuning peringatan 5 detik.
  - *Pelanggaran ke-2:* Layar penalti merah berdenyut dengan hitungan mundur **10:00 Menit**.
  - *Pintu Darurat Guru:* Masukkan PIN Pengawas (default: `1234`) untuk membuka kunci seketika tanpa menunggu 10 menit.

### B. Kelola Ujian & Bank Soal (Teacher Portal)
- **Editor Soal Semudah Google Form:** Mendukung Pilihan Ganda (A-E), Benar/Salah, Isian Singkat, dan Essay Uraian.
- **Dukungan Formula Matematika & Sains:** Menggunakan KaTeX LaTeX (contoh: `$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$` atau `$P = \rho \cdot g \cdot h$`).
- **Pengaturan Kebijakan Integritas (Strike Policy):**
  - *Mode 1: Rekam Saja (Record only)* — Ujian santai/formatif.
  - *Mode 2: Peringatan lalu Kunci (Warn then Lock)* — Standar ujian sekolah.
  - *Mode 3: Ketat (Strict Lock)* — Kunci langsung pada pelanggaran pertama.
- **Bank Soal Terorganisir:** Filter berdasarkan mata pelajaran (IPA, Matematika, Bahasa Indonesia) dan tingkat kesulitan.

### C. Live Monitor Pengawas Real-Time (Proctoring)
- **Daftar Meja Siswa Real-time:** Status indikator visual:
  - 🟢 **Fokus / Aman** (Layar penuh aktif)
  - 🟡 **Peringatan 1x** (Pernah keluar layar dalam batas toleransi)
  - 🔴 **Terkunci Penalti** (Sedang dalam masa lockout 10 menit)
  - ⚪ **Offline (HP Safe)** (Sinyal sekolah drop tapi siswa tetap aman mengerjakan)
  - 🔵 **Selesai** (Jawaban terkumpul)
- **Aksi Cepat 1-Klik Pengawas:** Tombol `[Buka Kunci]`, `[Kirim Peringatan Langsung]`, dan `[Audit Timeline]`.
- **Feed Log Insiden Detik demi Detik:** Mencatat waktu, nama siswa, jenis pelanggaran, durasi keluar layar, dan nomor soal yang sedang dibuka.

### D. Hasil, Koreksi Essay & Triage Integritas
- **Klasifikasi Triage Objektif (Spec Section 4):**
  - **CLEAR:** Bersih tanpa anomali.
  - **REVIEW:** Anomali minor (1x keluar layar singkat atau toleransi).
  - **SERIOUS:** Terkunci berkali-kali atau total waktu keluar layar `>30 detik`.
- **Timeline Integritas Per-Siswa (Audit Trail):** Garis waktu peristiwa kronologis detail untuk ditinjau guru.
- **Form Putusan Guru (Human Verdict):** Pilihan Disahkan (Cleared), Peringatan Lisan, Penyesuaian Nilai (Potong Nilai), atau Batalkan Ujian disertai Berita Acara.
- **Ekspor Nilai:** 1-klik unduh rekapan CSV / Excel serta cetak format Berita Acara resmi.

---

## 🚀 3. Cara Menjalankan & Membuka Website

Aplikasi ini berarsitektur **Zero-Dependency & Pure Web Standards (HTML5, Tailwind CSS, Lucide Icons, KaTeX)**.

### Opsi 1: Buka Langsung di Peramban (Cara Paling Cepat)
Cukup klik dua kali (*double click*) berkas:
```text
cbt-aman-portal/index.html
```
pada peramban Google Chrome, Safari, Mozilla Firefox, atau Microsoft Edge.

### Opsi 2: Menggunakan Server Lokal Python
Jalankan perintah berikut di terminal:
```bash
cd "cbt-aman-portal"
python3 -m http.server 8080
```
Buka tautan di browser: **`http://localhost:8080`**.

---

## 🌐 4. Cara Publikasi Gratis untuk Sekolah (Deployment)

Karena aplikasi ini sepenuhnya berbasis web statis tanpa dependensi backend rumit:
1. **GitHub Pages:**
   - Unggah folder `cbt-aman-portal` ke repositori GitHub.
   - Aktifkan GitHub Pages di tab *Settings > Pages*.
   - Siswa bisa mengakses melalui link sekolah (contoh: `https://sekolah.github.io/cbt-aman`).
2. **Cloudflare Pages / Vercel:**
   - Seret dan lepas (*drag & drop*) folder `cbt-aman-portal` ke dashboard Vercel / Cloudflare Pages.
   - Langsung aktif dengan domain kustom gratis dan CDN berkecepatan tinggi di Indonesia.

---

## 🔑 5. Informasi Akun & Data Bawaan

| Item | Nilai Default |
| --- | --- |
| **Token Ujian Utama** | `IPA-8A` |
| **PIN Buka Kunci Pengawas** | `1234` |
| **Paket Soal Demo** | PAS IPA Terpadu Kelas 8 (10 Soal Lengkap: PG, Isian, Essay, Rumus KaTeX) |
| **Jumlah Siswa di Monitor** | 12 Siswa Demo (Lengkap dengan status Aman, Peringatan, Terkunci, dan Offline) |

---

*Dikembangkan dengan penuh dedikasi untuk menjaga kejujuran dan memajukan pendidikan Indonesia.*
