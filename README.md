Berikut adalah README yang telah diperbarui sesuai dengan deskripsi dan konteks yang diberikan untuk proyek **SatriaData2024**:

---

# SatriaData2024 - Text Classification Model with BERT

Repositori ini merupakan salah satu solusi yang digunakan untuk mengikuti **Satria Data 2024 Divisi Big Data Challenge**. Tantangan ini melibatkan prediksi kategori dari sekumpulan data postingan platform X (dulunya dikenal sebagai Twitter) dengan imbalansi data yang signifikan. 

Pada dataset `dataset_penyisihan_bdc_2024.csv`, terdapat 5000 entri data dengan dua kolom utama:
- **Kolom text**: Berisi postingan dari platform.
- **Kolom label**: Berisi kategori dari setiap postingan.

Terdapat delapan kategori yang mencakup: 
- **Sumber Daya Alam**
- **Politik**
- **Demografi**
- **Pertahanan dan Keamanan**
- **Ideologi**
- **Ekonomi**
- **Sosial Budaya**
- **Geografi**

Tantangan utama dalam kompetisi ini adalah mengatasi ketidakseimbangan kelas (imbalansi data), di mana data berlabel "Politik" memiliki jumlah yang jauh lebih banyak dibandingkan label lainnya. Proyek ini menggunakan **model BERT** yang dilatih dengan berbagai teknik untuk mengatasi masalah ini.

## Setup

Struktur folder pada repositori ini adalah sebagai berikut:
- **Folder model**: Menyimpan hasil model yang telah dilatih.
- **Folder data**: Menyimpan dataset yang digunakan untuk pelatihan dan pengujian.
- **Folder logs**: Menyimpan log selama proses pelatihan.
- **Folder collab**: Menyimpan notebook yang akan dijalankan di Google Colab.

### Langkah-langkah untuk menjalankan model:
1. Jalankan notebook `collab/lastday.ipynb` untuk memulai pelatihan model. Model yang dilatih akan disimpan di dalam folder `model`.
2. Setelah model dilatih, jalankan notebook `satdatsubmit.ipynb` untuk melakukan prediksi pada data yang belum memiliki label dan menyimpan hasil dalam format CSV.

**Catatan**: Notebook ini dirancang untuk dijalankan di Google Colaboratory. Jika Anda ingin menjalankan di lingkungan lokal, pastikan untuk menyesuaikan jalur penyimpanan ke drive lokal Anda.

## Teknik yang Digunakan

Dalam proses pelatihan model, beberapa teknik dilakukan untuk mengatasi masalah imbalansi data yang sangat besar. Berikut adalah tahapan dan teknik yang digunakan:

### Data Wrangling
- **Label Encoding**: Mengubah label teks menjadi nilai numerik agar dapat digunakan dalam model pembelajaran mesin.
- **Penghapusan Stopwords**: Menghapus kata-kata yang tidak memiliki nilai signifikan dalam prediksi.
- **TF-IDF**: Menggunakan teknik Term Frequency-Inverse Document Frequency untuk mengubah teks menjadi representasi numerik.
- **Stratified Train-Test Split**: Membagi dataset menjadi data latih dan uji dengan mempertahankan distribusi kelas, sehingga setiap set tetap representatif terhadap keseluruhan data.

### Data Training
- **Transfer Learning dengan BERT**: Menggunakan model BERT yang telah dilatih sebelumnya untuk melakukan fine-tuning pada data spesifik yang relevan dengan tantangan ini.
- **SMOTE**: Menggunakan Synthetic Minority Over-sampling Technique (SMOTE) untuk menangani ketidakseimbangan kelas dengan membuat data sintetis untuk kelas minoritas.
- **Stratified K-Fold Cross-Validation**: Melakukan validasi silang dengan metode K-Fold yang disesuaikan dengan distribusi kelas untuk evaluasi yang lebih akurat.

### Evaluasi
Evaluasi dilakukan dengan menggunakan beberapa metrik untuk memastikan performa model pada data yang tidak seimbang. Metrik yang digunakan antara lain:
- **Balanced Accuracy**: Mengukur akurasi keseluruhan, dengan memperhitungkan keseimbangan kelas.
- **Precision**: Mengukur ketepatan prediksi untuk setiap kelas.
- **Recall**: Mengukur seberapa baik model menemukan data dari kelas yang benar.
- **F1-score**: Menggabungkan precision dan recall untuk memberikan gambaran umum tentang performa model.

## Cara Menjalankan

1. **Clone repositori ini**:
   ```bash
   git clone https://github.com/your-repo/SatriaData2024.git
   cd SatriaData2024
   ```

2. **Instalasi dependensi**:
   Pastikan semua pustaka yang dibutuhkan sudah terpasang, seperti `transformers`, `datasets`, `torch`, `pandas`, `scikit-learn`, `imbalanced-learn`, dan `nltk`. Anda dapat menginstal dependensi dengan:
   ```bash
   pip install transformers datasets torch pandas scikit-learn imbalanced-learn nltk
   ```

3. **Jalankan notebook**:
   Buka notebook `collab/lastday.ipynb` di Google Colab atau Jupyter Notebook. Pastikan untuk memount Google Drive jika menggunakan Colab:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```

4. **Latih model**: Ikuti langkah-langkah di dalam notebook untuk memulai proses pelatihan model.

5. **Hasil prediksi**: Setelah model selesai dilatih, jalankan `satdatsubmit.ipynb` untuk melakukan prediksi pada data yang belum berlabel dan menyimpan hasil prediksi dalam format CSV.

## Catatan Tambahan
Jika Anda menggunakan lingkungan lokal untuk menjalankan notebook ini, pastikan Anda menyesuaikan jalur penyimpanan dataset dan model sesuai dengan struktur direktori di komputer lokal Anda.
