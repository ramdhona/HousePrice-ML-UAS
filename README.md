
# Prediksi Harga Rumah dengan Model Artificial Neural Network (ANN)

**Nama Proyek:** Prediksi Harga Rumah Menggunakan Model Kecerdasan Buatan (Artificial Neural Network)

**Nama :** Dwi Ramdhona

**NIM :** A11.2022.14033  

**Mata Kuliah :** Pembelajaran Mesin

**Kelompok :** A11.4406

## 1. Ringkasan dan Permasalahan Proyek

### Permasalahan
Industri real estate menghadapi masalah prediksi harga rumah.  Banyak faktor memengaruhi harga rumah, termasuk lokasi, ukuran, dan jumlah kamar tidur. Model prediksi harga yang akurat sangat penting untuk menentukan nilai properti dan membantu pembeli atau penjual membuat keputusan yang lebih baik.

### Tujuan Proyek
Tujuan dari proyek ini adalah:
- Mengembangkan model kecerdasan buatan (Artificial Neural Network/ANN) untuk memprediksi harga rumah berdasarkan berbagai fitur rumah.
- Menggunakan dataset harga rumah untuk melatih dan mengevaluasi model.
- Menghasilkan prediksi harga rumah dalam mata uang USD dan IDR.

### Alur Penyelesaian
Proyek ini diselesaikan dengan langkah-langkah berikut:
1. **Persiapan Data**: Memuat dataset, melakukan analisis eksplorasi data (EDA), dan praproses data.
2. **Pembangunan Model**: Membangun dan melatih model jaringan syaraf tiruan (ANN).
3. **Evaluasi Model**: Mengevaluasi performa model menggunakan data uji dan menghitung error.
4. **Prediksi dan Visualisasi**: Menggunakan model untuk memprediksi harga rumah berdasarkan input dari pengguna dan menampilkan perbandingan antara harga aktual dan prediksi.

#### Bagan Alur Penyelesaian Proyek:
![bagan ML drawio](https://github.com/user-attachments/assets/0d0a4e4f-cecc-4c89-b4a9-86cd3fee7cf5)

## 2. Penjelasan Dataset, EDA, dan Proses Features Dataset

### Penjelasan Dataset
Dataset yang digunakan dalam proyek ini adalah dataset harga rumah yang mencakup berbagai fitur rumah. Setiap baris dalam dataset mewakili sebuah rumah dan memiliki fitur-fitur berikut:
- **bedrooms**: Jumlah kamar tidur
- **bathrooms**: Jumlah kamar mandi
- **sqft_living**: Ukuran rumah (sqft)
- **sqft_lot**: Ukuran lahan (sqft)
- **floors**: Jumlah lantai
- **waterfront**: Apakah rumah berada di dekat laut (1 jika ya, 0 jika tidak)
- **view**: Skor view (0-4)
- **condition**: Kondisi rumah (1-5)
- **sqft_above**: Ukuran rumah di atas tanah (sqft)
- **sqft_basement**: Ukuran ruang bawah tanah (sqft)
- **yr_built**: Tahun dibangun
- **yr_renovated**: Tahun renovasi (0 jika tidak ada)

### Eksplorasi Data (EDA)
Proses eksplorasi data (EDA) dimulai dengan:
1. **Info Data**: Mengecek informasi dasar tentang dataset, seperti tipe data dan jumlah data.
2. **Statistik Ringkasan**: Menampilkan statistik deskriptif seperti rata-rata, standar deviasi, dan nilai ekstrim untuk setiap fitur numerik.
3. **Visualisasi Korelasi**: Matriks korelasi digunakan untuk menganalisis hubungan antar fitur numerik.
4. **Nilai yang Hilang**: Mengecek nilai yang hilang dan persentase dari setiap kolom.

### Proses Features Dataset
- Kolom non-numerik dihapus untuk memudahkan analisis korelasi.
- Fitur numerik dipilih untuk digunakan dalam model prediksi harga rumah.
- Nilai yang hilang dihitung dan diatasi dengan penghapusan atau imputasi.

## 3. Proses Learning / Modeling

### Pembangunan Model
Model yang digunakan adalah **Artificial Neural Network (ANN)**, yang terdiri dari beberapa lapisan:
1. **Input Layer**: Memiliki jumlah unit yang sesuai dengan jumlah fitur numerik pada dataset.
2. **Hidden Layer**: Terdiri dari 1 lapisan tersembunyi dengan 32 unit menggunakan fungsi aktivasi ReLU.
3. **Output Layer**: Output model terdiri dari 1 unit yang memprediksi harga rumah.

### Pelatihan Model
- **Optimizer**: Optimizer yang digunakan adalah Adam, yang sering digunakan untuk jaringan syaraf tiruan.
- **Loss Function**: Fungsi kehilangan yang digunakan adalah Mean Squared Error (MSE), yang mengukur seberapa besar kesalahan prediksi harga rumah.
- **Epochs**: Model dilatih selama 100 epoch dengan batch size 32 untuk memastikan pelatihan yang optimal.
- **Validasi**: Data uji digunakan untuk validasi model, yang memastikan bahwa model tidak overfitting.

## 4. Performa Model

### Evaluasi Model
Setelah model dilatih, data uji yang dipisahkan digunakan untuk mengevaluasi kinerjanya.  Untuk menghitung kesalahan model, "Mean Squared Error (MSE)" digunakan untuk menghitung hasil evaluasi.

- **Test Loss**: Nilai kerugian pada data uji, yang menunjukkan seberapa baik model dalam memprediksi harga rumah.
- **Visualisasi**: Perbandingan antara harga rumah yang sebenarnya dengan harga rumah yang diprediksi divisualisasikan dalam bentuk plot **Actual vs Predicted Prices**.

### Hasil Prediksi
Setelah model selesai dilatih dan diuji, User dapat memasukkan spesifikasi rumah yang diinginkan untuk mendapatkan prediksi harga rumah.

## 5. Diskusi Hasil dan Kesimpulan

### Diskusi
- Model ANN yang dibangun menunjukkan kemampuan untuk memprediksi harga rumah dengan cukup baik. Namun, terdapat kesalahan prediksi yang dapat terjadi akibat kompleksitas data dan keterbatasan model.
- Visualisasi perbandingan harga aktual dan prediksi memperlihatkan bahwa model memberikan hasil yang cukup mendekati harga yang sebenarnya, meskipun masih ada ruang untuk perbaikan.

### Kesimpulan
- Model ANN berhasil digunakan untuk memprediksi harga rumah berdasarkan spesifikasi rumah.
- Model ini dapat digunakan dalam sektor real estate untuk membantu dalam penentuan harga rumah atau sebagai alat bantu dalam perencanaan investasi.

## 6. Instruksi Penggunaan

1. Pastikan Anda memiliki pustaka yang diperlukan, seperti `pandas`, `numpy`, `matplotlib`, `seaborn`, dan `tensorflow`. Anda dapat menginstalnya dengan menggunakan pip:
   ```bash
   pip install pandas numpy matplotlib seaborn tensorflow
   ```

2. Pastikan dataset `data.csv` tersedia di direktori yang sama dengan file notebook.

3. Jalankan file `index.ipynb` dan masukkan informasi rumah ketika diminta untuk mendapatkan prediksi harga rumah dalam USD dan IDR.

4. Anda akan melihat harga yang diprediksi dalam USD dan IDR yang dapat digunakan untuk evaluasi atau tujuan lainnya.

---


