# Kontribusi Anggota Kelompok 8

Repositori: `UTS-DL-Kelompok8` (`https://github.com/dheaawrdhani/UTS-DL-Kelompok8`)

## 1. Dhea Kusuma Wardhani (101032330059)
- **Pengelolaan Repositori & GitHub:** Menyusun struktur folder repositori, mengonfigurasi `.gitignore` agar berkas data mentah/besar (`data/`) tidak ikut ter-commit, mengatur alur commit dan push ke branch `main`, serta menyusun `README.md` dan `kontribusi.md`.
- **Konfigurasi Environment & Integrasi Berkas:** Menyiapkan dan memverifikasi dependensi pada `kode/requirements.txt` (`matplotlib`, `numpy`, `pandas`, `scikit-learn`, `torch`), serta mengintegrasikan berkas luaran dan laporan ke repositori (`LAPORAN UTS.pdf`, `prediksi_klasifikasi.csv`, `prediksi_rul.csv`, `cluster.csv`).
- **Tugas 2 — Regresi RUL Mesin:** Mengembangkan dan menguji eksperimen pemodelan regresi Remaining Useful Life (RUL) pada `kode/tugas2_rul/remaining useful life.ipynb` (GRU 2 lapis dengan window 30 siklus, perbandingan baseline Ridge, GradBoost, dan CNN1D, evaluasi RMSE validasi, serta analisis cakupan interval MC dropout) dan menyiapkan hasil prediksi RUL (`prediksi_rul.csv`).
- **Tugas 3 — Clustering Multimodal Material:** Mengembangkan dan menguji eksperimen clustering pada `kode/tugas3_clustering/clustering.ipynb` (pembelajaran representasi kontrastif InfoNCE, KMeans dengan `k=5`, evaluasi silhouette score, stabilitas ARI, dan perbandingan DEC) serta menyiapkan berkas keluaran `cluster.csv`.

## 2. Fidela Risyunira (101032300001)
- **Tugas 1 — Klasifikasi Multimodal Cacat Produk:** Mengembangkan dan menguji eksperimen klasifikasi cacat produk pada `kode/tugas1_klasifikasi/klasifikasi.ipynb` (arsitektur Cross-Attention Fusion dengan label smoothing `0,1`, evaluasi multi-seed dan macro-F1 validasi, analisis performa per kelas termasuk kelas gores, serta penyusunan hasil prediksi klasifikasi `prediksi_klasifikasi.csv`).
- **Penyusunan Laporan:** Berkontribusi dalam penyusunan dan perapian `LAPORAN UTS.pdf` berdasarkan hasil eksperimen dan analisis tugas kelompok.