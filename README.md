# 📘 Klasifikasi Penyakit Jantung Menggunakan Perbandingan Machine Learning dan Deep Learning
#👤 Informasi
# Nama: Nailah Adyan Nurahmah
# Repo: https://github.com/nailahadyan/Heart-Disease-Project-UAS
# Video: [...]
---
# 1. 🎯 Ringkasan Proyek

Penyakit jantung merupakan penyebab utama kematian secara global yang memerlukan deteksi dini melalui parameter klinis yang tepat. Proyek ini bertujuan untuk membangun sistem prediksi otomatis menggunakan dataset **UCI Heart Disease** untuk mengidentifikasi risiko pasien secara akurat. Tantangan utama dalam pemodelan ini adalah menangkap hubungan non-linear antar fitur medis yang kompleks, seperti korelasi antara detak jantung maksimal dan tipe nyeri dada. Untuk mengatasi hal tersebut, proyek ini membandingkan tiga algoritma: **Logistic Regression** (Baseline), **Random Forest** (Advanced), dan **Multilayer Perceptron** (Deep Learning).

---

# 2. 📄 Problem & Goals

**Problem Statements:**

* Bagaimana membangun model yang mampu mengidentifikasi risiko penyakit jantung secara akurat berdasarkan parameter klinis pasien?
* Adanya ketidakkonsistenan data (seperti nilai kosong yang disimbolkan '?') yang memerlukan teknik preprocessing agar tidak menurunkan performa model.
* Perlu membandingkan efektivitas antara model Machine Learning konvensional dengan model Deep Learning dalam menangani data kesehatan yang sensitif.

**Goals:**

* Membangun model klasifikasi dengan target akurasi minimal di atas **80%**.
* Menghasilkan model yang memiliki tingkat *Recall* tinggi guna meminimalkan kesalahan diagnosis pada pasien yang sebenarnya sakit (*False Negative*).
* Menentukan model terbaik melalui evaluasi metrik Accuracy, Precision, Recall, dan F1-Score untuk pengambilan keputusan medis yang lebih baik.

---

## 📁 Struktur Folder

```
project/
│
├── data/
│   └── heart.csv                    # Dataset utama (UCI Heart Disease)
|   └── hasil_uji_jantung_rf.csv     # Dataset hasil uji
│
├── notebooks/                       
│   └── Heart_Disease_Nailah Adyan_233307055_5b.ipynb   # Jupyter notebooks
│
├── models/                          # Saved models & outputs
│   ├── model_jantung_logreg.pkl     #
│   ├── model_jantung_rf.pkl         #
│   └── model_jantung_dl.h5       #
│
├── images/                          # Visualisai & Plot
│   ├── Class Distribution.png
│   ├── Heatmap korelasi.png
│   ├── Histogram (Distribusi Usia).png
│   ├── Matrix Logistic Regression.png
│   ├── Matrix Random Forest.png
│   ├── Matrix Deep Learning.png
│   └── Visualisai_Perbandingan.png
│
├── Laporan_UAS_DS_Nailah Adyan_233307055_5B.pdf
├── requirements.txt                 # Dependencies
└── README.md

```

---

# 3. 📊 Dataset

* **Sumber:** UCI Machine Learning Repository
* **Jumlah Data:** 303 sampel
* **Tipe Data:** Kategorikal (nominal/ordinal), Integer, dan Float

### Fitur Utama

| Fitur | Deskripsi |
| --- | --- |
| `age` | Usia pasien |
| `sex` | Jenis kelamin |
| `cp` | Tipe nyeri dada (chest pain) |
| `trestbps` | Tekanan darah istirahat |
| `chol` | Kadar kolesterol serum |
| `thalach` | Detak jantung maksimal yang dicapai |
| `target` | Diagnosis penyakit jantung (1 = Sakit, 0 = Sehat) |

---

# 4. 🔧 Data Preparation

* **Cleaning:** Penanganan nilai kosong ('?') menggunakan metode imputasi median untuk menjaga integritas data.
* **Transformasi:**
1. **Encoding:** Menyesuaikan fitur kategorikal agar dapat diproses oleh algoritma.
2. **Scaling:** Fitur numerik distandarisasi menggunakan `StandardScaler` untuk mengoptimalkan performa model Logistic Regression dan Deep Learning.


* **Splitting:** Data dibagi menjadi **80% Training Set** dan **20% Test Set**.

---

# 5. 🤖 Modeling

* **Model 1 – Baseline:** Logistic Regression (Pendekatan statistik linear).
* **Model 2 – Advanced ML:** Random Forest (Algoritma ensemble berbasis kumpulan pohon keputusan).
* **Model 3 – Deep Learning:** Multilayer Perceptron / MLP (Neural Network dengan 2 hidden layer dan layer Dropout).

---

# 6. 🧪 Evaluation

**Metrik:** Accuracy, Precision, Recall, dan F1-Score (Fokus utama pada Recall untuk kepentingan diagnosa medis).

### Tabel Hasil Perbandingan

| Model | Accuracy | Precision | Recall | F1-Score | Training Time |
| --- | --- | --- | --- | --- | --- |
| **Baseline** | 0.8689 | 0.81 | 0.93 | 0.87 | < 1s |
| **Advanced** | **0.8852** | **0.84** | **0.93** | **0.88** | < 1s |
| **Deep Learning** | 0.8689 | 0.81 | 0.93 | 0.87 | 14.73s |

---

# 7. 🏁 Kesimpulan

* **Model Terbaik:** **Random Forest**.
* **Alasan:** Memberikan akurasi tertinggi (**88.52%**) dan paling seimbang dalam menangani data medis tabular.
* **Insight penting:**
* Fitur **`cp` (Chest Pain)** dan **`thalach`** terbukti menjadi indikator paling kuat dalam klasifikasi risiko jantung.
* Ketiga model menunjukkan nilai **Recall** yang tinggi (0.93), menandakan sensitivitas yang baik terhadap deteksi pasien sakit.
* Deep Learning memerlukan waktu komputasi lebih lama tanpa memberikan peningkatan performa yang signifikan pada dataset berukuran kecil.



---

# 8. 🔮 Future Work

* **Data:** Mengumpulkan lebih banyak observasi dan melakukan feature engineering lebih lanjut.
* **Model:** Mencoba hyperparameter tuning yang lebih ekstensif atau menggunakan metode ensemble lain seperti XGBoost.
* **Deployment:** Membuat aplikasi web interaktif menggunakan Streamlit agar model dapat digunakan secara praktis.

---

# 9. Reproducibility

* **Python version:** 3.10 / 3.11
* **Main Libraries:** Pandas, Numpy, Scikit-learn, Tensorflow/Keras, Matplotlib, Seaborn.
