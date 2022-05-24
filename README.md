# Tugas-Akhir Praktikum Pemodelan Oseanografi Kelompok 17 
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Pemodelan Oseanografi 2022. Repositori ini memuat executable (.exe) file yang dapat memproses beberapa persamaan metode numerik untuk penyelesaian perhitungan numerik. Pengerjaan untuk repositori kali ini menggunakan bahasa pemrograman python yang dapat dilakukan pada beberapa platform seperti Google Colaboratory dan Jupyter Notebook. Sedangkan untuk library yang digunakan kali ini adalah Numpy, Matplotlib, IPython, Scipy, dan Pprint. Seluruh script yang dibuat adalah hasil kelompok 17 Oseanografi 2020. Semoga dapat bermanfaat!
# Authors (Kelompok 17)
1. Achmad Suva Fauzan     (26050120130049)
2. Ahmad Fauzi            (26050120140130)
3. Cheril Fadhia Azarine  (26050120140149)
4. Juwita Novianti        (26050120130101)
5. Nanda Marissa          (26050120140068)
6. Rio Prasetyo Marpaung  (26050120140047)
7. Syah Malfin Nazir      (26050120140129)
# Definisi Pemodelan Oseanografi 
Secara umum, model merupakan suatu tiruan dari benda ataupun objek yang akan dikembangkan dari sifat atau karakteristik objek sebelumnya. Pemodelan merupakan suatu langkah peniruan fenomena yang ada di alam. Pemodelan oseanografi sendiri merupakan suatu sistem untuk mempelajari suatu fenomena oseanografi (dinamika laut) ke dalam persamaan matematis dengan model numerik. Model numerik ini dapat menjelaskan kondisi pasang surut, arus, gelombang serta kondisi hidrodinamika di laut.
# Modul 1 = Persamaan Adveksi - Difusi 1D
Adveksi adalah pengangkutan materi dalam fluida, yaitu dengan air atau aliran udara, dimana kontaminan akan bergerak dengan cairan fluida pengangkutnya.
Digunakan 2 pendekatan secara numerik yaitu implisit dan eksplisit 

Persamaan dasar adveksi 1D 

![image](https://user-images.githubusercontent.com/105927079/169700996-e7aff633-64e7-4467-8a10-4b43c72caf89.png)

Persamaan tersebut dapat dibaca sebagai perubahan konsentrasi terhadap waktu dipengaruhi oleh kecepatan aliran fluida serta perubahan konsentrasi terhadap ruang 

Diskritisasi 1 D dengan metode upstream proses Adveksi

![image](https://user-images.githubusercontent.com/105935057/169765715-6f77ac0e-9628-4558-8012-8ed86fe539c7.png)

Terdapat berbagai macam metode penyelesaian dari persamaan adveksi, diantaranya yaitu FTCS, Leapfrog, dan Upstream

1. Metode FTCS (_Forward Time Center Space_) merupakan metode gabungan dari beberapa pendekatan beda hingga yaitu selisih maju terhadap waktu dan selisih pusat terhadap ruang. Solusi ini memiliki syarat kestabilan, yaitu

![image](https://user-images.githubusercontent.com/105927079/169706818-65ad54dd-6a60-4a41-bbe9-3928a7c0c77f.png)

2. Leapfrog/CTCS (_Center Time Center Space_) merupakan perluasan metode beda tengah terhadap ruang dan waktu. Skema metode ini didapatkan dari hasil turunan deret taylor dan termasuk skema yang konsisten jika C ≤ 1
3. Upstream (_Forward Time, Forward/Back Space_) merupakan penyempurna metode leapfrog yang dibuat untuk model positif. Metode ini menggunakan turunan beda maju untuk grid waktu dan untuk grid ruang bergantung pada arah kecepatan U. U > 0, turunan ruang dengan beda mundur ; U < 0, digunakan pendekatan beda maju untuk turunan ruang 

Difusi merupakan proses transport pasif. Di dalam proses difusi partikel zat akan bergerak dari daerah berkonsentrasi tinggi ke daerah dengan konsentrasi lebih rendah sehingga akan menghasilkan konsentrasi yang sama di dalam zat tersebut. Faktor-faktor yang mempengaruhi kecepatan difusi yaitu ukuran partikel, ketebalan membran, luas area, jarak dan suhu.

Persamaan dasar Difusi 1D

![image](https://user-images.githubusercontent.com/105927079/169743687-09aee6f4-223a-44bb-aad5-6e94b5a20d5f.png)

Diskritisasi 1 D proses Difusi

![image](https://user-images.githubusercontent.com/105935057/169765892-aea31ee7-adca-4bd0-b4cc-f74f3b308e54.png)

Dari diskritisasi 1D persamaan Adveksi dan Difusi, maka kita dapatkan persamaan adveksi-difusi 1D, dengan memisal kan

![image](https://user-images.githubusercontent.com/105935057/169766446-9e071f10-d0c3-451a-8cf7-db777edb3fcd.png)

Persamaan tersebut menjadi:

![image](https://user-images.githubusercontent.com/105935057/169766741-18efba59-66dd-48dc-ad8b-8aae2dadac4f.png)

Jika kita menerapkan metode beda maju untuk waktu, upstream untuk adveksi, dan beda tengah untuk difusi, maka persamaannya menjadi:

![image](https://user-images.githubusercontent.com/105935057/169766811-57f1e6ba-00ad-4fdf-b1ba-2a5daa088acb.png)

Dengan syarat kestabilan yang harus dipenuhi:

![image](https://user-images.githubusercontent.com/105935057/169767914-3c28cc77-6c48-4b6c-9ba0-3e3b33dad8bd.png)

Penerapan Adveksi-Difusi 1D di dalam bidang Oseaografi :

- Mengetahui konsentrasi dan penyebaran polutan di sungai, parit, dan cabang sungai

- Pemodelan polutan

- Konservasi lingkungan

# Modul 2 = Persamaan Adveksi - Difusi 2D
Adveksi merupakan mekanisme perpindahan massa suatu materi dari satu titik ke titik lainnya. 
Persamaan adveksi merupakan bentuk khusus dari persamaan diferensial parsial untuk hukum kekekalan.

Berikut merupakan persamaan Adveksi :

![adveksi](https://user-images.githubusercontent.com/105926904/169690594-614805b3-3ba2-48db-bf08-d8e3e4cb6b94.png)


Difusi merupakan mekanisme penyebaran konsentrasi akibat adanya kecepatan aliran dan perbedaan konsentrasi

Berikut merupakan persamaan Difusi :

![difusi](https://user-images.githubusercontent.com/105926904/169690723-3a60b557-3bd4-4a33-a461-fabc98cb716c.png)

![umum](https://user-images.githubusercontent.com/105926904/169799610-72cb2f86-3790-49e9-8cd8-a67cf355068e.png)

Persamaan di atas merupakan persamaan umum yang dapat menggambarkan proses adveksi-difusi pada suatu materi sehingga membentuk persamaan model 2D yang akan mendekati proses kejadian di alam. 

Metode Eksplisit pada model adveksi, persamaan beda hingga menggunakan pendekatan beda maju untuk turunan waktu, sedangkan turunan ruang dilakukan dengan melihat arah kecepatan. Jika u>0, pendekatan beda mundur. Jika u<0, pendekatan beda maju.

Diskritasi suku adveksi 2 dimensi:
![image](https://user-images.githubusercontent.com/105926880/169685498-648a30f8-7f0d-479a-b126-342e9fe76769.png)

Diskritasi suku difusi 2 dimensi:
![image](https://user-images.githubusercontent.com/105926880/169685716-eb077b84-10c1-4d48-8174-5a24a9148cd4.png)

Penerapan dalam bidang Oseanografi:

- Menghitung dan memodelkan persebaran nutrient di laut atau sungai

- Menghitung dan memodelkan persebaran polutan dari proses industri

- Mengetahui persebaran polutan dari laguna dengan menghitung input dan outputnya 

- Mengetahui sebaran kebocoran minyak di laut

# Modul 3 = Persamaan Hidrodinamika 1D
Hidrodinamika adalah 
# Modul 4 = Persamaan Hidrodinamika 2D

Perbedaan Antara 1 Dimensi dan 2 Dimensi

1 Dimensi :
- Penampang (cross section) tegak lurus terhadap aliran sungai
- Ketinggian air (water level) sama di seluruh penampang
- Kecepatan sama di seluruh penampang
- Lebih cocok untuk gradien yang rendah (tidak ada kemiringan)
- Digunakan untuk meneliti kadar kimia berdasarkan kedalaman atau luasannya

2 Dimensi :
- Kecepatan arus dan gelombang berbeda-beda
- Daerah yang direpresentasikan adalah x dan y
- Lebih cocok diterapkan pada kemiringan yang curam
- Kedalaman air tidak sama
- Digunakan  untuk meneliti kadar zat kimia berdasarkan kedalaman dan luasan di daerah penelitian

Konsep Model Hidrodinamika 2D

- Adanya 2 (dua) parameter yang dipakai atau di cari seperti pergerakan arus dan pengaruhnya (contoh: pergerakan sedimen)
- Anomali, dimana anomali ini dapat mengganggu hasil pemodelan. Dalam pemodelan gelombang, anomali ini dapat ditunjukkan seperti adanya badai yag dapat mempengaruhi angin pada perairan tersebut.

Penerapan di Bidang Oseanografi

- Pemodelan gelombang karena angin
- Pemodelan sampah plastik di laut
- Pemodelan coastal dynamics dan sedimentasi pantai

Secara umum, persamaan ini merupakan salah satu persamaan yang sering digunakan dalam penelitian oseanografi. Hal ini disebabkan persamaan ini mendekati bentuk asli dari fenomena yang ada di alam
