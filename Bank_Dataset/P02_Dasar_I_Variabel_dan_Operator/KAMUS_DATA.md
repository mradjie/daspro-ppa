# Kamus Data - Pertemuan 2 - Variabel, tipe data, operator, input/output

**Bank Dataset Sintetis Agroindustri**  
Modul Praktikum Dasar Pemrograman, PS Pengembangan Produk Agroindustri, SV UGM  
Sumber data: **CV Nusantara Pangan Lestari** (perusahaan fiktif, Sleman, DI Yogyakarta).  
Seluruh angka bersifat **sintetis** dan tidak boleh dipakai sebagai rujukan ilmiah.

**Catatan pemakaian.** Nilai dibaca manual dari tabel lalu diketik sebagai variabel Python. Berkas sengaja hanya 10 baris karena pandas belum diperkenalkan.

---

## p02_rendemen_dan_biaya_mini

Sepuluh batch produksi dengan bahan baku, hasil, dan komponen biaya.  
Ukuran: **10 baris x 8 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| kode_batch | teks | - | 10 nilai unik | BTC-2604-01 | 0 | Kode batch produksi. Kunci utama pada tabel batch_produksi. |
| kode_produk | teks | - | PRD-02; PRD-01; PRD-03 | PRD-02 | 0 | Kode unik produk. Kunci utama pada tabel produk; kunci tamu pada tabel lain. |
| bahan_baku_kg | bilangan desimal | kg | 92.10 - 132.10 | 115.9 | 0 | Bobot bahan baku yang diproses dalam batch. |
| produk_jadi_kg | bilangan desimal | kg | 8.89 - 13.78 | 11.43 | 0 | Bobot produk jadi yang dihasilkan. |
| biaya_bahan_baku_rp | bilangan bulat | Rp | 673.158.00 - 1.021.957.00 | 930445 | 0 | Biaya pembelian bahan baku untuk satu batch. |
| biaya_tenaga_kerja_rp | bilangan bulat | Rp | 201.776.00 - 319.828.00 | 315309 | 0 | Biaya tenaga kerja langsung satu batch. |
| biaya_energi_rp | bilangan bulat | Rp | 100.831.00 - 167.163.00 | 110523 | 0 | Biaya listrik dan gas satu batch. |
| jumlah_kemasan_pcs | bilangan bulat | pcs | 88.00 - 137.00 | 114 | 0 | Jumlah kemasan 100 g yang dihasilkan. |


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

