```markdown
<div align="center">

# 🌐 Woyauziaw Server (Termux Web Stack)

[![Termux](https://img.shields.io/badge/Platform-Termux-orange.svg?style=for-the-badge&logo=termux)](https://termux.dev)
[![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)](https://nginx.org/)
[![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://php.net/)
[![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white)](https://mariadb.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

Script automasi untuk membangun **Web Server Lokal** yang tangguh di Android via Termux. Menggunakan kombinasi Nginx, PHP-FPM, dan MariaDB, lengkap dengan fitur Manajemen Multi-Project Instan.

</div>

---

## ✨ Fitur Unggulan

- 🎯 **Instalasi Fleksibel:** Bebas menentukan nama folder web utama (misal: `htdocs` atau `websites`) dan folder `phpMyAdmin` sesuka hati.
- 🚀 **Auto-Install phpMyAdmin:** Otomatis mengunduh, mengekstrak, dan mengonfigurasi `config.inc.php` beserta enkripsi *Blowfish Secret* secara instan.
- 🎛️ **Perintah Induk (`ws`):** Kelola seluruh layanan server (Nginx, PHP, MySQL) hanya dengan satu perintah terminal yang terpusat.
- ⚡ **Instant Project Switcher (`switch`):** Pindah antar project web dalam hitungan detik menggunakan sistem *symlink*, tanpa perlu *restart* server Nginx!
- 🔒 **Aman & Terkompilasi:** Script didistribusikan dalam bentuk biner eksekusi (ELF) terenkripsi untuk menjaga integritas sistem.

---

## 🛠️ Persyaratan Sistem

Sebelum memulai instalasi, pastikan Termux kamu sudah *up-to-date* dan memiliki *package* inti berikut:

```bash
pkg update && pkg upgrade -y
pkg install git nginx php-fpm mariadb -y

```
## 📥 Cara Instalasi
Ikuti langkah-langkah di bawah ini secara berurutan di dalam Termux:
**1. Clone Repositori**
```bash
git clone [https://github.com/woyauziaw/webserver-installer.git](https://github.com/woyauziaw/webserver-installer.git)
cd webserver-installer

```
**2. Jalankan Installer**
```bash
chmod +x install.sh
./install.sh

```
**3. Konfigurasi Interaktif**
Sistem akan meminta beberapa input. Isi sesuai kebutuhanmu:
 * **Nama folder utama:** Tempat menyimpan semua project (Contoh: htdocs).
 * **Nama folder phpMyAdmin:** URL path rahasia untuk database (Contoh: pma_rahasia).
 * **Blowfish Secret:** Masukkan minimal 32 karakter acak. Kosongkan saja lalu tekan Enter jika ingin digenerate otomatis secara aman.
**4. Terapkan Konfigurasi**
```bash
source ~/.bashrc

```
## 📚 Panduan Penggunaan
Setelah instalasi selesai, kamu bisa menggunakan perintah **ws** dan **switch** di direktori mana saja.
### 🎛️ 1. Manajemen Server (ws)
Ketik ws diikuti salah satu perintah berikut:
| Perintah | Deskripsi |
|---|---|
| ws start | 🟢 Menyalakan Nginx, PHP-FPM, dan MariaDB sekaligus. |
| ws stop | 🔴 Mematikan seluruh proses server yang sedang berjalan. |
| ws restart | 🔄 Memuat ulang seluruh layanan server. |
| ws status | 📊 Memeriksa status aktif/tidaknya tiap layanan. |
| ws help | ℹ️ Menampilkan menu bantuan panel server. |
### 📂 2. Mengganti Project Aktif (switch)
Tidak perlu memindahkan file saat mengerjakan project yang berbeda! Cukup buat folder project di dalam direktori utamamu (misal: ~/htdocs), lalu gunakan:
```bash
switch nama_project_kamu

```
> **Catatan:** Perintah ini akan otomatis menghubungkan project tersebut ke jalur utama Nginx kamu. Jangan pernah melakukan switch ke folder phpMyAdmin!
> 
## 🌐 Cara Mengakses Web & Database
Setelah menjalankan ws start, buka browser di HP/PC kamu (jika dalam satu jaringan WiFi) dan akses:
 * **Web Utama:** http://127.0.0.1:8080 (atau http://localhost:8080)
 * **phpMyAdmin:** http://127.0.0.1:8080/nama_folder_pma_kamu
<div align="center">
Dibuat dengan ☕ oleh <b>woyauziaw</b>
</div>
```

```
