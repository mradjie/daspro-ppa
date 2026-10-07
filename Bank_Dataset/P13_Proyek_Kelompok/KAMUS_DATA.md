# Kamus Data - Pertemuan 13 - Proyek kelompok

**Bank Dataset Sintetis Agroindustri**  
Modul Praktikum Dasar Pemrograman, PS Pengembangan Produk Agroindustri, SV UGM  
Sumber data: **CV Nusantara Pangan Lestari** (perusahaan fiktif, Sleman, DI Yogyakarta).  
Seluruh angka bersifat **sintetis** dan tidak boleh dipakai sebagai rujukan ilmiah.

**Catatan pemakaian.** Kumpulan lengkap. Setiap kelompok memilih satu pertanyaan agroindustri lalu menempuh siklus penuh dari data mentah hingga rekomendasi.

---

## penjualan_harian_besar

Penjualan harian delapan produk di empat wilayah selama satu tahun.  
Ukuran: **11.680 baris x 7 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| tanggal | teks | - | 365 nilai unik | 2025-07-01 | 0 | Tanggal pencatatan. |
| kode_produk | teks | - | PRD-01; PRD-02; PRD-03; PRD-04; PRD-05; PRD-06; PRD-07; PRD-08 | PRD-01 | 0 | Kode unik produk. Kunci utama pada tabel produk; kunci tamu pada tabel lain. |
| wilayah | teks | - | DI Yogyakarta; Jawa Tengah; Jawa Timur; Jabodetabek | DI Yogyakarta | 0 | Wilayah pemasaran. |
| jumlah_terjual_pcs | bilangan bulat | pcs | 0.00 - 55.00 | 14 | 0 | Jumlah kemasan terjual. |
| harga_satuan_rp | bilangan bulat | Rp | 12.000.00 - 32.000.00 | 28000 | 0 | Harga jual satu kemasan sebelum diskon. |
| diskon_persen | bilangan desimal | % | 0.00 - 15.00 | 0.0 | 0 | Potongan harga yang diberikan. |
| total_penjualan_rp | bilangan bulat | Rp | 0.00 - 1.037.400.00 | 392000 | 0 | Nilai penjualan setelah diskon. |


## harga_komoditas_harian_besar

Harga harian delapan komoditas bahan baku di pasar acuan.  
Ukuran: **2.920 baris x 4 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| tanggal | teks | - | 365 nilai unik | 2025-07-01 | 0 | Tanggal pencatatan. |
| komoditas | teks | - | Nangka; Salak Pondoh; Nanas; Singkong; Sukun; Markisa; Rosella; Cabai Merah | Nangka | 0 | Komoditas yang dipasok. |
| kabupaten_pasar | teks | - | Sleman; Kediri; Gunungkidul; Cilacap; Magelang; Bantul; Temanggung | Sleman | 0 | Kabupaten lokasi pasar acuan pencatatan harga. |
| harga_rp_per_kg | bilangan bulat | Rp/kg | 2.000.00 - 49.800.00 | 9300 | 0 | Harga bahan baku di pasar acuan. |


## qc_proses_besar

Catatan QC penggorengan vakum selama satu tahun.  
Ukuran: **14.564 baris x 15 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| tanggal | teks | - | 313 nilai unik | 2025-07-01 | 0 | Tanggal pencatatan. |
| shift | teks | - | Pagi; Siang; Malam | Pagi | 0 | Shift kerja: Pagi, Siang, atau Malam. |
| kode_batch | teks | - | 939 nilai unik | BTC-250701-001 | 0 | Kode batch produksi. Kunci utama pada tabel batch_produksi. |
| kode_produk | teks | - | PRD-02; PRD-01; PRD-03 | PRD-02 | 0 | Kode unik produk. Kunci utama pada tabel produk; kunci tamu pada tabel lain. |
| mesin | teks | - | VF-01; VF-02; VF-03 | VF-01 | 0 | Kode mesin penggoreng vakum (VF-01 s.d. VF-03). |
| operator | teks | - | Bayu; Citra; Dewi; Fitri; Galih; Eko; Hana; Andi | Bayu | 0 | Nama operator mesin. |
| no_sampel | bilangan bulat | - | 1.00 - 22.00 | 1 | 0 | Nomor urut sampel yang diambil dari satu batch. |
| berat_bersih_g | bilangan desimal | g | 93.10 - 105.30 | 100.1 | 0 | Berat bersih isi kemasan. Pada berkas master merupakan klaim label; pada berkas QC merupakan hasil penimbangan sampel. |
| kadar_air_persen | bilangan desimal | % bb | 1.20 - 3.86 | 2.36 | 0 | Kadar air basis basah. |
| suhu_penggorengan_c | bilangan desimal | degC | 77.90 - 91.90 | 84.0 | 0 | Suhu minyak selama penggorengan vakum. |
| tekanan_vakum_cmhg | bilangan desimal | cmHg | 61.10 - 78.60 | 72.9 | 0 | Tekanan vakum selama penggorengan. |
| waktu_penggorengan_menit | bilangan desimal | menit | 43.20 - 65.40 | 55.1 | 0 | Lama penggorengan. |
| bahan_baku_kg | bilangan desimal | kg | 83.40 - 165.70 | 128.1 | 0 | Bobot bahan baku yang diproses dalam batch. |
| rendemen_persen | bilangan desimal | % | 6.15 - 13.27 | 8.59 | 0 | Nisbah produk jadi terhadap bahan baku dikali 100. |
| status_qc | teks | - | Lolos; Tolak | Lolos | 0 | Keputusan QC: Lolos bila kadar air <= 3,0% dan berat bersih 97-103 g. |


## umur_simpan_besar

Pengamatan mutu tiga produk keripik pada tiga suhu selama 42 hari.  
Ukuran: **189 baris x 10 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| kode_produk | teks | - | PRD-01; PRD-02; PRD-03 | PRD-01 | 0 | Kode unik produk. Kunci utama pada tabel produk; kunci tamu pada tabel lain. |
| suhu_simpan_c | bilangan bulat | degC | 27.00 - 45.00 | 27 | 0 | Suhu ruang penyimpanan selama pengamatan. |
| hari_ke | bilangan bulat | hari | 0.00 - 42.00 | 0 | 0 | Lama penyimpanan saat pengamatan dilakukan. |
| ulangan | bilangan bulat | - | 1.00 - 3.00 | 1 | 0 | Nomor ulangan pengukuran (duplo/triplo). |
| tanggal_uji | teks | - | 2026-03-02; 2026-03-09; 2026-03-16; 2026-03-23; 2026-03-30; 2026-04-06; 2026-04-13 | 2026-03-02 | 0 | Tanggal pengamatan (YYYY-MM-DD). |
| kadar_air_persen | bilangan desimal | % bb | 1.97 - 9.58 | 2.27 | 0 | Kadar air basis basah. |
| kekerasan_n | bilangan desimal | N | 1.72 - 14.64 | 12.52 | 0 | Gaya maksimum penetrasi sebagai indikator kerenyahan; nilai turun berarti produk melempem. |
| bilangan_peroksida_meq_kg | bilangan desimal | meq O2/kg | 0.78 - 10.40 | 0.83 | 0 | Indikator awal ketengikan oksidatif lemak. |
| warna_l | bilangan desimal | - | 41.10 - 66.07 | 62.58 | 0 | Nilai L* sistem CIELAB; makin besar makin terang. |
| skor_hedonik_keseluruhan | bilangan desimal | skala 1-7 | 1.39 - 6.51 | 6.36 | 0 | Skor kesukaan keseluruhan oleh panel terbatas. |


## sensori_hedonik_besar

Uji hedonik 120 panelis terhadap enam formula, dua sesi.  
Ukuran: **1.440 baris x 10 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| sesi | bilangan bulat | - | 1.00 - 2.00 | 1 | 0 | Nomor sesi pengujian (uji diulang pada dua hari berbeda). |
| kode_panelis | teks | - | 120 nilai unik | PNL-001 | 0 | Kode anonim panelis. Awalan PNL = panelis tidak terlatih, PTL = panelis terlatih. |
| jenis_kelamin | teks | - | Laki-laki; Perempuan | Laki-laki | 0 | Jenis kelamin panelis. |
| usia_tahun | bilangan bulat | tahun | 18.00 - 23.00 | 18 | 0 | Usia panelis. |
| kode_formula | teks | - | F1; F2; F3; F4; F5; F6 | F1 | 0 | Kode formula flakes mocaf-sukun (F1 s.d. F6). |
| skor_warna | bilangan bulat | skala 1-7 | 1.00 - 7.00 | 6 | 0 | Skor kesukaan terhadap warna (1 = sangat tidak suka, 7 = sangat suka). |
| skor_aroma | bilangan bulat | skala 1-7 | 2.00 - 7.00 | 5 | 0 | Skor kesukaan terhadap aroma (1 = sangat tidak suka, 7 = sangat suka). |
| skor_rasa | bilangan bulat | skala 1-7 | 2.00 - 7.00 | 5 | 0 | Skor kesukaan terhadap rasa (1 = sangat tidak suka, 7 = sangat suka). |
| skor_tekstur | bilangan bulat | skala 1-7 | 1.00 - 7.00 | 5 | 0 | Skor kesukaan terhadap tekstur (1 = sangat tidak suka, 7 = sangat suka). |
| skor_keseluruhan | bilangan bulat | skala 1-7 | 1.00 - 7.00 | 5 | 0 | Skor kesukaan keseluruhan (1 = sangat tidak suka, 7 = sangat suka). |


## sensori_profil_atribut

Penilaian 12 panelis terlatih, delapan atribut, triplo, format panjang.  
Ukuran: **1.728 baris x 5 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| kode_panelis | teks | - | 12 nilai unik | PTL-001 | 0 | Kode anonim panelis. Awalan PNL = panelis tidak terlatih, PTL = panelis terlatih. |
| kode_formula | teks | - | F1; F2; F3; F4; F5; F6 | F1 | 0 | Kode formula flakes mocaf-sukun (F1 s.d. F6). |
| ulangan | bilangan bulat | - | 1.00 - 3.00 | 1 | 0 | Nomor ulangan pengukuran (duplo/triplo). |
| atribut | teks | - | aroma_sukun; aroma_langu; rasa_manis; rasa_sepat; kerenyahan; kekerasan; intensitas_warna; kelarutan_mulut | aroma_sukun | 0 | Nama atribut sensori yang dinilai panel terlatih. |
| nilai | bilangan desimal | beragam | 0.00 - 9.70 | 0.78 | 0 | Nilai hasil pengukuran; satuan mengikuti kolom satuan atau parameter. |


## proksimat_formula_besar

Analisis proksimat enam formula, triplo, delapan kelompok pengujian.  
Ukuran: **144 baris x 11 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| kode_batch_uji | teks | - | UJI-01; UJI-02; UJI-03; UJI-04; UJI-05; UJI-06; UJI-07; UJI-08 | UJI-01 | 0 | Kode kelompok pengujian laboratorium. |
| tanggal_analisis | teks | - | 2026-02-02; 2026-02-09; 2026-02-16; 2026-02-23; 2026-03-02; 2026-03-09; 2026-03-16; 2026-03-23 | 2026-02-02 | 0 | Tanggal analisis dilakukan (YYYY-MM-DD). |
| kode_formula | teks | - | F1; F2; F3; F4; F5; F6 | F1 | 0 | Kode formula flakes mocaf-sukun (F1 s.d. F6). |
| ulangan | bilangan bulat | - | 1.00 - 3.00 | 1 | 0 | Nomor ulangan pengukuran (duplo/triplo). |
| kadar_air_persen | bilangan desimal | % bb | 5.97 - 7.73 | 6.13 | 0 | Kadar air basis basah. |
| kadar_abu_persen | bilangan desimal | % bb | 1.77 - 3.08 | 1.91 | 0 | Kadar abu basis basah. |
| kadar_protein_persen | bilangan desimal | % bb | 1.87 - 4.51 | 2.02 | 0 | Kadar protein kasar basis basah. |
| kadar_lemak_persen | bilangan desimal | % bb | 8.00 - 9.39 | 8.42 | 0 | Kadar lemak basis basah. |
| serat_kasar_persen | bilangan desimal | % bb | 1.92 - 5.25 | 1.92 | 0 | Kadar serat kasar basis basah. |
| karbohidrat_by_difference_persen | bilangan desimal | % bb | 75.77 - 81.88 | 81.53 | 0 | Karbohidrat dihitung sebagai 100 dikurangi air, abu, protein, dan lemak. |
| analis | teks | - | Rani; Sekar; Bagas; Yoga | Rani | 0 | Nama analis laboratorium. |


## master_produk

Daftar delapan produk CV Nusantara Pangan Lestari.  
Ukuran: **8 baris x 8 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| kode_produk | teks | - | PRD-01; PRD-02; PRD-03; PRD-04; PRD-05; PRD-06; PRD-07; PRD-08 | PRD-01 | 0 | Kode unik produk. Kunci utama pada tabel produk; kunci tamu pada tabel lain. |
| nama_produk | teks | - | Keripik Nangka Vakum; Keripik Salak Vakum; Keripik Nanas Vakum; Tepung Mocaf Premium; Tepung Sukun; Sari Buah Markisa; Sirup Rosella; Bubuk Cabai Kering | Keripik Nangka Vakum | 0 | Nama dagang produk. |
| kategori | teks | - | Keripik buah; Tepung; Minuman; Bumbu | Keripik buah | 0 | Kelompok produk: Keripik buah, Tepung, Minuman, atau Bumbu. |
| bahan_baku_utama | teks | - | Nangka; Salak Pondoh; Nanas; Singkong; Sukun; Markisa; Rosella; Cabai Merah | Nangka | 0 | Komoditas utama penyusun produk. |
| jenis_kemasan | teks | - | pouch; kemasan; botol | pouch | 0 | Bentuk kemasan primer: pouch, kemasan, atau botol. |
| berat_bersih_g | bilangan bulat | g | 50.00 - 500.00 | 100 | 0 | Berat bersih isi kemasan. Pada berkas master merupakan klaim label; pada berkas QC merupakan hasil penimbangan sampel. |
| harga_jual_rp | bilangan bulat | Rp | 12.000.00 - 32.000.00 | 28000 | 0 | Harga jual satu kemasan di tingkat konsumen. |
| tanggal_luncur | teks | - | 2021-03-01; 2022-08-15; 2020-01-10; 2023-02-01; 2022-05-20; 2023-09-01; 2021-11-11 | 2021-03-01 | 0 | Tanggal produk pertama kali dipasarkan (format YYYY-MM-DD). |


## master_pemasok

Daftar delapan pemasok bahan baku beserta wilayah dan status sertifikasi.  
Ukuran: **8 baris x 7 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| kode_pemasok | teks | - | SUP-01; SUP-02; SUP-03; SUP-04; SUP-05; SUP-06; SUP-07; SUP-08 | SUP-01 | 0 | Kode unik pemasok. Kunci utama pada tabel pemasok. |
| nama_pemasok | teks | - | Kelompok Tani Ngudi Rahayu; Koperasi Salak Sejahtera; KUB Tani Makmur; CV Singkong Mandiri; Gapoktan Sukun Lestari; Kelompok Tani Markisa Ijo; KWT Rosella Asri; UD Cabai Jaya | Kelompok Tani Ngudi Rahayu | 0 | Nama kelompok tani, koperasi, atau badan usaha pemasok. |
| komoditas | teks | - | Nangka; Salak Pondoh; Nanas; Singkong; Sukun; Markisa; Rosella; Cabai Merah | Nangka | 0 | Komoditas yang dipasok. |
| kabupaten | teks | - | Sleman; Kediri; Gunungkidul; Cilacap; Magelang; Bantul; Temanggung | Sleman | 0 | Kabupaten domisili pemasok. |
| provinsi | teks | - | DI Yogyakarta; Jawa Timur; Jawa Tengah | DI Yogyakarta | 0 | Provinsi domisili pemasok. |
| tahun_mulai_mitra | bilangan bulat | tahun | 2.017.00 - 2.023.00 | 2019 | 0 | Tahun pemasok mulai bermitra dengan perusahaan. |
| sertifikasi_prima | teks | - | Prima 3; Prima 2; Belum | Prima 3 | 0 | Status sertifikasi Prima 2 / Prima 3 / Belum. |


## master_formula_flakes

Enam formula flakes sarapan mocaf-sukun (F1-F6) sebagai gradasi substitusi.  
Ukuran: **6 baris x 6 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| kode_formula | teks | - | F1; F2; F3; F4; F5; F6 | F1 | 0 | Kode formula flakes mocaf-sukun (F1 s.d. F6). |
| mocaf_persen | bilangan bulat | % | 0.00 - 100.00 | 100 | 0 | Proporsi tepung mocaf dalam campuran tepung. |
| sukun_persen | bilangan bulat | % | 0.00 - 100.00 | 0 | 0 | Proporsi tepung sukun dalam campuran tepung. |
| gula_persen | bilangan desimal | % | 12.00 - 12.00 | 12.0 | 0 | Proporsi gula halus terhadap berat adonan. |
| lemak_persen | bilangan desimal | % | 8.00 - 8.00 | 8.0 | 0 | Proporsi minyak nabati terhadap berat adonan. |
| keterangan | teks | - | Kontrol mocaf penuh; Substitusi sukun 20%; Substitusi sukun 40%; Substitusi sukun 60%; Substitusi sukun 80%; Kontrol sukun penuh | Kontrol mocaf penuh | 0 | Catatan bebas. |


## agroindustri_mini.db

Basis data SQLite berisi empat tabel. Dibuka dengan `sqlite3.connect()` lalu dibaca melalui `pandas.read_sql()`. Tidak memerlukan server maupun akun.

| Tabel | Jumlah baris | Kunci utama | Kunci tamu |
|---|---|---|---|
| produk | 8 | kode_produk | - |
| pemasok | 8 | kode_pemasok | - |
| batch_produksi | 390 | kode_batch | kode_produk, kode_pemasok |
| hasil_uji_mutu | 2154 | id_uji | kode_batch |

```
produk    1 --- N  batch_produksi  N --- 1  pemasok
                    |
                    1
                    |
                    N
             hasil_uji_mutu
```

Kolom tiap tabel identik dengan salinan `db_*.csv` yang dijelaskan di atas.
