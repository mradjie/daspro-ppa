# Kamus Data - Pertemuan 7 - Pembersihan data

**Bank Dataset Sintetis Agroindustri**  
Modul Praktikum Dasar Pemrograman, PS Pengembangan Produk Agroindustri, SV UGM  
Sumber data: **CV Nusantara Pangan Lestari** (perusahaan fiktif, Sleman, DI Yogyakarta).  
Seluruh angka bersifat **sintetis** dan tidak boleh dipakai sebagai rujukan ilmiah.

**Catatan pemakaian.** Berkas KOTOR sengaja dirusak. Daftar lengkap jenis kerusakan ada pada kamus data. Kunci versi bersih tersedia di subfolder _kunci_asisten dan TIDAK dibagikan ke mahasiswa.

---

## p07_qc_gabungan_KOTOR

Gabungan catatan QC dan pemasok yang SENGAJA dirusak untuk latihan pembersihan data.  
Ukuran: **343 baris x 16 kolom**. Tersedia dalam format `.csv` dan `.xlsx`.

| kolom | tipe | satuan | rentang / nilai | contoh | kosong | keterangan |
|---|---|---|---|---|---|---|
| Tanggal  | teks | - | 86 nilai unik | 01/04/2026 | 0 | Tanggal pencatatan. SENGAJA bermasalah: format campur dan ada spasi pada nama kolom. |
| SHIFT | teks | - | 15 nilai unik | malam | 0 | Shift kerja. SENGAJA bermasalah: penulisan tidak konsisten (Pagi/pagi/PAGI/P/Shift Pagi). |
| Kode Batch | teks | - | 65 nilai unik | BTC-260401-003 | 0 | Kode batch produksi. Nama kolom memakai spasi dan huruf kapital. |
| kode produk | teks | - | PRD-03; PRD-01; PRD-02 | PRD-03 | 0 | Kode produk. Nama kolom memakai spasi. |
| kode_pemasok | teks | - | SUP-03; SUP-01; SUP-02 | SUP-03 | 0 | Kode unik pemasok. Kunci utama pada tabel pemasok. |
| mesin | teks | - | VF-02; VF-03; VF-01 | VF-02 | 0 | Kode mesin penggoreng vakum (VF-01 s.d. VF-03). |
| operator | teks | - | 35 nilai unik | Fitri | 3 | Nama operator mesin. |
| no_sampel | bilangan bulat | - | 1.00 - 9.00 | 3 | 0 | Nomor urut sampel yang diambil dari satu batch. |
| Berat Bersih (g) | teks | g atau kg | 89 nilai unik | n/a | 4 | Berat bersih. SENGAJA bermasalah: sebagian dicatat dalam kg (lihat kolom satuan_berat) dan ada pencilan tidak masuk akal. |
| satuan_berat | teks | - | g; kg | g | 0 | Satuan yang dipakai pada kolom Berat Bersih: g atau kg. |
| Kadar Air (%) | teks | % | 188 nilai unik | 2.07 | 3 | Kadar air. SENGAJA bermasalah: sebagian ditulis dengan koma desimal, sebagian diberi simbol %, sebagian kosong. |
| suhu_penggorengan | teks | degC | 55 nilai unik | 85.6 | 2 | Suhu penggorengan. SENGAJA bermasalah: terdapat nilai hilang dan pencilan. |
| Rendemen (%) | teks | % | 220 nilai unik |   9.99   | 8 | Rendemen. SENGAJA bermasalah: berspasi, kosong, dan bernilai mustahil. |
| Status QC | teks | - | 12 nilai unik | OK | 0 | Keputusan QC. SENGAJA bermasalah: banyak variasi penulisan (Lolos/lolos/OK/Ya, Tolak/reject/Tidak). |
| keterangan | teks | - |   ; alat kalibrasi ulang; listrik padam 10 menit; cek lagi!!; sampel ulang; bahan baku basah; operator baru |    | 161 | Catatan bebas. |
| catatan_tambahan | teks | - |  | (kosong) | 343 | Kolom kosong seluruhnya. SENGAJA disertakan agar mahasiswa berlatih membuang kolom tak berisi. |


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



### Daftar kerusakan yang sengaja ditanamkan

Berkas `p07_qc_gabungan_KOTOR` mengandung sembilan jenis masalah. Daftar ini
ditujukan bagi dosen dan asisten; mahasiswa sebaiknya menemukannya sendiri lebih dahulu.

| No | Jenis masalah | Letak | Petunjuk penanganan |
|---|---|---|---|
| 1 | Nama kolom tidak rapi: spasi di ujung, spasi di tengah, huruf kapital campur | seluruh header | `df.columns.str.strip().str.lower().str.replace(" ", "_")` |
| 2 | Satuan campur dalam satu kolom: berat sebagian gram, sebagian kilogram | `Berat Bersih (g)` dan `satuan_berat` | konversi bersyarat berdasarkan kolom satuan |
| 3 | Angka tersimpan sebagai teks: koma desimal, simbol `%`, spasi pengapit | `Kadar Air (%)`, `Rendemen (%)` | `str.strip()`, `str.replace(",", ".")`, lalu `pd.to_numeric(errors="coerce")` |
| 4 | Nilai hilang dengan tujuh penanda berbeda: kosong, `-`, `n/a`, `NA`, `tidak diukur`, `?`, `null` | beberapa kolom | argumen `na_values=` pada `read_csv` atau `replace()` |
| 5 | Kategori tidak konsisten | `Status QC`, `SHIFT`, `operator` | pemetaan dengan dictionary setelah `str.strip().str.lower()` |
| 6 | Format tanggal campur: `2026-04-01`, `01/04/2026`, `01-04-2026`, `1 Apr 2026` | `Tanggal ` | `pd.to_datetime(..., dayfirst=True, format="mixed")` |
| 7 | Pencilan tidak masuk akal: kadar air 230%, berat 1005 g dan 10,2 g, suhu 850 degC, rendemen negatif dan 98% | tujuh baris | pemeriksaan rentang wajar, bukan penghapusan otomatis |
| 8 | Duplikat: 14 baris identik penuh dan 9 baris duplikat sebagian | tersebar | `duplicated()` dan `drop_duplicates(subset=...)` |
| 9 | Kolom kosong seluruhnya dan kolom catatan berisi spasi | `catatan_tambahan`, `keterangan` | `dropna(axis=1, how="all")` setelah `replace(r"^\s*$", pd.NA, regex=True)` |

Jumlah baris berkas kotor lebih banyak daripada jumlah baris sebenarnya justru karena duplikat
pada butir 8. Setelah dibersihkan dengan benar, jumlah baris unik kembali ke 320.

