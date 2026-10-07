# Kamus Data - Pertemuan 5 - List, tuple, dictionary, fungsi

**Bank Dataset Sintetis Agroindustri**  
Modul Praktikum Dasar Pemrograman, PS Pengembangan Produk Agroindustri, SV UGM  
Sumber data: **CV Nusantara Pangan Lestari** (perusahaan fiktif, Sleman, DI Yogyakarta).  
Seluruh angka bersifat **sintetis** dan tidak boleh dipakai sebagai rujukan ilmiah.

**Catatan pemakaian.** Berkas .txt berisi dictionary formula siap tempel untuk latihan scale-up lab ke pilot plant.

---

## p05_formula_bahan_flakes

Rincian bahan tiap formula per 100 kg adonan beserta harga bahan.  
Ukuran: **42 baris x 5 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| nama_bahan | teks | - | Tepung mocaf; Tepung sukun; Gula halus; Minyak nabati; Garam; Susu bubuk; Perisa vanila | Tepung mocaf | 0 | Nama bahan penyusun formula. |
| kode_formula | teks | - | F1; F2; F3; F4; F5; F6 | F1 | 0 | Kode formula flakes mocaf-sukun (F1 s.d. F6). |
| jumlah_per_100kg_adonan | bilangan desimal | kg | 0.00 - 100.00 | 100.0 | 0 | Jumlah bahan untuk setiap 100 kg adonan. |
| harga_bahan_rp_per_kg | bilangan bulat | Rp/kg | 8.000.00 - 240.000.00 | 12500 | 0 | Harga beli bahan per kilogram. |
| satuan | teks | - | kg | kg | 0 | Satuan pengukuran nilai pada baris tersebut. |


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

