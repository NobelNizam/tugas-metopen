# Uji FINER Bab 1

Topik penelitian: klasifikasi kualitas air di England berdasarkan parameter fisikokimia dan kepadatan penduduk menggunakan pipeline Medallion Architecture berbasis Apache Spark.

| Kriteria | Hasil uji singkat | Status |
|---|---|---|
| Feasible | Dataset utama dan data WorldPop tersedia, sedangkan perangkat lunak yang direncanakan bersifat sumber terbuka dan dapat dijalankan secara lokal. Kelayakan tetap bergantung pada jumlah rekaman England yang benar-benar lengkap, kecocokan koordinat antardataset, kapasitas komputer, serta definisi label WQI yang dapat diterapkan pada data. | Layak bersyarat |
| Interesting | Penelitian menghubungkan persoalan kualitas air, tekanan urbanisasi, rekayasa data berskala besar, dan klasifikasi. Hasilnya dapat menunjukkan kapan Spark diperlukan dan apakah kepadatan penduduk memberi informasi tambahan pada data yang digunakan. | Layak |
| Novel | Kebaruan tidak terletak pada algoritma baru, melainkan pada integrasi data kualitas air dan kepadatan penduduk dalam pipeline berlapis serta pengujian terkontrol terhadap pipeline, fitur, dan algoritma. Klaim kebaruan perlu dibatasi pada konteks data dan eksperimen penelitian. | Layak dengan klaim terbatas |
| Ethical | Data yang digunakan bersifat sekunder dan tidak memuat identitas personal. Risiko utama ialah penafsiran kepadatan penduduk sebagai penyebab langsung pencemaran atau pemberian label negatif pada wilayah tertentu. Mitigasinya adalah memakai istilah proksi, melaporkan keterbatasan data, dan menghindari kesimpulan kausal. | Layak |
| Relevant | Penelitian mendukung pemantauan kualitas air dan SDG 6 sekaligus menjawab kebutuhan pengolahan data lingkungan yang besar dan dapat direproduksi. Luaran pipeline serta evaluasi model relevan bagi kajian sains data dan informatika lingkungan. | Layak |

## Kesimpulan

Topik memenuhi kerangka FINER dan dapat dilanjutkan dengan tiga catatan. Pertama, jumlah serta kelengkapan rekaman England harus diverifikasi sebelum menetapkan skenario eksperimen. Kedua, perhitungan WQI harus menjelaskan nilai acuan, unit analisis, dan penanganan parameter yang tidak lengkap. Ketiga, bila label WQI dihitung dari delapan parameter pada baris yang sama, model hanya mempelajari kembali aturan pembentukan label. Risiko kebocoran target ini perlu ditangani dengan merumuskan keluaran sebagai otomasi klasifikasi, memakai WQI pada waktu berikutnya sebagai target prediksi, atau menggunakan label independen yang tersedia.
