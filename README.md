# Coffee Quality — Exploratory Data Analysis & Preprocessing

## Deskripsi
Proyek ini membahas eksplorasi data dan preprocessing pada dataset **Coffee Quality Institute (CQI)**: hasil uji cita rasa (*cupping*) 1.311 sampel kopi Arabika dari 36 negara, termasuk Indonesia. Analisis dilakukan dengan Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy, dan scikit-learn.

Dataset ini dipilih karena masalah kualitas datanya beragam dan realistis, terutama kolom ketinggian kebun yang ditulis bebas (`"1.300 msnm"`, `"de 1600 a 1950"`, `"2800 ft"`, `"12oo"`).

## Tujuan
- Memahami struktur dan karakteristik dataset.
- Menganalisis missing values dan duplikasi (baris maupun kolom).
- Memvisualisasikan distribusi data menggunakan histogram, boxplot, dan QQ plot.
- Mengidentifikasi kandidat outlier menggunakan metode Interquartile Range (IQR).
- Membersihkan kolom teks berantakan (ketinggian, berat karung, tahun panen, tanggal).
- Melakukan imputasi, encoding, dan scaling, lalu memvalidasi hasilnya.

## Tools
- Python
- Google Colab / Jupyter Notebook
- Pandas dan NumPy
- Matplotlib dan Seaborn
- SciPy dan scikit-learn

## Struktur Proyek
- `Coffee_Quality_Preprocessing.ipynb` — notebook analisis dan preprocessing.
- `coffee_quality.csv` — dataset asli.
- `coffee_quality_clean.csv` — dataset hasil preprocessing.
- `README.md` — dokumentasi proyek.

## Cara Menjalankan
1. Unduh notebook dan dataset `coffee_quality.csv`.
2. Buka Google Colab.
3. Unggah notebook dan dataset.
4. Jalankan sel secara berurutan.

## Ringkasan Hasil
- Ukuran data: 1.311 × 44 → 1.310 × 39 (1 sampel dengan skor 0 dihapus karena kesalahan input).
- Kolom ketinggian berhasil diparsing dari puluhan format berbeda; nilai mustahil (hingga 190.164 m) diperbaiki atau ditandai tidak valid.
- Ketinggian yang hilang diisi median per negara dan ditandai dengan kolom `altitude_imputed`.
- Ditemukan korelasi positif lemah antara ketinggian kebun dan skor kopi (r ≈ 0,21).

## Catatan
Kandidat outlier tidak otomatis dihapus. Hanya data yang jelas merupakan kesalahan input yang dibuang; skor rendah yang wajar dan variasi cacat biji tetap dipertahankan. Beberapa aturan parsing (misalnya angka desimal kecil dianggap kilometer) merupakan asumsi dan dijelaskan di dalam notebook.

## Sumber Data
Coffee Quality Institute, dikumpulkan oleh James LeDoux: https://github.com/jldbc/coffee-quality-database
