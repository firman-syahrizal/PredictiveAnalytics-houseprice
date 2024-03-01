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

Berdasarkondisi yang telah diuraikan sebelumnya, akan dikembangkan model machine learning prediksi harga rumah dengan tujuan menyelesaikan permasalahan berikut:
- Dari berbagai variabel independen yang ada, variabel apa yang paling berpengaruh terhadap harga (variabel dependen) ?
- Bagaimana cara memanfaatkan dataset harga rumah untuk membuat model prediksinya menggunakan machine learning ?
- Bagaimana cara menentukan model prediksi harga yang baik ?

### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Jawaban pernyataan masalah 1
- Jawaban pernyataan masalah 2
- Jawaban pernyataan masalah n

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution statement. Misalnya, menggunakan dua atau lebih algoritma untuk mencapai solusi yang diinginkan atau melakukan improvement pada baseline model dengan hyperparameter tuning.
    - Solusi yang diberikan harus dapat terukur dengan metrik evaluasi.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

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


