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
---

# BAB III Implementasi

## 3.1 Dataset

Dataset yang digunakan pada proyek ini adalah **Mall Customers Dataset**, yang berisi informasi mengenai pelanggan sebuah pusat perbelanjaan. Dataset terdiri dari **200 data pelanggan** dengan lima atribut, yaitu:

| No | Atribut | Keterangan |
|----|----------|------------|
| 1 | CustomerID | ID pelanggan |
| 2 | Gender | Jenis kelamin |
| 3 | Age | Umur pelanggan |
| 4 | Annual Income (k$) | Pendapatan tahunan pelanggan |
| 5 | Spending Score (1-100) | Tingkat pengeluaran pelanggan |

Dataset ini digunakan untuk mengelompokkan pelanggan berdasarkan karakteristik usia, pendapatan tahunan, dan tingkat pengeluaran menggunakan algoritma K-Means Clustering.

---

## 3.2 Import Library

Tahap pertama adalah mengimpor beberapa library Python yang dibutuhkan selama proses analisis data.

Library yang digunakan antara lain:

- Pandas
- NumPy
- Matplotlib
- StandardScaler
- KMeans
- Silhouette Score

**Screenshot kode:**

> Tambahkan screenshot Cell 1 di sini.

Library tersebut digunakan untuk membaca dataset, melakukan preprocessing, membangun model clustering, melakukan visualisasi, dan mengevaluasi hasil clustering.

---

## 3.3 Membaca Dataset

Dataset dibaca menggunakan fungsi `read_csv()` dari library Pandas.

**Screenshot kode:**

> Tambahkan screenshot Cell 2 di sini.

Setelah dataset berhasil dibaca, dilakukan pengecekan isi dataset menggunakan fungsi `head()`. Hasilnya menunjukkan bahwa dataset memiliki lima atribut utama yang siap digunakan pada proses analisis.

---

## 3.4 Informasi Dataset

Tahap berikutnya adalah melihat informasi dataset menggunakan fungsi `info()` dan `describe()`.

**Screenshot kode:**

> Tambahkan screenshot Cell 3 dan Cell 4 di sini.

Hasil pemeriksaan menunjukkan bahwa dataset memiliki **200 data**, seluruh atribut numerik bertipe integer, sedangkan atribut Gender bertipe string.

---

## 3.5 Data Cleaning

Tahap preprocessing dilakukan dengan mengecek missing value dan data duplikat.

**Screenshot kode:**

> Tambahkan screenshot Cell 5, Cell 6, dan Cell 7 di sini.

Berdasarkan hasil pemeriksaan diperoleh:

- Missing Value = **0**
- Duplicate Data = **0**

Artinya dataset sudah bersih sehingga tidak diperlukan proses penghapusan maupun imputasi data.

---

## 3.6 Standardisasi Data

Sebelum proses clustering dilakukan, data dinormalisasi menggunakan StandardScaler.

**Screenshot kode:**

> Tambahkan screenshot Cell 8 di sini.

Standardisasi dilakukan agar seluruh atribut numerik memiliki skala yang sama sehingga proses perhitungan jarak pada algoritma K-Means menjadi lebih akurat.

---

## 3.7 Penentuan Jumlah Cluster Menggunakan Elbow Method

Sebelum melakukan proses clustering, terlebih dahulu ditentukan jumlah cluster yang optimal menggunakan **Elbow Method**. Metode ini dilakukan dengan menghitung nilai **Within Cluster Sum of Squares (WCSS)** pada beberapa nilai K, kemudian divisualisasikan dalam bentuk grafik.

**Screenshot kode dan hasil:**

> Tambahkan screenshot Cell 9 beserta grafik Elbow Method.

Berdasarkan grafik Elbow Method, terlihat bahwa titik siku (elbow) berada pada **K = 5**, sehingga jumlah cluster yang digunakan pada proses K-Means Clustering adalah **5 cluster**.

---

## 3.8 Implementasi K-Means Clustering

Setelah jumlah cluster ditentukan, proses pengelompokan dilakukan menggunakan algoritma **K-Means** dengan jumlah cluster sebanyak lima.

**Screenshot kode:**

> Tambahkan screenshot Cell 10.

Hasil proses clustering menghasilkan sebuah kolom baru bernama **Cluster** yang menunjukkan kelompok setiap pelanggan berdasarkan karakteristik usia, pendapatan tahunan, dan tingkat pengeluaran.

---

## 3.9 Visualisasi Hasil Clustering

Untuk mempermudah analisis, hasil clustering divisualisasikan menggunakan **Scatter Plot**. Setiap warna pada grafik menunjukkan kelompok (cluster) yang berbeda.

**Screenshot grafik:**

> Tambahkan screenshot Cell 11.

Berdasarkan visualisasi tersebut terlihat bahwa pelanggan berhasil dikelompokkan menjadi lima cluster dengan karakteristik yang berbeda-beda.

---

## 3.10 Evaluasi Model

Evaluasi dilakukan menggunakan **Silhouette Score** untuk mengetahui kualitas hasil clustering.

**Screenshot hasil:**

> Tambahkan screenshot Cell 12.

Hasil evaluasi menunjukkan nilai:

**Silhouette Score = 0.40846873777345605**

Nilai tersebut menunjukkan bahwa kualitas clustering berada pada kategori **cukup baik**, sehingga model K-Means mampu mengelompokkan pelanggan berdasarkan karakteristik yang dimiliki.

---

## 3.11 Hasil Clustering

Jumlah anggota pada setiap cluster ditunjukkan pada tabel berikut.

| Cluster | Jumlah Pelanggan |
|---------:|-----------------:|
| 0 | 58 |
| 1 | 40 |
| 2 | 26 |
| 3 | 45 |
| 4 | 31 |

**Screenshot hasil Cell 13:**

> Tambahkan screenshot Cell 13.

Distribusi tersebut menunjukkan bahwa jumlah anggota pada setiap cluster tidak sama, sehingga setiap kelompok memiliki karakteristik pelanggan yang berbeda.

---

## 3.12 Analisis Karakteristik Cluster

Berdasarkan hasil rata-rata setiap cluster diperoleh karakteristik sebagai berikut.

| Cluster | Usia | Pendapatan (k$) | Spending Score |
|---------:|------:|----------------:|---------------:|
| 0 | 55.28 | 47.62 | 41.71 |
| 1 | 32.88 | 86.10 | 81.53 |
| 2 | 25.77 | 26.12 | 74.85 |
| 3 | 26.73 | 54.31 | 40.91 |
| 4 | 44.39 | 89.77 | 18.48 |

**Screenshot hasil Cell 14:**

> Tambahkan screenshot Cell 14.

Analisis masing-masing cluster adalah sebagai berikut.

- **Cluster 0** terdiri dari pelanggan dengan usia relatif lebih tua, pendapatan menengah, dan tingkat pengeluaran yang cukup rendah.
- **Cluster 1** berisi pelanggan muda dengan pendapatan tinggi serta tingkat pengeluaran tinggi. Kelompok ini merupakan pelanggan yang paling potensial.
- **Cluster 2** terdiri dari pelanggan muda dengan pendapatan rendah namun memiliki tingkat pengeluaran yang tinggi.
- **Cluster 3** merupakan pelanggan dengan usia muda, pendapatan sedang, dan tingkat pengeluaran sedang.
- **Cluster 4** memiliki pendapatan tinggi tetapi tingkat pengeluaran paling rendah sehingga berpotensi menjadi target strategi promosi untuk meningkatkan pembelian.

  ---

# BAB IV Hasil dan Pembahasan

## 4.1 Hasil Clustering

Berdasarkan implementasi algoritma K-Means Clustering menggunakan dataset **Mall Customers**, diperoleh hasil pengelompokan sebanyak **5 cluster**. Proses clustering dilakukan menggunakan atribut **Age**, **Annual Income (k$)**, dan **Spending Score (1-100)** yang telah melalui tahap standardisasi menggunakan **StandardScaler**.

Hasil pengelompokan menunjukkan bahwa setiap cluster memiliki karakteristik pelanggan yang berbeda berdasarkan usia, pendapatan tahunan, dan tingkat pengeluaran. Visualisasi hasil clustering memperlihatkan bahwa sebagian besar data berhasil dikelompokkan dengan baik sesuai tingkat kemiripannya.

**Screenshot Visualisasi Clustering:**

> Tambahkan screenshot hasil Cell 11 di sini.

---

## 4.2 Evaluasi Hasil Clustering

Untuk mengetahui kualitas hasil clustering dilakukan evaluasi menggunakan **Silhouette Score**.

Hasil evaluasi diperoleh sebagai berikut:

| Metode Evaluasi | Hasil |
|-----------------|------:|
| Silhouette Score | **0.40846873777345605** |

Nilai tersebut menunjukkan bahwa hasil clustering berada pada kategori **cukup baik**, karena memiliki nilai lebih besar dari nol dan mendekati satu. Hal ini menunjukkan bahwa setiap cluster telah memiliki tingkat kemiripan yang cukup tinggi terhadap anggota dalam kelompoknya serta memiliki perbedaan yang cukup jelas dengan cluster lainnya.

**Screenshot Hasil Silhouette Score:**

> Tambahkan screenshot Cell 12 di sini.

---

## 4.3 Analisis Hasil Clustering

Distribusi jumlah pelanggan pada setiap cluster ditunjukkan pada tabel berikut.

| Cluster | Jumlah Pelanggan |
|---------:|-----------------:|
| 0 | 58 |
| 1 | 40 |
| 2 | 26 |
| 3 | 45 |
| 4 | 31 |

Berdasarkan hasil tersebut diketahui bahwa **Cluster 0** memiliki jumlah pelanggan terbanyak yaitu **58 orang**, sedangkan **Cluster 2** memiliki jumlah pelanggan paling sedikit yaitu **26 orang**.

Selanjutnya dilakukan analisis terhadap karakteristik masing-masing cluster berdasarkan nilai rata-rata setiap atribut.

| Cluster | Rata-rata Usia | Pendapatan (k$) | Spending Score |
|---------:|---------------:|----------------:|---------------:|
| 0 | 55.28 | 47.62 | 41.71 |
| 1 | 32.88 | 86.10 | 81.53 |
| 2 | 25.77 | 26.12 | 74.85 |
| 3 | 26.73 | 54.31 | 40.91 |
| 4 | 44.39 | 89.77 | 18.48 |

Berdasarkan tabel tersebut dapat dijelaskan bahwa:

- **Cluster 0** berisi pelanggan dengan usia relatif lebih tua, pendapatan menengah, dan tingkat pengeluaran yang cukup rendah.
- **Cluster 1** merupakan pelanggan dengan pendapatan tinggi dan tingkat pengeluaran tinggi sehingga menjadi kelompok pelanggan yang paling potensial.
- **Cluster 2** terdiri dari pelanggan muda dengan pendapatan rendah namun memiliki tingkat pengeluaran yang tinggi.
- **Cluster 3** berisi pelanggan dengan pendapatan dan tingkat pengeluaran sedang sehingga memiliki pola belanja yang cukup stabil.
- **Cluster 4** memiliki pendapatan tinggi tetapi tingkat pengeluaran paling rendah sehingga dapat menjadi target strategi promosi untuk meningkatkan aktivitas pembelian.

**Screenshot Hasil Analisis Cluster:**

> Tambahkan screenshot Cell 13 dan Cell 14 di sini.

---

# Kesimpulan

Berdasarkan hasil preprocessing dan implementasi algoritma **K-Means Clustering**, proses pengelompokan terhadap **200 data pelanggan** berhasil dilakukan dengan baik. Tahap preprocessing menunjukkan bahwa dataset tidak memiliki missing value maupun data duplikat sehingga dapat langsung digunakan dalam proses clustering.

Melalui metode **Elbow Method**, diperoleh jumlah cluster optimal sebanyak **5 cluster**. Selanjutnya algoritma K-Means berhasil mengelompokkan pelanggan berdasarkan atribut usia, pendapatan tahunan, dan tingkat pengeluaran sehingga setiap kelompok memiliki karakteristik yang berbeda.

Hasil evaluasi menggunakan **Silhouette Score sebesar 0.40846873777345605** menunjukkan bahwa kualitas clustering berada pada kategori **cukup baik**. Dengan demikian, hasil clustering dapat dimanfaatkan sebagai dasar dalam memahami karakteristik pelanggan dan membantu penyusunan strategi pemasaran yang lebih efektif.

---

# Daftar Pustaka

1. Han, J., Kamber, M., & Pei, J. (2012). *Data Mining: Concepts and Techniques*. Morgan Kaufmann.
2. Tan, P. N., Steinbach, M., & Kumar, V. (2019). *Introduction to Data Mining*. Pearson.
3. Pedregosa, F., et al. (2011). *Scikit-learn: Machine Learning in Python*. Journal of Machine Learning Research.
4. Pandas Development Team. *Pandas Documentation*. https://pandas.pydata.org/
5. Scikit-learn Developers. *Scikit-learn Documentation*. https://scikit-learn.org/
