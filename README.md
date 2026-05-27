# Smart Electrical Control System 🏠⚡

Proyek sistem kendali perangkat elektronik rumah pintar (Smart Home) berbasis **Arduino Uno** sebagai *hardware controller* dan **Processing** sebagai antarmuka pengguna grafis (**GUI**). Sistem ini memungkinkan pengguna mengendalikan kipas, lampu RGB (Anti-Mix Logic), dan buzzer secara *real-time* melalui komunikasi serial (USB).

---

## 👥 Anggota Tim (AGK)
* **Allysa**
* **Galih**
* **Keisya**

---

## 🎯 Fitur Utama
* **Smart Fan Control**: Menyalakan dan mematikan kipas DC dilengkapi visualisasi animasi baling-baling berputar pada GUI.
* **Anti-Mix RGB LED**: Kontrol lampu RGB individual (Merah, Hijau, Biru) dengan logika proteksi pencampuran warna (harus mematikan LED aktif terlebih dahulu sebelum mengganti warna).
* **Interactive Buzzer**: Aktifasi alarm buzzer dengan indikator gelombang suara dinamis pada aplikasi GUI.
* **Dual Display Status**: Sinkronisasi status perangkat secara *real-time* pada panel GUI Processing dan hardware LCD 16x2 (I2C).

---

## 🛠️ Komponen & Teknologi

### Perangkat Keras (Hardware)
* Arduino Uno (atau sejenisnya)
* LCD Display 16x2 dengan Modul I2C
* Modul Kipas DC (Fan)
* RGB LED
* Active/Passive Buzzer
* Kabel Jumper & Protboard / Rumah Maket

### Perangkat Lunak (Software)
* **Arduino IDE** (untuk *firmware* Arduino)
* **Processing IDE** (untuk pembuatan GUI Desktop)
* Library Arduino: `Wire.h` dan `LiquidCrystal_I2C.h`
* Library Processing: `processing.serial.*`

---

### 2. Protokol Komunikasi Serial
Tabel perintah data String yang dikirim dari Processing ke Arduino untuk mempermudah pemetaan fungsi kontrol.

## 🔌 Protokol Komunikasi Serial (9600 Baudrate)

| Perintah Serial | Perangkat Hardware | Status GUI | Status LCD (16x2) |
| :--- | :--- | :--- | :--- |
| `RED_ON` | LED Merah Aktif | RED LED ON | `R:1 G:0 B:0` |
| `GREEN_ON` | LED Hijau Aktif | GREEN LED ON | `R:0 G:1 B:0` |
| `BLUE_ON` | LED Biru Aktif | BLUE LED ON | `R:0 G:0 B:1` |
| `LED_OFF` | Semua LED Mati | ALL LED OFF | `R:0 G:0 B:0` |
| `FAN_ON` | Kipas Berputar | FAN ACTIVE | `F:ON` |
| `FAN_OFF` | Kipas Berhenti | FAN OFF | `F:OFF` |
| `BUZZ_ON` | Buzzer Berbunyi | BUZZER ACTIVE | `BZ:ON` |
| `BUZZ_OFF` | Buzzer Senyap | BUZZER OFF | `BZ:OFF` |

## 📊 Alur Kerja Sistem (Flowchart)

Sistem bekerja dengan mendeteksi input tombol pada GUI Processing, mengirimkan karakter perintah melalui serial COM, lalu dieksekusi oleh Arduino untuk mengubah status pin *output* dan memperbarui tampilan LCD.
