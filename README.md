# 📊 UAS Data Mining - Preprocessing dan Unsupervised Learning (K-Means Clustering)

## 👨‍🎓 Identitas Mahasiswa

- **Nama:** Ahmad Husni Kamalluddin
- **Mata Kuliah:** Data Mining
- **Topik:** Preprocessing dan Unsupervised Learning (K-Means Clustering)

---

# BAB I Pendahuluan

## 1.1 Latar Belakang

Data Mining merupakan proses menggali informasi dari sekumpulan data untuk menemukan pola yang bermanfaat. Pada proyek ini digunakan algoritma K-Means Clustering untuk mengelompokkan data pelanggan berdasarkan usia, pendapatan tahunan, dan tingkat pengeluaran.

...
---

# BAB II Landasan Teori

## 2.1 Data Mining

Data Mining merupakan proses untuk menemukan pola, hubungan, atau informasi yang bermanfaat dari sekumpulan data dalam jumlah besar. Proses ini memanfaatkan berbagai teknik statistik, kecerdasan buatan (Artificial Intelligence), dan Machine Learning untuk menghasilkan informasi yang dapat membantu pengambilan keputusan. Saat ini Data Mining banyak diterapkan pada berbagai bidang, seperti bisnis, kesehatan, pendidikan, dan pemasaran.

---

## 2.2 Machine Learning

Machine Learning adalah salah satu cabang dari Artificial Intelligence (AI) yang memungkinkan komputer mempelajari pola dari data tanpa harus diprogram secara rinci. Sistem akan belajar berdasarkan data yang diberikan sehingga mampu membuat prediksi atau menemukan pola secara otomatis.

Secara umum, Machine Learning dibagi menjadi tiga jenis, yaitu:

- **Supervised Learning**, yaitu pembelajaran menggunakan data yang telah memiliki label.
- **Unsupervised Learning**, yaitu pembelajaran menggunakan data tanpa label untuk menemukan pola atau kelompok data.
- **Reinforcement Learning**, yaitu pembelajaran berdasarkan sistem pemberian reward dan punishment.

Pada proyek ini digunakan metode **Unsupervised Learning**.

---

## 2.3 Unsupervised Learning

Unsupervised Learning merupakan metode pembelajaran mesin yang digunakan untuk menganalisis data tanpa adanya label atau target. Tujuan utama metode ini adalah menemukan pola, hubungan, maupun struktur tersembunyi di dalam data.

Salah satu teknik yang paling banyak digunakan dalam Unsupervised Learning adalah **Clustering**, yaitu proses mengelompokkan data berdasarkan tingkat kemiripan karakteristiknya.

---

## 2.4 Clustering

Clustering adalah teknik pengelompokan data ke dalam beberapa kelompok (cluster) sehingga data yang berada dalam satu kelompok memiliki karakteristik yang lebih mirip dibandingkan dengan data pada kelompok lainnya.

Teknik clustering banyak dimanfaatkan dalam berbagai bidang, antara lain:

- Segmentasi pelanggan
- Analisis pasar
- Sistem rekomendasi
- Analisis citra
- Deteksi pola data
- Analisis perilaku konsumen

Pada penelitian ini clustering digunakan untuk mengelompokkan pelanggan berdasarkan usia, pendapatan tahunan, dan tingkat pengeluaran.

---

## 2.5 Algoritma K-Means Clustering

K-Means merupakan salah satu algoritma clustering yang paling populer karena memiliki proses yang sederhana, cepat, dan mudah diimplementasikan.

Algoritma ini bekerja dengan membagi data ke dalam sejumlah kelompok (cluster) berdasarkan kedekatan jarak terhadap titik pusat cluster yang disebut **centroid**.

Tahapan algoritma K-Means adalah sebagai berikut:

1. Menentukan jumlah cluster (K).
2. Memilih centroid awal secara acak.
3. Menghitung jarak setiap data terhadap seluruh centroid menggunakan jarak Euclidean.
4. Menempatkan data pada centroid terdekat.
5. Menghitung kembali posisi centroid berdasarkan rata-rata anggota cluster.
6. Mengulangi proses hingga posisi centroid tidak berubah atau telah mencapai kondisi konvergen.

Pada proyek ini digunakan **K = 5** berdasarkan hasil pengujian menggunakan metode Elbow.

---

## 2.6 Data Preprocessing

Data preprocessing merupakan tahapan awal sebelum proses Machine Learning dilakukan. Tujuannya adalah meningkatkan kualitas data agar menghasilkan model yang lebih baik.

Tahapan preprocessing pada proyek ini meliputi:

- Pengecekan missing value.
- Pengecekan data duplikat.
- Standardisasi data menggunakan StandardScaler.

Hasil pemeriksaan menunjukkan bahwa dataset tidak memiliki missing value maupun data duplikat sehingga dapat langsung digunakan untuk proses clustering.

---

## 2.7 StandardScaler

StandardScaler merupakan teknik normalisasi yang digunakan untuk menyamakan skala setiap atribut numerik. Dengan proses ini setiap variabel akan memiliki rata-rata mendekati nol dan standar deviasi sebesar satu.

Standardisasi sangat penting pada algoritma K-Means karena proses perhitungan jarak Euclidean sangat dipengaruhi oleh perbedaan skala data.

---

## 2.8 Elbow Method

Elbow Method merupakan metode yang digunakan untuk menentukan jumlah cluster terbaik pada algoritma K-Means.

Metode ini dilakukan dengan menghitung nilai **Within Cluster Sum of Squares (WCSS)** untuk beberapa nilai K, kemudian divisualisasikan dalam bentuk grafik. Titik yang membentuk sudut menyerupai siku (elbow) menunjukkan jumlah cluster yang paling optimal.

Pada proyek ini, hasil Elbow Method menunjukkan bahwa jumlah cluster terbaik adalah **5 cluster**.

---

## 2.9 Silhouette Score

Silhouette Score merupakan metode evaluasi yang digunakan untuk mengukur kualitas hasil clustering.

Nilai Silhouette Score berada pada rentang **-1 hingga 1**, dengan interpretasi sebagai berikut:

- Nilai mendekati **1** menunjukkan hasil clustering sangat baik.
- Nilai mendekati **0** menunjukkan antar cluster saling berdekatan.
- Nilai kurang dari **0** menunjukkan hasil clustering kurang baik.

Pada proyek ini diperoleh nilai **Silhouette Score sebesar 0.40846873777345605**, yang menunjukkan bahwa hasil pengelompokan berada pada kategori **cukup baik**, sehingga algoritma K-Means mampu mengelompokkan data pelanggan dengan baik berdasarkan karakteristiknya.
