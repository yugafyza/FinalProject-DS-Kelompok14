# Segmentasi Pasar B2B & Strategi Go-To-Market (GTM) SaaS ERP UMKM di Indonesia

**Final Project Data Science — Kelompok 14**

## 📌 Ringkasan Proyek
Proyek ini bertujuan memetakan potensi pasar B2B di 38 provinsi Indonesia untuk menentukan wilayah ekspansi prioritas (*Ideal Customer Profile* / ICP) bagi penyedia layanan *Software-as-a-Service* (SaaS) ERP UMKM. Menggunakan pendekatan *unsupervised machine learning* (**K-Means Clustering**) dan pemeringkatan berbasis **Skor ICP Terbobot**, analisis ini menyaring 31 provinsi layak model menjadi 3 segmen pasar utama guna mengoptimalkan efisiensi anggaran akuisisi pelanggan (*Customer Acquisition Cost*).

## 📊 Sumber Dataset
1. **`umkm_provinsi.csv`**: Data jumlah unit usaha Mikro, Kecil, dan Menengah per provinsi.
2. **`internet.csv`**: Tingkat penetrasi pengguna internet per provinsi.
3. **`ekonomi.csv`**: Indikator pertumbuhan ekonomi / PDRB per provinsi.
4. **`jumlah-merchant-qris-per-provinsi-_31-maret-2025_.csv`**: Tingkat adopsi sistem pembayaran digital (merchant QRIS) per provinsi.

## ⚙️ Metodologi & Alur Analisis
1. **Data Cleaning & Feature Engineering**: Standardisasi 38 nama provinsi serta pembuatan fitur rasio densitas usaha dan penetrasi merchant QRIS per 1.000 unit usaha.
2. **Filtering & Normalisasi**: Penyaringan provinsi dengan ambang batas minimal 10.000 unit usaha (menghasilkan 31 provinsi layak model) dan normalisasi menggunakan `MinMaxScaler` (rentang 0–1).
3. **K-Means Clustering (`k=3`)**: Evaluasi menggunakan *Elbow Method* dan *Silhouette Score* menghasilkan nilai optimal pada `k=3` (`0.456720`).
4. **Pemeringkatan Skor ICP & Uji Sensitivitas**: Perhitungan skor komposit berbobot untuk menentukan Top 5 provinsi target ekspansi, dilengkapi perbandingan *baseline* serta uji sensitivitas bobot.

## 🏆 Hasil Utama (Top 5 Provinsi Target Ekspansi)
1. **DKI Jakarta**
2. **Jawa Barat**
3. **Banten**
4. **Kepulauan Riau**
5. **Jawa Tengah**

## 📁 Struktur File Repositori
- `FinalProject_DS_Kelompok14.ipynb` — Notebook utama berisi seluruh pipeline pembersihan data, pemodelan K-Means, visualisasi, dan uji sensitivitas.
- `data_siap_model.csv` — Dataset bersih hasil normalisasi untuk 31 provinsi layak model.
- `eval_kmeans.csv` & `fig_kmeans_eval.png` — Tabel dan grafik evaluasi *Inertia* serta *Silhouette Score* (`k=2` hingga `k=6`).
- `hasil_final_klaster_icp.csv` — Hasil lengkap pembagian klaster dan perhitungan skor ICP seluruh provinsi.
- `tabel_top5_segmen.csv` — Daftar peringkat 5 provinsi prioritas utama untuk strategi *Go-To-Market*.
- `uji_sensitivitas.csv` — Hasil pengujian stabilitas peringkat terhadap perubahan skenario bobot.
- `tabel_legalitas_scraping.csv` — Matriks kepatuhan dan legalitas akuisisi data (*lead generation*).

## 🚀 Cara Menjalankan Kode
1. Buka file `FinalProject_DS_Kelompok14.ipynb` menggunakan **Google Colab** atau **Jupyter Notebook**.
2. Pastikan keempat file dataset mentah (`.csv`) berada pada direktori kerja yang sama.
3. Jalankan seluruh sel secara berurutan (*Runtime -> Run all*).
