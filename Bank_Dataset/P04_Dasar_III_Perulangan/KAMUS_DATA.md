# Kamus Data - Pertemuan 4 - Perulangan dan akumulator

**Bank Dataset Sintetis Agroindustri**  
Modul Praktikum Dasar Pemrograman, PS Pengembangan Produk Agroindustri, SV UGM  
Sumber data: **CV Nusantara Pangan Lestari** (perusahaan fiktif, Sleman, DI Yogyakarta).  
Seluruh angka bersifat **sintetis** dan tidak boleh dipakai sebagai rujukan ilmiah.

**Catatan pemakaian.** Berkas .txt berisi list Python siap tempel; berkas .csv dipakai sebagai rujukan tabel.

---

## p04_kadar_air_50_sampel

Lima puluh hasil pengukuran kadar air dari dua batch keripik nangka.  
Ukuran: **50 baris x 3 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| no_sampel | bilangan bulat | - | 1.00 - 50.00 | 1 | 0 | Nomor urut sampel yang diambil dari satu batch. |
| kode_batch | teks | - | BTC-260415-001; BTC-260415-002 | BTC-260415-001 | 0 | Kode batch produksi. Kunci utama pada tabel batch_produksi. |
| kadar_air_persen | bilangan desimal | % bb | 1.61 - 3.09 | 2.9 | 0 | Kadar air basis basah. |

