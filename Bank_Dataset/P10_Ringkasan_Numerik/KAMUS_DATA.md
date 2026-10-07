# Kamus Data - Pertemuan 10 - Meringkas data secara numerik dan grafis

**Bank Dataset Sintetis Agroindustri**  
Modul Praktikum Dasar Pemrograman, PS Pengembangan Produk Agroindustri, SV UGM  
Sumber data: **CV Nusantara Pangan Lestari** (perusahaan fiktif, Sleman, DI Yogyakarta).  
Seluruh angka bersifat **sintetis** dan tidak boleh dipakai sebagai rujukan ilmiah.

**Catatan pemakaian.** Fokus pada rata-rata plus/minus SD, %RSD, median versus rata-rata saat ada pencilan, serta penyajian sebaran sebagai histogram dan boxplot. Tidak ada uji hipotesis pada pertemuan ini.

---

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


## p04_kadar_air_50_sampel

Lima puluh hasil pengukuran kadar air dari dua batch keripik nangka.  
Ukuran: **50 baris x 3 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| no_sampel | bilangan bulat | - | 1.00 - 50.00 | 1 | 0 | Nomor urut sampel yang diambil dari satu batch. |
| kode_batch | teks | - | BTC-260415-001; BTC-260415-002 | BTC-260415-001 | 0 | Kode batch produksi. Kunci utama pada tabel batch_produksi. |
| kadar_air_persen | bilangan desimal | % bb | 1.61 - 3.09 | 2.9 | 0 | Kadar air basis basah. |

