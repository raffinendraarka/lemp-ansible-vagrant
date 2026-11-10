# Otomasi LEMP Stack & WordPress Multi-Tier dengan Vagrant dan Ansible

Proyek ini merupakan implementasi otomasi infrastruktur *multi-tier architecture* menggunakan Vagrant sebagai *provisioning tool* dan Ansible untuk *configuration management*. Sistem memisahkan layanan Web Server (Nginx + PHP) dan Database Server (MariaDB) ke dalam VM target yang berbeda secara otomatis.

---

## 🏛️ Arsitektur Sistem

Arsitektur terdiri dari 3 Virtual Machine yang berjalan di Oracle VM VirtualBox:
- **VM Control Node** (`192.168.56.5`): Menjalankan Ansible untuk mengorkestrasi node target.
- **VM Web Server** (`192.168.56.10`): Menjalankan Nginx, PHP-FPM, dan source code WordPress.
- **VM Database Server** (`192.168.56.11`): Menjalankan MariaDB dengan basis data serta kredensial khusus untuk WordPress.

---

## 📋 Prasyarat Sistem (Prerequisites)

Sebelum menjalankan proyek ini, pastikan sistem host (laptop) telah terinstal:
- [Oracle VM VirtualBox](https://www.virtualbox.org/) (versi 6.1 atau 7.x)
- [Vagrant](https://developer.hashicorp.com/vagrant) (versi 2.2+)
- Git

---

## 🚀 Panduan Eksekusi (How to Use)

### 1. Clone Repositori
```bash
git clone [https://github.com/USERNAME_ANDA/NAMA_REPOSITORI.git](https://github.com/USERNAME_ANDA/NAMA_REPOSITORI.git)
cd NAMA_REPOSITORI