# Perbandingan Fungsi Aktivasi MLP — Dataset Iris

Notebook ini membandingkan performa **Multi-Layer Perceptron (MLP)** menggunakan tiga fungsi aktivasi pada hidden layer: **Sigmoid**, **Tanh**, dan **ReLU**, pada dataset **Iris**.


## Dataset
Menggunakan `sklearn.datasets.load_iris()` — identik dengan dataset Iris di Kaggle (150 sampel, 4 fitur, 3 kelas).

## Arsitektur Model
Hidden layer `(10, 10)`, solver Adam, max_iter 2000 — sama untuk ketiga model, hanya fungsi aktivasi yang berbeda.

## Cara Menjalankan
```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
jupyter notebook MLP_Iris_Activation_Comparison.ipynb
```
Lalu jalankan semua sel (Run All).

## Ringkasan Hasil (rata-rata 10 percobaan)

| Aktivasi | Accuracy | F1-Score | Final Loss | Iterasi Konvergen |
|---|---|---|---|---|
| Sigmoid | ~0.960 | ~0.960 | ~0.084 (tertinggi) | ~1375 (paling lambat) |
| Tanh    | ~0.960 | ~0.960 | ~0.067 | ~736 |
| ReLU    | ~0.957 | ~0.957 | ~0.057 (terendah) | ~686 (paling cepat) |

## Kesimpulan
**ReLU** paling efisien (konvergen tercepat, loss terendah) dengan akurasi tetap kompetitif. **Tanh** kompetitif dengan akurasi setara/lebih stabil. **Sigmoid** paling lambat konvergen karena vanishing gradient. Detail lengkap & alasan ada di sel terakhir notebook.
