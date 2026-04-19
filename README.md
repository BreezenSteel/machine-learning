# 🚗 Car Evaluation Classification Analysis

Proyek ini bertujuan untuk melakukan klasifikasi kelayakan mobil menggunakan dataset **Car Evaluation** dari **UCI Machine Learning Repository**. Analisis ini membandingkan performa model **XGBoost** dan **Random Forest** yang dioptimalkan menggunakan teknik metaheuristik **Particle Swarm Optimization (PSO)** untuk pencarian hyperparameter terbaik.

---

## 📊 Dataset Information

Dataset ini merupakan model keputusan hierarkis yang dikembangkan untuk mengevaluasi mobil berdasarkan karakteristik teknisnya.

- **Dataset Source**: Car Evaluation – UCI Machine Learning Repository  
- **Target Variable**: `unacc`, `acc`, `good`, `vgood`
- **Features**:
  - `buying`
  - `maint`
  - `doors`
  - `persons`
  - `lug_boot`
  - `safety`

Dataset ini bersifat kategorikal penuh dan sangat cocok untuk permasalahan klasifikasi multi-class.

---

## 🛠️ Methodology

### 1. Exploratory Data Analysis (EDA)

Dilakukan visualisasi distribusi fitur dan analisis hubungan antar variabel untuk memahami karakteristik data sebelum pemodelan.

### 2. Data Preprocessing

Karena seluruh fitur bersifat kategorikal ordinal, digunakan:

- **Ordinal Encoding** untuk mengubah kategori menjadi numerik berdasarkan tingkatannya

Contoh:
- `buying`: low < med < high < vhigh
- `safety`: low < med < high

### 3. Handling Imbalanced Data

Dataset memiliki ketidakseimbangan kelas yang cukup tinggi, terutama dominasi kelas:

- `unacc` (~70%)

Untuk mengatasi hal tersebut digunakan:

- **SMOTE (Synthetic Minority Over-sampling Technique)**

Tujuannya agar model tidak bias terhadap kelas mayoritas dan mampu mengenali kelas minoritas seperti `good` dan `vgood`.

### 4. Hyperparameter Optimization using PSO

Optimasi parameter dilakukan menggunakan:

- **Particle Swarm Optimization (PSO)**

PSO digunakan untuk mencari kombinasi hyperparameter terbaik secara efisien tanpa exhaustive search seperti Grid Search.

Model yang dioptimasi:

- **XGBoost**
- **Random Forest**

Fungsi objektif PSO menggunakan:

- **Cross Validation Accuracy**

### 5. Performance Evaluation

Pengujian dilakukan pada dua skenario split data:

- **80% Training : 20% Testing**
- **70% Training : 30% Testing**

Evaluasi model menggunakan:

- Accuracy Score
- Confusion Matrix
- Classification Report
- Feature Importance

---

## 💻 Tech Stack

### Language

- Python

### Main Libraries

- **Scikit-Learn** → preprocessing, evaluasi model
- **XGBoost** → gradient boosting framework
- **PySwarms** → optimasi PSO
- **Imbalanced-Learn (SMOTE)** → penanganan data tidak seimbang
- **Pandas & NumPy** → manipulasi data
- **Matplotlib & Seaborn** → visualisasi data

---

## 🚀 Analysis Pipeline

### Tahap 1

Memuat dataset dan melakukan encoding pada fitur kategorikal menggunakan ordinal encoding.

### Tahap 2

Melakukan oversampling menggunakan SMOTE untuk mengatasi dominasi kelas mayoritas.

### Tahap 3

Mendefinisikan fungsi objektif PSO berdasarkan akurasi cross-validation.

### Tahap 4

Menjalankan optimasi PSO untuk mendapatkan kombinasi hyperparameter terbaik pada:

- XGBoost
- Random Forest

### Tahap 5

Melatih model final menggunakan parameter terbaik dan mengevaluasi performanya menggunakan confusion matrix dan classification report.

---

## 📈 Main Findings

### 🔹 Pentingnya Fitur

Fitur **safety** ditemukan sebagai variabel yang paling berpengaruh dalam menentukan kelayakan mobil pada kedua model.

Hal ini menunjukkan bahwa tingkat keamanan menjadi faktor utama dalam proses evaluasi kendaraan.

### 🔹 Efektivitas PSO

Optimasi menggunakan **Particle Swarm Optimization (PSO)** berhasil menemukan hyperparameter optimal dengan akurasi sangat tinggi tanpa memerlukan exhaustive grid search yang lebih mahal secara komputasi.

### 🔹 Stabilitas Model

Baik **XGBoost** maupun **Random Forest** menunjukkan performa yang stabil pada kedua skenario split data:

- 80:20
- 70:30

Meskipun terdapat sedikit perbedaan akurasi, kedua model tetap memberikan hasil klasifikasi yang sangat baik.

### 🔹 Pengaruh SMOTE

Tanpa SMOTE, model cenderung bias terhadap kelas mayoritas (`unacc`).

Setelah dilakukan oversampling menggunakan SMOTE, performa model meningkat secara signifikan terutama dalam mendeteksi kelas minoritas seperti:

- `good`
- `vgood`

---

## 📋 Citation

Bohanec, M. (1988).  
**Car Evaluation Dataset**.  
UCI Machine Learning Repository.

DOI: https://doi.org/10.24432/C5JP48

---

## 📌 Purpose

Proyek ini dibuat untuk keperluan:

- Analisis data
- Penelitian machine learning
- Perbandingan algoritma klasifikasi
- Implementasi metaheuristic optimization pada hyperparameter tuning

---

## 👨‍💻 Author

Dibuat untuk keperluan riset dan pengembangan analisis klasifikasi berbasis machine learning.
