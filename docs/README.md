# Dokumentasi Proyek Pomodoro (Pomokit)

## 📋 Deskripsi Proyek

**Pomokit** adalah aplikasi timer Pomodoro berbasis command line yang diimplementasikan dalam bahasa Go. Aplikasi ini mengkombinasikan teknik Pomodoro tradisional dengan fitur-fitur modern seperti integrasi WhatsApp, screenshot otomatis, monitoring aktivitas mouse, dan analisis performa website menggunakan GTmetrix.

## 🏷️ Tentang Nama "Pomokit"

**Pomokit** adalah gabungan dari dua kata:
- **"Pomo"** - Singkatan dari **Pomodoro**, teknik manajemen waktu yang dikembangkan oleh Francesco Cirillo pada akhir 1980-an
- **"Kit"** - Berarti **perangkat/peralatan lengkap** dalam bahasa Inggris

### Asal Usul Teknik Pomodoro:
- **Pomodoro** berasal dari kata Italia yang berarti "tomat"
- Dinamakan demikian karena Cirillo menggunakan timer dapur berbentuk tomat saat mengembangkan teknik ini
- Teknik ini menggunakan interval waktu 25 menit untuk fokus kerja, diikuti istirahat pendek

### Mengapa "Pomokit":
- **"Kit"** menandakan bahwa aplikasi ini adalah **perangkat lengkap** untuk menerapkan teknik Pomodoro
- Tidak hanya timer sederhana, tetapi **toolkit komprehensif** yang mencakup:
  - Timer Pomodoro tradisional
  - Monitoring produktivitas
  - Integrasi komunikasi (WhatsApp)
  - Analisis performa website
  - Anti-cheat system
  - Reporting otomatis

**Pomokit = Pomodoro + Toolkit = Perangkat Lengkap untuk Teknik Pomodoro**

### Filosofi Nama:
- **"Pomo"** - Mengadopsi prinsip teknik Pomodoro yang terbukti efektif
- **"Kit"** - Menyediakan semua tools yang diperlukan dalam satu paket
- **Gabungan** - Menciptakan solusi yang lebih dari sekadar timer biasa

### Nilai yang Diwakili:
- **Efektivitas** - Berdasarkan teknik yang sudah teruji
- **Kelengkapan** - Semua fitur yang diperlukan tersedia
- **Modernitas** - Menggunakan teknologi terkini
- **Akuntabilitas** - Memberikan bukti dan laporan kerja
- **Kolaborasi** - Integrasi dengan platform komunikasi

### Versi Aplikasi:
- **Versi Saat Ini**: v0.2.4
- **Platform**: Cross-platform (Windows, Linux, macOS)
- **Bahasa Pemrograman**: Go 1.24.1+
- **Lisensi**: Open Source

## 🎯 Tujuan Proyek

Aplikasi ini dirancang untuk membantu pengguna dalam:
- Menerapkan teknik Pomodoro untuk manajemen waktu yang efektif
- Memantau produktivitas melalui screenshot otomatis
- Melaporkan kemajuan kerja ke grup WhatsApp
- Menganalisis performa website yang sedang dikerjakan
- Mencegah kecurangan dengan monitoring aktivitas mouse

## 🏗️ Arsitektur Sistem

### Komponen Utama:
1. **Timer Pomodoro** - Mengatur siklus kerja dan istirahat
2. **WhatsApp Integration** - Mengirim laporan dan notifikasi
3. **Screenshot System** - Mengambil screenshot otomatis
4. **Mouse Activity Monitor** - Memantau aktivitas mouse
5. **GTmetrix Integration** - Analisis performa website
6. **Display System** - Tampilan timer visual

## 🔄 Alur Penggunaan (Workflow)

### 1. Persiapan Awal
```
┌─────────────────┐
│   Jalankan App  │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│  Check Updates  │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│ Init Mouse Hook │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│ Download Assets │
└─────────┬───────┘
```

### 2. Input Konfigurasi
```
┌─────────────────┐
│ Input WA Group  │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│ Input URL Task  │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│ Input Milestone │
└─────────┬───────┘
```

### 3. Setup WhatsApp
```
┌─────────────────┐
│  Connect WA     │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│   QR Code       │
│   (if needed)   │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│ Send Start      │
│ Notification    │
└─────────┬───────┘
```

### 4. Siklus Pomodoro
```
┌─────────────────┐
│   Task Timer    │
│   (25 menit)    │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│  Break Timer    │
│   (5 menit)     │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│ Repeat 4x       │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│ Long Break      │
│  (15 menit)     │
└─────────┬───────┘
```

### 5. Finalisasi
```
┌─────────────────┐
│ Take Screenshot │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│ Generate Report │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│ Send to WA      │
└─────────┬───────┘
          │
          ▼
┌─────────────────┐
│   Complete      │
└─────────────────┘
```

## 📁 Struktur File Utama

### Core Files:
- **`pomodoro.go`** - Entry point dan alur utama aplikasi
- **`input.go`** - Fungsi input dan validasi
- **`whatsapp.go`** - Integrasi WhatsApp
- **`display/display.go`** - Sistem tampilan timer
- **`format.go`** - Formatting waktu
- **`screenshot.go`** - Sistem screenshot
- **`mouse.go`** - Monitoring aktivitas mouse
- **`gtmetrix.go`** - Analisis performa website

### Supporting Files:
- **`c/mouse_hook.c`** - DLL untuk mouse hook
- **`MouseHook.dll`** - Library untuk monitoring mouse
- **`go.mod`** - Dependencies Go

## 🔧 Fitur Utama

### 1. Timer Pomodoro
- **4 siklus kerja** (25 menit masing-masing)
- **4 istirahat pendek** (5 menit masing-masing)
- **1 istirahat panjang** (15 menit)
- **Total 1 siklus** = 2 jam 20 menit

### 2. Integrasi WhatsApp
- **Login otomatis** dengan QR code
- **Notifikasi start** ke grup
- **Laporan akhir** dengan screenshot
- **Analisis GTmetrix** (jika URL GTmetrix)

### 3. Screenshot System
- **Screenshot otomatis** setiap interval
- **Random selection** untuk laporan
- **PNG format** dengan UUID

### 4. Mouse Activity Monitor
- **DLL integration** untuk monitoring hardware
- **Anti-cheat detection**
- **Activity verification**

### 5. GTmetrix Integration
- **Web scraping** otomatis
- **Performance metrics** extraction
- **Report formatting**

## 📊 Output dan Hasil

### 1. Laporan WhatsApp
```
*Myika Pomodoro Report 1 cycle*
Hostname : [Nama Komputer]
IP : [IP Address]
Jumlah ScreenShoot : [Jumlah Screenshot]
Yang Dikerjakan :
|[Milestone yang diinput]

# [Token URL]

[GTmetrix Report - jika ada]
```

### 2. Screenshot
- **Format**: PNG
- **Nama**: UUID + .png
- **Konten**: Random screenshot dari sesi kerja

### 3. GTmetrix Report (jika ada)
```
📊 GTmetrix Performance Report
🌐 URL: [Original URL]
📈 Grade: [A-F]
⚡ Performance: [Score]
🏗️ Structure: [Score]
🚀 LCP: [Loading Time]
⚙️ TBT: [Total Blocking Time]
📱 CLS: [Cumulative Layout Shift]
```

## 🚀 Cara Penggunaan

### 1. Instalasi
```bash
# Download dari Release Page
# Atau build dari source
go mod tidy
go build
```

### 2. Menjalankan
```bash
./pomodoro
```

### 3. Input yang Diperlukan
1. **ID Grup WhatsApp** - Format: "Myika minta id grup : [ID]"
2. **URL Task** - URL yang akan dikerjakan
3. **Milestone** - Rencana kerja (minimal 17 karakter)

### 4. Setup WhatsApp
- Scan QR code yang muncul di browser
- Pastikan terhubung ke internet
- Jangan lepas tautan selama sesi

## ⚠️ Persyaratan Sistem

### Software:
- **Go 1.24.1+**
- **SQLite3**
- **Chrome/Chromium** (untuk GTmetrix scraping)

### Hardware:
- **Mouse** (untuk monitoring aktivitas)
- **Display** (untuk screenshot)
- **Internet** (untuk WhatsApp dan GTmetrix)

### Dependencies:
- **whatsmeow** - WhatsApp client
- **chromedp** - Browser automation
- **screenshot** - Screen capture
- **beeep** - Desktop notifications
- **termbox-go** - Terminal UI

## 🔍 Monitoring dan Anti-Cheat

### Mouse Activity Detection:
- **Hardware level monitoring**
- **DLL integration**
- **Activity verification**
- **Timeout-based detection**

### Screenshot Verification:
- **Random sampling**
- **Timestamp tracking**
- **File integrity check**

## 📈 Metrik dan Analytics

### Data yang Dikumpulkan:
1. **Waktu kerja** - Durasi setiap sesi
2. **Screenshot** - Bukti aktivitas
3. **Mouse activity** - Verifikasi kehadiran
4. **Website performance** - GTmetrix metrics
5. **System info** - Hostname, IP address

### Laporan yang Dihasilkan:
1. **WhatsApp notification** - Start dan finish
2. **Screenshot file** - Bukti visual
3. **Performance report** - GTmetrix data
4. **Activity log** - Mouse monitoring

## 🛠️ Troubleshooting

### Masalah Umum:
1. **WhatsApp tidak terhubung**
   - Pastikan internet stabil
   - Scan ulang QR code
   - Restart aplikasi

2. **Screenshot gagal**
   - Cek permission display
   - Pastikan tidak ada aplikasi blocking

3. **GTmetrix scraping gagal**
   - Cek URL valid
   - Pastikan laporan tidak expired
   - Cek koneksi internet

4. **Mouse hook error**
   - Pastikan MouseHook.dll ada
   - Run as administrator
   - Cek antivirus blocking

## 🔮 Pengembangan Masa Depan

### Fitur Potensial:
- **Web dashboard** untuk monitoring
- **Analytics dashboard** untuk statistik
- **Team collaboration** features
- **Custom timer** settings
- **Integration** dengan tools lain
- **Mobile app** companion

## 📝 Kesimpulan

Pomokit adalah solusi komprehensif untuk manajemen waktu produktif yang menggabungkan:
- **Teknik Pomodoro** tradisional
- **Teknologi modern** (WhatsApp, GTmetrix)
- **Monitoring otomatis** (screenshot, mouse activity)
- **Reporting real-time** ke grup kerja

Aplikasi ini ideal untuk:
- **Developer** yang ingin track produktivitas
- **Team leader** yang perlu monitor tim
- **Freelancer** yang ingin accountability
- **Student** yang belajar time management

Dengan fitur-fitur yang ada, Pomokit membantu pengguna tidak hanya mengatur waktu dengan baik, tetapi juga memberikan bukti dan analisis yang komprehensif tentang produktivitas mereka.
