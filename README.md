# Membuka Website Simaster dengan Trigger Word

**Dibuat oleh: Zufar Syaafi'**  
📧 Email: [zufar.syaafie@gmail.com](mailto:zufar.syaafie@gmail.com)  
🐙 GitHub: [@zufarsyaafie](https://github.com/zufarsyaafie)

---

## 📋 Daftar Isi

- [Pendahuluan](#pendahuluan)
- [Demo Video](#demo-video)
- [Fitur Utama](#fitur-utama)
- [Persyaratan Sistem](#persyaratan-sistem)
- [Instalasi](#instalasi)
- [Cara Penggunaan](#cara-penggunaan)
- [Trigger Word](#trigger-word)
- [Teknologi yang Digunakan](#teknologi-yang-digunakan)
- [Cara Kerja](#cara-kerja)
- [Konfigurasi](#konfigurasi)
- [Troubleshooting](#troubleshooting)
- [Kontribusi](#kontribusi)
- [Tentang Pengembang](#tentang-pengembang)
- [Acknowledgments](#acknowledgments)
- [Dukung Proyek Ini](#dukung-proyek-ini)

---

## 🎯 Pendahuluan

Proyek ini merupakan implementasi sistem deteksi **trigger word** (kata pemicu) menggunakan teknologi deep learning. Dengan memanfaatkan audio yang ditangkap melalui mikrofon, pengguna dapat memicu aksi spesifik—dalam hal ini membuka situs web Simaster—hanya dengan mengucapkan kata kunci yang telah ditentukan.

### Inspirasi
Sistem ini dikembangkan menggunakan Python di dalam Jupyter Notebook, dengan pustaka seperti Keras/TensorFlow untuk membangun model, PyDub untuk manipulasi audio, dan PyAudio untuk pemrosesan audio secara real-time. Proyek ini terinspirasi dari cara kerja asisten suara seperti Alexa atau Google Home, namun dengan fokus pada pembuatan kata pemicu dan aksi yang dapat dikustomisasi.

---

## 🎥 Demo Video

https://github.com/ZufarSyaafie/trigger-word/issues/1#issue-3183646310

> **Catatan**: Video demonstrasi akan menunjukkan proses dari mengucapkan kata "simaster" hingga terbukanya browser ke situs web yang dituju.

---

## ✨ Fitur Utama

- **🎙️ Deteksi Kata Pemicu Kustom**: Mampu mendeteksi kata kunci "simaster" secara akurat
- **⚙️ Sintesis Data Latih**: Menghasilkan dataset audio secara otomatis dengan menggabungkan rekaman kata positif, kata negatif, dan suara latar
- **🚀 Aksi Otomatis**: Membuka browser dan mengarah ke situs web Simaster secara otomatis setelah kata pemicu terdeteksi
- **🧠 Model Deep Learning**: Menggunakan arsitektur GRU (Gated Recurrent Unit) untuk efektivitas deteksi pada data sekuensial seperti audio
- **📈 Real-time Processing**: Menganalisis audio dari mikrofon secara langsung untuk deteksi instan
- **🔧 Fleksibel**: Arsitektur yang memungkinkan perubahan kata pemicu dan aksi dengan modifikasi sederhana

---

## 💻 Persyaratan Sistem

### Perangkat Keras
- **Mikrofon**: Mikrofon internal atau eksternal yang berfungsi dengan baik
- **RAM**: Minimal 4GB (disarankan 8GB untuk proses training)
- **Processor**: CPU dual-core atau lebih tinggi

### Perangkat Lunak
- **Python**: Versi 3.8 atau lebih baru
- **Jupyter Notebook/JupyterLab**: Untuk menjalankan file `.ipynb`
- **Sistem Operasi**: Windows 10/11, macOS, atau Linux

---

## 🚀 Instalasi

### 1. Clone Repository

```bash
git clone https://github.com/zufarsyaafie/trigger-word.git
cd trigger-word
```

### 2. Buat Virtual Environment (Disarankan)

**Dengan Python venv:**
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

**Dengan Conda:**
```bash
conda create --name triggerword_env python=3.10
conda activate triggerword_env
```

### 3. Install Dependencies

> **Catatan**: Disarankan untuk menginstal TensorFlow terlebih dahulu sesuai dengan panduan resmi untuk dukungan CPU/GPU Anda.

```bash
pip install tensorflow pydub pyaudio numpy ipython jupyter matplotlib
```

**Untuk instalasi PyAudio di Windows (jika mengalami masalah):**
```bash
pip install pipwin
pipwin install pyaudio
```

Kemudian buka file `model-maker.ipynb`.

---

## 📖 Cara Penggunaan

### Langkah-langkah:

1. **Jalankan Notebook**: Buka `model-maker.ipynb` di Jupyter
2. **Sintesis Data**: Jalankan sel-sel pada bagian "Data Synthesis" untuk membuat dataset
3. **Latih Model**: Jalankan sel-sel pada bagian "Model Development" untuk membangun dan melatih model deteksi
4. **Mulai Deteksi**: Jalankan sel pada bagian "Sound Detection" dan izinkan akses ke mikrofon
5. **Ucapkan Trigger Word**: Ucapkan kata "simaster" dengan jelas ke mikrofon
6. **Lihat Hasil**: Aplikasi akan mencetak "Website dibuka!" dan membuka tab browser baru
7. **Keluar**: Hentikan eksekusi sel di Jupyter untuk mematikan pendeteksian

### 💡 Tips Penggunaan

- Pastikan lingkungan sekitar tidak terlalu bising saat merekam atau saat deteksi
- Ucapkan kata pemicu dengan intonasi dan kecepatan yang mirip dengan data rekaman Anda
- Jika deteksi kurang akurat, coba latih ulang model dengan lebih banyak variasi data audio

---

## 🎤 Trigger Word

### Konfigurasi Kata Pemicu

**Trigger Word**: `"simaster"`
- **Kata**: Mengucapkan kata "simaster"
- **Fungsi**: Memicu aksi untuk membuka situs web
- **Indikator**: Teks "Website dibuka!" akan muncul di konsol
- **Aksi**: Membuka browser ke situs Simaster

---

## 🛠️ Teknologi yang Digunakan

### Pustaka Python
- **TensorFlow/Keras**: Untuk membangun, melatih, dan menjalankan model deep learning (GRU)
- **PyDub**: Untuk manipulasi file dan data audio seperti memotong, melapisi, dan menormalisasi
- **PyAudio**: Untuk mengakses stream audio langsung dari mikrofon
- **NumPy**: Untuk komputasi numerik, terutama dalam pemrosesan spektogram audio
- **IPython**: Untuk memutar dan menampilkan audio di dalam Jupyter Notebook

### Algoritma
- **Spectrogram Generation**: Mengubah sinyal audio dari domain waktu ke domain frekuensi-waktu
- **Gated Recurrent Unit (GRU)**: Jenis arsitektur Recurrent Neural Network (RNN) yang efisien untuk memproses data sekuensial
- **Audio Data Augmentation**: Menciptakan data latih dengan menggabungkan audio positif, negatif, dan latar belakang

---

## ⚙️ Cara Kerja

### Arsitektur Sistem

```
Input Audio → Preprocessing → Feature Extraction → GRU Model → Decision → Action
```

### Proses Detail:

1. **Data Synthesis & Preprocessing**
   - Mensintesis dataset dengan mengambil rekaman kata "simaster" (positif), kata-kata lain (negatif), dan suara latar
   - Audio digabungkan untuk membuat sampel latihan yang realistis
   - Data diubah menjadi spektogram untuk input model

2. **Model Training**
   - Model Recurrent Neural Network (RNN) dengan lapisan GRU dilatih menggunakan spektogram
   - Model belajar membedakan pola spektogram dari kata "simaster" dengan pola lainnya

3. **Real-time Audio Streaming**
   - PyAudio menangkap audio dari mikrofon dalam potongan-potongan pendek secara real-time

4. **Trigger Word Detection**
   - Setiap potongan audio diubah menjadi spektogram
   - Model memberikan prediksi apakah kata "simaster" terdeteksi

5. **Action Execution**
   - Jika prediksi melebihi ambang batas keyakinan (threshold), sistem mengeksekusi aksi
   - Membuka URL Simaster menggunakan modul `webbrowser`

---

## 🔧 Konfigurasi

### Mengubah Trigger Word atau Aksi

#### 1. Mengubah Kata Pemicu
```python
# 1. Ganti file audio di folder /raw-data/simaster/ 
# 2. Latih ulang model dengan menjalankan notebook
# 3. Kata pemicu baru siap digunakan
```

#### 2. Mengubah Aksi
```python
# Edit pada bagian "Sound Detection"
if prediction > 0.99:
    # Contoh: Mengubah URL target
    webbrowser.open("https://github.com/zufarsyaafie")
    print("Membuka GitHub!")
```

### Mengubah Parameter Training

```python
# Mengubah learning rate dan epoch
opt = Adam(lr=0.0001, beta_1=0.9, beta_2=0.999, decay=0.01)
model.compile(loss='binary_crossentropy', optimizer=opt, metrics=["accuracy"])

# Mengubah jumlah epoch
model.fit(X, Y, batch_size=5, epochs=10)  # Sesuaikan dengan kebutuhan
```

---

## 🐛 Troubleshooting

### Masalah Umum dan Solusi

#### 1. Mikrofon tidak terdeteksi oleh PyAudio
**Solusi:**
- Pastikan mikrofon terpasang dan berfungsi
- Periksa driver audio sudah terinstal dengan benar
- Tentukan indeks perangkat mikrofon secara manual jika diperlukan

#### 2. Model tidak akurat / deteksi gagal
**Solusi:**
- Tingkatkan jumlah dan variasi data di folder `/raw-data/`
- Tambahkan lebih banyak rekaman kata positif, negatif, dan suara latar
- Latih model untuk lebih banyak epoch
- Sesuaikan learning rate pada optimizer

#### 3. Error saat instalasi PyAudio (Windows)
**Solusi:**
```bash
# Metode 1: Menggunakan pipwin
pip install pipwin
pipwin install pyaudio

# Metode 2: Download wheel file
# Kunjungi: https://www.lfd.uci.edu/~gohlke/pythonlibs/#pyaudio
# Download file .whl sesuai versi Python Anda
pip install [nama_file.whl]
```

#### 4. TensorFlow GPU tidak terdeteksi
**Solusi:**
- Pastikan CUDA dan cuDNN sudah terinstal
- Verifikasi kompatibilitas versi TensorFlow dengan CUDA
- Gunakan versi CPU jika tidak memerlukan GPU acceleration

---

## 🤝 Kontribusi

Kontribusi sangat diterima! Berikut cara berkontribusi:

1. **Fork** repository ini
2. **Buat branch** untuk fitur baru (`git checkout -b feature/AmazingFeature`)
3. **Commit** perubahan (`git commit -m 'Add some AmazingFeature'`)
4. **Push** ke branch (`git push origin feature/AmazingFeature`)
5. **Buat Pull Request**

### 💡 Ide Pengembangan

- [ ] Membuat antarmuka pengguna (GUI) untuk merekam kata dan melatih model
- [ ] Mendukung banyak trigger word dengan aksi yang berbeda
- [ ] Mengemas aplikasi menjadi file eksekusi yang mandiri (`.exe`)
- [ ] Optimasi model untuk Raspberry Pi dan perangkat IoT
- [ ] Menambahkan lebih banyak jenis aksi (menjalankan skrip, mengontrol perangkat)
- [ ] Implementasi voice feedback dan notifikasi audio
- [ ] Integrasi dengan smart home systems

---

## 👨‍💻 Tentang Pengembang

**Zufar Syaafi'** adalah seorang developer yang tertarik pada deep learning dan aplikasi AI dalam kehidupan sehari-hari. Proyek ini dibuat sebagai eksplorasi teknologi pemrosesan audio dan aplikasinya dalam interaksi manusia-komputer.

**Kontak:**
- 📧 **Email**: [zufar.syaafie@gmail.com](mailto:zufar.syaafie@gmail.com)
- 🐙 **GitHub**: [@zufarsyaafie](https://github.com/zufarsyaafie)
- 💼 **LinkedIn**: [Zufar Syaafi'](https://linkedin.com/in/zufarsyaafie)

---

## 🙏 Acknowledgments

Terima kasih kepada:

- **Andrew Ng** - Untuk [Deep Learning Specialization Course](https://github.com/amanchadha/coursera-deep-learning-specialization) yang menjadi dasar proyek ini
- **DLology Blog** - Untuk artikel [How to do Real Time Trigger Word Detection with Keras](https://www.dlology.com/blog/how-to-do-real-time-trigger-word-detection-with-keras/) yang memberikan inspirasi
- **Keras & TensorFlow Team** - Untuk framework deep learning yang powerful
- **Python Community** - Untuk ekosistem pustaka yang luar biasa
- **Open Source Community** - Untuk dukungan dan inspirasi yang berkelanjutan

---

## ⭐ Dukung Proyek Ini

Jika proyek ini bermanfaat untuk Anda:
- Berikan ⭐ pada repository ini
- Bagikan ke teman-teman dan komunitas
- Kontribusi dengan ide atau kode
- Berikan feedback untuk perbaikan

**Terima kasih telah mencoba proyek Deteksi Trigger Word ini! 🎉**

---

*Dibuat dengan ❤️ menggunakan Python dan TensorFlow*
