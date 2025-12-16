# UTS UDB – Isolasi Network Docker & Kontrol Akses Database dengan ZeroTier

## Identitas
- Nama: Dedy Nurcahya
- NIM: 240104017
- Mata Kuliah: MANAJEMENT JARINGAN
- Tahun: 2025

---
### 1. Clone Repository
git clone https://github.com/dedynurcahya/240104017-udb-uts.git 

---
## Deskripsi Project
Project ini bertujuan untuk mengimplementasikan isolasi jaringan menggunakan Docker serta kontrol akses layanan database MySQL dan PostgreSQL. Akses ke layanan database dilakukan secara aman melalui Adminer yang hanya dapat diakses menggunakan jaringan virtual ZeroTier.

---

## Arsitektur Sistem
Sistem terdiri dari tiga container Docker:
1. **MySQL** (`uts_mysql`) – Database internal
2. **PostgreSQL** (`uts_postgres`) – Database internal
3. **Adminer** (`uts_adminer`) – Antarmuka manajemen database

Semua container berada pada satu jaringan Docker internal dan hanya Adminer yang dapat diakses dari luar melalui IP ZeroTier.

---

## Konfigurasi Network
- Docker Network: `uts_internal_net`
- Subnet: `172.30.17.0/24`

| Service | IP Container |
|------|-------------|
| MySQL | 172.30.17.10 |
| PostgreSQL | 172.30.17.20 |
| Adminer | 172.30.17.30 |

---

## Akses Service

### Adminer (via ZeroTier)

ZeroTier Network ID : e3918db48301bc95
ZeroTier IP Host    : 10.244.94.63
Adminer Port        : 8017
