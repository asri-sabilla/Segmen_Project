# 🎯 Customer Segmentation — Machine Learning Project
End-to-End ML Model for Targeted Marketing Strategy

## 📌 Project Overview
Sebuah perusahaan otomotif berencana memasuki pasar baru dan membutuhkan strategi pemasaran yang terarah. Untuk itu, project ini mengembangkan model Machine Learning yang mampu mengklasifikasikan calon pelanggan baru ke dalam 4 segmen (A, B, C, D) berdasarkan pola dari data pelanggan lama.

Model ini dirancang untuk memberikan wawasan mendalam tentang karakteristik pelanggan, memungkinkan perusahaan untuk menyusun kampanye pemasaran yang lebih personal, efisien, dan berdampak tinggi.

### Key Highlight
*   Model **Gradient Boosting** terpilih sebagai model terbaik untuk klasifikasi pelanggan.
*   Berhasil mengidentifikasi 4 segmen pelanggan dengan profil unik, di mana **Segmen 3** adalah "High Spender" yang cenderung muda dan belum menikah.
*   Menemukan korelasi menarik: semakin tua dan sudah menikah, skor pengeluaran cenderung menurun.
*   Berhasil memprediksi segmen untuk **2,627 calon pelanggan baru**, dengan **Segmen D** sebagai kelompok terbesar, memberikan arah yang jelas untuk fokus pemasaran.

---

## 🗂️ Repository Structure
```
├── data/
│   ├── train.csv                # Data pelanggan untuk pelatihan model
│   └── test.csv                 # Data calon pelanggan baru untuk prediksi
├── notebooks/
│   └── 01_customer_segmentation_eda.ipynb  # Eksplorasi Data Analisis (EDA)
├── src/
│   ├── preprocessing.py         # Script untuk pembersihan dan persiapan data
│   ├── train_model.py           # Script untuk pelatihan dan evaluasi model
│   └── predict.py               # Script untuk prediksi pada data baru
├── models/
│   └── gradient_boosting_model.pkl # Model terbaik yang sudah dilatih
├── assets/
│   └── segment_analysis.png     # Visualisasi kunci dari EDA
└── README.md
```

## 📊 Key Visualizations from EDA
Analisis eksplorasi data menghasilkan beberapa visualisasi kunci yang membentuk pemahaman kami tentang pelanggan, seperti distribusi `Spending Score` per segmen, hubungan antara `Usia` dan `Status Pernikahan`, serta matriks korelasi antar fitur.

---

## 🎯 Business Problem
Memasuki pasar baru tanpa pemahaman yang jelas tentang calon pelanggan dapat menyebabkan:
*   Pemborosan anggaran pemasaran pada target yang salah.
*   Pesan yang tidak relevan, menyebabkan rendahnya tingkat konversi.
*   Kesulitan dalam memprioritaskan prospek pelanggan yang paling berpotensi.

---

## 🎯 Objectives
*   Melakukan eksplorasi data (EDA) untuk memahami karakteristik dan pola tersembunyi.
*   Melakukan preprocessing data untuk mempersiapkannya bagi model Machine Learning.
*   Melatih berbagai model klasifikasi dan memilih model dengan performa terbaik.
*   Mengevaluasi performa model secara menyeluruh.
*   Menerapkan model terbaik untuk melakukan prediksi pada data calon pelanggan baru.
*   Menerjemahkan hasil prediksi menjadi strategi pemasaran yang dapat ditindaklanjuti.

---

## 🛠️ Tech Stack & Workflow
### 1️⃣ Data Processing & EDA (Python)
*   **Tools**: Python (Pandas, NumPy, Matplotlib, Seaborn)
*   **Proses**:
    *   Analisis distribusi fitur seperti `Age`, `Spending Score`, `Ever_Married`.
    *   Identifikasi korelasi antar fitur untuk menemukan hubungan menarik (misalnya, `Ever_Married` vs `Spending Score`).
    *   Visualisasi perbandingan karakteristik antar segmen.

### 2️⃣ Data Preprocessing
*   **Proses**:
    *   Menangani missing values.
    *   Melakukan encoding pada fitur kategorikal (`Profession`, `Ever_Married`, `Var_1`).
    *   Menstandarisasi fitur numerik jika diperlukan.

### 3️⃣ Modeling & Evaluation (Scikit-learn)
*   **Proses**:
    *   Melatih beberapa model klasifikasi seperti Logistic Regression, Random Forest, dan Gradient Boosting.
    *   Menggunakan metrik evaluasi seperti Akurasi, Precision, Recall, dan F1-Score.
    *   **Model Terpilih**: Gradient Boosting menunjukkan performa terbaik dan paling konsisten.

### 4️⃣ Prediction & Business Analysis
*   Menggunakan model Gradient Boosting untuk memprediksi segmen 2,627 calon pelanggan baru.
*   Menganalisis distribusi hasil prediksi untuk merumuskan implikasi bisnis dan rekomendasi strategi.

---

## 🔍 Key Insights & Findings
### 1️⃣ 💰 Spending Behavior by Segment
*   **Segmen 3 (High Spender):** Memiliki skor pengeluaran tertinggi. Mereka adalah pembelanja besar dan menjadi target utama untuk produk premium.
*   **Segmen 0 (Low Spender):** Cenderung hemat dengan skor pengeluaran terendah. Mereka lebih responsif terhadap penawaran hemat dan diskon.
*   **Segmen 1 & 2 (Middle Spender):** Menunjukkan pola pengeluaran standar, seimbang antara hemat dan boros.

### 2️⃣ 💍 Marital Status & Age Profile
*   **Segmen 3 (Young & Unmarried):** Didominasi oleh pelanggan yang **belum menikah** dan berusia lebih muda (median ~30 tahun). Ini adalah segmen yang dinamis dan terbuka terhadap inovasi.
*   **Segmen 0, 1, 2 (Mature & Married):** Mayoritas pelanggan di segmen ini sudah **menikah** dan berusia lebih tua (median ~40-50 tahun), menunjukkan stabilitas dan preferensi produk yang lebih teruji.

### 3️⃣ 📊 Key Feature Correlations
*   **Korelasi Positif:** `Ever_Married` ↔ `Age` (+0.56). Semakin tua, kemungkinan sudah menikah.
*   **Korelasi Negatif Kuat:** `Ever_Married` ↔ `Spending Score` (-0.63). Pelanggan yang sudah menikah cenderung lebih hemat. Ini adalah insight krusial untuk penargetan promo.

---

## 📌 Conclusion & Business Impact
Model klasifikasi berhasil memberikan gambaran jelas tentang pasar baru. Hasil prediksi pada 2,627 calon pelanggan menunjukkan distribusi sebagai berikut: **Segmen D > A > C > B**.

### 1. Implikasi & Rekomendasi Strategi Pemasaran
*   ** Segmen D (Dominan):** Fokuskan anggaran terbesar di sini. Gunakan strategi **promosi agresif, diskon, dan kampanye digital** untuk menarik segmen yang paling mudah diakses ini.
*   ** Segmen A (Potensial):** Sasar dengan **penawaran premium, fokus pada kualitas dan keunggulan produk**. Segmen ini memiliki potensi margin keuntungan tinggi.
*   ** Segmen C (Stabil):** Bangun loyalitas jangka panjang melalui **program edukasi dan penawaran personal**. Mereka dapat menjadi basis pelanggan yang setia.
*   ** Segmen B (Kecil):** Pendekatan ini perlu **riset lebih lanjut**. Lakukan pemasaran yang sangat selektif untuk menghindari pemborosan biaya.

### 2. Nilai Bisnis dari Model
*   **Targeting yang Tepat:** Tim sales dapat memprioritaskan prospek berdasarkan segmen, meningkatkan efisiensi.
*   **Efisiensi Biaya:** Mengurangi pengeluaran pemasaran yang tidak efektif.
*   **Penjualan Lebih Tinggi:** Pesan yang relevan meningkatkan probabilitas konversi.
*   **Peramalan Akurat:** Membantu membuat forecast penjualan yang lebih baik berdasarkan karakteristik segmen.

Model ini bukan hanya sekadar alat prediksi, tetapi aset strategis yang memungkinkan perusahaan memahami dan menaklukkan pasar baru dengan basis data yang solid.

---

## 👤 Author
**[Asri Sabilla Putri]** 🤖 Machine Learning Enthusiast | Data-Driven Marketing
🔗 LinkedIn: [[Link Portfolio Anda](https://www.linkedin.com/in/asrisabilla)]
🌐 Portfolio: [[Link Portfolio Anda](https://portofolio-asri.netlify.app/)]
