# ANALISIS SEGMENTASI PROFITABILITAS DAN EFEKTIVITAS DISKON PADA TRANSAKSI SUPERSTORE MENGGUNAKAN METODE K-MEANS CLUSTERING

## ABSTRAK

Persaingan bisnis yang semakin tinggi membuat perusahaan perlu memahami karakteristik transaksi secara lebih mendalam. Penelitian ini bertujuan menganalisis segmentasi transaksi Superstore berdasarkan profitabilitas dan diskon menggunakan metode K-Means Clustering. Dataset terdiri atas 10.993 baris dan 21 variabel. Tahap penelitian meliputi identifikasi data, eksplorasi kualitas data, penghapusan duplikasi, penanganan missing value, encoding data kategorikal, standardisasi data numerik, dan pembentukan empat cluster. Fitur yang digunakan adalah Sales, Quantity, Discount, Profit, Category, dan Region. Setelah preprocessing, dihasilkan empat kelompok transaksi: transaksi diskon tinggi dan merugi, transaksi premium, transaksi dengan kuantitas tinggi, dan transaksi umum. Hasil menunjukkan bahwa diskon tinggi tidak selalu menghasilkan profit yang tinggi. Hasil clustering dapat digunakan sebagai dasar evaluasi kebijakan diskon dan strategi peningkatan profitabilitas.

**Kata kunci:** Superstore, profitabilitas, diskon, segmentasi transaksi, K-Means Clustering.

---

# BAB I PENDAHULUAN

## 1.1 Latar Belakang

Perkembangan teknologi informasi menghasilkan volume data transaksi yang semakin besar. Data tersebut dapat dimanfaatkan untuk menemukan pola, hubungan, dan karakteristik tertentu yang mendukung pengambilan keputusan. Dalam konteks penjualan, perusahaan perlu mengetahui transaksi mana yang memberikan keuntungan, transaksi mana yang mengalami kerugian, serta bagaimana diskon berkaitan dengan profitabilitas.

Dataset Superstore merupakan dataset transaksi penjualan yang memiliki informasi mengenai pesanan, pelanggan, produk, wilayah, penjualan, kuantitas, diskon, dan profit. Banyaknya atribut dalam dataset memungkinkan dilakukan analisis segmentasi menggunakan teknik data mining.

Penelitian ini menggunakan K-Means Clustering untuk mengelompokkan transaksi berdasarkan karakteristik yang serupa. Pendekatan clustering dipilih karena dataset tidak menyediakan target kelas yang telah ditentukan sebelumnya. Fokus penelitian adalah mengidentifikasi kelompok transaksi dan menginterpretasikan hubungan antara nilai penjualan, kuantitas, diskon, profit, kategori produk, serta wilayah.

## 1.2 Identifikasi Masalah

1. Dataset memiliki missing value pada beberapa variabel.
2. Dataset memiliki baris duplikat yang dapat memengaruhi hasil analisis.
3. Belum diketahui kelompok transaksi berdasarkan profitabilitas dan diskon.
4. Belum diketahui apakah transaksi dengan diskon tinggi memiliki profit yang baik.

## 1.3 Rumusan Masalah

1. Bagaimana karakteristik dan kualitas dataset transaksi Superstore?
2. Bagaimana melakukan preprocessing terhadap missing value, data duplikat, dan variabel kategorikal?
3. Bagaimana segmentasi transaksi Superstore menggunakan K-Means Clustering?
4. Bagaimana karakteristik profitabilitas dan diskon pada setiap cluster?

## 1.4 Tujuan Penelitian

1. Mengidentifikasi struktur dan kualitas dataset Superstore.
2. Melakukan preprocessing agar dataset siap dianalisis.
3. Membentuk segmentasi transaksi menggunakan K-Means Clustering.
4. Menganalisis karakteristik profitabilitas dan diskon pada setiap cluster.

## 1.5 Manfaat Penelitian

### Manfaat Akademik

Penelitian ini menjadi contoh penerapan data mining dan unsupervised learning untuk menganalisis data transaksi.

### Manfaat Praktis

Hasil penelitian dapat membantu perusahaan mengevaluasi kebijakan diskon, menemukan transaksi berisiko rugi, dan menentukan strategi penjualan berdasarkan karakteristik setiap kelompok transaksi.

## 1.6 Batasan Penelitian

1. Dataset yang digunakan adalah `soal2_Superstore.csv`.
2. Metode yang digunakan adalah K-Means Clustering.
3. Fitur yang digunakan adalah Sales, Quantity, Discount, Profit, Category, dan Region.
4. Penelitian berfokus pada eksplorasi, preprocessing, clustering, dan interpretasi hasil.
5. Istilah efektivitas diskon digunakan dalam konteks perbandingan karakteristik cluster, bukan kesimpulan hubungan sebab-akibat.

## 1.7 Sistematika Penulisan

Bab I menjelaskan pendahuluan. Bab II membahas tinjauan pustaka dan landasan teori. Bab III menjelaskan metodologi penelitian. Bab IV menyajikan hasil dan pembahasan. Bab V berisi kesimpulan dan saran.

---

# BAB II TINJAUAN PUSTAKA

## 2.1 Big Data dan Analisis Data

Big Data adalah kumpulan data yang memiliki ukuran, kecepatan pertumbuhan, keragaman format, dan kompleksitas yang memerlukan metode pengolahan khusus. Dalam lingkungan bisnis, data transaksi dapat digunakan untuk memahami perilaku pelanggan, kinerja produk, efektivitas promosi, dan perbedaan pasar berdasarkan wilayah.

Analisis data merupakan proses mengubah data mentah menjadi informasi melalui pengumpulan, pembersihan, transformasi, eksplorasi, pemodelan, dan interpretasi. Penelitian ini menerapkan alur tersebut pada data transaksi Superstore. Fokusnya bukan hanya menghasilkan kelompok, tetapi juga menjelaskan karakteristik kelompok berdasarkan profitabilitas dan diskon.

## 2.2 Data Mining

Data mining adalah proses menemukan pola, hubungan, atau pengetahuan yang berguna dari data berukuran besar. Menurut Han, Kamber, dan Pei, data mining mencakup proses persiapan data, pencarian pola, evaluasi pola, dan penyajian pengetahuan. Teknik data mining yang umum meliputi klasifikasi, regresi, association rule, clustering, dan anomaly detection.

Pada penelitian ini, data mining digunakan untuk menemukan segmentasi transaksi tanpa label kelas awal. Hasil segmentasi kemudian digunakan sebagai bahan analisis bisnis.

## 2.3 Exploratory Data Analysis

Exploratory Data Analysis (EDA) adalah proses memahami karakteristik data sebelum pemodelan. EDA mencakup pemeriksaan ukuran data, tipe variabel, statistik deskriptif, distribusi data, missing value, duplikasi, dan outlier.

EDA penting karena kualitas data akan memengaruhi hasil clustering. Kesalahan tipe data, missing value, duplikasi, dan perbedaan skala dapat menyebabkan jarak antarobjek tidak merepresentasikan kemiripan yang sebenarnya.

## 2.4 Kualitas Data

Kualitas data dapat dilihat dari beberapa aspek, seperti kelengkapan, konsistensi, validitas, keunikan, dan ketepatan format. Missing value menunjukkan ketidaklengkapan data, sedangkan duplikasi dapat menyebabkan observasi tertentu memiliki bobot berlebihan. Oleh karena itu, pemeriksaan kualitas data harus dilakukan sebelum transformasi dan pemodelan.

Dalam penelitian ini, pemeriksaan kualitas data meliputi:

1. Pemeriksaan jumlah baris dan kolom.
2. Pemeriksaan tipe data setiap variabel.
3. Penghitungan missing value.
4. Penghitungan baris duplikat.
5. Pemeriksaan outlier pada variabel numerik.
6. Pemeriksaan nilai kategori dan format tanggal.

## 2.5 Preprocessing Data

Preprocessing adalah proses mempersiapkan data agar dapat digunakan oleh algoritma analisis. Tahap ini dapat meliputi pembersihan data, imputasi missing value, penghapusan duplikasi, transformasi tipe data, encoding, pemilihan fitur, dan standardisasi.

### 2.5.1 Penanganan Missing Value

Missing value numerik dapat ditangani dengan mean atau median. Median dipilih dalam penelitian ini karena lebih tahan terhadap pengaruh nilai ekstrem. Missing value kategorikal dapat diisi menggunakan modus, yaitu kategori yang paling sering muncul.

### 2.5.2 Penanganan Duplikasi

Data duplikat dihapus agar satu observasi tidak dihitung lebih dari satu kali. Penghapusan duplikasi dilakukan sebelum pembentukan model.

### 2.5.3 Encoding Variabel Kategorikal

Algoritma K-Means memerlukan input numerik. Oleh karena itu, variabel `Category` dan `Region` diubah menggunakan one-hot encoding. Setiap kategori diwakili oleh kolom indikator bernilai 0 atau 1.

### 2.5.4 Standardisasi

Standardisasi mengubah fitur numerik ke skala yang sebanding. StandardScaler menggunakan transformasi:

`z = (x - mean) / standard deviation`

Standardisasi diperlukan karena Sales dan Profit memiliki skala yang jauh berbeda dari Quantity dan Discount. Tanpa standardisasi, fitur dengan rentang besar dapat mendominasi perhitungan jarak.

## 2.6 Unsupervised Learning

Unsupervised learning adalah pembelajaran mesin yang bekerja tanpa variabel target. Algoritma mencari struktur atau pola tersembunyi dari data. Clustering merupakan salah satu bentuk unsupervised learning yang sesuai untuk segmentasi transaksi.

## 2.7 Clustering

Clustering mengelompokkan objek sehingga objek dalam cluster yang sama memiliki kemiripan lebih besar dibandingkan objek pada cluster berbeda. Hasil clustering tidak langsung bermakna secara bisnis; hasil tersebut harus diberi nama dan dijelaskan berdasarkan statistik fitur setiap cluster.

Dalam penelitian ini, cluster akan diberi interpretasi berdasarkan rata-rata Sales, Quantity, Discount, dan Profit, serta distribusi Category dan Region.

## 2.8 Algoritma K-Means

K-Means merupakan algoritma partisi yang membagi data ke dalam k cluster. Tahap algoritmanya adalah:

1. Menentukan jumlah cluster k.
2. Menginisialisasi centroid.
3. Menghitung jarak setiap data ke centroid.
4. Menetapkan data ke centroid terdekat.
5. Menghitung ulang centroid berdasarkan anggota cluster.
6. Mengulangi proses sampai perubahan centroid kecil atau iterasi selesai.

Fungsi objektif K-Means berusaha meminimalkan jumlah kuadrat jarak data terhadap centroid cluster-nya. Karena K-Means sensitif terhadap skala dan outlier, proses standardisasi dan pemeriksaan outlier perlu dilakukan terlebih dahulu.

## 2.9 Penentuan Jumlah Cluster

Jumlah cluster dapat ditentukan menggunakan elbow method atau silhouette score. Elbow method membandingkan nilai within-cluster sum of squares untuk beberapa nilai k dan mencari titik perubahan penurunan yang mulai melandai. Silhouette score mengukur seberapa dekat data dengan cluster sendiri dibandingkan dengan cluster lain.

Penelitian ini menggunakan empat cluster sebagai konfigurasi awal. Nilai tersebut akan dievaluasi dan dapat disesuaikan apabila pengujian menunjukkan jumlah cluster lain lebih baik.

## 2.10 Validasi Internal Cluster

Validasi internal digunakan untuk menilai kualitas cluster tanpa label kelas eksternal. Tiga ukuran yang digunakan adalah:

1. **Silhouette Score**, yang mengukur kedekatan data dengan cluster sendiri dibandingkan cluster terdekat. Nilai yang lebih besar menunjukkan pemisahan cluster yang lebih baik.
2. **Davies-Bouldin Index**, yang membandingkan jarak dalam cluster dengan jarak antar-cluster. Nilai yang lebih kecil menunjukkan cluster lebih kompak dan terpisah.
3. **Calinski-Harabasz Score**, yang membandingkan dispersi antar-cluster dengan dispersi dalam cluster. Nilai yang lebih besar umumnya menunjukkan struktur cluster yang lebih baik.

Elbow Method digunakan sebagai evaluasi visual melalui perubahan nilai inertia. Keputusan jumlah cluster tidak hanya didasarkan pada satu metrik, tetapi mempertimbangkan hasil beberapa metrik dan kemudahan interpretasi bisnis.

## 2.11 Pengujian Statistik Antar-Cluster

Kruskal-Wallis Test digunakan untuk menguji apakah terdapat perbedaan distribusi Sales, Discount, dan Profit antar-cluster. Uji ini dipilih karena data transaksi dapat tidak berdistribusi normal dan dapat mengandung outlier. Jika hasilnya signifikan, analisis lanjutan dapat menggunakan uji post-hoc Dunn untuk mengetahui pasangan cluster yang berbeda.

Hipotesis Kruskal-Wallis:

- H0: distribusi variabel sama pada seluruh cluster.
- H1: terdapat minimal satu cluster dengan distribusi yang berbeda.

Taraf signifikansi yang digunakan adalah 5% atau `alpha = 0,05`.

## 2.12 Korelasi Spearman

Korelasi Spearman digunakan untuk mengukur arah dan kekuatan hubungan monotonic antara Discount dan Profit. Spearman dipilih karena tidak mengharuskan data berdistribusi normal dan lebih sesuai untuk hubungan yang tidak harus linear.

Hipotesis korelasi:

- H0: tidak terdapat korelasi yang signifikan antara Discount dan Profit.
- H1: terdapat korelasi yang signifikan antara Discount dan Profit.

Nilai koefisien berkisar dari -1 sampai 1. Nilai positif menunjukkan hubungan searah, sedangkan nilai negatif menunjukkan hubungan berlawanan arah.

## 2.13 Chi-Square Test

Chi-Square Test of Independence digunakan untuk menguji hubungan antara variabel kategorikal `Category` dan label `Cluster`. Uji ini membantu mengetahui apakah distribusi kategori produk berbeda secara signifikan pada cluster yang terbentuk.

Hipotesis Chi-Square:

- H0: Category dan Cluster tidak memiliki hubungan.
- H1: Category dan Cluster memiliki hubungan.

## 2.14 Profitabilitas dalam Data Penjualan

Profitabilitas menunjukkan kemampuan transaksi atau produk menghasilkan keuntungan. Pada dataset ini, variabel `Profit` digunakan sebagai indikator utama. Profit positif menunjukkan keuntungan, sedangkan profit negatif menunjukkan kerugian.

Analisis profitabilitas tidak cukup dilakukan hanya berdasarkan Sales. Transaksi dengan Sales tinggi dapat tetap menghasilkan profit kecil atau negatif apabila diskon dan biaya terkait terlalu besar. Karena itu, Sales, Discount, Quantity, dan Profit dianalisis secara bersamaan.

## 2.15 Diskon dan Efektivitas Promosi

Diskon merupakan pengurangan harga atau insentif yang diberikan untuk mendorong pembelian. Diskon dapat meningkatkan Quantity dan Sales, tetapi juga dapat menurunkan margin. Efektivitas diskon dalam penelitian ini akan dilihat secara eksploratif dengan membandingkan diskon dan profit pada setiap cluster.

Perbandingan cluster tidak membuktikan hubungan sebab-akibat. Jika diperlukan pengukuran kausal atau pengaruh numerik, penelitian lanjutan dapat menggunakan korelasi, regresi, atau desain eksperimen.

## 2.16 Visualisasi Data

Visualisasi digunakan untuk membantu memahami data dan hasil clustering. Output yang akan digunakan meliputi:

1. Grafik jumlah missing value per kolom.
2. Grafik distribusi fitur numerik.
3. Boxplot untuk mendeteksi outlier.
4. Grafik jumlah anggota setiap cluster.
5. Scatter plot Sales dan Profit berdasarkan cluster.
6. Tabel profil rata-rata setiap cluster.
7. Grafik perbandingan Discount dan Profit antarcluster.

Setiap gambar, chart, dan tabel harus diikuti penjelasan mengenai pola yang terlihat dan kaitannya dengan tujuan penelitian.

## 2.17 Kerangka Pemikiran

Dataset Superstore → pemeriksaan kualitas data → EDA → preprocessing → pemilihan enam fitur → encoding dan standardisasi → penentuan jumlah cluster → K-Means → evaluasi cluster → visualisasi → interpretasi profitabilitas dan diskon.

## 2.18 Model Analisis Penelitian

Model analisis penelitian terdiri atas model clustering dan metode pengujian pendukung.

### 2.18.1 Model Utama: K-Means Clustering

K-Means digunakan sebagai model utama untuk membentuk segmentasi transaksi. Input model berupa fitur numerik yang telah distandardisasi dan fitur kategorikal yang telah diubah dengan one-hot encoding. Output model berupa label cluster untuk setiap transaksi dan centroid yang mewakili karakteristik pusat setiap cluster.

Model K-Means dalam penelitian ini menggunakan fitur:

- Sales
- Quantity
- Discount
- Profit
- Category hasil one-hot encoding
- Region hasil one-hot encoding

### 2.18.2 Model Validasi Cluster

Elbow Method digunakan untuk melihat perubahan inertia pada beberapa nilai k. Silhouette Score digunakan untuk mengukur kualitas pemisahan cluster. Davies-Bouldin Index digunakan untuk mengukur kemiripan antar-cluster, sedangkan Calinski-Harabasz Score digunakan untuk membandingkan dispersi antar-cluster dan dalam cluster.

Keempat metode tersebut tidak membentuk cluster baru secara langsung. Metode tersebut digunakan untuk menentukan dan menilai kualitas konfigurasi K-Means.

### 2.18.3 Model Pengujian Perbedaan Cluster

Kruskal-Wallis Test digunakan sebagai pengujian statistik untuk mengetahui apakah Sales, Discount, dan Profit berbeda secara signifikan antar-cluster. Uji ini merupakan metode nonparametrik untuk membandingkan lebih dari dua kelompok independen.

### 2.18.4 Model Pengujian Hubungan Variabel

Korelasi Spearman digunakan untuk menguji hubungan monotonic antara Discount dan Profit. Metode ini menghasilkan koefisien rho dan p-value.

Chi-Square Test of Independence digunakan untuk menguji hubungan antara variabel kategorikal Category dan label Cluster. Metode ini menggunakan tabel kontingensi dan menghasilkan nilai Chi-Square, derajat bebas, serta p-value.

## 2.19 Ringkasan Metode dan Output

| Metode atau Model | Tujuan | Output |
|---|---|---|
| K-Means Clustering | Membentuk segmentasi transaksi | Label cluster dan centroid |
| Elbow Method | Membantu memilih nilai k | Grafik inertia |
| Silhouette Score | Mengukur kualitas pemisahan cluster | Nilai silhouette |
| Davies-Bouldin Index | Mengukur kemiripan antar-cluster | Nilai DBI |
| Calinski-Harabasz Score | Mengukur rasio dispersi antar dan dalam cluster | Nilai CH |
| Kruskal-Wallis | Menguji perbedaan Sales, Discount, dan Profit antar-cluster | Statistik H dan p-value |
| Spearman | Menguji hubungan Discount dan Profit | Koefisien rho dan p-value |
| Chi-Square | Menguji hubungan Category dan Cluster | Nilai Chi-Square dan p-value |

---

# BAB III METODOLOGI PENELITIAN

## 3.1 Jenis Penelitian

Penelitian ini merupakan penelitian kuantitatif eksploratif. Analisis dilakukan terhadap data numerik dan kategorikal untuk menemukan segmentasi transaksi menggunakan algoritma K-Means.

## 3.2 Dataset dan Sumber Data

Dataset yang digunakan adalah `soal2_Superstore.csv`, yaitu berkas pendukung UTS mata kuliah Big Data Analysis and Data Visualisation. Dataset memuat data transaksi penjualan Superstore.

## 3.3 Variabel Penelitian

| Variabel | Jenis | Peran |
|---|---|---|
| Sales | Numerik | Nilai penjualan |
| Quantity | Numerik | Jumlah unit yang dibeli |
| Discount | Numerik | Besaran diskon |
| Profit | Numerik | Keuntungan atau kerugian |
| Category | Kategorikal | Kategori produk |
| Region | Kategorikal | Wilayah transaksi |

Enam variabel tersebut dipilih karena berkaitan langsung dengan nilai transaksi, volume pembelian, kebijakan diskon, profitabilitas, produk, dan lokasi pasar.

## 3.4 Tahapan Penelitian

1. Membaca dataset menggunakan Pandas.
2. Memeriksa dimensi data, tipe data, missing value, duplikasi, dan outlier.
3. Menghapus baris duplikat.
4. Mengisi missing value numerik menggunakan median.
5. Mengisi missing value kategorikal menggunakan modus.
6. Mengubah Category dan Region menggunakan one-hot encoding.
7. Melakukan standardisasi pada fitur numerik menggunakan StandardScaler.
8. Membentuk empat cluster menggunakan K-Means.
9. Menginterpretasikan ukuran dan profil setiap cluster.

## 3.5 Perangkat yang Digunakan

1. Google Colab.
2. Python.
3. Pandas.
4. Scikit-learn.
5. Matplotlib atau Seaborn untuk visualisasi tambahan.

## 3.6 Evaluasi

Evaluasi dilakukan melalui interpretasi ukuran dan rata-rata fitur setiap cluster. Untuk pengembangan selanjutnya, jumlah cluster dapat diuji menggunakan elbow method dan silhouette score.

---

# BAB IV IMPLEMENTASI DAN HASIL

Bab ini menyajikan proses implementasi secara berurutan. Seluruh proses akan dijalankan melalui `script.ipynb`. Notebook menghasilkan tabel dan visualisasi yang menjadi dasar pembahasan. Setelah setiap tabel atau gambar, hasil aktual akan dijelaskan berdasarkan output yang diperoleh.

## 4.1 Pemuatan Dataset

Tahap pertama adalah mengunggah dan membaca `soal2_Superstore.csv` menggunakan Pandas. Output yang dihasilkan:

- Tabel lima baris pertama.
- Tabel nama kolom dan tipe data.
- Tabel dimensi dataset.

**Tabel 4.1. Dimensi dan struktur dataset**

> Output tabel dari notebook diletakkan di sini.

**Pembahasan:** Uraikan jumlah baris, kolom, tipe data, dan kesesuaian dataset dengan tujuan penelitian.

## 4.2 Pemeriksaan Kualitas Data

Pemeriksaan dilakukan terhadap missing value, data duplikat, nilai unik, dan statistik deskriptif. Notebook menghasilkan tabel jumlah missing value dan tabel statistik numerik.

**Gambar 4.1. Jumlah missing value setiap kolom**

> Gambar hasil notebook diletakkan di sini.

**Pembahasan:** Jelaskan kolom dengan missing value terbanyak dan dampaknya terhadap analisis.

**Tabel 4.2. Pemeriksaan duplikasi dan statistik deskriptif**

> Output tabel dari notebook diletakkan di sini.

**Pembahasan:** Jelaskan jumlah duplikasi, rentang nilai, nilai rata-rata, dan kemungkinan adanya nilai ekstrem.

## 4.3 Eksplorasi Distribusi Data

Distribusi Sales, Quantity, Discount, dan Profit akan divisualisasikan menggunakan histogram atau grafik distribusi. Outlier akan diamati menggunakan boxplot.

**Gambar 4.2. Distribusi fitur numerik**

> Gambar hasil notebook diletakkan di sini.

**Pembahasan:** Jelaskan bentuk distribusi dan kecenderungan data pada setiap fitur.

**Gambar 4.3. Boxplot fitur numerik**

> Gambar hasil notebook diletakkan di sini.

**Pembahasan:** Jelaskan fitur yang memiliki nilai ekstrem dan keputusan apakah outlier dipertahankan atau ditangani.

## 4.4 Pembersihan dan Preprocessing

Data duplikat akan dihapus. Missing value numerik akan diisi menggunakan median, sedangkan missing value kategorikal akan diisi menggunakan modus. Category dan Region akan diproses dengan one-hot encoding. Sales, Quantity, Discount, dan Profit akan distandardisasi.

**Tabel 4.3. Perbandingan kondisi data sebelum dan sesudah preprocessing**

| Indikator | Sebelum Preprocessing | Sesudah Preprocessing | Perubahan yang Diharapkan |
|---|---:|---:|---|
| Jumlah baris | Diisi dari output notebook | Diisi dari output notebook | Duplikasi dihapus |
| Jumlah kolom awal | Diisi dari output notebook | Diisi dari output notebook | Fitur analisis dipilih |
| Jumlah missing value numerik | Diisi dari output notebook | 0 pada fitur model | Diisi dengan median |
| Jumlah missing value kategorikal | Diisi dari output notebook | 0 pada fitur model | Diisi dengan modus |
| Jumlah baris duplikat | Diisi dari output notebook | 0 | Duplikasi dihapus |
| Jumlah fitur numerik | 4 | 4 | Distandardisasi |
| Jumlah fitur kategorikal | 2 | Berubah menjadi fitur hasil encoding | One-hot encoding |
| Skala fitur numerik | Beragam | Sejajar/terstandardisasi | StandardScaler |
| Status data | Belum siap dimodelkan | Siap digunakan untuk K-Means | Pemeriksaan akhir |

**Pembahasan:** Jelaskan perubahan jumlah baris, jumlah missing value, jumlah fitur, dan kesiapan data untuk model.

## 4.5 Penentuan Jumlah Cluster

Sebelum model final ditetapkan, nilai k dapat dibandingkan menggunakan elbow method dan silhouette score. Hasil ini digunakan untuk mendukung pemilihan jumlah cluster.

**Gambar 4.4. Elbow method**

> Gambar hasil notebook diletakkan di sini.

**Gambar 4.5. Silhouette score untuk beberapa nilai k**

> Gambar hasil notebook diletakkan di sini jika pengujian silhouette dijalankan.

**Pembahasan:** Jelaskan alasan pemilihan jumlah cluster berdasarkan pola grafik dan pertimbangan interpretasi bisnis.

## 4.6 Validasi Internal Model

Notebook akan menghitung Silhouette Score, Davies-Bouldin Index, dan Calinski-Harabasz Score untuk beberapa nilai k. Output akan disajikan dalam tabel dan digunakan bersama Elbow Method untuk menentukan jumlah cluster yang paling sesuai.

**Tabel 4.4. Perbandingan metrik validasi cluster**

> Tabel berisi nilai k, inertia, Silhouette Score, Davies-Bouldin Index, dan Calinski-Harabasz Score dari notebook.

**Pembahasan:** Jelaskan nilai k yang memiliki Silhouette Score dan Calinski-Harabasz tertinggi serta Davies-Bouldin terendah. Jika metrik tidak memberikan rekomendasi yang sama, jelaskan alasan pemilihan konfigurasi final.

## 4.7 Pembentukan Model K-Means

Model K-Means akan dijalankan menggunakan jumlah cluster terpilih, `random_state=42`, dan `n_init=10`. Setiap baris akan diberi label cluster.

**Tabel 4.4. Jumlah anggota setiap cluster**

> Output tabel dari notebook diletakkan di sini.

**Gambar 4.6. Distribusi jumlah transaksi per cluster**

> Gambar hasil notebook diletakkan di sini.

**Pembahasan:** Jelaskan ukuran setiap cluster dan apakah terdapat cluster yang terlalu kecil atau terlalu dominan.

## 4.8 Profil dan Visualisasi Cluster

Profil cluster akan dihitung berdasarkan rata-rata Sales, Quantity, Discount, dan Profit. Distribusi Category dan Region pada setiap cluster juga akan diperiksa.

**Tabel 4.5. Profil rata-rata fitur numerik setiap cluster**

> Output tabel dari notebook diletakkan di sini.

**Gambar 4.7. Scatter plot Sales dan Profit berdasarkan cluster**

> Gambar hasil notebook diletakkan di sini.

**Gambar 4.8. Perbandingan Discount dan Profit antarcluster**

> Gambar hasil notebook diletakkan di sini.

**Pembahasan:** Jelaskan cluster dengan diskon tinggi, profit negatif, Sales tinggi, Quantity tinggi, dan karakteristik transaksi reguler.

## 4.9 Pengujian Statistik

### 4.9.1 Kruskal-Wallis Test

Kruskal-Wallis Test akan dilakukan terhadap Sales, Discount, dan Profit berdasarkan label cluster.

**Tabel 4.7. Hasil Kruskal-Wallis Test**

> Tabel berisi variabel, statistik H, p-value, dan keputusan pada alpha 0,05.

**Pembahasan:** Jika p-value kurang dari 0,05, variabel dinyatakan berbeda signifikan antar-cluster. Jika tidak, tidak terdapat cukup bukti statistik untuk menyatakan adanya perbedaan.

### 4.9.2 Korelasi Spearman

Korelasi Spearman akan menguji hubungan antara Discount dan Profit.

**Tabel 4.8. Hasil Korelasi Spearman**

> Tabel berisi koefisien rho, p-value, dan keputusan pengujian.

**Pembahasan:** Jelaskan arah hubungan, kekuatan hubungan, dan signifikansinya. Korelasi tidak boleh ditafsirkan sebagai hubungan sebab-akibat.

### 4.9.3 Chi-Square Test

Chi-Square Test akan menguji hubungan antara Category dan Cluster. Tabel kontingensi juga akan ditampilkan untuk memperlihatkan distribusi kategori pada setiap cluster.

**Tabel 4.9. Tabel Kontingensi Category dan Cluster**

> Output tabel kontingensi dari notebook diletakkan di sini.

**Tabel 4.10. Hasil Chi-Square Test**

> Tabel berisi nilai Chi-Square, derajat bebas, p-value, dan keputusan pengujian.

**Pembahasan:** Jika p-value kurang dari 0,05, terdapat hubungan signifikan antara kategori produk dan cluster.

## 4.10 Pengujian Hasil dan Interpretasi

Pengujian akan dilakukan menggunakan indikator berikut:

| No. | Aspek Pengujian | Kriteria |
|---:|---|---|
| 1 | Pembacaan data | Dataset terbaca tanpa error |
| 2 | Kualitas data | Missing value dan duplikasi teridentifikasi |
| 3 | Preprocessing | Data siap digunakan dan fitur model tidak kosong |
| 4 | Validasi cluster | Elbow, Silhouette, Davies-Bouldin, dan Calinski-Harabasz berhasil dihitung |
| 5 | Pembentukan model | K-Means menghasilkan label cluster |
| 6 | Distribusi cluster | Jumlah anggota dapat dihitung |
| 7 | Profil cluster | Rata-rata fitur setiap cluster tersedia |
| 8 | Kruskal-Wallis | Statistik H dan p-value tersedia |
| 9 | Spearman | Koefisien rho dan p-value tersedia |
| 10 | Chi-Square | Nilai Chi-Square dan p-value tersedia |
| 11 | Visualisasi | Chart dan tabel dapat dihasilkan |
| 12 | Interpretasi | Setiap cluster memiliki karakteristik yang dapat dijelaskan |
| 13 | Ekspor | File hasil dapat disimpan sebagai CSV |

**Tabel 4.11. Rekapitulasi hasil pengujian**

> Tabel diisi berdasarkan output aktual setelah notebook dijalankan.

**Pembahasan:** Jelaskan status setiap pengujian berdasarkan bukti output, bukan berdasarkan perkiraan.

---

# BAB V KESIMPULAN DAN SARAN SEMENTARA

Bab ini belum memuat kesimpulan akhir karena hasil implementasi dan pengujian belum dijalankan dalam notebook. Kesimpulan final harus ditulis setelah output aktual diperoleh.

## 5.1 Format Kesimpulan Setelah Pengujian

Kesimpulan akhir akan memuat:

1. Hasil pemeriksaan dimensi, missing value, dan duplikasi dataset.
2. Jumlah data setelah preprocessing.
3. Fitur yang berhasil digunakan dalam model.
4. Jumlah cluster dan jumlah anggota setiap cluster.
5. Karakteristik profitabilitas dan diskon pada masing-masing cluster.
6. Jawaban atas pertanyaan apakah pola diskon tinggi berkaitan dengan profitabilitas yang lebih baik berdasarkan hasil clustering.

## 5.2 Saran Sementara

Saran berikut masih bersifat rencana dan akan disesuaikan dengan hasil pengujian:

1. Mengevaluasi cluster yang memiliki diskon tinggi dan profit negatif.
2. Menguji jumlah cluster menggunakan elbow method atau silhouette score.
3. Menambahkan variabel biaya pengiriman, subkategori produk, dan waktu transaksi pada penelitian lanjutan.
4. Menggunakan analisis korelasi atau regresi apabila diperlukan pengukuran pengaruh diskon terhadap profit.
5. Mengembangkan hasil clustering menjadi dashboard interaktif setelah profil cluster final diperoleh.

---

# DAFTAR REFERENSI

1. Han, J., Kamber, M., & Pei, J. (2012). *Data Mining: Concepts and Techniques* (3rd ed.). Morgan Kaufmann.
2. Kelleher, J. D., Mac Namee, B., & D'Arcy, A. (2020). *Fundamentals of Machine Learning for Predictive Data Analytics* (2nd ed.). MIT Press.
3. Lloyd, S. (1982). Least squares quantization in PCM. *IEEE Transactions on Information Theory, 28*(2), 129–137.
4. MacQueen, J. (1967). Some methods for classification and analysis of multivariate observations. In *Proceedings of the Fifth Berkeley Symposium on Mathematical Statistics and Probability*, 281–297.
5. Pedregosa, F., et al. (2011). Scikit-learn: Machine learning in Python. *Journal of Machine Learning Research, 12*, 2825–2830.
6. Tan, P.-N., Steinbach, M., & Kumar, V. (2019). *Introduction to Data Mining* (2nd ed.). Pearson.
7. Tukiyat. (2026). *V322 UTS 2026/2027 Big Data Analysis and Data Visualisation*. Dokumen instruksi UTS, Universitas Pamulang.
8. Dataset `soal2_Superstore.csv`, berkas pendukung UTS mata kuliah Big Data Analysis and Data Visualisation.
9. Aggarwal, C. C. (2015). *Data Mining: The Textbook*. Springer.
10. Han, J., Kamber, M., & Pei, J. (2012). *Data Mining: Concepts and Techniques* (3rd ed.). Morgan Kaufmann.
11. Kaufman, L., & Rousseeuw, P. J. (1990). *Finding Groups in Data: An Introduction to Cluster Analysis*. Wiley.
12. Molnar, C. (2022). *Interpretable Machine Learning*. Available at: https://christophm.github.io/interpretable-ml-book/
13. McKinney, W. (2022). *Python for Data Analysis* (3rd ed.). O'Reilly Media.
14. Waskom, M. (2021). Seaborn: Statistical data visualization. *Journal of Open Source Software, 6*(60), 3021.
15. Virtanen, P., et al. (2020). SciPy 1.0: Fundamental algorithms for scientific computing in Python. *Nature Methods, 17*, 261–272.
16. Rousseeuw, P. J. (1987). Silhouettes: A graphical aid to the interpretation and validation of cluster analysis. *Journal of Computational and Applied Mathematics, 20*, 53–65.
17. Tibshirani, R., Walther, G., & Hastie, T. (2001). Estimating the number of clusters in a data set via the gap statistic. *Journal of the Royal Statistical Society: Series B, 63*(2), 411–423.
18. Jain, A. K. (2010). Data clustering: 50 years beyond K-Means. *Pattern Recognition Letters, 31*(8), 651–666.
19. Provost, F., & Fawcett, T. (2013). *Data Science for Business*. O'Reilly Media.

