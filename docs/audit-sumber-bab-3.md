# Audit sumber untuk Bab III

Tanggal pemeriksaan: 24 Oktober 2026. Audit ini memeriksa metadata Figshare versi 2, notebook harmonisasi, dan cuplikan awal CSV England. Audit belum mencakup seluruh 2.129.198 rekaman atau pemulihan metadata stasiun.

## Sumber yang diperiksa

- Dataset: https://doi.org/10.6084/m9.figshare.27800394.v2
- Metadata versi: https://api.figshare.com/v2/articles/27800394/versions/2
- Notebook `Data_Processing_Harmonization.ipynb`: https://ndownloader.figshare.com/files/50757300
- CSV England: https://ndownloader.figshare.com/files/50757318
- Pedoman CCME, pembaruan 2017: https://ccme.ca/en/res/wqimanualen.pdf
- WorldPop, contoh produk kepadatan UK tahun 2020: https://hub.worldpop.org/geodata/summary?id=44435

## Metadata lokasi

Header CSV England berisi `Country`, `Area`, `Waterbody Type`, `Date`, delapan parameter fisikokimia, `CCME_Values`, dan `CCME_WQI`. Tidak ada kolom koordinat atau ID stasiun. Contoh nama area mengandung teks kotak grid 10 km. Nama tersebut tidak cukup untuk menghubungkan rekaman dengan satu piksel WorldPop atau untuk membuktikan identitas stasiun. Bab III menetapkan pemulihan metadata resmi sebagai syarat integrasi dan pengelompokan spasial.

## Perhitungan WQI

Notebook sumber menggunakan pemeriksaan `value > standard` untuk semua parameter, termasuk DO dan pH, lalu memakai `len(df.columns)` sebagai penyebut F1, F2, dan jumlah penyimpangan ternormalisasi. F2 disamakan dengan F1 karena penghitungan dilakukan per baris.

Acuan yang tertulis dalam notebook adalah amonia 0,5; BOD 6; DO 14; ortofosfat 0,05; pH 8,5; suhu 25; nitrogen 20; dan nitrat 45. Nilai tersebut dicatat sebagai konfigurasi penerbit, bukan direkomendasikan sebagai baku mutu England. Bentuk kimia, kesesuaian acuan, arah pelanggaran, dan penyebut memerlukan audit tersendiri untuk penerapan CCME yang sesuai pedoman.

Pada baris pertama cuplikan CSV, skor terbitan `42.847368090419145` dapat direproduksi dari tiga parameter yang melampaui acuan, jumlah excursion `147.13333333333333`, dan penyebut 12. Penyebut 8 menghasilkan sekitar `37.2613488535`; penyebut 10 menghasilkan sekitar `40.6470546299`. Contoh satu baris ini menunjukkan sensitivitas terhadap jumlah kolom, tetapi belum membuktikan konfigurasi seluruh dataset. Notebook yang diperiksa juga mempunyai sel pemilihan sepuluh kolom; keadaan DataFrame pada saat dataset terbitan dihasilkan perlu ditelusuri lebih lanjut.

Bab III mempertahankan kelas sumber sebagai target otomasi WQI adaptasi dataset, menuntut dokumentasi ketidaksesuaian, dan memisahkan audit reproduksi dari penilaian mutu lingkungan yang sesuai pedoman. Skor, kelas, dan komponen WQI dilarang menjadi prediktor. Hasil klasifikasi tidak diposisikan sebagai ramalan masa depan atau penilaian resmi status mutu air.

## Penyesuaian rancangan

- Periode gabungan utama 2000–2020, dengan raster pada tahun yang sama.
- Lokasi harus dapat dipulihkan secara sah; centroid area tidak digunakan sebagai pengganti.
- Perbandingan delapan dan sembilan fitur menggunakan rekaman serta manifest partisi yang sama.
- Pengelompokan lokasi/sel dipakai untuk mengurangi kebocoran spasial.
- Pipeline dibandingkan setelah kesetaraan keluaran dipastikan.

Temuan ini tidak mengubah berkas Bab I dan Bab II. Pada penyatuan naskah akhir, pernyataan mengenai ketersediaan lokasi dan sifat label pada kedua bab tersebut perlu diselaraskan dengan audit ini.
