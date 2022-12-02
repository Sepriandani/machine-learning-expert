# Laporan Proyek Machine Learning - Seprian Dani
# _Bitcoin Predictive Analytics_

## Domain Proyek
### Latar Belakang
Cryptocurrency adalah salah satu uang digital yang berkembang pesat di dunia saat ini. Dalam proyek ini, mata uang kripto yang digunakan yaitu Bitcoin. Diharapkan membantu investor untuk membuat keputusan investasi yang tepat untuk mendapatkan keuntungan. Menggunakan Machine Learning dapat menganalisis fluktuasi harga mata uang kripto melalui data historis yang dikelola oleh teknologi Blockchain. Ini menghasilkan tingkat presisi tinggi dari analisis prediksi cryptocurrency menggunakan algoritma Machine Learning bersama dengan teknologi Blockchain.

Bitcoin telah menjadi tren bagi investor untuk menaruh uang dan kepercayaan mereka pada cryptocurrency selama beberapa tahun terakhir dan tidak diragukan lagi itu untuk jangka panjang. Jadi bukankah bagus jika kita bisa memprediksi harga Bitcoin ? Nilai Bitcoin naik pada Desember 2018.

Bitcoin merupakan mata uang kripto pertama, meskipun saat ini sudah banyak jenis mata uang kripto yang bermunculan bitcoin masih menjadi pilah utama investor hal itu dapat dilihat dari marketcap bitcoin yang masih menduduki peringkat pertama pada situs [coinmarketcap.com](https://coinmarketcap.com/). Bitcoin dapat digunakan dalam transaksi peer-to-peer, atau dibeli dan dijual di bursa dengan nilai spekulatif. Bitcoin dapat diperdagangkan setiap saat karena tidak memiliki periode tutup, inilah yang membedakannya dengan pasar lainnya. Bitcoin lebih mudah berubah dan berisiko bagi para pedagang. Faktor ketidakpastian yang ada, perlu dikurangi oleh para pedagang untuk meminimalkan risiko. Salah satu cara yang digunakan untuk melakukan hal tersebut adalah prediksi harga Bitcoin secara akurat.

Saat melakukan prediksi, di perlukan metode yang tepat. Salah satunya adalah dengan menerapkan machine learning. Machine learning adalah mesin yang dikembangkan untuk bisa belajar dengan sendirinya tanpa arahan dari penggunanya. Pembelajaran mesin dikembangkan berdasarkan disiplin ilmu lainnya seperti statistika, matematika dan data mining sehingga mesin dapat belajar dengan menganalisa data tanpa perlu di program ulang atau diperintah.
Penerapan machine learning membantu dalam proses analisis data besar dan kompleks, sehingga tugas bisa diselesaikan dengan cepat.

Berdasarkan hal tersebut, maka dilakukan penelitian tentang prediksi harga Bitcoin menggunakan machine learning. Proyek machine learning ini di buat agar dapat memprediksi harga pasar Bitcoin di masa mendatang. Dengan penerapan machine learning di harapkan dapat mengurangi tingkat kerugian investor akibat harga mata uang Bitcoin yang tidak stabil.

## Business Understanding

### Problem Statement
Berdasarkan pada latar belakang di atas, permasalahan yang dapat diselesaikan pada proyek ini adalah sebagai berikut:
* Bagaimana cara menganalisa data harga bitcoin?
* Bagaimana cara memproses data agar dapat di latih dengan baik oleh model?
* Bagaimana cara membangun model machine learning yang dapat memprediksi harga bitcoin dengan baik?

### Goals
Tujuan dibuatnya proyek ini adalah sebagai berikut:
* Dapat memprediksi harga bitcoin dengan akurat mengunakan model machine learning.
* Melakukan analisa dan mengolah data yang optimal agar diterima dengan baik oleh model machine learning.
* Membuat model machine learning yang dapat memahami pola pada data dengan baik.
* Membantu para investor agar dapat mengambil keputusan dengan baik saat melakukan transaksi.

### Solution Statement
Solusi yang dapat diterapkan agar goals diatas terpenuhi adalah sebagai berikut:
* Melakukan analisa, eksplorasi, pemrosesan pada data dengan memvisualisasikan data agar mendapat gambaran bagaimana data tersebut. Berikut adalah analisa yang dapat dilakukan :
    * Menangani missing value (data yang hilang) pada data.
    * Memeriksa korelasi antar data penting untuk memahami hubungan data target dan data fitur.
* Melakukan pemrosesan pada data seperti:
    * Mengatasi outlier pada data dengan menerapkan IQR method.
    * Normalisasi data pada fitur numerik.
* Membangun model regresi yang dapat memprediksi bilangan kontinu sesuai dengan permasalahan yang ingin di selesaikan. Beberapa algoritma yang akan digunakan pada model regresi proyek ini yaitu, sebagai berikut:
    * Support Vector Machine
    * K-Nearest Neighbours
    * Random Forest
* Menerapkan teknik Grid Search untuk mendapatkan parameter-parameter dengan performa terbaik pada masing-masing model.

## Data Understanding

Dataset yang di gunakan pada proyek machine learning ini merupakan dataset riwayat harga Bitcoin dari waktu ke waktu. Dataset tersebut dapat di unduh di website kaggle: [Cryptocurrency Historical Prices.](https://www.kaggle.com/datasets/sudalairajkumar/cryptocurrencypricehistory?select=coin_Bitcoin.csv)

### Deskripsi Variabel
Berdasarkan informasi dari [Kaggle](https://www.kaggle.com/datasets/sudalairajkumar/cryptocurrencypricehistory?select=coin_Bitcoin.csv) variabel dari dataseat adalah sebagai berikut :
* Name : Nama mata uang kripto
* Symbol : Singkatan mata uang kripto
* Date : tanggal pengamatan
* Open : Harga pembukaan pada hari tertentu
* High : Harga tertinggi pada hari tertentu
* Low : Harga terendah pada hari tertentu
* Close : Harga penutupan pada hari tertentu
* Volume : Volume transaksi pada hari tertentu
* Market Cap : Kapitalisasi pasar dalam USD

Setelah memahami deskripsi variabel pada data, langkah selanjutnya adalah mengecek informasi pada dataset

Setelah dilakukan analisa pada data, didapatkan informasi bahwa:
* Format dataset yaitu CSV (Comma-Seperated Values)
* Jumlah kolom data yang terdapat didalam dataset berjumla 10 kolom, antara lain: SNo, Name, Symbol, Date, High, Low, Open, Close, Volume, Marketcap.
* Terdapat 2992 jumlah sample yang terdapat didalam dataset.
* Terdapat 3 kolom dengan tipe object, yaitu: Name, Symbol, dan Date.
* Terdapat 6 kolom numerik dengan tipe data float64 yaitu: high, low, open, close, volume, dan marketcap.
* Terdapat 1 kolom dengan tipe data int64, yaitu: SNo. Kolom ini hanya nomor urut pada tabel


Uraian di atas menunjukkan bahwa setiap kolom telah memiliki tipe data yang sesuai. Selanjutnya, kita perlu mengecek deskripsi statistik dataseat

Tabel 1. Deskripsi statistik dataseat

|           |     **SNo** |     **High** |      **Low** |     **Open** |    **Close** |   **Volume** | **Marketcap** |
|----------:|------------:|-------------:|-------------:|-------------:|-------------:|-------------:|--------------:|
| **count** | 2991.000000 |  2991.000000 |  2991.000000 |  2991.000000 |  2991.000000 | 2.991000e+03 |  2.991000e+03 |
|  **mean** | 1496.000000 |  6893.326038 |  6486.009539 |  6700.146240 |  6711.290443 | 1.090633e+10 |  1.208761e+11 |
|  **std**  |  863.571653 | 11642.832456 | 10869.032130 | 11288.043736 | 11298.141921 | 1.888895e+10 |  2.109438e+11 |
|  **min**  |    1.000000 |    74.561096 |    65.526001 |    68.504997 |    68.431000 | 0.000000e+00 |  7.784112e+08 |
|  **25%**  |  748.500000 |   436.179001 |   422.879486 |   430.445496 |   430.569489 | 3.036725e+07 |  6.305579e+09 |
|  **50%**  | 1496.000000 |  2387.610107 |  2178.500000 |  2269.889893 |  2286.409912 | 9.460360e+08 |  3.741503e+10 |
|  **75%**  | 2243.500000 |  8733.926948 |  8289.800459 |  8569.656494 |  8576.238715 | 1.592015e+10 |  1.499957e+11 |
|  **max**  | 2991.000000 | 64863.098908 | 62208.964366 | 63523.754869 | 63503.457930 | 3.509679e+11 |  1.186364e+12 |

Berdasarkan Tabel 1 diatas memberikan informasi statistik pada masing-masing kolom, antara lain:
* Count  adalah jumlah sampel pada data.
* Mean adalah nilai rata-rata.
* Std adalah standar deviasi.
* Min yaitu nilai minimum setiap kolom. 
* 25% adalah kuartil pertama. Kuartil adalah nilai yang menandai batas interval dalam empat bagian sebaran yang sama. 
* 50% adalah kuartil kedua, atau biasa juga disebut median (nilai tengah).
* 75% adalah kuartil ketiga.
* Max adalah nilai maksimum.

Sebelum melakukan pemrosesan data untuk pelatihan, perlu dilakukan analisa pada data untuk mengetahui keadaan pada data seperti korelasi antar fitur dan outlier pada data. Berikut visualisasi data yang menunjukkan korelasi atar fitur dan outlier pada data

### Menagani Missing Value
Tahap selanjutnya kita harus mengecek apakah terdapat missing value pada dataset, karna missing value akan berperngaruh terhadap performa model nantinya

Tabel 2. Missing value pada masing-masing feature dataset

| SNo       | 0 |
|-----------|---|
| Name      | 0 |
| Symbol    | 0 |
| Date      | 0 |
| High      | 0 |
| Low       | 0 |
| Open      | 0 |
| Close     | 0 |
| Volume    | 0 |
| Marketcap | 0 |

Berdasarkan Tabel 2. Dapat diketahui bahwa tidak terdapat missing value pada dataseat

### Menangani Oulier
Pada tahap ini kita perlu mengecek outlier pada dataseat. kita akan menggunakan teknik visualisasi, yaitu jenis boxplot.

Gambar 1. Visualisasi outlier mengunakan teknik boxplot

![Outlier](/image/outlier.png)

Berdasarkan visualisasi Gambar 1, dapat dilihat bahwa banyak terdapat banyak outlier pada masing-masing kolom dataseat kecuali kolom SNo karna kolom tersebut hanyalah kolom nomor urut pada dataseat.
Untuk mengatasi oulier tersebut kita akan mengunakan teknik IQR (Inter Quartile Range) methode yaitu dengan menghapus data yang berada diluar interquartile range. Interquartile merupakan range diantara kuartil pertama(25%) dan kuartil ketiga(75%)

### Univariate Analysis
Pada tahap ini kita akan melakukan proses analisis data dengan teknik Univariate EDA. Karena target prediksi dari dataset ini ada pada fitur Close yang merupakan harga Bitcoin, jadi hanya fokus menganalisis korelasi data pada feature tersebut. Dari hasil visualisasi Gambar 2, dapat disimpulkan bahwa peningkatan harga bitcoin sebanding dengan penurunan jumlah sampel data.

Gambar 2. Visualisasi histogram masing-masing fitur pada dataset

![Univariate Analysis](/image/univariate-analysis.png)

### Multivariate Analysis
Pada tahap ini kita akan melakukan proses analisis data dengan teknik Multivariate EDA. Jika di lihat dari visualisasi Gambar 3. Fitur Close pada sumbu y memiliki korelasi dengan data pada fitur High, Low, Open, dan Marketcap. Korelasi yang terdapat pada data-data tersebut merupakan korelas yang tinggi, sedangkan untuk fitur Volume terlihat memiliki korelasi yang cukup lemah karena sebaran datanya tidak membentuk pola

Gambar 3. Visualisasi hubungan antara fitur mengunakan fungsi pairplot

![Multivariate Analysis](/image/multivariate-analysis.jpeg)

Untuk lebih jelasnya dapat dilihat melalui visualisasi Gambar 4, yang menunjukkan skor korelasi di tiap fitur dengan fitur Close. Pada fitur High, Low, Open dan Marketcap memiliki skor korelasi yang terbilang tinggi yaitu 1. Sedangkan pada fitur Volume memiliki skor korelasi yang cukup rendah yaitu 0.8. Sehingga fitur Volume ini dapat didrop dari dataset.

Gambar 4. Correlation Matrix

![Correlation Matrix](/image/correlation-matrix.png)
    
## Data Preparation
Tahap ini merupakan tahapan dalam mempersiapkan data untuk keperluan pelatihan model:
### Seleksi Fitur
Kolom data seperti (SNo, Name, Symbol, Date, Marketcap) tidak diperlukan untuk pelatihan, karena data tersebut akan mengganggu model dalam mempelajari data. Karena isi dari data tersebut tidak memiliki value yang berarti untuk dipelajari oleh model.

### Train-Test-Split
Membagi dataset menjadi data latih (train) dan data uji (test) merupakan hal yang harus kita lakukan sebelum membuat model.Data latih adalah sekumpulan data yang akan digunakan oleh model untuk melakukan pelatihan. Sedangkan, data uji adalah sekumpulan data yang akan digunakan untuk memvalidasi kinerja pada model yang telah dilatih. Karena data uji berperan sebagai data baru yang belum pernah dilihat oleh model, maka cara ini efektif untuk memeriksa performa model setelah proses pelatihan dilakukan. Proporsi pembagian dataset pada proyek ini menggunakan proporsi pembagian 80:20 yang berarti sebanyak 80% merupakan data latih dan 20% persen merupakan data uji.

### Standarisasi
Melakukan transformasi pada data fitur fitur yang akan dipelajari oleh model menggunakan library MinMaxScaler. MinMaxScaler mentransformasikan fitur dengan menskalakan setiap fitur ke rentang tertentu. Library ini menskalakan dan mentransformasikan setiap fitur secara individual sehingga berada dalam rentang yang diberikan pada set pelatihan, pada library ini memiliki range default antara 0 dan 1. Dengan merenapkan teknik normalisasi data, model akan dengan lebih mudah mengenali pola-pola yang terdapat pada data sehingga akan menghasilkan prediksi yang lebih baik daripada tidak menggunakan teknik normalisasi.

## Model Development
Pada tahap ini, kita akan mengembangkan model machine learning dengan tiga algoritma. Kemudian melakukan tuning hyperparameters untuk mendapatkan parameter dengan performa terbaik pada model, kita akan mengevaluasi performa masing-masing algoritma dan menentukan algoritma mana yang memberikan hasil prediksi terbaik. Ketiga algoritma yang akan kita gunakan, antara lain:

1. Support Vector Machine
2. K-Nearest Neighbours
3. Random Forest

#### **Support Vector Regression**
_Support Vector Regression_ (SVR) menggunakan prinsip yang sama dengan SVM pada kasus klasifikasi. Perbedaannya adalah jika pada kasus klasifikasi, SVM berusaha mencari ‘jalan’ terbesar yang bisa memisahkan sampel-sampel dari kelas berbeda, maka pada kasus regresi SVR berusaha mencari jalan yang dapat menampung sebanyak mungkin sampel di ‘jalan’. Pada pembuatan model ini dilakukan dengan menggunakan modul yang tersedia di library scikit-learn dengan menggunakan beberapa parameter sebagai berikut:

* `kernel` = rbf. Parameter ini merupakan metode yang digunakan untuk mengambil data sebagai input dan mengubahnya menjadi bentuk pemrosesan data yang diperlukan.
* `gamma` = 0.003. Secara intuitif, parameter gamma menentukan seberapa jauh pengaruh satu contoh pelatihan mencapai, dengan nilai rendah berarti 'jauh' dan nilai tinggi berarti 'dekat'. Parameter gamma dapat dilihat sebagai kebalikan dari radius pengaruh sampel yang dipilih oleh model sebagai vektor pendukung.
* `C (parameter Regularisasi)` = 100000. Parameter C menukar klasifikasi yang benar dari contoh pelatihan terhadap maksimalisasi margin fungsi keputusan. Untuk nilai C yang lebih besar, margin yang lebih kecil akan diterima jika fungsi keputusan lebih baik dalam mengklasifikasikan semua titik pelatihan dengan benar. C yang lebih rendah akan mendorong margin yang lebih besar, oleh karena itu fungsi keputusan yang lebih sederhana, dengan mengorbankan akurasi pelatihan. Dengan kata lain C berperilaku sebagai parameter regularisasi dalam SVR.


Pada tahap ini model akan melakukan pelatihan terhadap data latih untuk mendapatkan error seminimal mungkin, kemudian setelah pelatihan model melakukan prediksi terhadap data yang belum pernah di lihat sebelumnya menggunakan data uji. Namun algoritma ini memiliki keunggulan dan kekurangan.

Berikut keunggulan Support Vector Machine:
* SVR efektif pada data berdimensi tinggi (data dengan jumlah fitur atau atribut yang sangat banyak).
* SVR efektif pada kasus di mana jumlah fitur pada data lebih besar dari jumlah sampel.
* SVR menggunakan subset poin pelatihan dalam fungsi keputusan (disebut support vector) sehingga membuat penggunaan memori menjadi lebih efisien.

Berikut kelemahan Support Vector Machine:
* Sulit dipakai dalam problem berskala besar. Skala besar dalam hal ini dimaksudkan dengan jumlah sample yang diolah.

#### **K-Nearest Neighbours**
K-nearest neighbor adalah salah satu algoritma machine learning dengan pendekatan supervised learning yang bekerja dengan mengkelaskan data baru menggunakan kemiripan antara data baru dengan sejumlah data (k) pada lokasi yang terdekat yang telah tersedia. Algoritma ini menerapkan lazy learning” atau “instant based learning” dan merupakan algoritma non parametrik. Algoritma KNN digunakan untuk klasifikasi dan regresi. Pada pembuatan model ini akan menggunaka modul KNN yang terlah di sediakan oleh library _scikit-learn_ .Pada model ini hanya akan menggunakan 1 parameter yaitu `n_neighbours` (Jumlah tetangga). Jumlah _neighbours_ yang di gunakan yaitu sejumlah 5 neighbours. Kemudian, untuk menentukan titik mana dalam data yang paling mirip dengan input baru, KNN menggunakan perhitungan ukuran jarak. Metrik ukuran jarak yang digunakan secara default pada library sklearn adalah Minkowski distance. Setelah menentukan nilai-nilai pada parameter model melakukan pelatihan menggunakan data latih setelah itu model akan melakukan prediksi terhadap data yang belum pernah dilihat dengan menggunakan data uji. Namun algoritma ini memiliki keunggulan dan kekurangan.

Berikut keunggulan K-Nearest Neighbours:
* Sangat sederhana dan mudah dipahami
* Sangat mudah diterapkan
* Dapat digunakan dalam proses klasifikasi maupun regresi.
* Sangat mudah jika akan dilakukan penambahan data
* Parameter yang diperlukan sedikit, yaitu hanya jumlah tetangga yang dipertimbangkan (K), dan metode perhitungan jaraknya (distance metrik)

Berikut kelemahan K-Nearest Neighbours:
* Perlu menentukan nilai K yang tepat.
* Computation cost yang tinggi
* Waktu pemrosesan yang lama jika datasetnya sangat besar.
* Tidak cukup bagus jika diterapkan pada high dimensional data
* Sangat sensitif pada data yang memiliki banyak noise (noisy data), banyak data yang hilang (missing data), dan pencilan (outliers).

#### **Random Forest**
Algoritma ini merupakan sekumpulan algoritma decision tree. Konsep dasar decision tree adalah mengubah data menjadi aturan-aturan keputusan. Kombinasi dari masing–masing decision tree yang baik kemudian dikombinasikan ke dalam satu model. Random Forest bergantung pada sebuah nilai vector random dengan distribusi yang sama pada semua pohon yang masing masing decision tree memiliki kedalaman yang maksimal. Algoritma ini bisa menyelesaikan permasalahan klasifikasi dan regresi. Pada kasus klasifikasi, prediksi akhir diambil dari prediksi terbanyak pada seluruh pohon. Sedangkan, pada kasus regresi, prediksi akhir adalah rata-rata prediksi seluruh pohon. Untuk pembuatan model Random Forest, akan menggunakan beberapa parameter, antara lain:
* `n_estimator`: jumlah trees (pohon) di forest. Di sini kita set `n_estimator`=50.
* `max_depth`: kedalaman atau panjang pohon. Ia merupakan ukuran seberapa banyak pohon dapat membelah (splitting) untuk membagi setiap node ke dalam jumlah pengamatan yang diinginkan.

Setelah itu model akan melakukan pelatihan menggunakan data latih, setelah itu model bisa melakukan prediksi pada data yang belum pernah diliath dengan menggunakan data uji. Namun model ini memiliki beberapa keuntungan dan juga kelemahan.

Berikut keunggulan Random Forest:
* Algoritma Random Forest merupakan algoritma dengan pembelajaran paling akurat yang tersedia. Untuk banyak kumpulan data, algoritma ini menghasilkan pengklasifikasi yang sangat akurat.
* Berjalan secara efisien pada data besar.
* Dapat menangani ribuan variabel input tanpa penghapusan variabel.
* Memiliki metode yang efektif untuk memperkirakan data yang hilang dan menjaga akurasi ketika sebagian besar data hilang.

Berikut kelemahan Random Forest:

* Algoritma Random Forest overfiting untuk beberapa kumpulan data dengan tugas klasifikasi/regresi yang bising/noise.
* Untuk data yang menyertakan variabel kategorik dengan jumlah level yang berbeda, Random Forest menjadi bias dalam mendukung atribut dengan level yang lebih banyak. Oleh karena itu, skor kepentingan variabel dari Random Forest tidak dapat diandalkan untuk jenis data ini.

### Tuning Hyperparameters
Untuk melakukan tuning hyperparameter pada proyek ini menggunakan teknik Grid search. Grid search memungkinkan untuk menguji beberapa parameter sekaligus pada sebuah model. Dengan menerapkan teknik ini kita dapat melihat performa model terbaik dengan parameter tertentu.

## Evaluasi Model
Pada tahap ini metrik yang akan kita gunakan adalah MSE atau Mean Squared Error yang menghitung jumlah selisih kuadrat rata-rata nilai sebenarnya dengan nilai prediksi
sebelum menghitung nilai MSE dalam model, kita perlu melakukan proses scaling fitur numerik pada data uji. Hal ini harus dilakukan agar skala antara data latih dan data uji sama dan kita bisa melakukan evaluasi.

$$MSE = {1 \over N} \sum_{i=1}^n(y_i-ypred_i)^2$$

dimana:
N = Jumlah dataset
yi = Nilai sebenarnya
ypred = Nilai prediksi

Setelah melakukan scaling pada data uji kita evaluasi ketiga model kita dengan metrik MSE. hasil evaluasi yang didapatkan adalah sebagai berikut

Tabel 3. Hasil evaluasi model dengan metrik MSE

|         |  **train**  |   **test**   |
|--------:|:-----------:|:------------:|
| **SVR** | 8329.656534 |  7033.950142 |
| **KNN** |  12309.9332 | 22227.046939 |
|  **RF** | 3725.583761 | 16448.244813 |

Untuk memudahkan, mari kita plot metrik tersebut dengan bar chart

Gambar 5. Bar Chart evaluasi model

![Grafik Evaluasi](/image/grafik-evaluasi.png)

Dapat dilihat dari visulisasi Gambar 5 bahwa MSE pada model SVR merupakan MSE yang paling rendah dari kedua model lainnya, selain itu jumlah error pada saat pengujian tidak berbeda jauh dengan error pada saat pelatihan.

Pada proyek ini yang menjadi model dengan solusi terbaik adalah _Support Vector Regression (SVR)_. Dimana model ini memiliki nilai error paling rendah dari kedua model lainnya dan hasil prediksinya yang paling mendekati dengan angka sebenarnya.

Selajutnya kita lakukan prediksi harga Bitcoin mengunakan model yang telah dibuat, dan hasil yang didapatkan adalah sebagai berikut

Gambar 6. Bar Chart hasil prediksi model

![Grafik Prediksi](/image/grafik-prediksi.png)

Dapat juga dilihat melalui visualisasi Gambar 6 bahwa angka prediksi pada model SVR yang paling mendekati dengan angka sebenarnya.

## Kesimpulan
1. Pada proyek ini, model _Support Vector Regression (SVR)_ yang memiliki tingkat error paling rendah
2. Setelah dilakukannya Data Understanding diketahui bahwa fitur Close merupakan target utama untuk memprediksi harga Bitcoin
3. Dataset yang digunakan tidak memiliki missing value tetapi banyak terdapat outlier pada dataset 

## Referensi
[1] S. A. Basher dan P. Sadorsky, “Forecasting Bitcoin price direction with random forests: How important are interest rates, inflation, and market volatility?,” Mach. Learn. Appl., vol. 9, hlm. 100355, Sep 2022, doi: 10.1016/j.mlwa.2022.100355.

[2] S. Ali Alahmari, “PREDICTING THE PRICE OF CRYPTOCURRENCY USING SUPPORT VECTOR REGRESSION METHODS,” J. Mech. Contin. Math. Sci., vol. 15, no. 4, Apr 2020, doi: 10.26782/jmcms.2020.04.00023.

[3] H. Fatah dan A. Subekti, “PREDIKSI HARGA CRYPTOCURRENCY DENGAN METODE K-NEAREST NEIGHBOURS,” J. Pilar Nusa Mandiri, vol. 14, no. 2, hlm. 137, Sep 2018, doi: 10.33480/pilar.v14i2.894.

