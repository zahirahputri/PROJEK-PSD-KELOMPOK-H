Klasifikasi Kebakaran Hutan di Aljazair (Algerian Forest Fires)
Klasifikasi biner untuk memprediksi apakah pada suatu hari terjadi kebakaran hutan (`fire`) atau tidak (`not fire`) 
berdasarkan data cuaca dan indeks kebakaran hutan.

1. Deskripsi Singkat Proyek
Kebakaran hutan merugikan lingkungan dan ekonomi, sehingga deteksi dini berdasarkan kondisi cuaca sangat berguna. 
Proyek ini menerapkan tahapan dasar *data science workflow*: perumusan masalah, eksplorasi data, validasi dan pembersihan data, 
pemilihan dan transformasi fitur, pemodelan, evaluasi, serta interpretasi hasil.
Dataset: Algerian Forest Fires Dataset (UCI Machine Learning Repository)
- Sumber: https://archive.ics.uci.edu/dataset/547/algerian+forest+fires+dataset
- Periode data: Juni sampai September 2012
- Wilayah: Bejaia (timur laut Aljazair) dan Sidi-Bel Abbes (barat laut Aljazair)
- Jumlah observasi: 244 baris (122 per wilayah)
- Jumlah variabel: 14 kolom (13 fitur + 1 target)

Variabel target (`Classes`):
- `fire` = kode 1 (kelas positif): terjadi kebakaran hutan pada hari tersebut
- `not fire` = kode 0 (kelas negatif): tidak terjadi kebakaran hutan

Data dictionary:
- `day`, `month`, `year`: tanggal pengamatan (tidak digunakan sebagai fitur)
- `Temperature`: suhu maksimum pada tengah hari (°C)
- `RH`: kelembapan relatif (%)
- `Ws`: kecepatan angin (km/jam)
- `Rain`: curah hujan total dalam sehari (mm)
- `FFMC`: Fine Fuel Moisture Code (indeks FWI System)
- `DMC`: Duff Moisture Code (indeks FWI System)
- `DC`: Drought Code (indeks FWI System)
- `ISI`: Initial Spread Index (indeks FWI System)
- `BUI`: Buildup Index (indeks FWI System)
- `FWI`: Fire Weather Index (indeks FWI System)
- `Classes`: target, berisi `fire` atau `not fire`

Catatan kualitas data yang ditangani di notebook:
- File CSV berisi dua blok data (Bejaia dan Sidi-Bel Abbes) yang dipisahkan baris judul wilayah di tengah file.
  Baris judul dibuang dan kolom `Region` ditambahkan.
- Nama kolom dan nilai kelas memiliki spasi berlebih (misalnya `" RH"`, `"Rain "`, `"not fire   "`) sehingga dirapikan.
- Terdapat satu baris rusak (14 Juli 2012, Sidi-Bel Abbes) karena kolom `Classes` kosong dan nilainya bergeser.
- Seluruh kolom awalnya terbaca sebagai teks, sehingga tipe data numerik diperbaiki.
- Distribusi kelas relatif seimbang (sekitar 137 `fire` dan 106 `not fire`).
- Potensi *data leakage* pada fitur indeks turunan seperti `FWI` dibahas pada tahap feature selection.

Algoritma yang dibandingkan: (sementara)
1. Logistic Regression
2. Decision Tree

2. Anggota Kelompok
-   Sri Utami Desi Setyawati (K1D025068) | Github : '@utami.ds'
-   Zahirah Putri Ramadhana (K1D025070) | Github : '@zahirahputri'
-   Hanna Allyaardana (K1D025072) | Github : '@hanna
-   Nisrinaya Aprilla (K1D025074) | Github : '@
Kelompok : H
Kelas: Statistika B

3. Struktur Repositori
PROJEK-PSD-KELOMPOK-H/
├── README.md
├── Algerian_forest_fires_dataset_UPDATE.csv   
├── <nama_notebook>.ipynb                      # kode, output, visualisasi, evaluasi (MENYUSUL)
├── <Laporan_Proyek>.pdf                       # laporan BAB I-V, Daftar Pustaka, Lampiran (MENYUSUL)
├── <Slide_Presentasi>.pdf                     # maksimal 20 slide (PDF/PPTX) (MENYUSUL)
└── requirements.txt                           # daftar library Python (MENYUSUL)

4. Petunjuk Menjalankan Notebook
   - Langkah (Google Colab)
     - Unggah notebook ke Colab (File > Upload notebook).
     - Unggah file `Algerian_forest_fires_dataset_UPDATE.csv` ke sesi Colab, atau sesuaikan path pada sel pembacaan data.
     - Jalankan Runtime > Run all.

5. Penggunaan AI
   Penggunaan AI sebagai alat bantu didokumentasikan pada **Lampiran 2** laporan (aplikasi, tujuan, prompt, tautan percakapan, bentuk modifikasi, dan halaman penerapan).

6. Sumber Data dan Referensi
   Abid, F., & Izeboudjen, N. (2020). *Predicting Forest Fire in Algeria Using Data Mining Techniques: Case Study of the Decision Tech Algorithm.* Dataset: Algerian Forest Fires Dataset, UCI Machine Learning Repository. https://archive.ics.uci.edu/dataset/547/algerian+forest+fires+dataset
