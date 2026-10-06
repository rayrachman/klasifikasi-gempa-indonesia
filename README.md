# Klasifikasi Gempa Bumi Indonesia (Skala Minor vs Major)

**Penulis:** Moch Rayhan Aulia Rachman  
**Dataset:** [Katalog Gempa Bumi Indonesia (Kaggle)](https://kaggle.com)  
**Target Utama:** Mengklasifikasikan skala gempa bumi menjadi Minor (M < 5.0) dan Major (M >= 5.0) menggunakan algoritma Machine Learning dan memetakan kerentanan geospasialnya.

---

### 🚀 Ringkasan Alur Pengerjaan:
1. **Praproses & Data Cleaning:** Pembersihan data seismik historis BMKG/USGS (~92k baris data).
2. **Exploratory Data Analysis (EDA):** Pemetaan tren temporal dan spasial sebaran gempa.
3. **Seismic Feature Engineering:** Pembuatan fitur prediktor berbasis *lag magnitude*, *depth*, dan akumulasi energi (*rolling mean* & *rolling max*).
4. **Pemodelan Machine Learning:** Mengomparasikan 6 algoritma dengan validasi ketat *Stratified 5-Fold Cross-Validation*.
5. **Evaluasi Performa & Feature Importance:** Analisis fitur paling dominan terhadap eskalasi gempa skala Major.

### 📊 Hasil Akhir & Insight Utama:
*   **Champion Model:** Algoritma **Random Forest** berhasil terpilih dengan tingkat deteksi benar (**Recall kelas Major**) sebesar **76.06%**, **Akurasi ~80.36%**, dan **ROC-AUC ~0.8674** dengan performa cross-validation yang sangat stabil (\(\pm 0.23\%\)).
*   **Fitur Paling Berpengaruh:** Fitur `prev_mag_1` (magnitudo gempa terakhir sebelum kejadian) dan `depth` (kedalaman episentrum) menjadi prediktor fisik paling dominan dalam mendeteksi akumulasi stres lempeng bumi.
*   **Visualisasi Geospasial:** Dilengkapi dengan peta interaktif 38 Provinsi Indonesia menggunakan *Plotly Express* dan *REST API CARTO Voyager*.

*Catatan: Anda dapat melihat visualisasi peta interaktif dan menjalankan ulang notebook ini secara cloud langsung di https://www.kaggle.com/code/rayrachman/klasifikasi-gempa-bumi-indonesia-minor-vs-major*
