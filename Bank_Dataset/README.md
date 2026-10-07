# Bank Dataset Sintetis Agroindustri

**Modul Praktikum Dasar Pemrograman**
Program Studi Sarjana Terapan Pengembangan Produk Agroindustri, Sekolah Vokasi UGM

---

## 1. Ringkasan

Seluruh berkas dalam bank ini bersifat **sintetis**: dibangkitkan komputer dengan
*seed* tetap, bukan hasil pengukuran nyata. Angka-angkanya disusun agar masuk akal
secara teknologi pangan, tetapi **tidak boleh dikutip sebagai rujukan ilmiah**.

Semua berkas berasal dari satu perusahaan fiktif yang sama:

> **CV Nusantara Pangan Lestari (NPL)** — Sleman, DI Yogyakarta.
> Delapan produk: tiga keripik buah vakum, dua tepung, dua minuman, satu bumbu.
> Delapan pemasok komoditas dari DI Yogyakarta, Jawa Tengah, dan Jawa Timur.
> Satu proyek pengembangan produk: *flakes* sarapan mocaf–sukun, enam formula (F1–F6).

**Alasan desain.** Menggunakan satu perusahaan untuk seluruh pertemuan membuat
kode produk, kode batch, dan kode pemasok konsisten lintas berkas. Konsekuensinya,
data dari pertemuan berbeda dapat digabungkan — inilah yang membuat latihan `merge`
di Pertemuan 8 dan `JOIN` di Pertemuan 12 terasa nyata, dan yang memungkinkan
proyek Pertemuan 13 memakai beberapa berkas sekaligus.

## 2. Cara memakai

Setiap folder pertemuan **berdiri sendiri dan lengkap**. Mahasiswa cukup mengunduh
satu folder untuk satu praktikum. Beberapa berkas sengaja muncul di lebih dari satu
folder; duplikasi ini disengaja demi kesederhanaan operasional di lab.

Setiap folder berisi:

- berkas data dalam format **`.csv` dan `.xlsx`** (isi identik);
- berkas **`KAMUS_DATA.md`** — kamus data seluruh berkas di folder tersebut, lengkap
  dengan tipe, satuan, rentang nilai, contoh, jumlah sel kosong, dan keterangan tiap kolom.

Di tingkat akar tersedia **`Kamus_Data_Lengkap.xlsx`** dan `.csv` yang memuat definisi
seluruh kolom dari seluruh berkas dalam satu tabel.

### Membaca di Google Colab

```python
import pandas as pd
from google.colab import files
files.upload()                      # pilih berkas .csv dari folder pertemuan

df = pd.read_csv("qc_proses_kecil.csv")
df.head()
```

Untuk berkas SQLite pada Pertemuan 12:

```python
import sqlite3, pandas as pd
con = sqlite3.connect("agroindustri_mini.db")
pd.read_sql("SELECT * FROM produk", con)
```

## 3. Isi bank dataset

| Kelompok data | Berkas | Ukuran |
|---|---|---|
| Uji sensori hedonik | `sensori_hedonik_kecil`, `sensori_hedonik_besar` | 120 dan 1.440 baris |
| Profil atribut panel terlatih | `sensori_profil_atribut` | 1.728 baris (format panjang) |
| Analisis proksimat | `proksimat_formula_kecil`, `proksimat_formula_besar` | 15 dan 144 baris |
| Mutu selama penyimpanan | `umur_simpan_kecil`, `umur_simpan_besar` | 63 dan 189 baris |
| QC proses produksi | `qc_proses_kecil`, `qc_proses_besar` | 358 dan 14.564 baris |
| Penjualan | `penjualan_harian_besar`, `penjualan_bulanan_kecil`, `penjualan_per_kanal_bulanan` | 11.680, 96, 384 baris |
| Harga komoditas | `harga_komoditas_harian_besar`, `harga_komoditas_bulanan_kecil` | 2.920 dan 96 baris |
| Dataset sengaja "kotor" | `p07_qc_gabungan_KOTOR` | 343 baris (320 pengamatan sebenarnya) |
| Basis data SQLite | `agroindustri_mini.db` | 4 tabel, 2.560 baris |
| Tabel master | `master_produk`, `master_pemasok`, `master_formula_flakes` | 8, 8, 6 baris |
| Berkas kecil Pertemuan 2–5 | `p02_…`, `p03_…`, `p04_…`, `p05_…` | 10–50 baris |

**Mengapa ada versi kecil dan besar.** Versi kecil dipakai saat konsep baru
diperkenalkan, karena mahasiswa harus dapat melihat seluruh isi tabel dan memeriksa
hasilnya dengan tangan. Versi besar dipakai untuk menunjukkan hal yang tidak dapat
dikerjakan dengan nyaman di Excel — 14.564 baris catatan QC, misalnya, diringkas
menjadi satu tabel per mesin hanya dengan satu baris `groupby`.

## 4. Catatan khusus

**Pertemuan 7 — dataset kotor.** Berkas `p07_qc_gabungan_KOTOR` mengandung sembilan
jenis kerusakan yang ditanamkan dengan sengaja: nama kolom tidak rapi, satuan campur,
angka tersimpan sebagai teks, tujuh penanda nilai hilang yang berbeda, kategori tidak
konsisten, empat format tanggal, pencilan mustahil, duplikat penuh dan sebagian, serta
kolom kosong. Daftar lengkapnya ada pada `KAMUS_DATA.md` di folder tersebut. Versi
bersihnya disimpan di subfolder `_kunci_asisten` — **jangan dibagikan kepada mahasiswa
sebelum sesi selesai**.

**Pertemuan 11 — heatmap korelasi.** Data profil sensori dan proksimat sengaja disusun
sebagai gradasi F1→F6 sehingga beberapa pasangan variabel akan tampak berkorelasi kuat.
Sesuai batasan RPS, korelasi hanya boleh disajikan sebagai **alat penjelajahan visual**.
Mahasiswa belum menempuh Statistika; mereka tidak boleh menyimpulkan hubungan sebab-akibat
maupun perbedaan yang "nyata" atau "signifikan" dari data ini.

**Pertemuan 10 — ringkasan numerik dan grafik sebaran.** Data proksimat dibangkitkan
dengan simpangan baku yang realistis untuk analisis laboratorium, sehingga latihan %RSD
menghasilkan angka yang wajar (umumnya di bawah 10%). Beberapa nilai pada
`qc_proses_besar` sengaja menyimpang agar perbedaan median dan rata-rata terlihat, dan
agar histogram serta *boxplot* pada pertemuan yang sama memperlihatkan sesuatu.

**Reproduktibilitas.** Seluruh berkas dibangkitkan oleh empat skrip Python dengan
*seed* tetap (`20260726`). Menjalankan ulang skrip yang sama akan menghasilkan angka
yang persis sama.

## 5. Struktur folder

```
Bank_Dataset/
├── Kamus_Data_Lengkap.xlsx / .csv
├── README.md
├── P02_Dasar_I_Variabel_dan_Operator/
├── P03_Dasar_II_Percabangan/
├── P04_Dasar_III_Perulangan/
├── P05_Dasar_IV_Struktur_Data_dan_Fungsi/
├── P06_Pandas_I_Membaca_Data/
├── P07_Pandas_II_Data_Cleaning/        (berisi _kunci_asisten/)
├── P08_Pandas_III_Groupby_dan_Merge/
├── P09_Konsolidasi_dan_Ujian_Tengah/
├── P10_Ringkasan_Numerik/
├── P11_Visualisasi/
├── P12_SQL/                            (berisi agroindustri_mini.db)
├── P13_Proyek_Kelompok/                (berisi agroindustri_mini.db)
├── P14_Ujian_Praktek/
├── _sumber/                            (kumpulan berkas induk, dipakai gen_05)
├── _skrip_pembangkit/
└── _arsip_16_pertemuan/                (folder versi lama, boleh dihapus)
```

Pertemuan 1 tidak memiliki folder data tersendiri karena sesinya berisi asistensi,
kontrak praktikum, dan demonstrasi pembuka; lembar kerja P01 memakai berkas harga
komoditas dari folder `P11_Visualisasi`.

## 6. Perubahan dari versi 16 pertemuan

Jumlah acara praktikum diubah menjadi 14 tanpa mengurangi cakupan topik. Pemetaan
folder yang berubah:

| Versi 16 pertemuan | Versi 14 pertemuan |
|---|---|
| `P11_Visualisasi_I` + `P12_Visualisasi_II` | `P11_Visualisasi` |
| `P13_SQL_I_SELECT_WHERE_GROUPBY` + `P14_SQL_II_JOIN` | `P12_SQL` |
| `P15_Proyek_Kelompok` | `P13_Proyek_Kelompok` |
| `P16_Ujian_Praktek` | `P14_Ujian_Praktek` |

Folder `P02` sampai `P10` tidak berubah isinya. Folder versi lama dipindahkan ke
`_arsip_16_pertemuan/` dan dapat dihapus bila tidak lagi diperlukan.
