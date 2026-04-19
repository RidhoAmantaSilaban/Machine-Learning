# README: Supervised Learning - Analisis Regresi Data Perumahan USA

Buku catatan ini mendemonstrasikan alur kerja lengkap untuk melakukan regresi linier pada dataset `USA_Housing.csv` untuk memprediksi harga rumah. Ini mencakup persiapan data, analisis data eksplorasi, pelatihan model, dan evaluasi, termasuk pengujian asumsi.

## 1. Persiapan
*   **Pustaka**: Mengimpor pustaka yang diperlukan seperti `numpy`, `pandas`, `matplotlib`, `seaborn`, `sklearn` (untuk `LinearRegression`, `train_test_split`, `metrics`), dan `statsmodels` (untuk `het_breuschpagan`, `durbin_watson`, `shapiro`).
*   **Pemuatan Data**: Memuat dataset `USA_Housing.csv` ke dalam DataFrame pandas.

## 2. Analisis Data Eksplorasi (EDA)
*   **Ikhtisar Data**: Menyediakan ringkasan DataFrame menggunakan `df.info()` dan `df.describe()`.
*   **Plot Pasangan**: Memvisualisasikan hubungan antar semua fitur menggunakan `seaborn.pairplot()`.
*   **Distribusi Harga**: Memeriksa distribusi variabel target ('Price') menggunakan histogram dan plot densitas.
*   **Analisis Korelasi**: Menghitung dan memvisualisasikan matriks korelasi antara fitur numerik menggunakan `df.corr()` dan `seaborn.heatmap()`.

## 3. Pra-pemrosesan Data
*   **Pemilihan Fitur**: Menghapus kolom 'Address' yang non-numerik.
*   **Pemisahan Fitur/Target**: Memisahkan dataset menjadi variabel prediktor (`X`) dan variabel target (`y`).
*   **Pemisahan Data Latih-Uji**: Membagi data menjadi set pelatihan (70%) dan pengujian (30%) untuk pengembangan dan evaluasi model.

## 4. Pelatihan Model Regresi
*   **Inisialisasi Model**: Menginisialisasi model `LinearRegression` dari `sklearn.linear_model`.
*   **Pelatihan Model**: Melatih model regresi linier pada data pelatihan (`X_train`, `y_train`).
*   **Analisis Koefisien**: Menampilkan _intercept_ dan koefisien dari model yang terlatih, memberikan wawasan tentang dampak setiap fitur terhadap harga rumah.

## 5. Analisis Hasil Pelatihan
*   **Signifikansi Statistik**: Menghitung _standard error_ dan statistik-t untuk setiap koefisien untuk menilai signifikansi statistik individualnya. Bagian ini menyoroti bahwa meskipun beberapa fitur mungkin memiliki koefisien besar, signifikansinya juga tergantung pada _standard error_nya.
*   **Visualisasi**: Menyajikan _scatter plot_ dari variabel prediktor individual terhadap 'Price' untuk memeriksa hubungan secara visual.

## 6. Evaluasi Model dan Pengujian Asumsi
*   **Prediksi & Residu**: Menghasilkan prediksi pada set pengujian dan menghitung residu (perbedaan antara nilai aktual dan prediksi).
*   **Uji Normalitas**: Melakukan uji Shapiro-Wilk pada residu untuk memeriksa normalitas.
*   **Pemeriksaan Homoskedastisitas**: Memvisualisasikan residu terhadap nilai prediksi untuk menilai homoskedastisitas (varians residu yang konstan).
*   **Aktual vs. Prediksi**: Memplot harga rumah aktual terhadap harga yang diprediksi untuk memvisualisasikan kinerja model.
*   **Metrik Kinerja**: Menghitung _Mean Absolute Error_ (MAE), _Root Mean Squared Error_ (RMSE), dan R-squared untuk set pelatihan dan pengujian untuk mengkuantifikasi akurasi model dan kekuatan penjelasannya.

## 7. Kesimpulan
*   **Ringkasan Kinerja**: Menyimpulkan bahwa model berkinerja baik dengan nilai R-squared yang tinggi (sekitar 0.92), menunjukkan bahwa model menjelaskan sebagian besar varians dalam harga rumah. Namun, perbedaan antara RMSE dan MAE menunjukkan adanya beberapa _outlier_ (prediksi dengan kesalahan besar).