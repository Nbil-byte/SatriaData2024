# SatriaData2024

Pada Satria Data 2024 Divisi Big Data Challange tersaji sekumpulan data postingan dari platform X atau yang dulunya dikenal dengan tweeter. Pada data/dataset_penyisihan_bdc_2024.csv terdapat 5000 entri data dengan kolom text dan kolom label. Kolom text berisi postingan dan kolom label merupakan kategori dari setiap postingan. Terdapat 8 kategori untuk setiap postingan yaitu Sumber Daya Alam, Politik, Demografi, Pertahanan dan Keamanan, Ideologi, Ekonomi, Sosial Budaya, Geografi. Peserta ditantang untuk membuat model untuk memprediksi data yang belum memiliki label data/dataset_unlabeled_penyisihan_bdc_2024.csv dengan imbalansi data yang sangat besar. Data berlabel politik memiliki jumlah yang sangat banyak jika dibandingkan dengan yang lainnya. Repositori ini adalah satu pendekatan model yang saya gunakan pada mengikuti perlombaan ini.

# Setup
Folder model merupakan letak penyimpanan model, folder data merupakan letak penyimpanan data, folder logs merupakan letak penyimpanan log, dan folder collab merupakan letak file notebook yang akan dijalankan.

Pada repositori ini cukup jalankan notebook collab/lastday.ipynb untuk membuat model dan model akan tersimpan di file model. Kemudian jalankan satdatsubmit.ipynb untuk membuat forecasting cluster dan hasil forecasting akan didapatkan dalam bentuk csv. 


*Notes: notebook menggunakan google colaboratory tolong sesuaikan dengan drive lokal jika ingin melakukan training data

# Teknik yang digunakan
Setelah melakukan data exploratory ditemukan imbalansi yang sangat besar terhadap data dengan label politik yang berjumlah sekitar 3000 entri. Teknik-teknik berikut dilakukan untuk menghasilkan model yang representatif.

Data Wrangling:
  Pengubahan label teks menjadi numerik (label encoding).
  Penghapusan stopwords.
  TF-IDF untuk transformasi teks menjadi representasi numerik.
  Stratified Train-Test Split untuk menjaga distribusi kelas.

Data Training:
  Penggunaan model BERT (transfer learning) untuk fine-tuning model pada data spesifik.
  SMOTE untuk mengatasi masalah ketidakseimbangan kelas.
  Cross-validation dengan Stratified K-Fold untuk evaluasi yang lebih akurat.

Evaluation:
  Menggunakan metrik seperti balanced accuracy, precision, recall, dan F1-score untuk mengevaluasi performa model.
