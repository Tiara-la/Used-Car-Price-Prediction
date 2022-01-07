# Laporan Proyek Machine Learning - Nama Anda
---
## Domain Proyek
---
- Latar Belakang

Saya memilih domain ekonomi dan bisnis yaitu berupa bisnis penjualan mobil bekas di India. Latar belakang saya memilih domain ini adalah karena zaman modern sekarang ini tren penjualan mobil bekas sangat diminati. Berbeda dengan harga mobil baru, harga mobil bekas dipengaruhi oleh banyak faktor. Seperti contohnya mobil yang bermerek sama dan berspesifikasi sama belum tentu memiliki harga yang sama. Hal yang dinilai paling penting adalah kualitas mobil tersebut apakah masih layak pakai atau tidak. Para pembeli biasanya sebelum membeli akan menilai beberapa hal terlebih dahulu seperti tahun kapan mobil ini dibeli, berapa kilometer jarak yang sudah ditempuhnya, sudah berganti berapa kali pemilik, dll.

Mengapa permasalahan tersebut harus diselesaikan karena untuk memudahkan para peminat atau pembeli mobil bekas bisa mengetahui harga yang layak dari mobil yang akan mereka beli. Dan memudahkan penjual dalam menentukan harga yang pas dengan mobil yang akan mereka jual. Karena kualitas mobil dan harga mobil berpengaruh terhadap keputusan pembelian mobil bekas. Jika harga dan kualitasnya tidak cocok ada kemungkinan besar pembeli tidak akan jadi membeli. Maka diperlukanlah model analisis prediksi yang tepat mengenai harga mobil bekas berdasarkan spesifikasinya. )

Sumber referensi terkait: [Referensi 1](http://eprints.undip.ac.id/14009/), [Referensi 2](http://journal.unj.ac.id/unj/index.php/jrmsi/article/view/785/694), [Referensi 3](https://www.jurnal.syntaxliterate.co.id/index.php/syntax-literate/article/view/2716/2076)

## Business Understanding
---
Latar belakang permasalahan ini adalah para penjual mobil bekas ingin menggunakan sebuah sistem yang dapat memudahkan mereka dalam menentukan harga mobil bekas. Jadi permasalahan yang dihadapi adalah bagaimana cara memprediksi harga mobil bekas yang tepat berdasarkan fitur atau karakteristik tertentu. Dan berikut uraian lebih lengkap mengenai penjelasan permasalahan tersebut :
### Problem Statements
Berdasarkan kondisi yang telah diuraikan sebelumnya, saya akan mengembangkan sebuah sistem prediksi harga mobil untuk menjawab permasalahan berikut.
- Bagaimana cara melakukan pra-premosesan data harga mobil bekas agar dapat digunakan untuk membuat model yang baik?
- Dari serangkaian fitur yang ada, fitur apa yang paling berpengaruh terhadap harga mobil?
- Berapa harga pasar mobil dengan karakteristik atau fitur tertentu?  

### Goals

Untuk  solusi permasalahan tersebut, tujuan atau goals nya adalah sebagai berikut:
- Melakukan pra-pemrosesan data harga mobil bekas yang baik agar dapat digunakan dalam membuat model yang baik.
- Mengetahui fitur yang paling berkorelasi dengan harga mobil.
- Membuat model machine learning yang dapat memprediksi harga mobil seakurat mungkin berdasarkan fitur-fitur yang ada.

### Solution statements
Prediksi harga adalah tujuan yang ingin dicapai. Harga merupakan variabel kontinu. Dan jenis permasalahan ini termasuk permasalahan regresi. Oleh karena itu, metodologi pada proyek ini adalah: membangun model regresi dengan harga mobil sebagai target.Solusi yang dapat dilakukan diantaranya :
- Untuk teknik pra-pemrosesan data dilakukan pada tahap Data Preparation dengan teknik berikut :
    - Melakukan Encoding Fitur Kategori yaitu mengganti nilai data kategorik menjadi data numerik supaya data kategorik dapat diolah oleh model
    - Melakukan pembagian dataset menjadi dua bagian dengan rasio 90% untuk data latih dan 10% untuk data uji
    - Melakukan standardisasi data pada semua fitur data.
- Untuk Mengetahui fitur yang paling berkorelasi dengan harga mobil menggunakan **Exploratory Data Analysis - Multivariate Analysis** : 
        - Analisis Hubungan Fitur Numerik dengan Harga
        - Analisis Hubungan Fitur Kategorik dengan Harga

- Untuk membuat model machine learning yang dapat memprediksi harga mobil seakurat mungkin berdasarkan fitur-fitur yang ada saya menggunakan 3 model algoritma yaitu:
1. **K-nearest neighbor**. Algoritma KNN menggunakan ‘kesamaan fitur’ untuk memprediksi nilai dari setiap data yang baru. KNN bekerja dengan membandingkan jarak satu sampel ke sampel pelatihan lain dengan memilih sejumlah k-tetangga terdekat. 
    - Kelebihan : mudah dipahami dan digunakan, tangguh terhadap data training sample yang noisy, efektif apabila data training sample-nya besar, memiliki konsistensi yang kuat.
    - Kekurangan : jika dihadapkan pada jumlah fitur atau dimensi yang besar dan nilai komputasi yang tinggi.

2. **Random Forest**. Algoritma Random Forest adalah model prediksi yang terdiri dari beberapa model dan bekerja secara bersama-sama. Dalam teknik bagging, sejumlah model dilatih dengan teknik sampling with replacement (proses sampling dengan penggantian). Algoritma ini disusun dari banyak algoritma pohon (decision tree) yang pembagian data dan fiturnya dipilih secara acak. 
    - Kelebihan : dapat mengatasi noise dan missing value serta dapat mengatasi data dalam jumlah yang besar. 
    - Kekurangan : interpretasi yang sulit dan membutuhkan tuning model yang
tepat untuk data. 

3. **Boosting Algorithm**. Algoritma boosting bekerja dengan membangun model dari data latih. Kemudian ia membuat model kedua yang bertugas memperbaiki kesalahan dari model pertama. Model ditambahkan sampai data latih terprediksi dengan baik atau telah mencapai jumlah maksimum model untuk ditambahkan. Algoritma ini menggabungkan beberapa model sederhana dan dianggap lemah (weak learners) sehingga membentuk suatu model yang kuat (strong ensemble learner). Pada setiap tahapan, model akan memeriksa apakah observasi yang dilakukan sudah benar. Untuk semua kasus dalam data latih memiliki weight atau bobot yang sama. Bobot yang lebih tinggi kemudian diberikan pada model yang salah sehingga mereka akan dimasukkan ke dalam tahapan selanjutnya. Proses iteratif ini berlanjut sampai model mencapai akurasi yang diinginkan. 
    - Kelebihan : Mampu meningkatkan hasil klasifikasi
    - Kekurangan : Lemah pada data dengan kompleksitas yang
tinggi

## Data Understanding
---
Dataset yang saya gunakan adalah dataset harga mobil bekas [Kaggel](https://www.kaggle.com/balajimummidi/used-cars-in-cars24/data?select=Cars24.csv). Didalam dataset set ini terdapat 5918 rows × 11 columns.

Variabel-variabel pada Harga Mobil Kaggle dataset adalah sebagai berikut:
- Unnamed: 0 : nomor baris
- Car Brand : Nama mobil
- Model : model mobil	
- Price	: harga jual mobil bekas
- Model Year : tahun produksi mobil
- Location	: Lokasi di mana mobil dijual atau tersedia untuk dibeli
- Fuel : bahan bakar mobil
- Driven (Kms) : jumlah Kilometer yang telah dilalui mobil
- Gear :  transmisi gigi mobil (Otomatis/Manual)
- Ownership : Apakah kepemilikannya adalah Tangan Pertama, Tangan Kedua atau lainnya
- EMI (monthly) : cicilan bulanan yang diberikan kepada pembeli jika membeli mobil tersebut

Tahapan yang dilakukan untuk memahami data adalah :
- **Data loading** untuk membaca file dataset  dalam komputer atau local machine. upload dataset tersebut langsung ke file storage di Google Colab.
- **Exploratory Data Analysis (EDA)** merupakan proses investigasi awal pada data untuk menganalisis karakteristik, menemukan pola, anomali, dan memeriksa asumsi pada data. 

1. **Exploratory Data Analysis - Deskripsi Variabel** untuk memahami deskripsi variabel pada data. Untuk mengecek informasi pada dataset dengan fungsi info() dan menggunakan fungsi describe() untuk memberikan informasi statistik pada masing-masing kolom.

2. **Exploratory Data Analysis - Menangani Missing Value dan Outliers**  untuk cek adanya missing value atau tidak. Kemudian mendeteksi dan menangani outliers. Teknik yang digunakan adalah teknik visualisasi data dan IQR method. Teknik visualisasi yang digunakan adalah jenis boxplot. Boxplot menunjukkan ukuran lokasi dan penyebaran, serta memberikan informasi tentang simetri dan outliers. Visualisasi hanya digunakan pada data numerik ['Model_Year', 'Price', 'Driven', 'Ownership', 'EMI']. Selanjutnya adalah mengatasi outliers tersebut dengan metode IQR dengan membuat batas bawah dan batas atas.
Berikut persamaannya:

     Batas bawah = Q1 - 1.5 * IQR
     
      Batas atas = Q3 + 1.5 * IQR

3. **Exploratory Data Analysis - Univariate Analysis** analisis univariate adalah melakukan analisis terhadap satu jenis (variasi). Dengan kata lain, analisis univariate merupakan proses untuk mengeksplorasi dan menjelaskan setiap variabel dalam kumpulan data secara terpisah. Cara yang digunakan adalah membagi fitur pada dataset menjadi dua bagian, yaitu numerical features dan categorical features. Lalu melakukan analisis terhadap **fitur kategori** terlebih dahulu ['Car_Brand', 'Model', 'Location', 'Fuel', 'Gear']. 
![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/fuel%20uni.png)  
Dari data persentase dapat kita simpulkan bahwa bahan bakar yang paling banyak digunakan adalah jenis bahan bakar Petrol dan Diesel.
![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/car%20brand%20uni.png)  
Dari data persentase dapat kita simpulkan bahwa car brand paling banyak muncul adalah brand Maruti.  
![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/gear%20uni.png)  
Dari data persentase dapat kita simpulkan bahwa jenis transmisi gigi mobil yang paling banyak adalah manual.
![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/model%20uni.png)  
Dari data persentase dapat kita lihat kalau diagram terlalu jenis model sehingga diagram tidak bisa terbaca. Namun data analisis menyebutkan model Alto 800LXI adalah model yang lebih banyak keluar dengan 143 jumlah sampel.
![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/location%20uni.png)  
Dari data persentase dapat kita simpulkan bahwa daerah yang paling banyak menjual mobil bekas adalah kota Delhi, lalu diikuti kota Mumbai, Bangalore, Chennai, dan Hyderabad.
Setelah fitur kategori dilanjutkan dengan **fitur numerik** dengan melihat histogram masing-masing fiturnya, seperti berikut :
![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/histo%20numerik.png)  
Dari histogram diatas kita bisa memperoleh beberapa informasi, antara lain:
    - Peningkatan harga mobil sebanding dengan penurunan jumlah driven.
    - Rentang harga mobil cukup tinggi yaitu dari skala EMI 7000 sampai 10000.
    - Rentang harga mobil cukup tinggi yaitu dari Tahun 2014 sampai 2018.
    - Rata-rata pemilik mobil adalah dari pemilik pertama

4. **Exploratory Data Analysis - Multivariate Analysis** Analisis multivariate adalah melakukan analisis terhadap banyak variasi variabel. Dengan kata lain, multivariate analysis merupakan proses eksplorasi yang melibatkan banyak (dua atau lebih) variabel pada data. Pertama mengecek rata-rata harga terhadap masing-masing fitur untuk mengetahui pengaruh fitur kategori terhadap harga.
![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/multi%20car_brand.png)
![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/multi%20fuel2.png)
![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/multi%20model.png)
![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/multi%20location.png)
![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/multi%20gear.png)  
Dengan mengamati rata-rata harga relatif terhadap fitur kategori di atas, kita memperoleh insight sebagai berikut:
- Pada fitur 'car_brand' jika dilihat setiap car brand memiliki harga rata-rata yang berbeda-beda tergantung dari nama brandnya. Jika berasal dari brand yang terkenal maka harga mobil akan cenderung mahal.Dari sini dapat disimpulkan bahwa car_brand memiliki pengaruh terhadap harga.
- Pada fitur 'fuel' Diesel memiliki harga rata-rata tertinggi diantara grade lainnya. Mobil berbahan bakar diesel lebih mahal karena biaya perawatannya lebih mahal. Dari sini dapat disimpulkan bahwa fuel memiliki pengaruh terhadap harga. [(Sumber)](https://www.autofun.co.id/berita/bikin-penasaran-kenapa-sih-harga-mobil-diesel-lebih-mahal-dari-mobil-bensin-22220)

- Pada fitur 'model' jika dilihat diagram model memang tidak terlihat datanya karena jumlah model yang terlalu banyak. Namun jika dilihat secara umum model dari sebuah mobil cenderung berpengaruh dengan harga mobil. Dari sini dapat disimpulkan bahwa model memiliki pengaruh terhadap harga.
- Pada 'location'  disini dilihat bahwa daerah mumbai memiliki harga rata-rata lebih tinggi dari yang lainnya. Namun harga rata-rata cenderung sama disemua daerah. Dari sini dapat disimpulkan bahwa location memiliki pengaruh yayng kecil terhadap harga.
- Pada fitur 'gear' Automatic memiliki harga rata-rata lebih tinggi dari Manual. Jika dilihat secara umum juga kebanyakan mobil Automatic lebih mahal daripada mobil manual. Dari sini dapat disimpulkan bahwa Transmission memiliki pengaruh terhadap harga.

## Data Preparation
---
Berikut merupakan solusi dari teknik pra-premosesan yang sudah disebutkan sebelumnya yang saya gunakan pada tahap data preparation adalah:
- **Encoding Fitur Kategori** Melakukan proses encoding fitur kategori dengan teknik one-hot-encoding. Proses encoding ini dilakukan dengan fitur get_dummies. Fungsinya adalah mengganti nilai data kategorik menjadi data numerik . Variabel kategori dalam dataset ini, yaitu 'Car_Brand', 'Model', 'Location', 'Fuel', 'Gear'. Alasan menggunakan teknik ini adalah karena model machine learning tidak dapat mengolah data kategorik, sehingga perlu melakukan konversi data kategorik menjadi data numerik.
- **Train_test_spilt** Pembagian dataset dengan fungsi train_test_split dari library sklearn. Membagi dataset menjadi data latih (train) dan data uji (test). Perbandingan yang saya terapkan adalah 90:10, 90% untuk data latih dan 10% untuk data uji. Alasannya adalah agar tidak mengotori data uji dengan informasi yang didapat dari data latih dan menghindari kebocoran data (data leakage). 
- **Standarisasi**  Teknik yang digunakan adalah teknik StandarScaler dari library Scikitlearn, StandardScaler melakukan proses standarisasi fitur dengan mengurangkan mean (nilai rata-rata) kemudian membaginya dengan standar deviasi untuk menggeser distribusi. StandardScaler menghasilkan distribusi dengan standar deviasi sama dengan 1 dan mean sama dengan 0. Alasan menggunakan teknik ini adalah supaya performa model lebih baik dan konvergen lebih cepat ketika dimodelkan. Karena data memiliki skala relatif sama atau mendekati distribusi normal. Selain itu proses scaling dan standarisasi membantu untuk membuat fitur data menjadi bentuk yang lebih mudah diolah oleh algoritma.

## Modeling
---
Dalam menyelesaikan permasalahan saya mengembangkan model dari 3 algoritma machine learning yaitu **K-nearest neighbor**, **Random Forest**, dan **Boosting Algorithm**. Dari ketiga algoritma ini, model akan dibuat seakurat mungkin, yaitu model dengan nilai kesalahan sekecil mungkin. Lalu akan mengevaluasi performa masing-masing algoritma dan menentukan algoritma mana yang memberikan hasil prediksi terbaik dan yang memiliki nilai kesalahan prediksi terkecil. 

Setelah menerapkan 3 algoritma di atas didapat hasil prediksi bahwa algoritma **Random Forest** lah yang memiliki hasil paling mendekati dengan nilai yang benar. Hal ini ditunjukan pada tabel berikut :

![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/evaluasi.png)


## Evaluation
---
Metrik digunakan untuk mengevaluasi seberapa baik model Anda dalam memprediksi harga. Untuk kasus regresi ini, metrik yang saya gunakan adalah Mean Squared Error (MSE) dan Root Mean Squared Error (RSME).

 **MSE atau Mean Squared Error** Metrik ini menghitung selisih rata-rata nilai sebenarnya dengan nilai prediksi. 
 - Kelebihan MSE yaitu sederhana dalam perhitungan. 
 - Kelemahan yang dimiliki MSE adalah akurasi hasil peramalan sangat kecil      karena tidak memperhatikan apakah hasil peramalan lebih besar atau lebih     kecil dibandingkan kenyataannya. 
Berikut hasil evaluasi dengan metrik MSE :

 algorithm | train      |test
-----------|------------|-----	
KNN        | 1.1639e+06 | 1.74399e+06
RF         | 79.2499    | 117.142
Boosting   | 803786     | 772898

MSE didefinisikan dalam persamaan berikut :

![Gambar Memotret](https://d17ivq9b7rppb3.cloudfront.net/original/academy/2021071619431112f1106e20559e77c855cea11d1b1479.jpeg)  

N = jumlah dataset

yi = nilai sebenarnya

y_pred = nilai prediksi  


**RMSE atau Root Mean Squared Error** RMSE (Root Mean Square Error) adalah akar kuadrat dari MSE. Nilai RMSE digunakan untuk menggambarkan tingkat error data model yang digunakan. Semakin kecil nilai RMSE maka semakin tinggi nilai akurasi sistem. 
- Kelebihan : menghukum large error lebih sehingga bisa lebih tepat dalam beberapa kasus, menghindari penggunaan pengambilan nilai absolut, yang tidak diinginkan dalam banyak perhitungan matematis
- Kekurangan : tidak mendeskripsikan kesalahan rata-rata saja dan memiliki implikasi lain yang lebih sulit untuk dipahami

Berikut merupakan hasil evaluasi dari metrik RSME : 
algorithm | train      |test
-----------|------------|-----	
KNN        | 34.1159    | 41.7611
RF         | 0.281514   | 0.342261
Boosting   | 28.3511    | 27.801

MSE didefinisikan dalam persamaan berikut :

![Gambar Memotret](https://github.com/Tiara-la/Gambar-EDA/raw/main/rsme.png)  

n = jumlah dataset

Yi = nilai sebenarnya

yi = nilai prediksi

**---Ini adalah bagian akhir laporan---**



