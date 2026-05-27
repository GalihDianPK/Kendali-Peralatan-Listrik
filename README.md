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

## 📊 Alur Kerja Sistem (Flowchart)

Sistem bekerja dengan mendeteksi input tombol pada GUI Processing, mengirimkan karakter perintah melalui serial COM, lalu dieksekusi oleh Arduino untuk mengubah status pin *output* dan memperbarui tampilan LCD.
