# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding
Jaya Jaya Institut merupakan salah satu institusi pendidikan perguruan yang telah berdiri sejak tahun 2000. Hingga saat ini ia telah mencetak banyak lulusan dengan reputasi yang sangat baik. Akan tetapi, terdapat banyak juga siswa yang tidak menyelesaikan pendidikannya alias dropout.
Jumlah dropout yang tinggi ini tentunya menjadi salah satu masalah yang besar untuk sebuah institusi pendidikan. Oleh karena itu, Jaya Jaya Institut ingin mendeteksi secepat mungkin siswa yang mungkin akan melakukan dropout sehingga dapat diberi bimbingan khusus.

### Permasalahan Bisnis
Di banyak institusi pendidikan, dropout _student_ menjadi masalah serius yang dapat mempengaruhi reputasi institusi dan keseimbangan keuangan jangka panjang. Sama halnya yang terjadi di Jaya Jaya Institut. Dengan memanfaatkan data yang ada saat pendaftaran _student_ dan performa akademis mereka pada akhir semester pertama dan kedua, kita dapat membangun model klasifikasi untuk memprediksi kemungkinan seorang _student_ untuk melakukan dropout. Urgensinya adalah untuk mengidentifikasi faktor-faktor yang dapat mempengaruhi keputusan dropout tersebut, seperti jalur akademis, faktor demografis, dan sosial-ekonomi.

Efek jangka panjang dari masalah ini termasuk penurunan angka kelulusan, peningkatan biaya akibat kehilangan pendapatan _student_, dan dampak negatif terhadap citra institusi. Dengan mengantisipasi dropout melalui model prediksi yang tepat, institusi dapat mengambil langkah-langkah intervensi yang diperlukan untuk meningkatkan retensi _student_ dan menciptakan lingkungan akademik yang lebih sukses.


### Cakupan Proyek
- Dalam proyek ini, dataset telah disediakan dan dapat ditemukan di folder dataset (`data.csv`) atau melalui tautan yang tercantum di bagian  berikutnya.  
- Menganalisis struktur dan sifat data, meliputi tipe variabel, jumlah entri, serta mendeteksi keberadaan data yang hilang atau tidak valid.

Analisis Eksploratif Data (EDA):  
- Melaksanakan penelusuran awal pada data untuk menemukan pola, serta keterkaitan antara variabel.  
- Menyajikan data dalam bentuk visual untuk memahami distribusi variabel dan mengidentifikasi adanya anomali atau outlier.

Preparing Data
- Mengelola data yang hilang, mencari data duplikat, atau tidak valid dalam dataset.  
- Menyesuaikan format variabel tertentu agar sesuai untuk proses analisis selanjutnya.  
- Melakukan penyesuaian variabel numerik melalui normalisasi atau standardisasi.

Analisis Faktor-Faktor yang Mempengaruhi Dropout:

-Melakukan analisis  untuk mengidentifikasi variabel-variabel yang signifikan mempengaruhi dropout.
-Menggunakan teknik  untuk menemukan hubungan antar variabel.

 Pembuatan Model untuk Memprediksi Mahasiswa:  
- Memisahkan dataset menjadi data pelatihan dan data pengujian untuk pengembangan model.  
- Menerapkan teknik resampling seperti `SMOTE`, `Random Under Sampling`, dan `No Resampling` untuk menangani `unbalanced` data.  
- Menggunakan PCA untuk mengekstraksi komponen utama yang optimal.  
- Merancang dan melatih model prediksi dengan algoritma machine learning berikut:  
  - Random Forest  
  - Logistic Regression  
  - Decision Tree  
  - XGB  
  - Gradient Boosting  
  - SVM  

Membuat Dashboard  menggunakan `supabase` dan `Metabase`


### Persiapan

- <a href="https://github.com/dicodingacademy/dicoding_dataset/blob/main/students_performance/">Dataset Jaya Jaya Institut</a>
Dataset ini berisi `37` Column dan jumlah data sebesar`4424`


Setup environment:

- Pastikan terhubung ke internet untuk dapat melakukan install module `library`
- Buka cmd atau powershell as administrator
- install library berikut

```bash
pip install -r requirements.txt
```
- buat virtual environment dengan menjalankan perintah berikut

```
python -m venv env source env/bin/activate
```

- buka file `notebook.ipynb` untuk meilhat langkah-langkah analisis data

- untuk run Dashboard metabase jalankan perintah berikut:
```
docker -compose up
```

## Business Dashboard
business-dashboard yang dibuat menggunakan metabase dan mencakup visualisasi berikut
<img src="tarishrisqan_dashboard_2.png" alt="Database Supabase" height="300">
<img src="tarishrisqan_dashboard_1.png" alt="Database Supabase" height="300">

- pertama, memperlihatkan total `Student` dari Universitas tersebut
- menunjukukan jumlah dari Rata-Rata `Umur` Mahasiswa di Kampus tersebut
- menunjukan total dari `Nationality` dari mahasiswa di kampus tersebut
- menunjukan rata-rata `Inflation Rate` dari Kampus Tersebut
- menunjukan Visualisasi Pembagian  `Beasiswa` Untuk Mahasiswa dari Kampus tersebut
- menunjukan Visualisasi Pembagian `Gender`  Mahasiswa Di kampus tersebut
- menunjukan Pembagian Pie Chart `Student Status` di kampus tersebut
- menunjukan Pembagian `Debtor` dengan menggunakan Pie Chart Dari Kampus Tersebut
- menunjukan Pembagian `Marital Status` di kampus tersebut
- menunjukan Pembagian `Student Course` di kampus tersebut
- menunjukan Pembagian `Student Tuition` di Kampus tersebut
- menunjukan Chart pembagian program International dan reguler `Course` Di kampus tersebut


## Menjalankan Sistem Machine Learning

##### Untuk Menjalankan Streamlit
Untuk menjalankan aplikasi ini, silahkan cari file yang bernamaa `prediction.py` , kemudian masukkan command berikut dan tekan Enter:
```bash
streamlit run prediction.py
```

## Conclusion
* Student yang mendaftar  pembelajaran paling banyak berada di usia `18 Tahun` kemudian di angka `19 Tahun` dan `20 Tahun`.

* jurusan yang paling banyak diambil oleh mahasiswa `international` adalah `Journalism and Communication` dan jurusan yang paling banyak diambil oleh mahasiswa `reguler` adalah `Nursing`

* Di semester pertama bahwa Rata-Rata mahasiswa mengambil sebanyak `6 Mata kuliah` 

* Model machine learning Logistic Regression yang dikembangkan memiliki akurasi 90% dan SVM dengan akurasi 92%. Namun Logistic Regression lebih stabil dibandingkan SVM dari uji coba yang sudah dilakukan. Sehingga pada kasus ini menggunakan Logistic Regression sebagai model utama untuk melakukan prediksi status student Dropout ataupun Graduate. Model dapat melakukan prediksi dan sudah dideploy menggunakan Streamlit.

* Mahasiswa dengan utang atau kinerja akademik yang buruk lebih rentan untuk dropout. Hutang dapat menjadi beban tambahan yang menghambat kemajuan akademik.

* Mahasiswa yang tidak mendapatkan beasiswa cenderung memiliki tingkat dropout yang lebih tinggi  dibandingkan dengan yang menerima beasiswa. Hal ini menunjukkan pentingnya dukungan finansial dalam memotivasi student untuk menyelesaikan pendidikan mahasiswa.

### Rekomendasi Action Items
- Memberikan fasilitas khusus bagi mahasiswa yang sudah menikah atau bekerja, seperti opsi pembelajaran daring untuk mendukung fleksibilitas dalam mengikuti proses belajar.
- Lebih banyak memberikan program pertukaran pelajar agar dapat menarik mahasiswa dari negara lain dan dapat meningkatkan Rank dari kampus tersebut
- Lebih banyak memberikan program beasiswa agar bisa membantu mahasiswa yang kurang mampu
- Berikan program pembelajaran tambahan agar dapat mengurani nilai Dropout pada mahasiswa


### Login Metabase
- `Email` : root@mail.com
- `password` : root123 
