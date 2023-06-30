# HepatitisCPred
Projek Mandiri membangun Classifier untuk Hepatitis C

By Muhammad Iqbal Aldeena

## Background
Menurut Lembaga Center for Disease Control Amerika Serikat, **Hepatitis C adalah infeksi hati yang disebabkan oleh virus hepatitis C (HCV). Hepatitis C menyebar melalui kontak dengan darah dari orang yang terinfeksi.** Banyak pasien tertular Hepatitis C karena **saling berbagi jarum** atau peralatan lainnya yang digunakan untuk mempersiapkan dan memasukkan obat-obatan kedalam darah.

Hepatitis sendiri terbagi 3, yaitu Hepatitis A, B, dan C. Vaksin sudah tersedia untuk pencegahan Hepatitis A dan B, namun **belum ada vaksin untuk Hepatitis C**. Ini sangat berbahaya, mengingat walau Hepatitis C biasanya berada pada tingkat akut, di sebagian orang virus ini akan naik menjadi tingkat kronis, yang dapat **menyebabkan masalah kesehatan jangka panjang** lainnya, seperti **Fibrosis** dan **Sirosis**.

Lebih dari **50%** orang yang terkena Hepatitis C akan naik ke tingkat kronis. Dan sekitar **5% hingga 25% pasien** akan terkena sirosis dalam 10-20 tahun. Semakin lama seseorang terjangkit dengan Hepatitis C, akan semakin besar kerusakan pada liver, yang menyebabkan fibrosis.

Sumber:
- [CDC : Hepatitis C](https://www.cdc.gov/hepatitis/hcv/index.htm#:~:text=Hepatitis%20C%20is%20a%20liver,to%20prepare%20and%20inject%20drugs.)
- [Hepatitis C dan Fibrosis](https://www.healthline.com/health/hepatitis-c-fibrosis-score#fibrosis-score)

## **Goals**
Tujuan Projek ini adalah membangun sebuah *classifier* yang dapat menentukan kondisi seorang pasien, baik dalam kondisi Hepatitis, Fibrosis, ataupun Sirosis.

## **Data**
Data yang digunakan berisi nilai-nilai hasil laboratorium untuk para donor darah dan pasien Hepatitis.

Keterangan Kolom :
-  Category : Kategori Pasien (0:Donor Darah, 0s: Suspek Donor Darah, 1:Hepatitis, 2:Fibrosis, 3:Cirrhosis)
-  Age : Umur dalam Tahun
-  Sex : Jenis Kelamin
-  ALB : Nilai Albumin
-  ALP : Alkali fosfatase
-  ALT : Alanin transaminase
-  AST : Aspartat Transaminase
-  BIL : Bilirubin
-  CHE : Asetilkolinesterase
-  CHOL : Kolesterol
-  CREA : Kreatinin
-  GGT : Gamma-Glutamil Transferase
-  PROT : Protein

Sumber:
- [Data](https://archive.ics.uci.edu/dataset/571/hcv+data)
- [Informasi Tiap Kolom](https://rstudio-pubs-static.s3.amazonaws.com/782255_662e3ed516fe41a2b89cea20400e3fec.html)


## **Hasil EDA**
- Rata-rata pasien memiliki umur sekitar 47 tahun.
- Persentase pasien dengan umur 30 - 50 cukup besar.
- Kolom yang berdistribusi normal hanyalah kolom CHE dan CHOL.
- Hampir semua kolom tidak memiliki jarak yang terlalu jauh antara mean dan median, terkecuali ALT, AST, CREA, dan GGT.
- Hampir semua kolom kecuali ALB, PROT, dan Age tersebar dengan luas.
- Hampir Tidak ada Korelasi Kategorikal antara Jenis Kelamin dan Kategori Pasien.
- Tidak ada nilai laboratorium yang berkorelasi kuat dengan umur.
- 91.7% data yang ada adalah pasien yang merupakan atau mungkin merupakan seorang Donor Darah.
- Lebih dari 60% pasien dalam data merupakan lelaki.
- pada pria, Tingkat Hepatitis C jauh lebih tinggi dalam bentuk persentase.
- Semua Kolom nilai Laboratorium memiliki Outlier.

## **Hasil Modelling**
Akurasi Model yang didapatkan:
- KNN (5 neighbors)   : 90%
- Naive Bayes         : 90%
- Random Forest       : 90%

Akurasi Model setelah Oversampling:
- **KNN                 : 98%**
- Naive Bayes         : 80%
- Random Forest       : 100% (Overfit)
 
Akurasi Model setelah Box-Cox Transformation:
- KNN                 : 84%
- Naive Bayes         : 88%
- Random Forest       : 92.3%

**Model Terbaik yang ditemukan adalah dengan menggunakan Algoritma K-Nearest Neighbor pada data yang telah di oversample**.
 


