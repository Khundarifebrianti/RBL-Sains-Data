# RBL-Sains-Data
Prediksi Harga Ponsel Pintar Samsung 
# Domain Proyek 
Harga devise Handphone merupakan salah satu hal yang sangat cepat berubah dengan seiring waktu dan berkembangnya zaman. Kemampuan memprediksi harga ponsel pintar tentunya membantu pembeli sebelum melakukan transaksi jual beli ponsel pintar

Dalam hal jual beli ponsel pintar sangat bergantung kepada spesifikasi seperti, kapasitas RAM, processor, camera, price, dan battrey. Salah satu faktor yang menarik untuk ditelusuri lebih lanjut adalah faktor dari ratings dan harga ponsel pintar. Oleh karena itu, dengan pertimbangan faktor tersebut sangat mempengaruhi harga pada ponsel. Kemudian harga ponsel dapat diestimasi dengan melihat seberapa besar korelasi pengaruh pada faktor-faktor tersebut. 

Dalam membuat model regresi banyak algoritma yang bisa dipilih. Algoritma yang paling umum dan sering digunakan adalah regresi. Dengan menggunakan regresi dan memasukkan faktor-faktor dari spesifikasi ponsel yang ingin didapatkan maka dapat diprediksi harga ponsel. 

# Business Understanding 
Pengembangan model prediksi harga ponsel pintar samsung berpotensi menjadi salah satu alat bantu dalam mengambil keputusan oleh calon pembeli ponsel pintar samsung. Manfaat nyata dari hasil prediksi harga ponsel yang akurat akan membantu pembeli dan penjual dalam membuat kesepakatan. 

# Problem Statements 
- Berdasarkan pengolahan data yang diperoleh, fitur apa saja yang berpengaruh terhadap penentuan harga ponsel pintar
- Bagaimana cara mengolah data set agar didapat model yang sesuai untuk memprediksi harga ponsel pintar samsung.
- Bagaimana cara meningkatkan nilai performa model harpa ponsel?

# Goals 
- Mengekplorasi seluruh fitur yang ada pada dataset dan melihat korelasi harga dari semua fitur untuk menemukan faktor yang berpengaruh dan faktor yang tidak berpengaruh
- Melakukan proses data wragling dan data preparation terhadap dataset yang kemudian akan dibuat model prediksi harga ponsel pintar Samsung
- Melakukan variasi model untuk memperoleh model paling baik dari beberapa model yang paling baik dari model yang lainnya.

# Solution statements 
- Untuk eksplorasi fitur akan dilakukan analisis univariat dan analisis multivariat. Analisis univariate dilakukan untuk mengetahui persebaran dari sebuah data tunggal. Analisis multivariate dilakukan untuk mengetahui korelasi antar fitur. Teknik yang akan dilakukan adalah catplot, pairplot, dan heatmap untuk melihat Correlation Matrix dari semua fitur yang dimiliki.
- Untuk mendapatkan model prediksi digunakan proses Data Wragling yang meliputi Data Gathering, Data Assesing, dan Data Cleaning.
- Untuk menguji performa model dilakukan pengecekan menggunakan metrik evaluasi

# Data Understanding 
Data yang digunakan dalam pembuatan model merupakan data sekunder. Data diambil dari kaggle dengn nama dataset "Samsung_Mobile_New_Data"
URL : _https://www.kaggle.com/code/rautaishwarya/data-cleaning-and-price-prediction/notebook#Model-Building_
Berikut merupakan detail dari dataset 
- Dataset berupa CSV
- Dataset terdiri dari 407 dengan 11 buah fitur yang diukur
- Dataset terdiri dari 5 data kategori dan 6 data numerik
- Dataset tidak memiliki missing value

# Variabel-variabel pada dataset adalah sebagai berikut: 
- Name : Nama model ponsel pintar Samsung dengan berbagai variasi
- Rattings: Peringkat dan ulasan pengguna terkait dengan setiap model dan mencerminkan kepuasan pelanggan
- Price : Harga ponsel Samsung, yang menunjukkan berbagai variasi harga
- imgURL: Gambar terkait model, memfasilitasi untuk membandingkan perbandingan visual
- Storage_ram: Detail tentang kapasitas penyimpanan dan konfigurasi RAM untuk setiap perangkat
- Processor: Rincian sistem operasi dan prosesor untuk menilai kinerja dan kemampuan perangkat
- camera: Informasi tentng spesifikasi kamera yang digunakan pada setiap variasi perangkat
- Display: Spesifikasi terkait layar, seperti ukuran, resolusi, dan teknologi dimana akan memberikan informasi kepada pengguna mengenai pengalaman visual
- Battery: Spesifikasi terkait batteray, termasuk kapasitas dan daya tahan 

Untuk memahami data lebih lanjut, dilakukan Analisis Univariat dan Analisis Multivariat, serta Visualisasi Data

Analisis Univariat merupakan analisis data yang hanya merepresentasikan informasi yang terdapat pada satu variabel. Jenis visualisasi ini umumnya digunakan untuk memberikan gambaran terkait distribusi sebuah variabel dalam suatu dataset. Sedangkan, Analisis Multivariat merupakan jenis analisis data yang terdapat dalam lebih dari dua variabel. Jenis visualisasi ini digunakan untuk merepresentasikan hubungan dan pola yang terdapat dalam multidimensional data.

Selain melalui analisis, dilakukan juga Visualisasi Data. Memvisualisasikan data memberikan wawasan mendalam tentang perilaku berbagai fitur-fitur yang tersedia dalam dataset. Teknik visualisasi yang digunakan pada pembuatan model proyek ini adalah dengan menggunakan catplot yang digunakan untuk memplot distribusi data pada data kategori, pairplot yang digunakan untuk melakukan hubungan antar fitur dalam dataset, dan heatmap yang menampilkan korelasi antar fitur yang ada dalam dataset dalam bentuk matriks.

Berikut adalah hasil Exploratory Data Analysis (EDA), dimana Gambar 1 merupakan EDA Analisis Univariat dan Gambar 2 merupakan EDA Analisis Multivariat.

![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/85ebf9dd-c65a-4eea-9a4f-041e4e058a14)
Gambar 1a. Analisis Univariat (Data Kategori)

![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/b690063c-fbde-4e7e-8a23-0a0c82cea553)
Gambar 1b. Analisis Univariate (Data Numerik)

Berdasarkan Gambar 1a, dapat dilihat bahwa distribusi data kategori pada nama memiliki perbandingan yang tidak sama. Lebih jauh, pada Gambar 1b, untuk data numerik memiliki karakteristik, yaitu:
- median dari price banyak terdistribusi pada rentang price, namun nilai terbanyak terdapat pada nilai 2000.
- rata-rata terbanyak untuk data ratings dan camera yaitu di antara angka 40-200 
- ram dan storage terbanyak masing-masing berada di antara angka 60 dan 200. Distribusi Price miring ke kanan (right-skewed). Hal ini akan berimplikasi pada model.

![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/4105ba7f-eb8f-4149-b6c4-8f3b7d6b8c73)
![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/ecfbd442-bca3-40ce-9481-400470cd9f7d)

Dengan mengamati rata-rata 'price' relatif terhadap fitur kategori di atas, diperoleh insight sebagai berikut:

Pada fitur 'display', rata-rata 'price' cenderung bervariasi. Rentangnya berada antara 14000 hingga 25000. Nilai 'price' tertinggi berada pada nilai 'display' yaitu 'HD+AMOLED' dan nilai 'price' terendah berada pada nilai 'display' yaitu 'LCD'. Sehingga, fitur 'display' memiliki pengaruh yang signifikan terhadap rata-rata 'Price'. Kesimpulan akhir, fitur kategori memiliki pengaruh terhadap 'Price'.

![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/220dcd8c-cc2e-4f0d-aae2-476ebe6acf2b)
Fungsi pairplot dari library seaborn menunjukkan relasi pasangan dalam dataset. Dari grafik, terlihat plot relasi masing-masing fitur numerik pada dataset. Pada pola sebaran data grafik pairplot sebelumnya, terlihat bahwa 'ram' memiliki korelasi dengan fitur 'price'. Sedangkan kedua fitur lainnya terlihat memiliki korelasi yang lemah karena sebarannya tidak membentuk pola

Koefisien korelasi berkisar antara -1 dan +1. Ia mengukur kekuatan hubungan antara dua variabel serta arahnya (positif atau negatif). Mengenai kekuatan hubungan antar variabel, semakin dekat nilainya ke 1 atau -1, korelasinya semakin kuat. Sedangkan, semakin dekat nilainya ke 0, korelasinya semakin lemah

![image](https://github.com/khundari/RBL-Sains-Data/assets/164993658/9c9ac052-b76f-4595-919f-f3c49b9b5f22)
Jika diamati, fitur 'ram' memiliki skor korelasi yang cukup besar (0.61) dengan fitur target 'price'. Artinya, fitur 'price' berkorelasi cukup tinggi dengan keempat fitur tersebut. Sementara itu, fitur lainnya memiliki korelasi negatif sehingga, fitur tersebut dapat di-drop.

# Data Preparation 
Data Peparation merupakan tahapan penting dalam proses pengembangan model machine learning. Pada tahap ini lakukan proses transformasi pada data sehingga menjadi bentuk yang cocok untuk proses pemodelan. Ada beberapa tahapan yang umum dilakukan pada data preparation, antara lain, seleksi fitur, transformasi data, feature engineering, dan dimensionality reduction.
Pada bagian ini lakukan empat tahap persiapan data, yaitu:
Encoding fitur kategori. Reduksi dimensi dengan Principal Component Analysis (PCA). Pembagian dataset dengan fungsi train_test_split dari library sklearn. Standarisasi.
Pada proses Data Preparation dilakukan kegiatan seperti Data Gathering, Data Assessing, dan Data Cleaning. Pada proses Data Gathering, data diimpor sedemikian rupa agar bisa dibaca dengan baik menggunakan dataframe Pandas. Untuk proses Data Assessing, berikut adalah beberapa pengecekan yang dilakukan:
- Duplicate data (data yang serupa dengan data lainnya)
- Missing value (data atau informasi yang "hilang")
- Outlier (data yang menyimpang dari rata-rata sekumpulan data )
Pada proses Data Cleaning, secara garis besar, terdapat tiga metode yang dapat digunakan antara lain seperti berikut:
- Dropping (metode yang dilakukan dengan cara menghapus sejumlah baris data)
- Imputation (metode yang dilakukan dengan cara mengganti nilai yang "hilang" atau tidak tersedia dengan nilai tertentu yang bisa berupa median atau mean dari data)
- Interpolation (metode menghasilkan titik-titik data baru dalam suatu jangkauan dari suatu data)

Pada kasus proyek ini tidak terdapat data duplikat dan tidak ditemukan Missing Value. Untuk outlier sendiri dilakukan metode dropping menggunakan metode IQR. IQR sendiri didapatkan dengan cara mengurangi Q3 dengan Q1 sebagaimana rumusan berikut.
![image](https://github.com/khundari/RBL-Sains-Data/assets/162407298/6856196a-a6d9-4f76-8497-26a6d30c687d)
dimana Q1 adalah kuartil pertama dan Q3 adalah kuartil ketiga.
Dengan menggunakan metode IQR, dapat ditentukan outlier melalui suatu nilai batas yang ditentukan. Setelah menggunakan metode IQR dimana dataset yang sebelumnya berjumlah 407 menjadi 5 row x 27 columns.

pca.explained_variance_ratio_.round(3)

Potongan kode tersebut memberikan keluaran berupa array([1., 0])
Dari output di atas 100% informasi pada satu fitur 'storage'terdapat pada PC pertama. Sedangkan sisanya, sebesar 0% terdapat pada PC kedua.

Berdasarkan hasil ini, reduksi fitur (dimensi) dan hanya mempertahankan PC (komponen) pertama saja. PC pertama ini akan menjadi fitur 'phone properties' menggantikan ketiga fitur lainnya ('storage', 'ram'). Beri nama fitur ini 'phone properties'

# Modeling 
Seperti yang dijelaskan di awal, model yang dipilih adalah model regresi karena merupakan salah satu algoritma yang paling umum digunakan dalam pembuatan model prediksi. Dalam bentuk yang sederhana, regresi terdiri dari intersep dan slope yang dituliskan dalam rumusan berikut

![image](https://github.com/khundari/RBL-Sains-Data/assets/162407298/0adbe59d-61ea-4833-a36e-a2bda5041249)

dimana:

- y adalah variabel kriterium (variabel terikat yang digunakan untuk memprediksi)
- a adalah intersep (variabel konstan yang memiliki arti sebagai titik perpotongan suatu garis dengan sumbu Y),
- b adalah slope (nilai koefisien yang menyatakan ukuran kemiringan suatu garis), dan
- X adalah variabel prediktor (variabel yang digunakan untuk memprediksi atau menjelaskan variabel lain dalam suatu model)

Secara umum, regresi ini itu sendiri digunakan untuk meramalkan pengaruh variabel prediktor terhadap variabel kriterium atau membuktikan ada atau tidaknya hubungan fungsional antara variabel bebas (X) dengan variabel terikat (y).

Namun begitu terdapat kelebihan dan kekurangan dari model regresi, yaitu:

Kelebihan regresi:

Kemudahan untuk digunakan
Kekuatan Prediktor dalam mengidentifikasi sekuat apa pengaruh yang diberikan oleh variabel prediktor (variabel independen) terhadap variabel lainnya (variabel dependen).
Dapat memprediksi nilai/tren di masa yang mendatang
Kelemahan dari model regresi adalah karena hasil ramalan dari analisis regresi merupakan nilai estimasi sehingga kemungkinan untuk tidak sesuai dengan data aktual tetaplah ada.

Pada proyek yang dikerjakan, algoritma regresi yang coba dibandingkan adalah regresi linear, regresi ridge, random forest regressor, dan random forest regressor dengan hyperparamter tuning. Regresi linear adalah teknik analisis data yang memprediksi nilai data yang tidak diketahui dengan menggunakan nilai data lain yang terkait dan diketahui dimana secara matematis dimodelkan sebagai persamaan linier, regresi ridge merupakan metode estimasi koefisien regresi yang diperoleh melalui penambahan konstanta bias c, dan random forest adalah suatu algoritma yang digunakan pada klasifikasi data dalam jumlah yang besar dimana teknik klasifikasi random forest dilakukan melalui penggabungan pohon dengan melakukan training pada sampel data yang dimiliki.

Untuk meningkatkan model, dilakukan hyperparamter tuning. Adapun paramater yang di-tuning antara lain n_estimators', 'max_depth', 'min_samples_split', dan 'min_samples_leaf. Untuk memudahkan proses tuning digunakan GridSearchCV. GridSearchCV itu sendiri merupakan bagian dari modul scikit-learn yang dapat digunakan untuk mendapatkan nilai hyperparameter secara otomatis. Grid Search adalah metode yang digunakan untuk mencari parameter yang paling tepat untuk meningkatkan performa model dengan mencoba seluruh kombinasi hyperparameter yang diberikan.

Berikut adalah nilai parameter tuning

params = {'n_estimators' : [50,80,100],
          'max_depth' : [3,5,10],
           'min_samples_split':[2,3,4],
            'min_samples_leaf': [2,3,4]}

Berdasarkan hasil pengujian, terpilih grid.best_params_yaitu

{'max_depth': 10,
 'min_samples_leaf': 4,
 'min_samples_split': 2,
 'n_estimators': 100}

 Parameter dengan nilai inilah yang kemudian dibuat sebagai model.

 # Evaluation 
 Adapun metrik yang sebagai alat ukur perfoma model yang dibuat antara lain MSE · MAE · R2.

Berikut merupakan rumus dari masing-masing metrik yang digunakan:
![image](https://github.com/khundari/RBL-Sains-Data/assets/162407298/7dfb236e-81b5-4626-b176-2376b9b03af6)
yi mewakili nilai yang diamati, ŷi mewakili nilai prediksi, n adalah jumlah titik data, Var(y) mewakili varians dari nilai yang diamati.

Berikut merupakan penjelasan kegunaan dari masing-masing metrik yang digunakan:

- MAE menghitung rata-rata dari selisih absolut antara nilai prediksi dan nilai aktual. Semakin kecil nilai MAE, semakin baik kualitas model tersebut.
- MSE menghitung rata-rata dari selisih kuadrat antara nilai prediksi dan nilai aktual. Semakin kecil nilai MSE, semakin baik kualitas model tersebut.
- R2 digunakan untuk menilai seberapa besar pengaruh variabel independen tertentu terhadap variabel dependen
![image](https://github.com/khundari/RBL-Sains-Data/assets/162407298/cfca46ca-26fa-4539-9d88-cff4592a09c3)
Berdasarkan Matriks diatas, secara umum Model 4 (RF2) menampilkan hasil performa yang lebih baik dimana memiliki nilai R^2 yaitu sebesar  0.09195059382785553 .
Secara lebih jauh perbandingan Model 1, 2, 3, dan 4 bisa dilihat pada Gambar berikut.
![image](https://github.com/khundari/RBL-Sains-Data/assets/162407298/aa917cf3-c9aa-4cc6-8da2-5e2b128cb611)

Berdasarkan gambar disamping terlihat bahwa error train dan test dari model 4 (RF2) jauh lebih baik dibandingkan model lalinnya

![image](https://github.com/khundari/RBL-Sains-Data/assets/162407298/a977ddbb-a485-4fd0-9834-c47cbae737e7)

Terlihat bahwa prediksi dengan Random Forest (RF), baik RF1 ataupun RF2 memberikan hasil yang paling mendekati y_true.

# Referensi 
[1]  Aqsho Ramadhan, Y., Faqih, A. and Dwilestari, G. (2023) ‘Prediksi penjualan handphone di toko X Menggunakan Algoritma regresi linear’, Jurnal Informatika Terpadu, 9(1), pp. 40–44. doi:10.54914/jit.v9i1.692. 
[2]  Pramesti, D. and Wiga Maulana Baihaqi (2023) ‘Perbandingan prediksi Jumlah Transaksi Ojek online menggunakan Regresi Linier dan random forest’, Generation Journal, 7(3), pp. 21–30. doi:10.29407/gj.v7i3.20676. 
[3]  Fitri, E. (2023) ‘Analisis Perbandingan metode regresi Linier, random forest regression dan gradient boosted trees regression method untuk prediksi Harga Rumah’, Journal of Applied Computer Science and Technology, 4(1), pp. 58–64. doi:10.52158/jacost.v4i1.491. 
[4]  Prof. Rupali et al. (2023) ‘Stock market price prediction by LSTM & linear regression algorithm using machine learning’, International Journal For Multidisciplinary Research, 5(2). doi:10.36948/ijfmr.2023.v05i02.2152. 
