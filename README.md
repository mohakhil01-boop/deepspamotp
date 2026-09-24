# OMG-NEXUS

> WhatsApp OTP Spam Tool — 14 Platform Indonesia  
> **Retry Loop Edition** — spam terus-menerus sampai CTRL+C

---

## ⚠️ Platform Support

| Platform | Status |
|----------|--------|
| **Acode + Alpine Linux** | ✅ **SUPPORTED** |
| Termux | ❌ **NOT SUPPORTED** |
| Windows / Linux Desktop | ⚠️ Belum ditest |
| macOS | ⚠️ Belum ditest |

**PENTING:** Script ini **TIDAK SUPPORT TERMUX**. Jangan coba install di Termux — bakal error karena perbedaan environment, library, dan path. Gunakan **Acode + Alpine Linux** sebagai environment resmi.

---

## 📋 Apa Itu OMG-NEXUS?

Tool spam OTP WhatsApp ke 14 platform Indonesia:

1. Internet Rakyat
2. PTSP Kemenag
3. HRS-BRE
4. Rumah123
5. Paper.id
6. DuniaGames
7. BonusBelanja
8. Matahari
9. Auto2000
10. SIDEMANG Palembang
11. Klook
12. PlanetBan
13. TuneUp
14. Hainaya

**Fitur:**
- Spam OTP loop ke semua platform (retry sampai CTRL+C)
- Spam OTP brute (loop + jeda custom)
- Spam OTP pilih platform tertentu (loop)
- Info system
- Random User-Agent, email, nama tiap request
- Auto-normalize nomor (08xx / 62xx / +62xx)
- IP publik auto-fetch

---

## 🛠️ Cara Install di Acode + Alpine Linux

### 1. Buka Acode, aktifkan Alpine Linux terminal

Pastikan lo udah setup **Alpine Linux** di Acode (lewat plugin Terminal / Alpine). Kalo belum, install Alpine dulu.

### 2. Update package manager

```sh
apk update && apk upgrade
```

### 3. Install Python & pip

```sh
apk add python3 py3-pip
```

### 4. Install library yang dibutuhkan

```sh
pip3 install requests colorama
```

Opsional (buat info RAM di menu Info System):

```sh
pip3 install psutil
```

### 5. Clone repo atau copy script

```sh
git clone https://github.com/artcasds/omg-nexus.git
cd omg-nexus
```

Atau copy langsung file `omg-nexus.py` ke folder kerja lo.

### 6. Jalankan

```sh
python3 omg-nexus.py
```

---

## 🎮 Cara Pakai

Setelah script jalan, lo bakal liat menu:

```
╭─────────────────────────────────────────────────────────────╮
│   Nama      : NEX-OTP            │ Platform  : 14 WA OTP     │
│   Status    : FREE               │ IP Publik : xxx.xxx.xxx  │
│   Mode      : RETRY LOOP         │ Stop      : CTRL+C       │
╰─────────────────────────────────────────────────────────────╯

╭──────────────── [ MENU ] ────────────────╮
│ [01] SPAM OTP LOOP (SEMUA PLATFORM)      │
│ [02] SPAM OTP BRUTE (LOOP + JEDA)        │
│ [03] SPAM OTP PILIH PLATFORM (LOOP)      │
│ [04] INFO SYSTEM                         │
│ [05] KELUAR                              │
╰──────────────────────────────────────────╯
```

### Menu 01 — Spam OTP Loop (Semua Platform)

- Masukin nomor target (format `08xx`, `62xx`, atau `+62xx`)
- Masukin delay antar round (default 3 detik)
- Script bakal spam 14 platform terus-menerus
- **CTRL+C** buat stop

### Menu 02 — Spam OTP Brute (Loop + Jeda)

- Masukin nomor target
- Masukin delay antar round (default 60 detik)
- Script loop spam 14 platform dengan jeda panjang
- **CTRL+C** buat stop

### Menu 03 — Spam OTP Pilih Platform (Loop)

- Masukin nomor target
- Pilih platform (1–14)
- Masukin delay antar round (default 3 detik)
- Script spam platform yang dipilih terus-menerus
- **CTRL+C** buat stop

### Menu 04 — Info System

Nampilin OS, Python version, CPU core, RAM, dan IP publik.

### Menu 05 — Keluar

Exit script.

---

## 📦 Dependencies

| Package | Fungsi |
|---------|--------|
| `python3` | Runtime |
| `py3-pip` | Package manager Python |
| `requests` | HTTP request ke endpoint OTP |
| `colorama` | Warna terminal (hijau/merah/kuning) |
| `psutil` | (Opsional) Info RAM di menu Info System |

Install semua:

```sh
apk add python3 py3-pip
pip3 install requests colorama psutil
```

---

## 🐛 Troubleshooting

### Error: `ModuleNotFoundError: No module named 'requests'`

Jalankan:
```sh
pip3 install requests colorama
```

### Error: `ModuleNotFoundError: No module named 'colorama'`

Jalankan:
```sh
pip3 install colorama
```

### Karakter kotak (`╭─╮`) muncul sebagai `?` atau random

Pastikan terminal Alpine lo support UTF-8. Kalo masih error, script udah ada `sys.stdout.reconfigure(encoding='utf-8')` — tapi kalo console tetap gak support, coba ganti font terminal atau pakai terminal lain.

### Gagal konek ke platform (TIMEOUT)

- Cek koneksi internet
- Beberapa platform mungkin down atau endpoint berubah
- Kalo kena `LIMIT`, tunggu beberapa menit

### Script gak jalan di Termux

**Ya, emang gak support Termux.** Pindah ke Acode + Alpine Linux. Perbedaan environment Termux vs Alpine:
- Termux pakai path `/data/data/com.termux/files/usr/`
- Alpine pakai `/usr/`
- Library dan package manager beda

---

## 🚫 Disclaimer

Script ini dibuat untuk **tujuan edukasi** dan **pengujian keamanan**. Penyalahgunaan script ini untuk spam, harassment, atau aktivitas ilegal lainnya **bukan tanggung jawab author**. Gunakan dengan risiko sendiri.

---

## 📝 License

MIT License — bebas modif, bebas distribusi, tapi jangan hapus credit.


---

## 🔄 Changelog

### v2.0 — Retry Loop Edition
- Menu 01 & 03 sekarang loop sampai CTRL+C
- Tambah counter round `[R001]`, `[R002]`, dst
- Tambah delay custom per round
- Tambah info Mode & Stop di header

### v1.0 — Initial Release
- Spam OTP ke 14 platform
- Menu single, brute, pick platform
- Info system
