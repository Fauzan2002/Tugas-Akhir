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
Secara umum, model merupakan suatu tiruan dari benda ataupun objek yang akan dikembangkan dari sifat atau karakteristik objek sebelumnya. Pemodelan merupakan suatu langkah peniruan fenomena yang ada di alam. Pemodelan oseanografi sendiri merupakan suatu sistem untuk mempelajari suatu fenomena oseanografi (dinamika laut) ke dalam persamaan matematis dengan model numerik. Model numerik ini dapat menjelaskan kondisi pasang surut, arus, gelombang serta kondisi hidrodinamika di laut. Praktikum kali ini akan membahas mengenai empat persamaan yang familiar digunakan dalam pemodelan, yaitu persamaan adveksi difusi 1D dan 2D, serta persamaan hidrodinamika 1D dan 2D. Keempat persamaan ini akan menjadi dasar dari pemodelan hidroseanografi yang dipakai dalam berbagai penelitian.
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
Hidrodinamika merupakan cabang ilmu yang mempelajari tentang fenomena yang terjadi pada fluida, dimana fluida dianggap tidak termampatkan (incompressible) dan tidak memiliki viskositas atau dapat diabaikan. Dalam ilmu hidrodinamika, terdapat setidaknya 3 pemodelan yang digunakan dalam berbagai bidang yaitu Model Hidrodinamika 1-Dimensi, 2-Dimensi, dan 3-Dimensi. Pada modoul ini, pemodelan hidrodinamika yang digunakan adalah model hidrodinamika 1-Dimensi yang merupakan model paling sederhana dengan arah tinjauan satu sumbu saja; sumbu x atau sumbu y.

Model hidrodinamika dalam air laut dapat digunakan untuk mengkaji disipasi panas di laut, sebaran radionulkir, pengkajian klimatologi laut atau sekadar hubungan antara elevasi muka air laut dengan salah satu faktor oseanografi suatu perairan. Model hidrodinamika sendiri dibangun berdasarkan dua konsep utama yaitu Hukum Momentum dan Konservasi Massa. Untuk menghasilkan suatu "produk" dari model hidrodinamika 1D (seperti grafik, simulasi perubahan arus yang ditinjau, penyelesaian perhitungan dsb), memerlukan script pemodelan. Salah satu contoh script yang dilakukan untuk mengetahui korelasi antara elevasi muka air laut dan kecepatan arus terhadap ruang dan waktu dengan bahasa pemrograman Phyton adalah sebagai berikut: 

**Library Pemrograman**

`import matplotlib.pyplot as plt` (digunakan untuk menampilkan visualisai hasil code)

`import numpy as np` (digunakan untuk perhitungan)

**Input Nilai Parameter yang Dibutuhkan**

```
Proses Awal
p = 5000 #Panjang Grid
T = 1200 #Waktu Simulasi
A = 0.5 #Amplitudo
D = 15 #Depth/Kedalaman
dt = 2
dx = 100
To = 300 #Periode

Pameter Lanjutan
g = 9.8
pi = np.pi 
C = np.sqrt(g*D) #Kecepatan Arus
s = 2*pi/To #Kecepatan Sudut Gelombang
L = C*To #Panjang Gelombang
k = 2*pi/L #Koefisien Panjang Gelombang
Mmax = int(p//dx)
Nmax = int(T//dt)
```

**Persamaan Hidrodinamika 1D**

```
zo = [None for _ in range(Mmax)]
uo = [None for _ in range(Mmax)]

hasilu = [None for _ in range(Nmax)]
hasilz = [None for _ in range(Nmax)]
```
**Perintah Looping untuk Menyelesaikan Nilai uo dan zo**

```
for i in range(1, Mmax+1):
  zo[i-1] = A*np.cos(k*(i)*dx)
  uo[i-1] = A*C*np.cos(k*((i)*dx+(0.5)*dx))/(D+zo[i-1])
for i in range(1, Nmax+1):
  zb = [None for _ in range(Mmax)]
  ub = [None for _ in range(Mmax)]
  zb[0] = A*np.cos(s*(i)*dt)
  ub[-1] = A*C*np.cos(k*L-s*(i)*dt)/(D+zo[-1])
  for j in range (1, Mmax):
    ub[j-1] = uo[j-1]-g*(dt/dx)*(zo[j]-zo[j-1])
  for k in range(2, Mmax+1):
    zb[k-1] = zo[k-1]-(D+zo[k-1])*(dt/dx)*(ub[k-1]-ub[k-2])
    hasilu[i-1] = ub
    hasilz[i-1] = zb
  for p in range(0, Mmax):
    uo[p] = ub[p]
    zo[p] = zb[p]
```

**Pembuatan Grafik**

Digunakan fungsi def untuk menggabungkan perintah perhitungan

```
def rand_col_hex_string():
  return f'#{format(np.random.randint(0,16777215), "#08x")[2:]}'
  
hasilu_np = np.array(hasilu)
hasilz_np = np.array(hasilz)

fig0, ax0 = plt.subplots(figsize=(12,8))
for i in range (1, 16):
  col0 = rand_col_hex_string()
  line, = ax0.plot(hasilu_np[:,i-1], c=col0, label=f'n={i}')
  ax0.legend()

  ax0.set(xlabel='Waktu', ylabel='Kecepatan Arus', title='''Nama_NIM
  Perubahan Kecepatan Arus Dalam Grid Tertentu di Sepanjang Waktu''')
  ax0.grid()

fig1, ax1 = plt.subplots(figsize=(12,8))
for i in range(1, 16):
  col1= rand_col_hex_string()
  line, = ax1.plot(hasilz_np[:,i-1], c=col1, label=f'n={i}')
  ax1.legend()

  ax1.set(xlabel='Waktu', ylabel='Elevasi Muka Air', 
          title='''Nama_NIM
          Perubahan Elevasi Permukaan Air Dalam Grid Tertentu di Sepanjang Waktu''')
  ax1.grid()

fig2, ax2 = plt.subplots(figsize=(12,8))
for i in range(1, 16):
  col2= rand_col_hex_string()
  line, = ax2.plot(hasilu_np[i-1], c=col2, label=f't={i}')
  ax2.legend()

  ax2.set(xlabel='Grid', ylabel='Kecepatan Arus', 
          title='''Nama_NIM
          Perubahan Kecepatan Arus Dalam Grid Tertentu di Sepanjang Waktu''')
  ax2.grid()

fig3, ax3 = plt.subplots(figsize=(12,8))
for i in range(1, 16):
  col3= rand_col_hex_string()
  line, = ax3.plot(hasilz_np[i-1], c=col3, label=f't={i}')
  ax3.legend()

  ax3.set(xlabel='Grid', ylabel='Kecepatan Arus', 
          title='''Nama_NIM
          Perubahan Kecepatan Arus Dalam Grid Tertentu di Sepanjang Waktu''')
  ax3.grid()
```

**Perintah untuk Menampilkan Hasil Grafik**

```
plt.show()
```

**Contoh Hasil Grafik**

<img width="421" alt="image" src="https://user-images.githubusercontent.com/105927357/169933049-d4016852-3f10-4fd0-a21c-4fe1182eb2e2.png">

<img width="426" alt="image" src="https://user-images.githubusercontent.com/105927357/169933089-a10b7a70-6e33-4a41-9ab1-ce60765f641f.png">

<img width="425" alt="image" src="https://user-images.githubusercontent.com/105927357/169933105-a79598dd-abe4-416c-beaa-875c47f9c80c.png">

<img width="430" alt="image" src="https://user-images.githubusercontent.com/105927357/169933118-d413d0d0-e3ce-47ca-be2b-2e3c717d2592.png">

**Penjelasan Grafik**

Keempat grafik pemodelan membentuk pola grafik yang sama yaitu sinusoidal. Interval grid yang digunakan adalah 0-50 sementara interval waktu yang digunakan adalah 0-600. Grafik yang tidak beraturan terbentuk seiring rentang waktu bertambah dan kecepatan arus meningkat. Dari sini dapat diketahui bahwa semakin besar nilai kecepatan arus, maka grafik akan semakin tidak beraturan sebab semakin sulit untuk menangkap data lapangan. Nilai kecepatan arus yang sudah memiliki referensi nilai dari waktu sebelumnya juga menjelaskan mengapa grafik yang dihasilkan lebih kompleks. Selain itu, saat grid bertambah, kecepatan awal arus akan berkurang secara eksponensial. Hal ini sama dengan teori gelombang amplitudo kecil yaitu komponen kecepatan akan berkurang dengan bertambahnya jarak ke bawah dihitung dari muka air.Pola grafik beraturan hanya terjadi pada waktu dan grid di awal saja, selanjutnya mulai tidak beraturan sebab nilai kecepatan arus kian meningkat sehingga semakin sulit untuk menangkap data karena gangguan yang muncul juga turut meningkat.


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

- Adanya 2 (dua) parameter yang dipakai atau dicari seperti pergerakan arus dan pengaruhnya (contoh: pergerakan sedimen). Parameter ini biasanya akan ditemukan dalam berbagai website pemerintah atau bisa berasal dari penelitian lapangan yang kita lakukan
- Anomali, dimana anomali ini dapat mengganggu hasil pemodelan. Dalam pemodelan gelombang, anomali ini dapat ditunjukkan seperti adanya badai yang dapat mempengaruhi angin pada perairan tersebut. Anomali ini juga akan menentukan korelasi atau hubungan antar parameter tersebut, apakah positif atau negatif

Penerapan di Bidang Oseanografi

- Pemodelan gelombang karena angin
- Pemodelan sampah plastik di laut
- Pemodelan coastal dynamics dan sedimentasi pantai

Secara umum, persamaan ini merupakan salah satu persamaan yang sering digunakan dalam penelitian oseanografi. Hal ini disebabkan persamaan ini mendekati bentuk asli dari fenomena yang ada di alam. Dan persamaan ini merupakan persamaan yang yang menjadi dasar dalam aplikasi pemodelan, semisal Delft 3D dan MIKE 21. Contoh dalam penggunaan script pada modeling hodrodinamika 2 dimensi ini adalah sebagai berikut:
Copyright (c) 2018 Siphon Contributors.
# Distributed under the terms of the BSD 3-Clause License.
# SPDX-License-Identifier: BSD-3-Clause
"""
NDBC Bouy Meteorological Data Request
=====================================
The NDBC keeps a 45-day recent rolling file for each bouy. This examples shows how to access
the basic meteorogical data from a buoy and make a simple plot.
"""

import matplotlib.pyplot as plt

from siphon.simplewebservice.ndbc import NDBC

####################################################
# Get a pandas data frame of all of the observations, meteorogical data is the default
# observation set to query
df = NDBC.realtime_observations('46036') #Station ID
df.head()

##############################################
# Let's make a simple times series plot to checkout what the data look like.
fig, (ax1, ax2, ax3) = plt.subplots(3, 1, figsize=(12, 10))
ax2b = ax2.twinx()

# Pressure
ax1.plot(df['time'], df['pressure'], color='black')
ax1.set_ylabel('Pressure [hPa]')
fig.suptitle('Syah Malfin Nazir_26050120140129_B', fontsize=18)


# Wind Speed, gust, direction
ax2.plot(df['time'], df['wind_speed'], color='tab:orange')
ax2.plot(df['time'], df['wind_gust'], color='tab:olive', linestyle='--')
ax2b.plot(df['time'], df['wind_direction'], color='tab:blue', linestyle='-')
ax2.set_ylabel('Wind Speed [m/s]')
ax2b.set_ylabel('Wind Direction')


# Water temperature
ax3.plot(df['time'], df['water_temperature'], color='tab:brown')
ax3.set_ylabel('Water Temperature [degC]')

plt.show()
