🚗 Car Evaluation Classification Analysis

Proyek ini bertujuan untuk melakukan klasifikasi kelayakan mobil menggunakan dataset Car Evaluation dari UCI Machine Learning Repository. Analisis ini membandingkan performa model XGBoost dan Random Forest yang dioptimalkan menggunakan teknik Metaheuristic Particle Swarm Optimization (PSO) untuk pencarian hyperparameter.

📊 Dataset Information

Dataset ini merupakan model keputusan hierarkis yang dikembangkan untuk mengevaluasi mobil berdasarkan karakteristik teknisnya.

Link Dataset: UCI Machine Learning Repository - Car Evaluation

Target Variable: unacc, acc, good, vgood.

Fitur: buying, maint, doors, persons, lug_boot, safety.

🛠️ Key Features & Methodology

Exploratory Data Analysis (EDA): Visualisasi distribusi fitur dan korelasi antar variabel.

Preprocessing: - Menggunakan Ordinal Encoding untuk mengubah data kategorikal menjadi numerik sesuai urutan tingkatannya.

Penanganan data tidak seimbang (Imbalanced Data) menggunakan SMOTE (Synthetic Minority Over-sampling Technique).

Hyperparameter Tuning (PSO): Implementasi algoritma metaheuristik Particle Swarm Optimization untuk menemukan parameter terbaik bagi XGBoost dan Random Forest secara efisien.

Performance Comparison: Pengujian dilakukan pada dua skenario data split:

80% Training : 20% Testing

70% Training : 30% Testing

💻 Tech Stack

Bahasa: Python

Library Utama:

Scikit-Learn: Evaluasi model dan preprocessing.

XGBoost: Gradient boosting framework.

PySwarms: Library khusus untuk optimasi PSO.

Imbalanced-Learn (SMOTE): Penyeimbangan kelas target.

Pandas & Numpy: Manipulasi data.

Matplotlib & Seaborn: Visualisasi data.

🚀 Pipeline Analisis

Tahap 1: Memuat data dan melakukan encoding pada fitur kategorikal.

Tahap 2: Melakukan oversampling dengan SMOTE untuk mengatasi dominasi kelas unacc (70%).

Tahap 3: Mendefinisikan fungsi objektif untuk PSO (berdasarkan akurasi Cross-Validation).

Tahap 4: Menjalankan optimasi PSO untuk mendapatkan kombinasi parameter terbaik.

Tahap 5: Melatih model final dan mengevaluasi menggunakan Confusion Matrix dan Classification Report.

📈 Temuan Utama (Findings)

Berdasarkan hasil eksekusi kodingan:

Pentingnya Fitur: Fitur safety ditemukan sebagai variabel yang paling berpengaruh terhadap penentuan kelayakan mobil pada kedua model.

Efektivitas PSO: Optimasi PSO berhasil menemukan hyperparameter optimal yang memberikan akurasi sangat tinggi tanpa perlu melakukan exhaustive grid search.

Stabilitas Model: Baik XGBoost maupun Random Forest menunjukkan performa yang stabil, namun terdapat sedikit perbedaan akurasi pada variasi split data (80:20 vs 70:30).

Data Balancing: Tanpa SMOTE, model cenderung bias terhadap kelas mayoritas. Penggunaan SMOTE secara signifikan meningkatkan kemampuan model dalam mendeteksi kelas minoritas (vgood dan good).

📋 Citation

Bohanec, M. (1988). Car Evaluation [Dataset]. UCI Machine Learning Repository. https://www.google.com/search?q=https://doi.org/10.24432/C5JP48.

Dibuat untuk keperluan analisis data dan riset machine learning.
