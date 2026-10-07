# Kamus Data - Pertemuan 3 - Operator logika dan percabangan

**Bank Dataset Sintetis Agroindustri**  
Modul Praktikum Dasar Pemrograman, PS Pengembangan Produk Agroindustri, SV UGM  
Sumber data: **CV Nusantara Pangan Lestari** (perusahaan fiktif, Sleman, DI Yogyakarta).  
Seluruh angka bersifat **sintetis** dan tidak boleh dipakai sebagai rujukan ilmiah.

**Catatan pemakaian.** Dipakai untuk menyusun aturan terima/tolak bahan baku dan penetapan kelas mutu.

---

## p03_penerimaan_bahan_baku_mini

Dua puluh dokumen penerimaan bahan baku segar dengan parameter mutu awal.  
Ukuran: **20 baris x 9 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| kode_penerimaan | teks | - | 20 nilai unik | TRM-001 | 0 | Nomor dokumen penerimaan bahan baku. |
| tanggal | teks | - | 2026-04-06; 2026-04-07; 2026-04-08; 2026-04-09; 2026-04-10; 2026-04-11; 2026-04-12 | 2026-04-06 | 0 | Tanggal pencatatan. |
| komoditas | teks | - | Salak Pondoh; Nangka; Nanas | Salak Pondoh | 0 | Komoditas yang dipasok. |
| kode_pemasok | teks | - | SUP-02; SUP-01; SUP-03 | SUP-02 | 0 | Kode unik pemasok. Kunci utama pada tabel pemasok. |
| bobot_kg | bilangan desimal | kg | 113.20 - 196.10 | 196.1 | 0 | Bobot bahan baku yang diterima. |
| kadar_air_persen | bilangan desimal | % bb | 71.60 - 87.20 | 77.2 | 0 | Kadar air basis basah. |
| total_padatan_terlarut_brix | bilangan desimal | degBrix | 9.20 - 18.10 | 15.0 | 0 | Total padatan terlarut buah segar. |
| cacat_fisik_persen | bilangan desimal | % | 0.00 - 13.70 | 13.4 | 0 | Proporsi bahan cacat: memar, busuk, atau ukuran tidak seragam. |
| suhu_terima_c | bilangan desimal | degC | 22.60 - 33.40 | 27.1 | 0 | Suhu bahan baku saat diterima di gudang. |


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

