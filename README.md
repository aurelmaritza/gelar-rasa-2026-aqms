# Dari Akar ke Kejernihan

Analisis pencemaran udara dan dampaknya terhadap kesehatan di 27 stasiun pemantauan Indonesia, 2024–2026. Repositori ini berisi seluruh proses pengolahan data untuk cabang Dashboard Analysis Gelar Rasa 2026: profiling, pembersihan, pembentukan tabel untuk Tableau, *exploratory data analysis*, dan analisis untuk kelima tujuan.

**Tim Adek gamau ikut** (UPN “Veteran” Jawa Timur): Fildzah Syarafina Sumantri, Aurel Maritza Maheswari Ahmad, Laras Ayu Pradanti

**Dashboard:** [tautan Tableau Public]

## Isi

| Notebook | Isi |
|---|---|
| `01_profiling.ipynb` | Ukuran data, satuan, status `qc_flag`, nilai tidak wajar, dan cakupan waktu tiap file |
| `02_pembersihan.ipynb` | Konversi satuan, aturan status sensor, sensor macet, penyeragaman waktu, pengeluaran JMB-02 |
| `03_tabel_siap_pakai.ipynb` | Tabel lokasi, udara per jam, udara harian (ISPU dan baku mutu), kesehatan harian, ekspor `.hyper`, diagram relasi, status sensor |
| `04_eda.ipynb` | Sebaran polutan, pelampauan baku mutu, korelasi antarvariabel, sifat data kesehatan |
| `05_t1_kondisi_tren.ipynb` | Tujuan 1: kondisi dan tren kualitas udara |
| `06_t2_waktu_wilayah_kritis.ipynb` | Tujuan 2: jam, hari, bulan, dan episode kabut asap |
| `07_t3_faktor_pengaruh.ipynb` | Tujuan 3: cuaca, lalu lintas, jarak ke jalan, tipe lokasi, Gradient Boosting |
| `08_t4_dampak_kesehatan.ipynb` | Tujuan 4: regresi quasi-Poisson per RS, meta-analisis, efek jeda, episode asap |
| `09_t5_kecukupan_jaringan.ipynb` | Tujuan 5: keandalan, jarak antarstasiun, skor prioritas, rekomendasi |
| `10_angka_dashboard_dan_laporan.ipynb` | Perhitungan ulang angka di kartu dashboard dan laporan |

Hasil berupa ringkasan Excel dan gambar ada di folder `hasil/`.

## Menjalankan ulang

1. Letakkan dataset dari panitia (27 file `*_AQMS.csv`, `HLT-01_health_outcomes_daily.csv`, `sites.csv`, `sensors.csv`, `hospitals.csv`, `metadata_sensors.csv`, `metadata_dates.csv`) di `data/raw/`. Dataset tidak disertakan di repositori ini.
2. Pasang pustaka: `pip install -r requirements.txt`
3. Jalankan notebook di folder `notebooks/` sesuai urutan nomor. Notebook 02 dan 03 mengisi `data/clean/` dan `data/mart/`, yang dipakai notebook berikutnya dan menjadi sumber data dashboard.

Data yang dipakai adalah dataset sintetis dari panitia, sehingga besaran efek tidak mewakili kondisi nyata.
