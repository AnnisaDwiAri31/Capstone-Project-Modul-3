[sumber data bike sharing](http://capitalbikeshare.com/system-data)
## **Contents** 

1. Business Problem Understanding
2. Data Understanding
3. Data Preprocessing
4. Modeling
5. Conclusion
6. Recommendation

## **Business Problem Understanding**

### **Context**

Sistem *sharing* sepeda merupakan generasi baru dari penyewaan sepeda tradisional di mana seluruh proses, mulai dari keanggotaan, penyewaan, hingga pengembalian, menjadi otomatis. Melalui sistem ini, pengguna dapat dengan mudah menyewa sepeda dari lokasi tertentu dan mengembalikannya di lokasi lain. Saat ini, terdapat lebih dari 500 program berbagi sepeda di seluruh dunia yang terdiri dari lebih dari 500 ribu sepeda. Saat ini, minat besar ada pada sistem ini karena peran pentingnya dalam masalah lalu lintas, lingkungan, dan kesehatan.

Selain dari aplikasi dunia nyata yang menarik dari sistem *sharing* sepeda, karakteristik data yang dihasilkan oleh sistem-sistem ini membuat menarik untuk dilakukan penelitian. Berbeda dengan layanan transportasi lain seperti bis atau kereta bawah tanah, durasi perjalanan, titik keberangkatan, dan titik kedatangan secara eksplisit tercatat dalam sistem-sistem ini. Fitur ini menjadikan sistem *sharing* sepeda sebagai jaringan sensor virtual yang dapat digunakan untuk mendeteksi mobilitas di kota. Oleh karena itu, diharapkan bahwa peristiwa-peristiwa penting di kota dapat dideteksi dengan memantau data-data ini.

### **Problem statement**

Dalam era sistem sharing sepeda yang otomatis, di mana pengguna dapat dengan mudah menyewa dan mengembalikan sepeda dari lokasi tertentu, data yang dihasilkan oleh sistem ini menjadi sumber informasi berharga untuk analisis mobilitas di kota. Namun, tantangan utama yang dihadapi adalah meningkatkan kinerja model prediksi untuk membantu dalam pengelolaan dan pengoptimalan layanan sepeda berbagi. Dengan melibatkan fitur-fitur seperti durasi perjalanan, titik keberangkatan, titik kedatangan, serta faktor-faktor cuaca, pengembangan model prediksi yang akurat dapat memberikan wawasan penting tentang mobilitas kota dan memfasilitasi pengambilan keputusan yang lebih efektif

### **Goals**

Tujuan ini dapat membantu dalam meningkatkan efisiensi, ketersediaan, dan kualitas layanan bike sharing serta memberikan manfaat yang lebih besar bagi pengguna dan komunitas secara keseluruhan.

### **Metric Evaluation**

Untuk mengevaluasi kinerja model, akan digunakan metrik evaluasi standar untuk regresi, termasuk Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), dan Mean Absolute Percentage Error (MAPE). Metrik-metrik ini akan digunakan untuk membandingkan kinerja model sebelum dan sesudah penyetelan. Selain itu, akan dilakukan evaluasi menggunakan skor cross-validation untuk memvalidasi kinerja model secara keseluruhan. Hasil evaluasi ini akan memberikan wawasan tentang seberapa baik model dapat memprediksi jumlah total sepeda yang dipinjam, serta membantu dalam menentukan apakah penyetelan model telah berhasil meningkatkan kinerjanya.

- Sebelum tuning, model DecisionTreeRegressor dan RandomForest menunjukkan kinerja yang cukup baik, tetapi dengan nilai RMSE, MAE, dan MAPE yang beragam.
- Setelah dilakukan tuning, model RandomForest mengalami peningkatan kinerja yang signifikan dengan memperoleh parameter terbaik yaitu {'n_estimators': 200, 'max_features': 'sqrt', 'max_depth': 20}.
- Skor cross-validation yang tinggi, mencapai 0.693, menunjukkan bahwa model RandomForest yang disesuaikan mampu memprediksi dengan akurat.
- Prediksi model setelah tuning memiliki rentang nilai yang luas, memberikan fleksibilitas yang baik dalam menghadapi berbagai situasi.
- Fitur yang paling berpengaruh adalah hr,temp dan hum
Secara keseluruhan, proses tuning berhasil meningkatkan kinerja model RandomForest secara substansial, menghasilkan model yang lebih dapat diandalkan dalam memprediksi data.
