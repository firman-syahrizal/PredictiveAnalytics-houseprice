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
Data yang digunakan adalah data California Housing Prices yang dapat ditemukan pada [Kaggle](https://www.kaggle.com/datasets/camnugent/california-housing-prices/data).
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
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.


