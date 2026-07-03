# Customer Transaction Clustering and Classification

## Deskripsi Proyek
Proyek ini bertujuan untuk melakukan segmentasi nasabah berdasarkan karakteristik transaksi menggunakan metode **K-Means Clustering**, kemudian membangun model **Decision Tree** untuk mempelajari hasil segmentasi tersebut.

Dataset terdiri dari **2.512 data transaksi** yang berisi informasi transaksi, profil nasabah, serta aktivitas penggunaan rekening. Hasil clustering menghasilkan dua kelompok utama nasabah yang memiliki karakteristik berbeda berdasarkan nilai transaksi, usia, saldo rekening, dan durasi transaksi.

---

# Dataset

Jumlah Data : **2.512 transaksi**

## Deskripsi Fitur

| Fitur | Deskripsi |
|--------|-----------|
| TransactionID | ID unik transaksi |
| AccountID | ID unik akun nasabah |
| TransactionAmount | Nilai transaksi |
| TransactionDate | Tanggal dan waktu transaksi |
| TransactionType | Jenis transaksi (Credit/Debit) |
| Location | Kota transaksi di Amerika Serikat |
| DeviceID | ID perangkat yang digunakan |
| IP Address | Alamat IP saat transaksi |
| MerchantID | ID merchant |
| AccountBalance | Saldo rekening setelah transaksi |
| PreviousTransactionDate | Tanggal transaksi sebelumnya |
| Channel | Kanal transaksi (Online, ATM, Branch) |
| CustomerAge | Usia nasabah |
| CustomerOccupation | Pekerjaan nasabah |
| TransactionDuration | Lama transaksi (detik) |
| LoginAttempts | Jumlah percobaan login |

---

# Tujuan

- Melakukan segmentasi nasabah menggunakan K-Means Clustering.
- Mengidentifikasi karakteristik masing-masing cluster.
- Menggunakan Decision Tree untuk mempelajari pola hasil clustering.
- Mengevaluasi performa model klasifikasi.

---

# Hasil Clustering

## Cluster 0
### Nasabah Stabil dengan Saldo Relatif Tinggi

### Mean (Scaled)

| Fitur | Nilai |
|--------|------:|
| Transaction Amount | -0.01 |
| Customer Age | 0.02 |
| Transaction Duration | 0.03 |
| Account Balance | 0.01 |

### Mean (Original Value)

| Fitur | Nilai |
|--------|------:|
| Transaction Amount | 255.55 |
| Customer Age | 45.06 tahun |
| Transaction Duration | 121.12 detik |
| Account Balance | 5,142.17 |

### Karakteristik

- Usia nasabah relatif lebih dewasa.
- Memiliki saldo rekening lebih tinggi.
- Durasi transaksi sedikit lebih lama.
- Nilai transaksi relatif stabil.
- Menggambarkan kelompok nasabah yang lebih mapan secara finansial.

---

## Cluster 1
### Nasabah Muda dengan Transaksi Cepat dan Saldo Relatif Rendah

### Mean (Scaled)

| Fitur | Nilai |
|--------|------:|
| Transaction Amount | 0.01 |
| Customer Age | -0.02 |
| Transaction Duration | -0.03 |
| Account Balance | -0.01 |

### Mean (Original Value)

| Fitur | Nilai |
|--------|------:|
| Transaction Amount | 258.15 |
| Customer Age | 44.33 tahun |
| Transaction Duration | 117.30 detik |
| Account Balance | 5,058.81 |

### Karakteristik

- Usia relatif lebih muda dibanding Cluster 0.
- Saldo rekening sedikit lebih rendah.
- Durasi transaksi lebih singkat.
- Nilai transaksi sedikit lebih tinggi.
- Mewakili nasabah dengan aktivitas transaksi yang lebih cepat namun kondisi finansial relatif kurang stabil dibanding Cluster 0.

---

# Hasil Klasifikasi Decision Tree

## Model Awal

| Metric | Class 0 | Class 1 |
|---------|---------|---------|
| Precision | 1.00 | 1.00 |
| Recall | 1.00 | 1.00 |
| F1-Score | 1.00 | 1.00 |

**Accuracy : 100%**

---

## Model Baru

| Metric | Class 0 | Class 1 |
|---------|---------|---------|
| Precision | 1.00 | 1.00 |
| Recall | 1.00 | 1.00 |
| F1-Score | 1.00 | 1.00 |

**Accuracy : 100%**

---

## Model Setelah Hyperparameter Tuning

| Metric | Class 0 | Class 1 |
|---------|---------|---------|
| Precision | 0.78 | 1.00 |
| Recall | 1.00 | 0.72 |
| F1-Score | 0.88 | 0.84 |

**Accuracy : 86%**

---

# Kesimpulan

Proses clustering berhasil membagi data menjadi dua kelompok utama dengan karakteristik yang berbeda:

- **Cluster 0** terdiri dari nasabah yang lebih dewasa, memiliki saldo rekening lebih tinggi, dan durasi transaksi sedikit lebih lama sehingga dapat dikategorikan sebagai nasabah yang lebih stabil secara finansial.
- **Cluster 1** terdiri dari nasabah yang relatif lebih muda dengan saldo rekening lebih rendah, transaksi sedikit lebih besar, serta durasi transaksi lebih singkat.

Model Decision Tree mampu mempelajari hasil clustering dengan sangat baik. Model awal dan model baru menghasilkan akurasi sebesar **100%**, sedangkan model setelah hyperparameter tuning mengalami penurunan performa menjadi **86%**, yang menunjukkan bahwa tuning tidak selalu meningkatkan kinerja model.

---

# Teknologi yang Digunakan

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

# Library

```python
pandas
numpy
matplotlib
seaborn
scikit-learn
```

---

# Hasil Akhir

- Jumlah data: **2.512 transaksi**
- Jumlah cluster: **2**
- Algoritma clustering: **K-Means**
- Algoritma klasifikasi: **Decision Tree**
- Akurasi terbaik Decision Tree: **100%**
