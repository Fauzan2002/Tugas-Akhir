# Tugas-Akhir
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Pemodelan Oseanografi 2022. Repositori ini memuat executable (.exe) file yang dapat memproses beberapa persamaan metode numerik untuk penyelesaian perhitungan numerik. Pengerjaan untuk repositori kali ini menggunakan bahasa pemrograman python yang dapat dilakukan pada beberapa platform seperti Google Colaboratory dan Jupyter Notebook. Sedangkan untuk library yang digunakan kali ini adalah Numpy, Matplotlib, IPython, Scipy, dan Pprint. Seluruh script yang dibuat adalah hasil kelompok 17 Oseanografi 2020. Semoga dapat bermanfaat!
# Definisi Pemodelan Oseanografi 
Secara umum, model merupakan suatu tiruan dari benda ataupun objek yang akan dikembangkan dari sifat atau karakteristik objek sebelumnya. Pemodelan merupakan suatu langkah peniruan fenomena yang ada di alam. Pemodelan oseanografi sendiri merupakan suatu sistem untuk mempelajari suatu fenomena oseanografi (dinamika laut) ke dalam persamaan matematis dengan model numerik. Model numerik ini dapat menjelaskan kondisi pasang surut, arus, gelombangserta kondisi hidrodinamika di laut.
# Modul 1 = Persamaan Adveksi - Difusi 1D
# Modul 2 = Persamaan Adveksi - Difusi 2D
Adveksi merupakan mekanisme perpindahan massa suatu materi dari satu titik ke titik lainnya. 
Persamaan adveksi merupakan bentuk khusus dari persamaan diferensial parsial untuk hukum kekekalan.

![adveksi](https://user-images.githubusercontent.com/105926904/169690594-614805b3-3ba2-48db-bf08-d8e3e4cb6b94.png)


Difusi merupakan mekanisme penyebaran konsentrasi akibat adanya kecepatan aliran dan perbedaan konsentrasi

∂F/∂t= A_d  (∂^2 F)/(∂x^2 )+A_d  (∂^2 F)/(∂y^2)

∂F/∂t= -u ∂F/∂x-v ∂F/∂x 	∂F/∂t= A_d  (∂^2 F)/(∂x^2 )+A_d  (∂^2 F)/(∂y^2)

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
# Modul 4 = Persamaan Hidrodinamika 2D
Secara umum, persamaan ini merupakan salah satu persamaan yang sering digunakan dalam penelitian oseanografi. Hal ini disebabkan persamaan ini mendekati bentuk asli dari fenomena yang ada di alam
