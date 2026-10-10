# Rancangan Penyempurnaan Bab 1 Pendahuluan

## Tujuan

Menyempurnakan Bab 1 agar masalah, tujuan, metode pengujian, manfaat, dan batasan penelitian saling konsisten serta dapat dilaksanakan dengan data dan infrastruktur yang telah direncanakan.

## Ruang Lingkup

Perubahan dilakukan pada `template-ta-sd-itera/bab/1-pendahuluan.tex`. Hasil uji kelayakan topik dengan kerangka FINER ditulis secara singkat pada `template-ta-sd-itera/uji-finer-bab1.md`. Dokumen dikompilasi melalui `bab1-pustaka.tex` untuk memperbarui `bab1-pustaka.pdf`.

Perubahan tidak mencakup penulisan Bab 2--5, pengembangan pipeline, pengumpulan data baru, atau pengujian pada data Indonesia.

## Struktur Isi

Latar belakang terdiri atas tepat lima paragraf dengan urutan berikut:

1. Urgensi pemantauan kualitas air permukaan dalam konteks SDG 6.
2. Hubungan tekanan urbanisasi dan kualitas air serta alasan kepadatan penduduk digunakan sebagai proksi.
3. Peluang dan tantangan pengolahan dataset kualitas air berskala besar.
4. Celah penelitian pada integrasi data fisikokimia dan kepadatan penduduk serta kebutuhan membandingkan model.
5. Usulan penelitian, pendekatan utama, dan tiga fokus pengujian.

Bagian sesudah latar belakang mempertahankan diagram alur penelitian, kemudian memuat tiga rumusan masalah, tiga tujuan yang sejajar, batasan masalah, manfaat teoretis dan praktis, matriks konsistensi, serta sistematika penulisan.

## Rumusan Masalah dan Tujuan

Rumusan masalah menggunakan kata kerja operasional berikut:

1. Mengevaluasi kinerja pipeline Medallion Architecture berbasis Apache Spark terhadap pipeline sekuensial berbasis Pandas berdasarkan waktu pemrosesan dan throughput.
2. Menganalisis pengaruh penambahan fitur kepadatan penduduk terhadap kinerja klasifikasi WQI.
3. Membandingkan kinerja Random Forest dan XGBoost dalam mengklasifikasikan WQI.

Setiap tujuan menggunakan nomor dan objek pengukuran yang sama dengan rumusan masalah terkait. Adaptasi ke Indonesia ditempatkan sebagai peluang penelitian lanjutan, bukan sasaran yang diuji dalam penelitian ini.

## Pengukuran dan Konsistensi

Kinerja pipeline diukur dengan waktu pemrosesan ujung ke ujung dan throughput dalam baris per detik. Pengaruh fitur kepadatan penduduk diuji melalui perbandingan model dengan dan tanpa fitur tersebut. Random Forest dan XGBoost dibandingkan pada partisi data dan prosedur evaluasi yang sama menggunakan akurasi dan macro F1-score. RMSE tidak digunakan untuk menilai label kelas; metrik tersebut hanya relevan apabila skor WQI kontinu dimodelkan sebagai keluaran terpisah.

Matriks konsistensi memiliki enam kolom: nomor, rumusan masalah, tujuan penelitian, data atau variabel, metode analisis, serta indikator dan luaran. Setiap baris mewakili tepat satu pasangan rumusan masalah dan tujuan.

## Prinsip Penulisan

Bahasa dibuat formal, langsung, dan bervariasi tanpa ungkapan promosi, klaim berlebihan, atau pola kalimat generik. Istilah asing dicetak miring sesuai kebiasaan template. Paragraf tidak memakai cetak tebal. Klaim faktual penting menggunakan sitasi yang tersedia pada pustaka proyek.

## Uji FINER

Dokumen FINER menilai lima unsur: feasible, interesting, novel, ethical, dan relevant. Setiap unsur diberi kesimpulan singkat dan catatan risiko. Kelayakan dinyatakan bersyarat pada tersedianya sumber daya komputasi lokal, kecocokan koordinat kedua dataset, dan kejelasan metode pembentukan label WQI. Klaim kebaruan dibatasi sebagai kebaruan kontekstual dan integratif, bukan kebaruan algoritmik.

## Verifikasi

Verifikasi mencakup pemeriksaan jumlah paragraf latar belakang, keselarasan satu-per-satu rumusan masalah dan tujuan, ketiadaan `\textbf` dalam paragraf, kelengkapan matriks, validitas seluruh kunci sitasi, serta kompilasi `latexmk -pdf bab1-pustaka.tex` tanpa galat fatal. PDF akhir diperiksa untuk memastikan tabel dan diagram dapat dibaca serta tidak keluar dari batas halaman.
