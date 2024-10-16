# SatriaData2024

Pada Satria Data 2024 Divisi Big Data Challange tersaji sekumpulan data postingan dari platform X atau yang dulunya dikenal dengan tweeter. Pada data/dataset_penyisihan_bdc_2024.csv terdapat 5000 entri data dengan kolom text dan kolom label. Kolom text berisi postingan dan kolom label merupakan kategori dari setiap postingan. Terdapat 8 kategori untuk setiap postingan yaitu Sumber Daya Alam, Politik, Demografi, Pertahanan dan Keamanan, Ideologi, Ekonomi, Sosial Budaya, Geografi. Peserta ditantang untuk membuat model untuk memprediksi data yang belum memiliki label data/dataset_unlabeled_penyisihan_bdc_2024.csv dengan imbalansi data yang sangat besar. Data berlabel politik memiliki jumlah yang sangat banyak jika dibandingkan dengan yang lainnya. Repositori ini adalah satu pendekatan model yang saya gunakan pada mengikuti perlombaan ini.

# Setup
Folder model merupakan letak penyimpanan model, folder data merupakan letak penyimpanan data, folder logs merupakan letak penyimpanan log, dan folder collab merupakan letak file notebook yang akan dijalankan.

Pada repositori ini cukup jalankan notebook collab/lastday.ipynb untuk membuat model dan model akan tersimpan di file model. Kemudian jalankan satdatsubmit.ipynb untuk membuat forecasting cluster dan hasil forecasting akan didapatkan dalam bentuk csv. *Notes: notebook menggunakan google colaboratory tolong sesuaikan dengan drive lokal jika ingin melakukan training data  
