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

<p align="center"><strong>Tabel 2.1. Ringkasan metode analisis dan output yang dihasilkan</strong></p>

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

Tabel 2.1 menjelaskan fungsi setiap metode, alasan penggunaannya, serta bentuk output yang dihasilkan. K-Means digunakan untuk membentuk kelompok transaksi, sedangkan metrik validasi digunakan untuk menilai kualitas kelompok. Uji statistik digunakan sebagai pendukung interpretasi, bukan untuk menggantikan analisis profil cluster.

---

# BAB III METODOLOGI PENELITIAN

## 3.1 Jenis Penelitian

Penelitian ini merupakan penelitian kuantitatif eksploratif. Analisis dilakukan terhadap data numerik dan kategorikal untuk menemukan segmentasi transaksi menggunakan algoritma K-Means.

## 3.2 Dataset dan Sumber Data

Dataset yang digunakan adalah `soal2_Superstore.csv`, yaitu berkas pendukung UTS mata kuliah Big Data Analysis and Data Visualisation. Dataset memuat data transaksi penjualan Superstore.

## 3.3 Variabel Penelitian

<p align="center"><strong>Tabel 3.1. Variabel yang digunakan dalam penelitian</strong></p>

| Variabel | Jenis | Peran |
|---|---|---|
| Sales | Numerik | Nilai penjualan |
| Quantity | Numerik | Jumlah unit yang dibeli |
| Discount | Numerik | Besaran diskon |
| Profit | Numerik | Keuntungan atau kerugian |
| Category | Kategorikal | Kategori produk |
| Region | Kategorikal | Wilayah transaksi |

Tabel 3.1 menunjukkan enam variabel yang digunakan dalam penelitian. Sales dan Profit menggambarkan nilai ekonomi transaksi, Quantity menggambarkan volume pembelian, Discount menggambarkan insentif harga, sedangkan Category dan Region memberikan konteks produk serta wilayah. Keenam variabel tersebut dipilih karena secara langsung mendukung analisis profitabilitas dan efektivitas diskon.

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

Evaluasi dilakukan melalui elbow method, Silhouette Score, Davies-Bouldin Index, Calinski-Harabasz Score, profil rata-rata fitur, serta pengujian statistik. Hasil evaluasi digunakan untuk menjelaskan kualitas pemisahan cluster dan karakteristik bisnis setiap kelompok.

---

# BAB IV IMPLEMENTASI DAN HASIL

## 4.1 Pemuatan dan pemeriksaan data

Dataset `soal2_Superstore.csv` berhasil dibaca menggunakan Pandas. Dataset awal berisi **10.993 baris dan 21 kolom**. Kolom mencakup atribut transaksi, pelanggan, produk, wilayah, Sales, Quantity, Discount, dan Profit. Sebanyak **999 baris duplikat** ditemukan. Setelah duplikasi dihapus, jumlah data menjadi **9.994 baris**.

Pemeriksaan juga menunjukkan missing value pada sejumlah kolom. Pada enam fitur model, missing value awalnya adalah: Sales 1.646, Quantity 1.588, Discount 1.697, Profit 1.689, Category 1.671, dan Region 1.668. Kondisi ini menjadi alasan penggunaan imputasi pada tahap preprocessing.

![Jumlah missing value pada fitur analisis](hasil-analisis/gambar_missing_value.png)
<p align="center"><em>Gambar 4.1. Jumlah missing value pada fitur analisis</em></p>

Gambar 4.1 memperlihatkan jumlah nilai kosong pada Sales, Quantity, Discount, Profit, Category, dan Region. Nilai kosong muncul pada seluruh fitur analisis, sehingga data tidak dapat langsung dimasukkan ke model. Missing value numerik ditangani dengan median agar pengaruh nilai ekstrem lebih kecil, sedangkan missing value kategorikal diisi dengan modus agar proses encoding dapat dilakukan.

## 4.2 Preprocessing

Fitur yang digunakan adalah Sales, Quantity, Discount, Profit, Category, dan Region. Missing value numerik diisi dengan median, sedangkan missing value kategorikal diisi dengan modus melalui `ColumnTransformer` dan `Pipeline`. Category dan Region diubah menggunakan one-hot encoding, sedangkan empat fitur numerik distandardisasi menggunakan `StandardScaler`.

Setelah preprocessing, matriks input model memiliki ukuran **9.994 baris dan 11 fitur**. Dengan demikian, data tidak lagi memiliki nilai kosong pada fitur yang digunakan oleh model dan seluruh fitur berada pada representasi yang dapat diproses K-Means.

<p align="center"><strong>Tabel 4.1. Perbandingan kondisi data sebelum dan sesudah preprocessing</strong></p>

| Indikator | Sebelum preprocessing | Sesudah preprocessing |
|---|---:|---:|
| Jumlah baris | 10.993 | 9.994 |
| Jumlah kolom awal | 21 | 11 fitur model |
| Jumlah duplikasi | 999 | 0 |
| Missing value pada fitur model | Ada | Ditangani dengan imputasi |
| Fitur kategorikal | Category dan Region | One-hot encoding |
| Fitur numerik | Sales, Quantity, Discount, Profit | Standardisasi |

Tabel 4.1 menunjukkan perubahan utama dari data mentah menjadi data siap model. Jumlah baris berkurang karena 999 duplikasi dihapus. Jumlah fitur model menjadi 11 karena Category dan Region diubah menjadi beberapa kolom indikator melalui one-hot encoding. Missing value diisi menggunakan median untuk fitur numerik dan modus untuk fitur kategorikal sehingga data tetap dapat digunakan tanpa menghilangkan seluruh transaksi yang memiliki nilai kosong.

## 4.3 Penentuan dan validasi jumlah cluster

Notebook menghitung inertia untuk k=2 sampai k=8 serta tiga metrik validasi. Hasil terbaik tidak sama untuk semua metrik: Silhouette Score terbaik diperoleh pada k=5, sedangkan Davies-Bouldin Index dan Calinski-Harabasz Score terbaik pada k=8. Perbedaan ini menunjukkan bahwa tidak ada satu nilai k yang unggul mutlak pada seluruh ukuran.

Penelitian ini mempertahankan **k=4** karena konfigurasi tersebut telah ditetapkan dalam rancangan analisis dan menghasilkan profil bisnis yang mudah dibedakan. Pemilihan ini harus dipahami sebagai segmentasi eksploratif, bukan klaim bahwa k=4 adalah satu-satunya jumlah cluster yang paling optimal secara matematis.

![Elbow method](hasil-analisis/gambar_elbow_method.png)
<p align="center"><em>Gambar 4.2. Elbow method untuk k=2 sampai k=8</em></p>

Gambar 4.2 menunjukkan penurunan inertia ketika jumlah cluster bertambah. Inertia selalu cenderung turun karena data dibagi ke dalam kelompok yang lebih banyak. Oleh sebab itu, grafik ini tidak digunakan secara tunggal; hasilnya dibandingkan dengan Silhouette Score, Davies-Bouldin Index, Calinski-Harabasz Score, dan kemudahan interpretasi bisnis.

<p align="center"><strong>Tabel 4.2. Metrik validasi untuk berbagai nilai k</strong></p>

| k | Inertia | Silhouette | Davies-Bouldin | Calinski-Harabasz |
|---:|---:|---:|---:|---:|
| 2 | 46.370,8931 | 0,2158 | 2,2780 | 1.225,8758 |
| 3 | 40.578,7715 | 0,1984 | 1,7249 | 1.413,4102 |
| 4 | 35.877,9785 | 0,2462 | 1,4137 | 1.501,9197 |
| 5 | 32.452,2314 | 0,2696 | 1,3745 | 1.508,8422 |
| 6 | 29.857,3459 | 0,2115 | 1,5186 | 1.485,4585 |
| 7 | 26.969,5103 | 0,2274 | 1,4460 | 1.548,5256 |
| 8 | 24.329,1798 | 0,2364 | 1,3209 | 1.626,0257 |

Tabel 4.2 menampilkan hasil lengkap metrik validasi untuk nilai k=2 sampai k=8. Inertia digunakan untuk elbow method, sedangkan Silhouette, Davies-Bouldin, dan Calinski-Harabasz digunakan untuk menilai kualitas pemisahan cluster. Silhouette tertinggi terdapat pada k=5, sementara Davies-Bouldin terendah dan Calinski-Harabasz tertinggi terdapat pada k=8. Nilai k=4 tetap digunakan karena memberikan segmentasi yang lebih sederhana dan mudah dikaitkan dengan tujuan analisis, dengan catatan bahwa pemilihan tersebut bersifat eksploratif.

## 4.4 Hasil pembentukan cluster

Model yang digunakan adalah `KMeans(n_clusters=4, random_state=42, n_init=10)`. Distribusi anggota cluster adalah sebagai berikut.

<p align="center"><strong>Tabel 4.3. Distribusi anggota dan interpretasi awal cluster</strong></p>

| Cluster | Jumlah transaksi | Persentase | Interpretasi awal |
|---:|---:|---:|---|
| 0 | 1.318 | 13,19% | Diskon tinggi dan profit negatif |
| 1 | 12 | 0,12% | Transaksi bernilai sangat tinggi dan sangat profitabel |
| 2 | 1.344 | 13,45% | Kuantitas tinggi dengan profit positif |
| 3 | 7.320 | 73,24% | Transaksi umum dengan diskon rendah |

Cluster 3 merupakan kelompok dominan, sedangkan Cluster 1 sangat kecil. Ketimpangan ini menunjukkan adanya sejumlah kecil transaksi ekstrem yang dipisahkan dari transaksi umum. Karena Cluster 1 hanya berisi 12 transaksi, interpretasinya perlu dilakukan secara hati-hati dan sebaiknya diverifikasi pada data asli.

![Jumlah transaksi per cluster](hasil-analisis/gambar_jumlah_cluster.png)
<p align="center"><em>Gambar 4.3. Jumlah transaksi pada setiap cluster</em></p>

Gambar 4.3 memperlihatkan ketidakseimbangan ukuran cluster. Cluster 3 mendominasi data dengan 7.320 transaksi, sedangkan Cluster 1 hanya berisi 12 transaksi. Kondisi tersebut menunjukkan bahwa Cluster 1 kemungkinan merepresentasikan transaksi ekstrem atau khusus, sehingga kesimpulan mengenai cluster tersebut harus disampaikan dengan hati-hati.

## 4.5 Profil cluster

<p align="center"><strong>Tabel 4.4. Profil rata-rata fitur numerik setiap cluster</strong></p>

| Cluster | Sales rata-rata | Quantity rata-rata | Discount rata-rata | Profit rata-rata |
|---:|---:|---:|---:|---:|
| 0 | 159,57 | 2,72 | 0,82 | -32,80 |
| 1 | 10.610,80 | 4,75 | 0,09 | 3.429,80 |
| 2 | 697,56 | 12,14 | 0,10 | 99,20 |
| 3 | 131,45 | 2,06 | 0,01 | 21,62 |

Cluster 0 merupakan kelompok yang paling jelas menunjukkan risiko kebijakan diskon. Rata-rata Discount sebesar 0,82 diikuti Profit negatif sebesar -32,80. Hal ini menunjukkan bahwa diskon tinggi pada kelompok ini tidak menghasilkan profitabilitas yang lebih baik.

Cluster 1 memiliki Sales dan Profit rata-rata paling tinggi, tetapi hanya terdiri atas 12 transaksi. Kelompok ini dapat disebut transaksi premium atau transaksi bernilai ekstrem. Cluster 2 memiliki Quantity tertinggi, yaitu 12,14 unit per transaksi, dengan Sales dan Profit positif. Cluster 3 berisi sebagian besar transaksi, dengan diskon sangat rendah, Sales relatif rendah, dan Profit tetap positif.

Pola pada grafik jumlah cluster, scatter Sales-Profit, dan grafik Discount-Profit mendukung interpretasi tersebut: Cluster 1 tampak sebagai titik transaksi bernilai tinggi, Cluster 0 terkonsentrasi pada diskon tinggi dan profit negatif, sedangkan Cluster 3 menjadi kelompok transaksi reguler.

![Sales dan Profit berdasarkan cluster](hasil-analisis/gambar_sales_profit_cluster.png)
<p align="center"><em>Gambar 4.4. Scatter plot Sales dan Profit berdasarkan cluster</em></p>

Gambar 4.4 memperlihatkan posisi transaksi berdasarkan Sales dan Profit. Cluster 1 berada pada nilai Sales dan Profit yang sangat tinggi, sedangkan Cluster 0 mencakup transaksi dengan profit negatif. Cluster 3 terkonsentrasi pada area transaksi bernilai lebih rendah dan profit yang relatif kecil tetapi positif. Pola ini mendukung hasil rata-rata pada Tabel 4.4.

![Perbandingan Discount dan Profit](hasil-analisis/gambar_discount_profit_cluster.png)
<p align="center"><em>Gambar 4.5. Perbandingan rata-rata Discount dan Profit antarcluster</em></p>

Gambar 4.5 membandingkan rata-rata Discount dan Profit antarcluster. Skala Profit jauh lebih besar daripada skala Discount, sehingga batang Discount tampak kecil pada grafik. Walaupun demikian, pola penting tetap terlihat: Cluster 0 memiliki Discount tertinggi dan Profit negatif, sedangkan Cluster 1 memiliki Profit tertinggi. Untuk membaca angka secara tepat, pembaca perlu merujuk Tabel 4.4.

## 4.6 Pengujian statistik

Kruskal-Wallis digunakan untuk membandingkan Sales, Discount, dan Profit antar-cluster. Karena cluster dibentuk menggunakan fitur-fitur tersebut, perbedaan antar-cluster memang diharapkan dan hasil uji statistik harus ditafsirkan sebagai bukti perbedaan distribusi, bukan sebagai hubungan sebab-akibat.

<p align="center"><strong>Tabel 4.5. Hasil uji Kruskal-Wallis</strong></p>

| Variabel | Statistik H | p-value | Keputusan pada α=0,05 |
|---|---:|---:|---|
| Sales | 524,6686 | 2,15 × 10⁻¹¹³ | Berbeda signifikan |
| Discount | 3.628,9535 | < 0,001 | Berbeda signifikan |
| Profit | 439,5899 | 5,87 × 10⁻⁹⁵ | Berbeda signifikan |

Ketiga p-value lebih kecil dari 0,05. Oleh karena itu, terdapat bukti bahwa distribusi Sales, Discount, dan Profit berbeda antar-cluster. Hasil ini konsisten dengan profil cluster, tetapi tidak berarti bahwa clustering membuktikan pengaruh diskon terhadap profit.

Korelasi Spearman antara Discount dan Profit digunakan sebagai analisis tambahan. Hasil korelasi tidak boleh diterjemahkan sebagai bukti bahwa diskon secara langsung menyebabkan perubahan profit. Untuk menyatakan pengaruh, diperlukan analisis lanjutan yang mengendalikan faktor lain seperti produk, wilayah, kuantitas, dan waktu.

Koefisien Spearman diperoleh sebesar **-0,2503** dengan p-value **1,43 × 10⁻¹⁰²**. Hubungan tersebut negatif, signifikan secara statistik, tetapi kekuatannya lemah sampai sedang. Artinya, pada dataset ini kenaikan Discount cenderung berasosiasi dengan penurunan Profit, namun Discount bukan satu-satunya faktor yang menentukan profitabilitas.

<p align="center"><strong>Tabel 4.6. Hasil korelasi Spearman Discount dan Profit</strong></p>

| Variabel X | Variabel Y | Rho Spearman | p-value | Interpretasi |
|---|---|---:|---:|---|
| Discount | Profit | -0,2503 | 1,43 × 10⁻¹⁰² | Hubungan negatif dan signifikan |

Tabel 4.6 menunjukkan hubungan monotonic negatif yang lemah sampai sedang. Hasil ini merupakan asosiasi dan bukan bukti kausalitas.

Chi-Square digunakan untuk menguji keterkaitan Category dengan Cluster. Jika p-value kurang dari 0,05, distribusi kategori produk berbeda secara signifikan antar-cluster. Hasil ini dapat membantu menjelaskan apakah segmentasi profitabilitas juga berkaitan dengan kategori produk.

<p align="center"><strong>Tabel 4.7. Tabel kontingensi Category dan Cluster</strong></p>

Tabel kontingensi Category dan Cluster menunjukkan jumlah berikut.

| Category | Cluster 0 | Cluster 1 | Cluster 2 | Cluster 3 |
|---|---:|---:|---:|---:|
| Furniture | 252 | 0 | 305 | 1.249 |
| Missing | 202 | 4 | 187 | 1.112 |
| Office Supplies | 745 | 2 | 586 | 3.780 |
| Technology | 119 | 6 | 266 | 1.179 |

Uji Chi-Square menghasilkan χ²=113,9216, derajat bebas 9, dan p-value **2,33 × 10⁻²⁰**. Dengan demikian, terdapat hubungan signifikan antara Category dan Cluster. Namun, hubungan ini bersifat asosiasi dan tidak dapat langsung dianggap sebagai hubungan sebab-akibat.

<p align="center"><strong>Tabel 4.8. Hasil uji Chi-Square Category dan Cluster</strong></p>

| Statistik Chi-Square | Derajat bebas | p-value | Keputusan |
|---:|---:|---:|---|
| 113,9216 | 9 | 2,33 × 10⁻²⁰ | Terdapat hubungan signifikan |

## 4.7 Ringkasan hasil

<p align="center"><strong>Tabel 4.9. Ringkasan hasil utama penelitian</strong></p>

| Aspek | Hasil |
|---|---|
| Data awal | 10.993 baris, 21 kolom |
| Duplikasi | 999 baris |
| Data setelah deduplikasi | 9.994 baris |
| Fitur setelah encoding | 11 fitur |
| Model | K-Means, k=4, random_state=42 |
| Cluster terbesar | Cluster 3, 7.320 transaksi |
| Cluster dengan diskon tertinggi | Cluster 0, Discount 0,82 |
| Cluster dengan profit terendah | Cluster 0, Profit -32,80 |
| Cluster dengan Sales tertinggi | Cluster 1, Sales 10.610,80 |
| Cluster dengan Quantity tertinggi | Cluster 2, Quantity 12,14 |

Hasil tersebut menjawab tujuan penelitian: transaksi dapat dikelompokkan berdasarkan karakteristik nilai penjualan, kuantitas, diskon, profit, kategori, dan wilayah. Temuan utama adalah bahwa diskon tinggi tidak otomatis meningkatkan profit. Pada data ini, kelompok dengan diskon tertinggi justru memiliki rata-rata profit negatif.

# BAB V KESIMPULAN DAN SARAN

## 5.1 Kesimpulan

1. Dataset Superstore terdiri atas 10.993 baris dan 21 kolom. Ditemukan 999 baris duplikat sehingga data yang digunakan setelah pembersihan berjumlah 9.994 baris.
2. Missing value pada fitur numerik ditangani dengan median, missing value kategorikal dengan modus, Category dan Region melalui one-hot encoding, serta fitur numerik melalui standardisasi. Hasil preprocessing menghasilkan 11 fitur model.
3. K-Means dengan empat cluster menghasilkan distribusi yang tidak seimbang: Cluster 0 berjumlah 1.318, Cluster 1 berjumlah 12, Cluster 2 berjumlah 1.344, dan Cluster 3 berjumlah 7.320 transaksi.
4. Cluster 0 memiliki diskon rata-rata tertinggi, yaitu 0,82, tetapi profit rata-ratanya negatif sebesar -32,80. Temuan ini menunjukkan bahwa diskon tinggi tidak selalu efektif untuk menghasilkan keuntungan.
5. Cluster 1 memiliki Sales dan Profit rata-rata tertinggi, tetapi ukurannya sangat kecil sehingga lebih tepat dipandang sebagai kelompok transaksi bernilai ekstrem. Cluster 2 memiliki kuantitas rata-rata tertinggi, sedangkan Cluster 3 merupakan transaksi umum dengan diskon rendah dan profit positif.
6. Hasil clustering dapat digunakan untuk mengevaluasi strategi diskon, tetapi tidak membuktikan hubungan sebab-akibat. Keputusan bisnis sebaiknya mempertimbangkan ukuran cluster, stabilitas model, kategori produk, wilayah, dan faktor biaya lainnya.

## 5.2 Saran

1. Perusahaan perlu mengevaluasi transaksi pada Cluster 0, terutama aturan diskon yang menghasilkan profit negatif.
2. Cluster 1 perlu diperiksa sebagai transaksi ekstrem untuk memastikan tidak terdapat kesalahan input, transaksi khusus, atau karakteristik pelanggan yang berbeda.
3. Penelitian lanjutan sebaiknya membandingkan k=4 dengan k=5 dan k=8 karena metrik validasi memberikan rekomendasi yang berbeda.
4. Analisis berikutnya dapat menambahkan Sub-Category, Ship Mode, waktu transaksi, biaya pengiriman, dan margin agar efektivitas diskon dapat dianalisis lebih lengkap.
5. Untuk mengukur pengaruh diskon, gunakan regresi atau analisis kausal dengan mengendalikan Sales, Quantity, Category, Region, dan periode transaksi.
6. Hasil cluster dapat dikembangkan menjadi dashboard yang menampilkan profit, diskon, jumlah transaksi, dan rekomendasi tindakan untuk setiap kelompok.

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

