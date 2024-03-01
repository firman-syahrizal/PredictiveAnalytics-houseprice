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
    - Histogram digunakan untuk menampilkan persebaran data.
    - catplot digunakan untuk visualisasi fitur kategori.
    - pairplot digunakan untuk visualisasi hubungan dua fitur dengan bentuk scatter.
    - heatmap digunakan untuk menampilkan correlation matrix.
- a

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

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


