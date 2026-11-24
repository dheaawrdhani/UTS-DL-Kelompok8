# UTS-DL-Kelompok8

# UTS Deep Learning - Kelompok 8

Repositori ini berisi pekerjaan UTS Deep Learning untuk tiga tugas pada data pabrik fiktif: klasifikasi multimodal, regresi sisa umur pakai (RUL), dan clustering multimodal.

**Anggota**

| Nama | NIM |
|---|---|
| Fidela Risyunira | 101032300001 |
| Dhea Kusuma Wardhani | 101032330059 |

## Ringkasan Tugas dan Hasil

| Tugas | Notebook | Pendekatan final | Hasil utama | Keluaran |
|---|---|---|---|---|
| 1. Klasifikasi cacat produk (7 kelas, gambar + sensor) | `klasifikasi.ipynb` | Cross-Attention Fusion + label smoothing 0,1 | Macro-F1 validasi 0,4870 (3 seed: 0,4646 ± 0,0212), pada subset 4.000 sampel | `prediksi_klasifikasi.csv` |
| 2. Regresi RUL mesin press (deret waktu) | `remaining_useful_life.ipynb` | GRU 2 lapis, window 30 siklus | RMSE validasi 20,82 siklus | `prediksi_rul.csv` |
| 3. Clustering tipe material (gambar + spektrum, tanpa label) | `clustering.ipynb` | Representasi kontrastif (InfoNCE) + KMeans, k = 5 | Silhouette 0,482; stabilitas ARI 1,000 antar seed | `cluster.csv` |

Rincian metode, tabel hasil, analisis, dan keterbatasan ada di laporan (`laporan/`).

<<<<<<< HEAD
=======
```

>>>>>>> origin/main
## Persiapan

**Lingkungan.** Notebook dijalankan dengan Python 3.13 dan PyTorch (CPU).

```bash
pip install numpy pandas matplotlib scikit-learn torch
pip install umap-learn   # opsional, untuk visualisasi UMAP di Tugas 3 (jika tidak ada, dipakai t-SNE)
```

**Data.** Letakkan folder `data_uts_dl` (berisi `kamus_data.md`, berkas `.npz`, dan CSV) di komputer masing-masing, lalu ubah path datanya di tiap notebook:

| Notebook | Variabel yang perlu disesuaikan |
|---|---|
| `klasifikasi.ipynb` | `DATA_DIR` (saat ini path absolut Windows, ubah ke lokasi data di komputer kalian) |
| `remaining_useful_life.ipynb` | `DATA_DIR` (default `../../data/data_uts_dl`) |
| `clustering.ipynb` | `DATA_DIR` (default `../../data/data_uts_dl`) |

## Cara Menjalankan

Jalankan sel dari atas ke bawah pada tiap notebook. Seed dibuat tetap (42) agar hasil bisa direproduksi.

- **Tugas 1.** Eksperimen memakai subset stratified 4.000 sampel (3.200 latih, 800 validasi) dan 8 epoch agar cepat di CPU. Untuk memakai data penuh, ubah `SUBSET_N` menjadi jumlah seluruh data latih.
- **Tugas 2.** Pelatihan GRU dan CNN1D memakan waktu sekitar 1 menit per epoch (GRU) di CPU. Turunkan `EPOCHS` atau naikkan `STRIDE` bila terlalu lambat.
- **Tugas 3.** Pelatihan kontrastif (20 epoch) memakan waktu sekitar 17 menit di CPU. Setelah selesai, embedding tersimpan di `hasil_t3/embeddings.npz`; set `RETRAIN = False` untuk memakainya tanpa melatih ulang.

## Catatan dan Keterbatasan

- Tugas 1: skor dihitung pada subset kecil. Kelas `gores` belum terdeteksi (F1 0), prediksi uji sangat condong ke `normal`, dan lini B (60% data uji, hanya 25% data latih) menunjukkan performa lebih rendah.
- Tugas 2: interval ketidakpastian MC dropout terlalu sempit (cakupan 71,5% dari target sekitar 95%). Model final dipilih berdasarkan RMSE; gabungan GRU + CNN1D lebih baik pada skor asimetris.
- Tugas 3: tanpa label, kualitas hanya dinilai dengan metrik internal. Hasil DEC identik dengan KMeans pada data ini.

## Berkas Keluaran

| Berkas | Format |
|---|---|
| `prediksi_klasifikasi.csv` | 16.000 baris: `id_unit`, `kelas` |
| `prediksi_rul.csv` | 300 baris: `id_unit`, `rul` (0 sampai 150) |
<<<<<<< HEAD
| `cluster.csv` | 36.000 baris: `id_sampel`, `cluster` (5 klaster) |
=======
| `cluster.csv` | 36.000 baris: `id_sampel`, `cluster` (5 klaster) |
>>>>>>> origin/main
