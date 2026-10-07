# Kamus Data - Pertemuan 6 - Membaca CSV/XLSX, anatomi DataFrame, loc dan iloc

**Bank Dataset Sintetis Agroindustri**  
Modul Praktikum Dasar Pemrograman, PS Pengembangan Produk Agroindustri, SV UGM  
Sumber data: **CV Nusantara Pangan Lestari** (perusahaan fiktif, Sleman, DI Yogyakarta).  
Seluruh angka bersifat **sintetis** dan tidak boleh dipakai sebagai rujukan ilmiah.

**Catatan pemakaian.** Mulai dari berkas kecil agar isi DataFrame dapat dilihat utuh, lalu berpindah ke berkas besar.

---

## proksimat_formula_kecil

Analisis proksimat lima formula, triplo, satu kelompok pengujian.  
Ukuran: **15 baris x 11 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| kode_batch_uji | teks | - | UJI-01 | UJI-01 | 0 | Kode kelompok pengujian laboratorium. |
| tanggal_analisis | teks | - | 2026-02-02 | 2026-02-02 | 0 | Tanggal analisis dilakukan (YYYY-MM-DD). |
| kode_formula | teks | - | F1; F2; F3; F4; F5 | F1 | 0 | Kode formula flakes mocaf-sukun (F1 s.d. F6). |
| ulangan | bilangan bulat | - | 1.00 - 3.00 | 1 | 0 | Nomor ulangan pengukuran (duplo/triplo). |
| kadar_air_persen | bilangan desimal | % bb | 6.17 - 7.44 | 6.17 | 0 | Kadar air basis basah. |
| kadar_abu_persen | bilangan desimal | % bb | 1.84 - 2.78 | 1.92 | 0 | Kadar abu basis basah. |
| kadar_protein_persen | bilangan desimal | % bb | 1.88 - 3.98 | 1.88 | 0 | Kadar protein kasar basis basah. |
| kadar_lemak_persen | bilangan desimal | % bb | 8.28 - 9.23 | 8.55 | 0 | Kadar lemak basis basah. |
| serat_kasar_persen | bilangan desimal | % bb | 2.22 - 4.63 | 2.36 | 0 | Kadar serat kasar basis basah. |
| karbohidrat_by_difference_persen | bilangan desimal | % bb | 76.73 - 81.49 | 81.49 | 0 | Karbohidrat dihitung sebagai 100 dikurangi air, abu, protein, dan lemak. |
| analis | teks | - | Rani; Sekar; Yoga; Bagas | Rani | 0 | Nama analis laboratorium. |


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

