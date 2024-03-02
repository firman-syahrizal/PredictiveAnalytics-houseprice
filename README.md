# Laporan Proyek Machine Learning - Firman Syahrizal

## Domain Proyek

Prediksi harga rumah memiliki peranan yang penting dalam penentuan kebijakan real estate nasional [[1](https://www.sciencedirect.com/science/article/abs/pii/S0957417423014835)]. 

Prediksi harga rumah menjadi hal yang penting sekarang ini, terlebih bagi beberapa pemangku kepentigan seperti pemiliki rumah, agen penjualan rumah, maupun lembaga pembuat kebijakan [[2](https://www.sciencedirect.com/science/article/abs/pii/S2214579622000491)]. 

Analisis pasar real estate menarik perhatian peneliti maupun praktisi [[3](https://www.sciencedirect.com/science/article/pii/S014829632200039X)].

Seiring dengan berkembangnya teknologi, saat ini terdapat model machine learning yang dapat digunakan untuk memprediksi harga rumah. Model machine learning regresi menjadi pilihan yang tepat sebagai solusi dalam prediksi harga rumah. Harga rumah yang ditentukan oleh banyak faktor baik faktor seperti lokasi, kota, dan populasi [[4](https://www.sciencedirect.com/science/article/pii/S1877050922001016)]. 

Perkembangan model dalam prediksi harga rumah  dapat ditingkatkan akurasinya dengan teknik PCA [[5](https://www.researchgate.net/publication/366979465_Real-estate_price_prediction_with_deep_neural_network_and_principal_component_analysis)]. 


## Business Understanding

Berdasar latar belakang yang ada dapat disimpulkan jika pembuatan model machine learning untuk prediksi harga rumah dapat membantu banyak pihak lebih bijak dalam mengambil keputusan. Sekarang ini, jumlah data terkait jual beli rumah sudah banyak, pemanfaatan machine learning tentunya cocok diterapkan dalam mupaya mengekstrak informasi berdasar data yang besar.

### Problem Statements

Berdasar kondisi yang telah diuraikan sebelumnya, akan dikembangkan model machine learning prediksi harga rumah dengan tujuan menyelesaikan permasalahan berikut:
- Dari berbagai variabel independen yang ada, variabel apa yang paling berpengaruh terhadap harga (variabel dependen) ?
- Bagaimana cara memanfaatkan dataset harga rumah untuk membuat model prediksinya menggunakan machine learning ?
- Bagaimana cara menentukan model prediksi yang baik ?

### Goals

Dibuat model predictive machine learning dengan tujuan:
- Mengetahui variabel independen yang memiliki korelasi tinggi dengan variabel dependen (harga rumah).
- Dataset yang dimodelkan dengan teknik regresi dapat digunakan untuk memprediksi harga rumah. 
- Model machine learning akan dijui pada tahap evaluasi untuk dilihat performanya. Evaluasi dapat dilakukan dengan menggunakan beberapa metric pengujian.

    ### Solution statements
  Solusi yang ditawarkan adalah dengan membuat model prediksi harga rumah dengan tipe regresi karena harga tergolong dalam data kontinu.
    - Variabel independen yang memiliki korelasi tinggi dapat diketahui dengan analisis multivariat. Analisis multivariat adalah analisis yang digunakan untuk menunjukkan hubungan antara dua variabel (fitur) atau lebih. Fitur kategori dapat dilihat pengaruhnya dengan melihat korelasi antara harga rata-rata rumah terhadap masing-masing fitur. Sedangkan data numerik dapat dilihat hubungannya menggunakan fungsi fairplot() dan corr().
    - Pembuatan model machine learning dimulai dengan memahami data, mengubah data kedalam bentuk yang dapat difahami komputer, memodelkan data menggunakan algoritma yang sesuai, dan mengevaluasi model. Terdapat lima model yang akan digunakan, Linear Regression, K-Nearest Neighbor, Random Forest, Boosting, dan Support Vector Regression.
    - Metric yang dapat dipakai untuk evaluasi model diantaranya MSE, MAE, dan RMSE.

## Data Understanding
Data yang digunakan adalah data California Housing Prices yang dapat ditemukan pada laman : https://www.kaggle.com/datasets/camnugent/california-housing-prices/data .
Berikut merupakan kondisi data yang digunakan:
- Dataset merupakan data dengan format CSV.
- Dataset terdiri dari 20640 sampel.
- Dataset memiliki sepuluh kolom.
- Dataset memiliki data kategori dan data numerik.

### Variabel-variabel pada California Housing Prices dataset adalah sebagai berikut:
- longitude : merupakan letak geografis suatu lokasi pada garis bujur.
- latitude : merupakan letak geografis suatu lokasi pada garis lintang.
- housing_age : nilai tengah umur rumah pada suatu kawasan (blok)
- rooms : banyaknya ruangan pada suatu kawasan (blok).
- bedrooms : banyaknya kamar tidur pada suatu kawasan (blok).
- population : banyaknya orang/ penghuni pada suatu kawasan (blok).
- households : banyaknya penghuni rumah/ grup orang pada kawasan (blok).
- income : jumlah pendapatan pemiliki rumah pada suatu kawasan dalam satuan sepuluh ribu USD.
- price : median harga rumah di suatu kawasan dalam USD, price ini yang merupakan fitur target.
- ocen_proximity : lokasi rumah relatif terhadap laut.

**Tahapan Explorasi Data**
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.
- Untuk lebih memahami data, dilakukan dua analisis data yaitu univariat analysis dan multivariat analysis.
- Baik analisis univariat maupun multivariat keduanya dibedakan menjadi dua, fitur kategori dan numerik.
- Penggunaan visualisasi dengan gambar dipilih karena dapat menyajikan data dalam format yang lebih informatif.
- Teknik visualisasi data dalam bentuk histogram untuk analisis univariat. Sedangkan pada analisis multivariat menggunakan catplot, pairplot, dan heatmap.
    - histogram digunakan untuk menampilkan persebaran data.
    - catplot digunakan untuk visualisasi fitur kategori.
    - pairplot digunakan untuk visualisasi hubungan dua fitur dengan bentuk scatter.
    - heatmap digunakan untuk menampilkan correlation matrix.

    #### Analisis Univariat
  Hasil analisis univariat baik untuk data kategori maupun numerik divisualisasi pada gambar berikut.
  
  ![Univariate Analysis-Categorical Feature](https://github.com/firman-syahrizal/PredictiveAnalytics-houseprice/assets/156873837/15f3614d-1e24-46a7-86ec-4e5d74c72029)

  Gambar 3.1a Visualisasi Univariat Fitur Kategori

  ![Univariate Analysis-Numrical Feature](https://github.com/firman-syahrizal/PredictiveAnalytics-houseprice/assets/156873837/ec5fc199-2586-43d8-b4b2-218be0bd6517)
  
  Gambar 3.1b Visualisasi Univariat Fitur Numerik

Berdasarkan dua visualisasi diatas:
- Terdapat lima kategori pada fitur ocean_proximity, secara berurutan dari yang jumlahnya terbanyak yaitu <1H Ocean, Inland, Near Ocean, Near Bay, dan Island. Terlihat jika data yang dimiliki banyak tersebar pada <1H Ocean dan Inland.
- Berdasar histogram diatas, fitur *rooms, bedrooms, population, households, income* dan *price* memiliki persebaran data yang relatif baik.
Dari histogram fitur target, *price* terdapat beberapa informasi diantaranya:
    1. Sampel mendekati distribusi normal dengan sedikit condong ke kiri yang berarti lebih banyak ditemukan sampel yang memiliki pendapatan relatif rendah.
    2. Harga rumah memiliki rentang harga yang cukup beragam mulai dari 100000 USD hingga hampir 500000 USD.
    3. Harga rumah kurang dari 200000 USD mendominasi.
    4. Distribusi normal dari harga rumah juga condong ke kiri.

    #### Analisis Multivariat
  *Multivariate analysis* digunakan untuk menunjukkan hubungan antara dua atau lebih variabel pada suatu data. Akan dilakukan analisis data pada fitur numerik dan kategori. Visualisasi dari analisis multivariat ditampilkan pada dua gambar berikut.

  ![Multivariate Analysis-Categorical Feature](https://github.com/firman-syahrizal/PredictiveAnalytics-houseprice/assets/156873837/49acfbe3-949b-4c56-9eec-7f08ab1d21b7)

  Gambar 3.2a Visualisasi Multivariat Fitur Kategori

  ![Multivariate Analysis-Numerical Feature](https://github.com/firman-syahrizal/PredictiveAnalytics-houseprice/assets/156873837/93382600-4562-4ac0-8328-a331cea6bc82)

  Gambar 3.2b Visualisasi Multivariat Fitur Numerik

  Berdasarkan dua visualisasi diatas didapati:
  - Untuk fitur kategori, terlihat jika rata-rata harga rumah cukup dipengaruhi oleh posisinya relatif terhadap laut. Rumah yang bernilai island memiliki harga yang relatif tinggi dibanding lainnya. Kemudian rumah dengan *ocean proximity*; *nearbay, <1H ocean*, dan *near ocean* memiliki harga yang relatif sama. Sedangkan rumah yang *ocean proximity*-nya *inland* memiliki harga yang relatif rendah.
  - Untuk fitur numerik, terlihat jika hanya fitur *income* saja yang memiliki korelasi dengan fitur *price* (target), sisanya memiliki korelasi yang lemah. Jika diperhatikan lebih dalam lagi, maka terlihat jika fitur *rooms, bedrooms*, dan *households* memiliki korelasi yang tinggi. Nantinya ketiga fitur ini akan dikurangi dimensinya dengan teknik PCA.

Untuk melihat besarnya korelasi antar fitur dapat digunakan *Correlation Matrix* yang hasilnya ditampilkan pada gambar berikut.

![Multivariate Analysis-Correlation Matrix](https://github.com/firman-syahrizal/PredictiveAnalytics-houseprice/assets/156873837/55a60830-26ab-4e76-b678-ae21e9d82e48)

Gambar 3.3 Correlation Matrix Fitur Numerik

Dengan Correlation Matrix, terlihat jika fitur *income* memiliki skor korelasi yang tinggi terhadap fitur target, *price*. Tampak juga jika fitur *population* memiliki skor korelasi yang sangat kecil terhadap fitur target. Hal ini menandakan fitur *population* memiliki korelasi yang rendah terhadap fitur target, sehingga fitur tersebut dapat di-*drop* saja.

## Data Preparation
Pada dasarnya tahapan yang dilakukan dalam membuat model machine learning adalah tahap iteratif, dimana tahapan bisa berulang ke tahap sebelumnya jika diperlukan. Salah satunya yaitu antara tahap Data Understanding dan Data Preparation. 

Terdapat dua tahapan utama dalam data preparation, *data cleaning* dan *data transformation*.

Tahap *data cleaning* dilakukan beriringan dengan tahap *data understanding*, sedangkan tahap *data transformation* dilakukan setelah *data understanding*.

#### **Data Cleaning**: 

Setelah data diimpor tahap selajutnya adalah memastikan data yang digunakan telah bersih dari data pengotor maupun data null-value. Tahap yang dilakukan yaitu :

1. Menagani *missing value*

      Dalam data ditemukan nilai *missing value* sebanyak 207 sampel saat mengunakan fungsi isna(). Jika dibandingkan dengan jumlah sampel yang hampir 21000 maka *missing value* sebanyak 207 data bukanlah data yang banyak, sehingga apabila data ini dihapus tidak akan memberi pengaruh yang besar terhadap keseluruhan data. Pengapusan data yang terdapat *missing value* menggunakan fungsi dropna().
  
2. Menangani *outlier*
  
      Data numerik dimungkinkan mimiliki nilai yang keluar dari lingkungan pengamatannya yang disebut dengan *outlier*. *Outlier* ini dapat mengganggu dataset dengan memberi pengaruh nilai yang kurang merepresentasikan data. Oleh karenanya data *outlier* ini perlu ditangani terlebhih dahulu dengan cara.
   - Lihat adakah *outlier* di dataset mengunakan teknik visualisasi *bloxplot* yang ditampilkan pada gambar berikut.
     ![Data Cleaning-Bloxplot](https://github.com/firman-syahrizal/PredictiveAnalytics-houseprice/assets/156873837/d6e73145-5497-4e4c-a709-a625fb137dcb)

     Gambar 4.1 Visualisasi Outlier

   - Tangani *outlier* dengan metode IQR.
     Metode IQR digunakan untuk mengidentifikasi *outlier* yang berada diluar Q1 dan Q3. *Outlier* yang diidentifikasi menggunakan boxplot didefinisikan sebagai data yang nilainya diatas 1,5 Q3 dan 1,5 Q1. Data yang berada diluar nilai batas ini akan dibuang. 

Karena dataset yang digunakan terdapat *missing value* dan *outlier*, data perlu dilakukan pembersihan dahulu. Pada akhir tahap ini didapati jumlah sampel berkurang dari yang awalnya sebanyak 20640 menjadi 17434 sampel. Data dengan 17434 sampel inilah yang digunakan untuk tahap *Data Understanding*. 

#### **Data Transformation**: 

Tahap *data preparation* (*data transformation*) merupakan tahap untuk mentransformasi data menjadi bentuk yang dapat dimengerti oleh mesin.
Pada bagian ini akan dilakukan empat tahap persiapan data, yaitu:
1. *Encoding* fitur kategori
   
   Supaya data dapat diproses menggunakan metode *Machine Learning*, data yang awalnya berupa fitur kategori diubah menjadi variabel numerik dengan cara one-hot-encoding.

2. Reduksi dimensi dengan *Principal Component Analysis* (PCA)

   Teknik pengurangan dimensi adalah prosedur yang digunakan untuk mengurangi jumlah fitur dengan tetap mempertahankan informasi pada data. Salah satu tekniknya adalah *Principal Component Analysis*, PCA. Teknik PCA digunakan untuk mereduksi dimensi, mengekstrak fitur, dan mentransformasi data dengan mereduksi dimensi-datanya.
Teknik PCA menggunakan metode aljabar linear. PCA digunakan ketika variabel dalam data memiliki korelasi yang tinggi. Korelasi tinggi ini mengindikasikan adanya data yang berulang atau *redudant*.
Jika dilihat terdapat kolom yang memiliki relasi yang tinggi yaitu *rooms, bedrooms,* dan *households*. Maka ketiga fitur ini akan dilihat korelasinya dan dilakukan peringkasan dimensi menggunakan teknik PCA (Gambar 4.1).

    ![Data Preparation-PCA](https://github.com/firman-syahrizal/PredictiveAnalytics-houseprice/assets/156873837/ccbfcbf8-9072-4526-9032-c77519dc7dc5)

    Gambar 4.2 Korelasi Fitur rooms, bedrooms, dan households

    Karena ketiga fitur memiliki korelasi yang tinggi, maka dapat diterapkan teknik PCA untuk mengurangi dimensinya. Didapati proporsi informasi dari tiga komponen PCA yaitu [0.985, 0.014, 0.001]. Berdasar hasil ini, dapat direduksi fitur dan hanya memepertahankan PC (komponen) pertama saja. PC pertama ini menggantikan fitur *rooms, bedrooms,* dan *households* dengan nama *capacity*.

3. Pembagian dataset degan fungsi train_test_split

    Tahapan lain dalam *data preparation* adalah pembagian data menjadi data *train *dan *test*. Tahap pembagian data ini dilakukan sebelum transformasi data lain supaya data uji tidak terkotori oleh data latih.
    Pentingnya pembagian data uji sebelum transformasi salah satunya agar ketika data dilakukan proses *scaling*, data uji tidak diikutsertakan dahulu.
    Proporsi pembagian data latih dan uji bisanya 80:20 atau untuk dataset yang berukuran kecil, sedngkan 90:10 dapat digunakan untuk dataset yang berukuran besar.
    Karena ukuran dataset tergolong besar maka rasio pembagian data latih dan uji yang digunakan sebesar 90:10.

    Sekarang dataset telah dibagi menjadi dua bagian dengan 15690 sampel data latih dan 1744 sampel data uji.

4. Standarisasi

   Salah satu cara yang digunakan untuk meningkatkan performa *machine learning* adalah proses standarisasi, membuat data memiliki skala relatif sama atau mendekati distribusi normal. Proses *scaling* dan standarisasi membantu membuat fitur menjadi bentuk yang lebih mudah diolah oleh algoritma.
    StandarScaler digunakan untuk mentransformasi data dengan mengurangkan rata-rata kemudian membaginya dengan standar deviasi untuk menggeser distribusi.         Dengan StandarScaler data akan memiliki nilai standar deviasi sebesar 1 dan rata-rata 0.
    Tahap satndarisasi juga hanya dilakukan pada data latih saja. Untuk data uji sendiri akan menjalani tahap standarisasi ketika proses evaluasi.


## Modeling
Pada tahap ini akan dibuat lima model *machine learning* yang nantinya akan di cek model mana yang terbaik pada tahap evaluasi. Kelima model tersebut yaitu

* Linear Regression
* K-Nearest Neighbor
* Random Forest (Bagging Algoritm)
* Boosting
* Support Vector Regression

#### 1. **Model Lienear Regressi**
Model Liear Regression merupakan algoritma yang bertujuan mencari *best-fitting straight line* melewati suatu set datapoint. Garis ini merepresentasikan hubungan linear antara satu atau lebih fitur (variabel independen) dan *single continous output variable* (variabel dependen).

Model Linear Regression dipilih karena mudah difahami, efisien dalam pelatihan dan uji, serta model ini cocok digunakan sebagai awalan membuat model *machine learning*. Sayangnya model ini menggunakan asumsi linear antar fitur terhadap variabel target.

#### 2. **Model K-Nearest Neighbor**
Model K-Nearest Neighbor atau yang dikenal sebagai KNN merupakan algoritma yang sederhana dibandingkan algoritma lain. Karena kesederhanaannya, maka model ini cocok digunakan untuk membuat model pertama sebelum mencoba model lain.
Algoritma KNN sendiri menggunakan 'kesamaan fitur' untuk memprediksi nilai terhadap *input*-an data baru. Data baru ini akan dinilai kemiripannya terhadap data set pelatihan.
KKN bekerja dengan membandingkan jarak satu sampel ke sampel pelatihan lain dengan memilih sejumlah K *nearest neighbor*. KNN sendiri dapat digunakan pada model klasifikasi dan regresi.

Parameter yang diatur adalah n_neighbors yaitu jumlah tetangga terdekat yang digunakan.

Keunggulannya adalah model ini termasuk simpel sehingga mudah difahami, sifatnya yang nonparametric membuatnya tetap cocok digunakan pada data yang standar distribusinya kurang baik. Kekurangannya adalah prosesnya yang lambat, performanya dapat meurun ketika banyak fitur, dan sensitif terhadap outlier.

#### 3. **Model Random Forest**
Random Forest termasuk dalam algoritma *supervised learning* yang dapat digunakan untuk menyelesaikan permasalahan klasifikasi maupun regresi.
Random Forest masuk kedalam kategori *ensamble (group) learning*. Model enseamble merupakan model prediksi yang dibentuk dari beberapa model dan bekerja secara bersama-sama. Setiap model membuat prediksi secara independen yang nantinya semua predisksi ini digabung untuk membuat keputusan akhir.
Random Forest pada dasarnya merupakan versi bagging dari algoritma dari decision tree. Dan, bagging adalah teknik melatih model dengan sampel acak.

Parameter yang diatur:
- n_estimator, jumlah decision trees yang digunakan
- max_depth, jumlah maksimal berapa banyak decicion tree dapat membelah
- random_State, mengatur random generator
- n_jobs, berapa banyak pekerjaan dapat diselesaikan dalam satu waktu

Keunggulan dari algoritma ini karena kekaurasiannya yang tinggi, bekerja optimal terhadap outlier, dan mampu menagani data dengan banyak fitur. Kelemahan dari model ini sumber daya yang digunakan tinggi dan terkadang tidak mudah untuk memahami *exact logic* dari hasil prediksinya.

#### 4. **Model Boosting**
Sama seperti teknik bagging, algoritma boosting juga dipakai pada model ensembel (terdiri dari beberapa model yang bekerja secara bersama-sama). Jika pada teknik bagging model dilatih secara paralel, bedanya pada model boosting, model dilatih secara berurutan (iteratif).
Model yang dibangun berikutnya merupakan model yang bertugas memperbaiki kesalahan dari model sebelumnya. Tujuan dari model ini adalah memanfaatkan model sederhana (yang dianggap lemah) untuk membentuk model yang kuat.

Parameter yang diatur:
- learning rate, kontrol kontribusi setiap pohon
- random_state, mengatur random generator

Model ini dipilih karena dapat memerikan hasil yang lebih akurat dibanding *indivisual weaker leaner*, tetap bekerja baik pada data dengan noise dan outlier, dan mampu mengatasi missing value. Sayangnya metode ini juga memiliki kelemahan pada intrepretasi hasil prediksi yang mungkin *exact logic*-nya tidak mudah difahami dan terkadang dapat mengalami overfitting.

#### 5. **Model Support Vector Regression**
SVR merupakan adaptasi dari algoritma *Support Vector Machine* (SVM) untuk kasus regresi. Ide utama dari SVR adalah mencari hyperplane (*or decision boundary*) yang fit terhadap titik-titik data sebanyak mungkin dengan suatu batas toleransi tertentu.

parameter yang diatur:
-c, mengatur nilai kompleksitas dan margin
-epsilon, ukuran margin diamana tidak ada penalti atas kesalahan yang dilakukan

Jika pada model pertama data diasumsikan berbentuk linear, disini data nonlinear dapat dimodelkan lebih baik. Selain itu model ini juga dapat mengatasi interaksi antar fitur yang kompleks. Selain itu model ini juga tetap optimal pada data dengan outlier, dan mampu bekerja dengan baik pada data dengan banyak fitur. Sayangnya model ini bisa saja memberi prediksi yang sulit diinterpretasikan.

**Model yang dipilih**
Nantiya kelima model ini akan dievaluasi performanya menggunakan tiga metric. Melalui tiga metric ini dapat dipilih model yang memberikan hasil terbaik.

## Evaluation
Evaluasi terhadap model yang telah dibuat merupakan langkah yang penting untuk menentukan performa model dalam memprediksi data. Salah stu cara untuk mengevaluasi model dengan menggunakan metric. terdapat tiga metric yang umum digunakan untuk mengukur seberapa besar perbedaan antara hasi prediksi model dengan data aktual. Ketiga metric tersebut adalah MSE, RMSE, dan MAE.

#### **Mean Squared Error (MSE)**
MSE dihitung dengan mencari rata-rata dari selisih kuadrat antara nilai prediksi dengan nilai aktual. Semakin kecil nilai MSE, performa model semakin baik. Rumus MSE ditampilkan sebagai berikut

$$ MSE = (1/n) * Σ (y_i - p_i)^2 $$

dengan 
- m = jumlah data
- y_i = nilai aktual data ke i
- p_i = nilai prediksi model untuk data ke i

#### **Root Mean Squared Error (RMSE)**
Secara sederhana, RMSE adalah akar kuadrat dari MSE. Sama seperti nilai MSE, semakin kecil nilai RMSE, performa model semakin baik. Berikut adalah rumus RMSE

$$ RMSE = √MSE $$

##### **Mean Absolute Error (MAE)**
MAE menghitung nilai rata-rata dari selisih absolute antara nilai prediksi dengan nilai aktual. Semakin kecil nilai MAE, performa model semakin baik. Rmums MAE ditampilkan sebagai berikut

$$ MAE = (1/n) * Σ |y_i - p_i| $$

dengan
- m = jumlah data
- y_i = nilai aktual data ke i
- p_i = nilai prediksi model untuk data ke i

### Hasil Proyek
Hasil proyek disajikan dalam format tabel sebagai berikut

Tabel 6.1 Tabel Perbandingan Performa Keempat Model

|Model| MSE | RMSE | MAE |
|---|---|---|---|
|LR|3.574985e+09|59791.180104|44888.178862|
|KNN|3.139460e+09|56030.881730|39517.884748|
|RF|1.857054e+09|43093.549604|28927.727758|
|Boosting|3.904569e+09|62486.552494|47956.272228|
|SRV|8.689392e+09|93216.907069|73541.503952|

Dari tabel diatas didapati jika model Random Forest dan K-Nearest Neighbor memiliki nilai yang paling kecil dibanding model lainnya. Sehingga model Random Forest dan K-Nearest Neighbor merupakan model terbaik untuk memprediksi harga ruma dengan dataset yang digunakan.

Lebih dalam lagi, nilai MSE ditampilkan pada gambar dibawah

![Evaluasi-MSE](https://github.com/firman-syahrizal/PredictiveAnalytics-houseprice/assets/156873837/9264123b-2d29-4773-a376-1281fd957144)

Gambar 6.1 Hasil MSE dari Kelima Model

Melalui Gambar 6.1 terlihat jika model Random Forest dan KNN memiliki nilai MSE terkecil yang menandakan performanya lebih baik dibanding model lainnya. 

terakhir, dilakukan juga perbandingan antara hasil prediksi dengan nilai aktual yang ditampilkan pada tabel berikut

Tabel 6.2 Perbandingan Nilai Prediksi terhadap Nilai Aktual

|    |y_true|LR|KNN|RF|Boosting|SVR|
|---|---|---|---|---|---|---|
|2757|75500.0|82489.57|78730.0|74341.49|92270.56|169510.8|

Berdasarkan tabel diatas juga terlihat model Random Forest dan KNN memiliki hasil yang paling mendekati dengan nilai aktual.

Dari tahap evaluasi dapat disimpulkan jika terdapat dua model yang memiliki performa baik dibanding lainnya, yaitu model Random Forest dan K-Nearest Neighbor.

## Referensi

[1] C. Zhan, Y. Liu, Z. Wu, M. Zhao, dan T. W. S. Chow, “A hybrid machine learning framework for forecasting house price,” Expert Systems with Applications, vol. 233. Elsevier BV, hlm. 120981, Des 2023. doi: 10.1016/j.eswa.2023.120981. 
[2] A. Karamanou, E. Kalampokis, dan K. Tarabanis, “Linked Open Government Data to Predict and Explain House Prices: The Case of Scottish Statistics Portal,” Big Data Research, vol. 30. Elsevier BV, hlm. 100355, Nov 2022. doi: 10.1016/j.bdr.2022.100355.
[3] T. Potrawa dan A. Tetereva, “How much is the view from the window worth? Machine learning-driven hedonic pricing model of the real estate market,” Journal of Business Research, vol. 144. Elsevier BV, hlm. 50–65, Mei 2022. doi: 10.1016/j.jbusres.2022.01.027. 
[4] A. B. Adetunji, O. N. Akande, F. A. Ajala, O. Oyewo, Y. F. Akande, dan G. Oluwadara, “House Price Prediction using Random Forest Machine Learning Technique,” Procedia Computer Science, vol. 199. Elsevier BV, hlm. 806–813, 2022. doi: 10.1016/j.procs.2022.01.100. 
[5] F. Mostofi, V. Toğan, dan H. B. Başağa, “Real-estate price prediction with deep neural network and principal component analysis,” Organization, Technology and Management in Construction: an International Journal, vol. 14, no. 1. Walter de Gruyter GmbH, hlm. 2741–2759, Jan 01, 2022. doi: 10.2478/otmcj-2022-0016. 
