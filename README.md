# ⚖️ Analisis Regresi WLS (Weighted Least Squares) dengan Python & R

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![R](https://img.shields.io/badge/R-4.0+-purple.svg)
![License](https://img.shields.io/badge/License-MIT-red.svg)
![Affiliation](https://img.shields.io/badge/Affiliation-UNTIRTA-orange.svg)

Repositori ini menyajikan alur kerja lanjutan untuk analisis regresi linier menggunakan metode **Weighted Least Squares (WLS)**. Proyek ini berfungsi sebagai solusi ketika asumsi homoskedastisitas (varians sisaan yang konstan) dalam model Ordinary Least Squares (OLS) tidak terpenuhi. Implementasi paralel disediakan untuk **Python** dan **R**, menunjukkan cara mendiagnosis dan memperbaiki heteroskedastisitas.

## ✨ Fitur Utama

- **🔍 Diagnosis Heteroskedastisitas**: Memulai dengan model OLS untuk melakukan diagnosis menggunakan uji formal (Breusch-Pagan) dan analisis visual (plot sisaan absolut vs. prediktor).
- **⚖️ Skema Pembobotan Cerdas**: Menunjukkan proses penentuan skema pembobotan (`weighting scheme`) yang tepat berdasarkan sumber heteroskedastisitas yang teridentifikasi secara visual.
- **🛠️ Pemodelan WLS Lintas Platform**: Membangun model WLS menggunakan `statsmodels.wls` di Python dan fungsi `lm()` dengan argumen `weights` di R untuk memperbaiki model.
- **🔄 Validasi Ulang Asumsi**: Melakukan kembali serangkaian uji asumsi klasik pada model WLS untuk memastikan bahwa masalah heteroskedastisitas telah berhasil diatasi.
- **📊 Analisis Komparatif**: Memungkinkan perbandingan langsung antara hasil model OLS awal dengan model WLS yang telah diperbaiki.

## 🔧 Tumpukan Teknologi (Tech Stack)

- **Bahasa**: `Python 3.7+`, `R 4.0+`
- **Pustaka Python**: `statsmodels`, `pandas`, `numpy`, `scipy`, `matplotlib`, `seaborn`, `openpyxl`
- **Pustaka R**: `lmtest`, `car`, `nlme`, `readxl`, `knitr`, `rmarkdown`
- **Lingkungan**: `Jupyter Notebook / Lab`, `RStudio`

## 🚀 Cara Memulai

### Prasyarat
- **Perangkat Lunak**: Python 3.7+, R 4.0+, Jupyter Notebook/Lab, dan RStudio.
- **File Data**: Pastikan file `data_simulasi_gls.xlsx` berada di dalam direktori proyek Anda.

### Instalasi & Penggunaan

1.  **Unduh Repositori**: *Clone* atau unduh proyek ini ke komputer Anda.

2.  **Untuk Pengguna Python**:
    - Buka terminal atau command prompt, lalu instal paket yang diperlukan:
      ```bash
      pip install pandas openpyxl numpy statsmodels scipy matplotlib seaborn jupyterlab
      ```
    - Jalankan Jupyter Lab/Notebook dan buka file Python (.ipynb).
    - **Penting**: Ubah `file_path` di dalam skrip agar sesuai dengan lokasi file `data_simulasi_gls.xlsx` di komputer Anda.

3.  **Untuk Pengguna R**:
    - Buka RStudio, lalu instal paket yang diperlukan dengan menjalankan perintah berikut di *console*:
      ```r
      install.packages(c("lmtest", "car", "nlme", "readxl", "knitr", "rmarkdown"))
      ```
    - Buka file `.Rmd` atau `.md`.
    - **Penting**: Ubah `file_path` di dalam skrip agar sesuai dengan lokasi file `data_simulasi_gls.xlsx` di komputer Anda.

4.  **Jalankan Analisis**: Eksekusi semua sel (Python) atau *chunks* (R) untuk mereplikasi seluruh proses analisis dari diagnosis hingga pemodelan WLS.

## 📊 Metrik Hasil & Ringkasan Output WLS

Analisis ini akan menghasilkan ringkasan model WLS. Metrik seperti R-squared pada WLS harus diinterpretasikan dengan hati-hati karena dihitung pada data yang telah ditransformasi. AIC dan BIC menjadi metrik yang lebih andal untuk perbandingan model.

| Metrik           | Deskripsi                                                                 | Contoh Nilai    |
| ---------------- | ------------------------------------------------------------------------- | --------------- |
| `R-squared`      | Persentase varians yang dijelaskan pada data yang telah diboboti.         | `0.165`         |
| `Adj. R-squared` | `R-squared` yang disesuaikan untuk model WLS.                             | `0.138`         |
| `AIC` / `BIC`    | Kriteria informasi untuk perbandingan model (nilai lebih rendah lebih baik). | `1118` / `1128` |
| `P-value (BP Test)`| P-value Uji Breusch-Pagan pada sisaan WLS (diharapkan > 0.05).          | `0.08`          |
| `Durbin-Watson`  | Statistik untuk mendeteksi autokorelasi pada sisaan WLS.                  | `0.720`         |
| `VIF`            | Nilai VIF tidak terpengaruh oleh pembobotan (tetap sama seperti OLS).     | `< 5`           |


## ⚖️ Lisensi & Ketentuan Penggunaan

- **Hak Cipta**: © 2025 Ferdian Bangkit Wijaya - Seluruh Hak Dilindungi.
- **Penggunaan Akademik**: Diizinkan secara bebas untuk keperluan penelitian, tesis, dan pendidikan non-komersial dengan atribusi.
- **Penggunaan Komersial**: Memerlukan izin tertulis dari pengembang.

## 👨‍💻 Author

- **Ferdian Bangkit Wijaya**
- Program Studi Statististika, Fakultas Teknik
- **Universitas Sultan Ageng Tirtayasa (UNTIRTA)**
- Banten, Indonesia 🇮🇩

---

> Proyek ini dirancang sebagai panduan praktis untuk menangani pelanggaran asumsi heteroskedastisitas dalam regresi linier, dengan menunjukkan alur kerja yang logis dan dapat direplikasi di Python dan R.
