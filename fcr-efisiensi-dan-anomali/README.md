# Analisis Efisiensi FCR dan Deteksi Anomali pada Peternakan Layer Periode 2023

**Disusun oleh:** [Jefirel.A.P]  
**Tanggal:** [01/03/2026]  
**Periode Data:** 1 Januari 2023 – 30 Juni 2024  
**Jumlah Data:** 42.982 baris  
**Jumlah Kandang:** 80 kandang (20 per lokasi)

---

## Ringkasan Eksekutif

Laporan ini menyajikan analisis efisiensi pakan (FCR) dan deteksi anomali pada 80 kandang ayam petelur yang tersebar di 4 lokasi (Dataran Tinggi, Dataran Sedang, Dataran Rendah, Pesisir). Data mencakup periode 1,5 tahun dengan total 42.982 observasi.

**Temuan Utama:**
- Rata-rata FCR keseluruhan: **2,78** (dalam rentang normal 2,2–2,8)
- Tingkat anomali FCR: **0,31%** (369 data terdeteksi sebagai outlier)
- Total kerugian finansial: **Rp5,38 Miliar**
- **Lokasi Pesisir** memiliki FCR terendah (2,76) dan kerugian per kg telur terendah (Rp1.923/kg)
- **Lokasi Dataran Tinggi** memiliki FCR tertinggi (2,79) dan kerugian per kg telur tertinggi (Rp2.035/kg)

**Rekomendasi Prioritas:**
1. Intervensi di **Dataran Tinggi** (kerugian per kg tertinggi dan FCR tertinggi)
2. Investigasi anomali di **Pesisir** (jumlah anomali tertinggi: 129 data)
3. Benchmark praktik terbaik antar lokasi untuk menyamakan efisiensi

---

## Temuan Utama

### 1. Statistik Deskriptif Dataset

| **Variabel** | **Mean** | **Std** | **Min** | **Max** |
|--------------|----------|---------|---------|---------|
| Umur (minggu) | 55,7 | 22,2 | 16,0 | 94,0 |
| Populasi | 1.499 | 2,7 | 1.470 | 1.500 |
| Mortalitas | 0,01 | 0,10 | 0 | 3 |
| Produksi Telur | 1.045 | 188 | 525 | 1.392 |
| Pakan (kg) | 168,1 | 10,6 | 145,0 | 191,1 |
| Suhu (°C) | 26,6 | 4,0 | 18,0 | 38,0 |
| **FCR** | **2,78** | **0,57** | **1,98** | **5,00** |
| HDP (%) | 69,7 | 12,5 | 35,0 | 92,8 |

### 2. Perbandingan FCR Antar Lokasi

| **Lokasi** | **Rata-rata FCR** | **Std** | **Min** | **Max** |
|------------|-------------------|---------|---------|---------|
| Dataran Rendah | 2,786 | 0,568 | 1,981 | 4,997 |
| Dataran Sedang | 2,776 | 0,567 | 1,986 | 5,000 |
| Dataran Tinggi | 2,788 | 0,568 | 1,984 | 4,997 |
| Pesisir | **2,758** | 0,572 | 1,990 | 4,995 |

### 3. Hasil Uji Tukey HSD

| **Pasangan** | **Selisih** | **p-adj** | **Reject** | **Kesimpulan** |
|--------------|-------------|-----------|------------|----------------|
| Rendah vs Sedang | -0,0101 | 0,5652 | False | Tidak berbeda signifikan |
| Rendah vs Tinggi | +0,0017 | 0,9964 | False | Tidak berbeda signifikan |
| Rendah vs Pesisir | **-0,0280** | **0,0017** | **True** | Pesisir berbeda (lebih baik) |
| Sedang vs Tinggi | +0,0118 | 0,4289 | False | Tidak berbeda signifikan |
| Sedang vs Pesisir | -0,0180 | 0,0947 | False | Tidak berbeda signifikan |
| Tinggi vs Pesisir | **-0,0297** | **0,0007** | **True** | Pesisir berbeda (lebih baik) |

**Kesimpulan:** 
- **Pesisir** secara signifikan lebih efisien daripada **Dataran Rendah** dan **Dataran Tinggi**
- Ketiga lokasi lainnya (Rendah, Sedang, Tinggi) tidak berbeda signifikan satu sama lain
- Urutan FCR (terbaik → terburuk): **Pesisir > Sedang > Rendah > Tinggi**

### 4. Analisis Korelasi

| **Variabel** | **Korelasi dengan FCR** | **Interpretasi** |
|--------------|-------------------------|------------------|
| Produksi Telur | **-0,93** | Sangat kuat negatif → Semakin tinggi produksi, semakin rendah FCR |
| HDP | **-0,93** | Sangat kuat negatif → Semakin tinggi HDP, semakin rendah FCR |
| Umur | **+0,44** | Positif sedang → Semakin tua ayam, FCR cenderung naik |
| Populasi | **-0,30** | Negatif lemah → Populasi lebih besar sedikit menurunkan FCR |
| Suhu | -0,00 | Tidak ada korelasi dengan FCR |

### 5. Deteksi Anomali FCR

- **Persentase anomali FCR:** 0,31% (369 data)
- **Distribusi anomali per lokasi:**

| **Lokasi** | **Jumlah Anomali** |
|------------|---------------------|
| Pesisir | 129 |
| Dataran Rendah | 86 |
| Dataran Tinggi | 82 |
| Dataran Sedang | 72 |

**Pesisir** menjadi lokasi dengan anomali FCR terbanyak, mengindikasikan adanya fluktuasi performa yang perlu diinvestigasi.

---

## Analisis Kerugian Finansial

### Parameter:
- Target FCR industri: **2,5**
- Harga pakan: **Rp7.000/kg**
- Rumus kerugian: `(FCR - target) × total_telur_kg × harga_pakan`

### Total Kerugian

| **Metrik** | **Nilai** |
|------------|-----------|
| **Total Kerugian** | **Rp5.375.567.120** |
| Rata-rata per kandang | Rp67.194.589 |
| Rata-rata per hari | Rp9.807.970 |

### Kerugian per Lokasi

| **Lokasi** | **Kerugian Aktual (Rp)** | **Persentase** |
|------------|--------------------------|----------------|
| Dataran Tinggi | 1.430.077.000 | 26,60% |
| Dataran Sedang | 1.379.273.000 | 25,66% |
| Dataran Rendah | 1.331.738.000 | 24,77% |
| Pesisir | 1.234.480.000 | 22,96% |
| **TOTAL** | **5.375.567.120** | **100%** |

### Kerugian per kg Telur (Efisiensi Intrinsik)

| **Lokasi** | **Kerugian per kg (Rp/kg)** | **Peringkat Efisiensi** |
|------------|-----------------------------|------------------------|
| **Pesisir** | **1.923** | 🥇 **Paling Efisien** |
| Dataran Sedang | 1.996 | 🥈 |
| Dataran Rendah | 2.019 | 🥉 |
| Dataran Tinggi | 2.035 | 4️⃣ **Paling Boros** |

### Interpretasi Gabungan

| **Lokasi** | **FCR** | **Kerugian per kg** | **Kerugian Aktual** | **Kesimpulan** |
|------------|---------|---------------------|---------------------|----------------|
| **Dataran Tinggi** | Tertinggi (2,788) | Tertinggi (Rp2.035) | Tertinggi (Rp1,43 M) | **Prioritas utama** untuk intervensi |
| **Dataran Rendah** | Sedang (2,786) | Sedang (Rp2.019) | Sedang (Rp1,33 M) | Perlu evaluasi |
| **Dataran Sedang** | Rendah (2,776) | Rendah (Rp1.996) | Tinggi (Rp1,38 M) | Volume besar, efisiensi sedang |
| **Pesisir** | Terendah (2,758) | Terendah (Rp1.923) | Terendah (Rp1,23 M) | **Benchmark** untuk lokasi lain |

---

##  Rekomendasi Bisnis

| **Prioritas** | **Lokasi** | **Dasar Data** | **Tindakan yang Disarankan** | 
|--------------|------------|----------------|------------------------------|
| 🔴 **1** | **Dataran Tinggi** | FCR tertinggi, kerugian per kg tertinggi, kerugian aktual tertinggi | Audit manajemen pakan, kualitas air, kesehatan ternak. Evaluasi ventilasi dan kepadatan kandang. |
| 🟡 **2** | **Pesisir** | Jumlah anomali tertinggi (129 data) | Investigasi penyebab fluktuasi FCR (pakan tidak konsisten, gangguan lingkungan). Stabilkan performa. |
| 🟡 **3** | **Dataran Rendah & Sedang** | Kerugian aktual besar, efisiensi sedang | Adopsi praktik terbaik dari Pesisir. Standarisasi SOP pemberian pakan. |
| 🟢 **4** | **Semua Lokasi** | - | Monitoring rutin FCR dan deteksi anomali menggunakan metode IQR. |

### Target Penurunan FCR

Jika FCR di semua lokasi dapat diturunkan ke level Pesisir (2,758):

| Lokasi | Selisih FCR | Total Telur (kg) | Penghematan Pakan (kg) | Penghematan (Rp) |
|--------|-------------|------------------|------------------------|------------------|
| Dataran Tinggi | 0,030 | 702.570 | 21.077 | 147.539.000 |
| Dataran Rendah | 0,028 | 659.750 | 18.473 | 129.311.000 |
| Dataran Sedang | 0,018 | 690.903 | 12.436 | 87.052.000 |
| **TOTAL** | - | - | **51.986 kg** | **Rp363.902.000** |

*Catatan: Perhitungan menggunakan data aktual selama periode 1,5 tahun (Jan 2023 – Jun 2024). Angka telah dibulatkan untuk keperluan penyajian.*

---

##  Langkah Selanjutnya

| **Minggu** | **Aktivitas** | **Penanggung Jawab** |
|------------|---------------|----------------------|
| 1 | Validasi data dan audit lapangan di Dataran Tinggi | Tim Teknis |
| 2–3 | Analisis faktor penyebab anomali di Pesisir | Tim Analisis |
| 4 | Implementasi perbaikan pilot di 5 kandang prioritas | Manajer Kandang |
| 5–8 | Monitoring dan evaluasi | Tim Operasional |
| 9 | Rencana ekspansi ke semua lokasi | Manajemen |

---

##  Lisensi

Laporan ini dan seluruh kode analisis yang menyertainya dilisensikan di bawah **MIT License**.

Kontak:
📧 [jefirelap@gmail.com]
🔗 linkedin.com/in/Jefirelap


