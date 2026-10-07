# Kamus Data - Pertemuan 14 - Ujian praktek dan responsi

**Bank Dataset Sintetis Agroindustri**  
Modul Praktikum Dasar Pemrograman, PS Pengembangan Produk Agroindustri, SV UGM  
Sumber data: **CV Nusantara Pangan Lestari** (perusahaan fiktif, Sleman, DI Yogyakarta).  
Seluruh angka bersifat **sintetis** dan tidak boleh dipakai sebagai rujukan ilmiah.

**Catatan pemakaian.** Berkas kecil dipilih agar waktu ujian habis untuk berpikir, bukan menunggu proses baca data.

---

## qc_proses_kecil

Catatan QC penggorengan vakum selama satu bulan.  
Ukuran: **358 baris x 15 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| tanggal | teks | - | 22 nilai unik | 2026-04-01 | 0 | Tanggal pencatatan. |
| shift | teks | - | Pagi; Siang; Malam | Pagi | 0 | Shift kerja: Pagi, Siang, atau Malam. |
| kode_batch | teks | - | 66 nilai unik | BTC-260401-001 | 0 | Kode batch produksi. Kunci utama pada tabel batch_produksi. |
| kode_produk | teks | - | PRD-01; PRD-03; PRD-02 | PRD-01 | 0 | Kode unik produk. Kunci utama pada tabel produk; kunci tamu pada tabel lain. |
| mesin | teks | - | VF-03; VF-02; VF-01 | VF-03 | 0 | Kode mesin penggoreng vakum (VF-01 s.d. VF-03). |
| operator | teks | - | Dewi; Hana; Fitri; Andi; Citra; Galih; Eko; Bayu | Dewi | 0 | Nama operator mesin. |
| no_sampel | bilangan bulat | - | 1.00 - 9.00 | 1 | 0 | Nomor urut sampel yang diambil dari satu batch. |
| berat_bersih_g | bilangan desimal | g | 96.30 - 103.40 | 97.3 | 0 | Berat bersih isi kemasan. Pada berkas master merupakan klaim label; pada berkas QC merupakan hasil penimbangan sampel. |
| kadar_air_persen | bilangan desimal | % bb | 1.46 - 3.71 | 2.59 | 0 | Kadar air basis basah. |
| suhu_penggorengan_c | bilangan desimal | degC | 78.90 - 91.00 | 83.1 | 0 | Suhu minyak selama penggorengan vakum. |
| tekanan_vakum_cmhg | bilangan desimal | cmHg | 64.00 - 76.70 | 73.8 | 0 | Tekanan vakum selama penggorengan. |
| waktu_penggorengan_menit | bilangan desimal | menit | 49.00 - 63.60 | 57.0 | 0 | Lama penggorengan. |
| bahan_baku_kg | bilangan desimal | kg | 93.80 - 151.40 | 118.1 | 0 | Bobot bahan baku yang diproses dalam batch. |
| rendemen_persen | bilangan desimal | % | 6.87 - 12.39 | 11.04 | 0 | Nisbah produk jadi terhadap bahan baku dikali 100. |
| status_qc | teks | - | Lolos; Tolak | Lolos | 0 | Keputusan QC: Lolos bila kadar air <= 3,0% dan berat bersih 97-103 g. |


## umur_simpan_kecil

Pengamatan mutu Keripik Nangka pada tiga suhu selama 42 hari.  
Ukuran: **63 baris x 10 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| kode_produk | teks | - | PRD-01 | PRD-01 | 0 | Kode unik produk. Kunci utama pada tabel produk; kunci tamu pada tabel lain. |
| suhu_simpan_c | bilangan bulat | degC | 27.00 - 45.00 | 27 | 0 | Suhu ruang penyimpanan selama pengamatan. |
| hari_ke | bilangan bulat | hari | 0.00 - 42.00 | 0 | 0 | Lama penyimpanan saat pengamatan dilakukan. |
| ulangan | bilangan bulat | - | 1.00 - 3.00 | 1 | 0 | Nomor ulangan pengukuran (duplo/triplo). |
| tanggal_uji | teks | - | 2026-03-02; 2026-03-09; 2026-03-16; 2026-03-23; 2026-03-30; 2026-04-06; 2026-04-13 | 2026-03-02 | 0 | Tanggal pengamatan (YYYY-MM-DD). |
| kadar_air_persen | bilangan desimal | % bb | 1.97 - 7.65 | 2.27 | 0 | Kadar air basis basah. |
| kekerasan_n | bilangan desimal | N | 1.72 - 12.86 | 12.52 | 0 | Gaya maksimum penetrasi sebagai indikator kerenyahan; nilai turun berarti produk melempem. |
| bilangan_peroksida_meq_kg | bilangan desimal | meq O2/kg | 0.78 - 7.90 | 0.83 | 0 | Indikator awal ketengikan oksidatif lemak. |
| warna_l | bilangan desimal | - | 46.02 - 62.58 | 62.58 | 0 | Nilai L* sistem CIELAB; makin besar makin terang. |
| skor_hedonik_keseluruhan | bilangan desimal | skala 1-7 | 2.23 - 6.51 | 6.36 | 0 | Skor kesukaan keseluruhan oleh panel terbatas. |


## sensori_hedonik_kecil

Uji hedonik 30 panelis terhadap empat formula, satu sesi.  
Ukuran: **120 baris x 10 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| sesi | bilangan bulat | - | 1.00 - 1.00 | 1 | 0 | Nomor sesi pengujian (uji diulang pada dua hari berbeda). |
| kode_panelis | teks | - | 30 nilai unik | PNL-001 | 0 | Kode anonim panelis. Awalan PNL = panelis tidak terlatih, PTL = panelis terlatih. |
| jenis_kelamin | teks | - | Laki-laki; Perempuan | Laki-laki | 0 | Jenis kelamin panelis. |
| usia_tahun | bilangan bulat | tahun | 18.00 - 23.00 | 19 | 0 | Usia panelis. |
| kode_formula | teks | - | F1; F2; F3; F4 | F1 | 0 | Kode formula flakes mocaf-sukun (F1 s.d. F6). |
| skor_warna | bilangan bulat | skala 1-7 | 3.00 - 7.00 | 6 | 0 | Skor kesukaan terhadap warna (1 = sangat tidak suka, 7 = sangat suka). |
| skor_aroma | bilangan bulat | skala 1-7 | 3.00 - 7.00 | 7 | 0 | Skor kesukaan terhadap aroma (1 = sangat tidak suka, 7 = sangat suka). |
| skor_rasa | bilangan bulat | skala 1-7 | 3.00 - 7.00 | 6 | 0 | Skor kesukaan terhadap rasa (1 = sangat tidak suka, 7 = sangat suka). |
| skor_tekstur | bilangan bulat | skala 1-7 | 3.00 - 7.00 | 6 | 0 | Skor kesukaan terhadap tekstur (1 = sangat tidak suka, 7 = sangat suka). |
| skor_keseluruhan | bilangan bulat | skala 1-7 | 3.00 - 7.00 | 6 | 0 | Skor kesukaan keseluruhan (1 = sangat tidak suka, 7 = sangat suka). |


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

