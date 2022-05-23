# Tugas-Akhir
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Pemodelan Oseanografi 2022. Repositori ini memuat executable (.exe) file yang dapat memproses beberapa persamaan metode numerik untuk penyelesaian perhitungan numerik. Pengerjaan untuk repositori kali ini menggunakan bahasa pemrograman python yang dapat dilakukan pada beberapa platform seperti Google Colaboratory dan Jupyter Notebook. Sedangkan untuk library yang digunakan kali ini adalah Numpy, Matplotlib, IPython, Scipy, dan Pprint. Seluruh script yang dibuat adalah hasil kelompok 17 Oseanografi 2020. Semoga dapat bermanfaat!
# Definisi Pemodelan Oseanografi 
Secara umum, model merupakan suatu tiruan dari benda ataupun objek yang akan dikembangkan dari sifat atau karakteristik objek sebelumnya. Pemodelan merupakan suatu langkah peniruan fenomena yang ada di alam. Pemodelan oseanografi sendiri merupakan suatu sistem untuk mempelajari suatu fenomena oseanografi (dinamika laut) ke dalam persamaan matematis dengan model numerik. Model numerik ini dapat menjelaskan kondisi pasang surut, arus, gelombangserta kondisi hidrodinamika di laut.
# Modul 1 = Persamaan Adveksi - Difusi 1D
Adveksi adalah pengangkutan materi dalam fluida, yaitu dengan air atau aliran udara, dimana kontaminan akan bergerak dengan cairan fluida pengangkutnya.
Digunakan 2 pendekatan secara numerik yaitu implisit dan eksplisit 

Persamaan dasar adveksi 1D 

![image](https://user-images.githubusercontent.com/105927079/169700996-e7aff633-64e7-4467-8a10-4b43c72caf89.png)

Persamaan tersebut dapat dibaca sebagai perubahan konsentrasi terhadap waktu dipengaruhi oleh kecepatan aliran fluida serta perubahan konsentrasi terhadap ruang 

Terdapat berbagai macam metode penyelesaian dari persamaan adveksi, diantaranya yaitu FTCS, Leapfrog, dan Upstream

1. Metode FTCS (_Forward Time Center Space_) merupakan metode gabungan dari beberapa pendekatan beda hingga yaitu selisih maju terhadap waktu dan selisih pusat terhadap ruang. Solusi ini memiliki syarat kestabilan, yaitu ![image](https://user-images.githubusercontent.com/105927079/169706818-65ad54dd-6a60-4a41-bbe9-3928a7c0c77f.png)
2. Leapfrog/CTCS (_Center Time Center Space_) merupakan perluasan metode beda tengah terhadap ruang dan waktu. Skema metode ini didapatkan dari hasil turunan deret taylor dan termasuk skema yang konsisten jika C ≤ 1
3. Upstream (_Forward Time, Forward/Back Space_) merupakan penyempurna metode leapfrog yang dibuat untuk model positif. Metode ini menggunakan turunan beda maju untuk grid waktu dan untuk grid ruang bergantung pada arah kecepatan U. U > 0, turunan ruang dengan beda mundur ; U < 0, digunakan pendekatan beda maju untuk turunan ruang 

Difusi merupakan proses transport pasif. Di dalam proses difusi partikel zat akan bergerak dari daerah berkonsentrasi tinggi ke daerah dengan konsentrasi lebih rendah sehingga akan menghasilkan konsentrasi yang sama di dalam zat tersebut. 

Persamaan dasar difusi 1D
![image](https://user-images.githubusercontent.com/105927079/169743687-09aee6f4-223a-44bb-aad5-6e94b5a20d5f.png)


# Modul 2 = Persamaan Adveksi - Difusi 2D
Adveksi merupakan mekanisme perpindahan massa suatu materi dari satu titik ke titik lainnya. 
Persamaan adveksi merupakan bentuk khusus dari persamaan diferensial parsial untuk hukum kekekalan.

![adveksi](https://user-images.githubusercontent.com/105926904/169690594-614805b3-3ba2-48db-bf08-d8e3e4cb6b94.png)


Difusi merupakan mekanisme penyebaran konsentrasi akibat adanya kecepatan aliran dan perbedaan konsentrasi

![difusi](https://user-images.githubusercontent.com/105926904/169690723-3a60b557-3bd4-4a33-a461-fabc98cb716c.png)

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
