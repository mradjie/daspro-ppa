# Kamus Data - Pertemuan 12 - Pengantar SQL: SELECT, WHERE, GROUP BY, dan JOIN

**Bank Dataset Sintetis Agroindustri**  
Modul Praktikum Dasar Pemrograman, PS Pengembangan Produk Agroindustri, SV UGM  
Sumber data: **CV Nusantara Pangan Lestari** (perusahaan fiktif, Sleman, DI Yogyakarta).  
Seluruh angka bersifat **sintetis** dan tidak boleh dipakai sebagai rujukan ilmiah.

**Catatan pemakaian.** Berkas agroindustri_mini.db dibuka dengan sqlite3 lalu dibaca melalui pandas.read_sql. Salinan CSV/XLSX disertakan agar hasil SQL dapat dibandingkan dengan pandas. JOIN dilatih pada relasi batch_produksi ke produk dan hasil_uji_mutu ke batch_produksi.

---

## db_produk

Salinan tabel produk dari agroindustri_mini.db.  
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


## db_pemasok

Salinan tabel pemasok dari agroindustri_mini.db.  
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


## db_batch_produksi

Salinan tabel batch_produksi dari agroindustri_mini.db.  
Ukuran: **390 baris x 9 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| kode_batch | teks | - | 390 nilai unik | BTC-20260105-0001 | 0 | Kode batch produksi. Kunci utama pada tabel batch_produksi. |
| kode_produk | teks | - | PRD-08; PRD-02; PRD-01; PRD-04; PRD-03; PRD-06; PRD-07; PRD-05 | PRD-08 | 0 | Kode unik produk. Kunci utama pada tabel produk; kunci tamu pada tabel lain. |
| kode_pemasok | teks | - | SUP-08; SUP-02; SUP-01; SUP-04; SUP-03; SUP-06; SUP-07; SUP-05 | SUP-08 | 0 | Kode unik pemasok. Kunci utama pada tabel pemasok. |
| tanggal_produksi | teks | - | 129 nilai unik | 2026-01-05 | 0 | Tanggal batch diproduksi (YYYY-MM-DD). |
| shift | teks | - | Malam; Siang; Pagi | Malam | 0 | Shift kerja: Pagi, Siang, atau Malam. |
| bahan_baku_kg | bilangan desimal | kg | 78.40 - 227.90 | 171.7 | 0 | Bobot bahan baku yang diproses dalam batch. |
| produk_jadi_kg | bilangan desimal | kg | 7.74 - 137.95 | 29.5 | 0 | Bobot produk jadi yang dihasilkan. |
| rendemen_persen | bilangan desimal | % | 7.23 - 74.53 | 17.18 | 0 | Nisbah produk jadi terhadap bahan baku dikali 100. |
| supervisor | teks | - | Drs. Hartono; Rizal S.TP.; Widya S.TP.; Ir. Nuraini | Drs. Hartono | 0 | Penanggung jawab produksi batch. |


## db_hasil_uji_mutu

Salinan tabel hasil_uji_mutu dari agroindustri_mini.db.  
Ukuran: **2.154 baris x 9 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| id_uji | bilangan bulat | - | 1.00 - 2.154.00 | 1 | 0 | Nomor unik hasil uji. Kunci utama tabel hasil_uji_mutu. |
| kode_batch | teks | - | 390 nilai unik | BTC-20260105-0001 | 0 | Kode batch produksi. Kunci utama pada tabel batch_produksi. |
| parameter | teks | - | Kadar air; Kadar abu; Bilangan peroksida; Angka lempeng total; Kapang khamir; Berat bersih; Skor hedonik | Kadar air | 0 | Nama parameter mutu yang diukur. |
| nilai | bilangan desimal | beragam | -0.17 - 102.93 | 2.19 | 0 | Nilai hasil pengukuran; satuan mengikuti kolom satuan atau parameter. |
| satuan | teks | - | %; meq O2/kg; log CFU/g; g; skala 1-7 | % | 0 | Satuan pengukuran nilai pada baris tersebut. |
| metode | teks | - | Oven 105 C; Tanur 550 C; Titrasi iodometri; Cawan tuang; Cawan sebar; Timbang digital; Uji hedonik 15 panelis | Oven 105 C | 0 | Metode analisis yang dipakai. |
| tanggal_uji | teks | - | 152 nilai unik | 2026-01-05 | 0 | Tanggal pengamatan (YYYY-MM-DD). |
| analis | teks | - | Sekar; Rani; Yoga; Bagas; Intan | Sekar | 0 | Nama analis laboratorium. |
| status_mutu | teks | - | Memenuhi; Tidak memenuhi | Memenuhi | 0 | Memenuhi / Tidak memenuhi terhadap batas spesifikasi internal. |


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
