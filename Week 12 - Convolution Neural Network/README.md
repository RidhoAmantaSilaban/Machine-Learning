#  CNN Trash Classification — Deteksi Jenis Sampah


## Deskripsi Proyek

Proyek ini mengimplementasikan model CNN untuk mengklasifikasikan gambar sampah ke dalam 6 kategori. Model dibangun menggunakan **TensorFlow/Keras** dan dilatih menggunakan dataset publik dari Kaggle.

CNN dipilih karena kemampuannya dalam:
- Mendeteksi fitur spasial dari gambar (tepi, sudut, tekstur, bentuk)
- Efisiensi parameter melalui *weight sharing* pada filter konvolusi
- Mempertahankan struktur spasial data gambar

---

##  Kelas yang Diklasifikasikan

| No | Kelas | Deskripsi |
|----|-------|-----------|
| 1 | `cardboard` | Kardus / karton |
| 2 | `glass` | Kaca / botol kaca |
| 3 | `metal` | Logam / kaleng |
| 4 | `paper` | Kertas |
| 5 | `plastic` | Plastik / botol plastik |
| 6 | `trash` | Sampah umum lainnya |

---

##  Struktur File

```
project/
│
├── CNN_Trash_Classification.ipynb   # Notebook utama (training & evaluasi)
├── README.md                        # Dokumentasi proyek ini
├── PENJELASAN_PROGRAM.md            # Penjelasan detail setiap cell notebook
│
└── data/                            # Folder dataset (download dari Kaggle)
    ├── train/
    │   ├── cardboard/
    │   ├── glass/
    │   ├── metal/
    │   ├── paper/
    │   ├── plastic/
    │   └── trash/
    └── test/
        ├── cardboard/
        ├── glass/
        ├── metal/
        ├── paper/
        ├── plastic/
        └── trash/
```

---

##  Requirements

```
python >= 3.8
tensorflow >= 2.10
numpy
matplotlib
seaborn
scikit-learn
kaggle
```

Install semua dependensi sekaligus:

```bash
pip install tensorflow matplotlib seaborn scikit-learn kaggle
```


##  Arsitektur Model CNN

```
Input (128×128×3)
       │
  ┌────▼────┐
  │ Conv2D  │  32 filter, kernel 3×3, ReLU
  │ BN      │  Batch Normalization
  │ Pool    │  MaxPooling 2×2
  └────┬────┘
       │
  ┌────▼────┐
  │ Conv2D  │  64 filter, kernel 3×3, ReLU
  │ BN      │  Batch Normalization
  │ Pool    │  MaxPooling 2×2
  └────┬────┘
       │
  ┌────▼────┐
  │ Conv2D  │  128 filter, kernel 3×3, ReLU
  │ BN      │  Batch Normalization
  │ Pool    │  MaxPooling 2×2
  └────┬────┘
       │
   Flatten
       │
  Dense(256) + ReLU + Dropout(0.5)
       │
  Dense(128) + ReLU + Dropout(0.3)
       │
  Dense(6) + Softmax   ← Output: probabilitas 6 kelas
```

---

## Konfigurasi Training

| Parameter | Nilai |
|-----------|-------|
| Image Size | 128 × 128 |
| Batch Size | 32 |
| Epochs | 20 (maks) |
| Optimizer | Adam |
| Loss Function | Categorical Crossentropy |
| Metrics | Accuracy |
| Early Stopping | patience = 5 |
| Reduce LR | factor = 0.5, patience = 3 |

---
