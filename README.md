# Capstone-3

Project Introduction

Hunian adalah bagian yang tidak terpisahkan dari kehidupan manusia. Maslow dalam teori hierarchy of needs (1954) mengategorikan kebutuhan hunian sebagai salah satu kebutuhan fisiologis paling dasar yang harus dipenuhi manusia sebelum kebutuhan-kebutuhan lainnya. Perorangan atau perusahaan biasanya membuat penawaran apartemen (unit) di platform dengan menentukan harga apartemen mereka. Cara itu cukup sulit bagi pemilik apartemen untuk menyesuaikan dengan harga pasar. Jika harganya terlalu tinggi dibandingkan dengan harga pasar, tentu akan sulit untuk melakukan penjualan. Sebaliknya, jika terlalu rendah, pemilik akan kesulitan untuk mendapatkan keuntungan yang maksimal. Daegu adalah kota terbesar di wilayah Gyeongsang Utara. Selama Dinasti Joseon, kota ini menjadi pusat administratif, ekonomi, dan budaya seluruh wilayah Gyeongsang, yang sebagian besar perannya sekarang diambil alih oleh Busan di Gyeongsang Selatan. Saat ini, Daegu merupakan wilayah metropolitan terbesar ke-4 dalam hal populasi, dan masih menjadi kota perdagangan terbesar ke-3 di Korea Selatan.

Penentuan harga penjualan apartemen di Daegu banyak dipengaruhi oleh beberapa atribut atau spesifikasi dari aset tersebut, misalnya: Jenis lorong pada apartemen, durasi waktu ke stasiun kereta bawah tanah, nama stasiun kereta bawah tanah, jumlah fasilitas yang terdekat (ETC), jumlah fasilitas kantor publik, jumlah universitas terdekat, jumlah tempat parkir basement, tahun pembangunan apartemen, jumlah fasilitas apartemen yang ditawarkan dalam aplikasi/platform serta luasan apartemen. Hal inilah yang menyebabkan proses prediksi harga akan menjadi lama. Disinilah Machine Learning berperan untuk mempermudah proses prediksi harga jual apartemen. Salah satu peran dalam Machine Learning adalah kemampuan untuk belajar dari data transaksi sebelumnya dan ini akan menjadi model yang akan dapat digunakan untuk memberikan prediksi harga jual apartemen.

Berdasarkan permasalahan tersebut, akan dibuatkan sebuah model Machine Learning yang bertujuan untuk mendapatkan prediksi harga yang paling memadai, lebih cepat dan dapat diandalkan agar menjadi referensi harga yang memberikan keuntungan maksimal bagi penjual aset apartemen berdasarkan fitur-fitur yang relevan. Model ini akan dinilai menggunakan Mean Absolut Error (MAE), dengan target MAE kurang dari 50.000 Won. Stakeholder utama adalah agen real estat yang mencari estimasi harga yang dapat diandalkan untuk transaksi properti di Daegu, Kor-sel.

Berikut adalah rangkuman dari pemodelan yang telah dibentuk:
Pemilihan Model Terbaik: Dari 12 model yang dievaluasi, model terbaik dipilih berdasarkan metrik MSE, RMSE, MAE, MAPE dan R2. Model yang terpilih adalah Gradient Boosting Regressor.
Parameter Hyperparameter Terbaik:
learning_rate: 0.05
max_depth: 3
n_estimators: 300
min_samples_leaf: 1
min_samples_split: 15
Kinerja Model pada Data Uji:

Skor R2: 0.8071830685175123,
menunjukkan bahwa model dapat memprediksi sekitar 80.71% variabilitas dalam harga apartemen di Daegu, mengindikasikan hubungan yang kuat antara variabel independen (fitur) dan variabel dependen (harga rumah). Ini menunjukkan bahwa prediksi model sangat akurat dan andal, sehingga berguna untuk memprediksi nilai rumah.

Mean Absolute Error (MAE): 37736.72530588421,
menunjukkan rata-rata kesalahan absolut prediksi harga apartemen adalah sekitar 37.736 Won. Nilai MAE yang lebih rendah diinginkan, dan 37.736 Won adalah relatif rendah, mengindikasikan bahwa prediksi model umumnya dekat dengan harga sebenarnya.

Root Mean Squared Error (RMSE): 46333.2169264815,
menunjukkan akar kuadrat dari rata-rata kesalahan kuadrat prediksi harga apartemen adalah sekitar 46.333 Won. Mirip dengan MAE, nilai RMSE yang lebih rendah diinginkan, dan 46.333 Won adalah relatif rendah, mengindikasikan bahwa prediksi model memiliki dispersi atau penyebaran yang rendah di sekitar harga sebenarnya.

Model Gradient Boosting Regressor yang dipilih menunjukkan performa yang baik dengan R2 yang tinggi, mengindikasikan prediksi harga apartemen yang cukup akurat. Nilai MAE dan RMSE menunjukkan tingkat kesalahan yang dapat diterima mengingat kompleksitas dan variabilitas harga apartemen di Daegu.

Kelemahan model:
Dari hasil hyperparameter tunning menunjukan perubahan score yang tidak signifikan lebih baik dari sebelum tunning sehingga pada masa yang akan datang perlu untuk meningkatkan score setelah tunning dengan metode yang lebih advanced.

Ukuran data pada data set yang digunakan pada model ini terbatas atau dapat dikatakan hanya sedikit dibandingkan rentang waktu yang sangat panjang (sejak tahun dibangunnya apartemen yang sudah tua) sehingga ukuran data yang lebih kecil dibandingkan penggunaan model untuk memprediksi pada jangka waktu yang panjang ke masa depan akan menurunkan performa akurasi model jika ukuran data set model < perkembangan data set kemasa berikutnya.

Model ini tidak dapat digunakan jika terdapat perubahan faktor eksternal yang secara aktualnya dapat mempengaruhi harga jual yang terjadi dilapangan, selain itu, kenaikan harga jual apartemen dari tahun ke tahun tidak dapat diprediksi jika tidak ada fitur yang berpengaruh terhadap pertumbuhan harga jual seperti inflasi, demografi, pajak dan sebagainya karena keterbatasan fitur yang digunakan pada model ini.

kesimpulan bisnis:
jika sebelumnya dengan begitu cukup sulit bagi pemilik apartemen untuk menyesuaikan dengan harga pasar. Jika harganya terlalu tinggi dibandingkan dengan harga pasar, tentu akan sulit untuk melakukan penjualan. Sebaliknya, jika terlalu rendah, pemilik akan sulit mendapatkan keuntungan yang maksimal maka dengan adanya Machine Learning yang dibuat ini dapat memberikan harga yang cukup akurat dengan berbagai fitur yang di perhitungkan saat ini dengan estimasi rata-rata selisih akurasi harga jual hanya 37.736 Won

Rekomendasi:
Rekomendasi model:
Melakukan Iterative Feature Selection, Kelebihan dari Iterative Feature Selection adalah lebih banyak kombinasi model yang kita coba. Metode ini berpotensi untuk dapat mengungguli metode feature selection lainnya untuk mendapatkan model yang lebih baik.

Penambahan ukuran data set serta fitur yang Lebih Komprehensif dapat meningkatkan akurasi dan masa pakai dari model yang dibuat. Menambahkan lebih banyak fitur relevan terkait harga apartemen dapat membantu meningkatkan akurasi model. Penambahan fitur-fitur yang relevan juga perlu mempertimbangkan dinamika faktor internal maupun eksternal yang dapat berubah setiap saat sesuai prinsip jual beli properti hunian seperti apartemen.

selain itu, model yang telah dibuat hendaknya dapat dilakukan update data secara periodik dan perlakuan hyperparameter tunning kembali.

Rekomendasi bisnis dan Estimasi keuntungan bisnis:
Selain keuntungan yang akan didapatkan pada penawar adalah berkurangnya biaya dan waktu untuk melakukan estimasi harga apartemen di Daegu yang ingin tawarkan kepada calon pembeli, estimasi keuntungan bagi bisnis karena penerapan Machine Learning ini adalah maksimum profit bagi penjual apartemen.

Berdasarkan fakta Saat ini bahwa Daegu merupakan wilayah metropolitan terbesar ke-4 dalam hal populasi dan masih menjadi kota perdagangan terbesar ke-3 di Korea Selatan selain itu, kelompok usia dewasa muda menjadi kelompok usia paling mendominasi dibandingkan kelompok usia lainnya dan Kelompok usia inilah yang dijadikan target pasar hunian karena minat yang cukup tinggi dalam memiliki hunian sehingga pangsa pasar dan permintaan terhadap kepemilikan apartemen juga tinggi.

jika dalam pemodelan 3 fitur yang paling mempengaruhi pembentukan harga jual yaitu jenis Hallway dengan teras, ukuran apartemen yang luas serta tahun dibangunnya maka rekomendasi bisnis yang dapat diberikan adalah melakukan renovasi terhadap aset yang dimiliki seperti memberikan teras dan membuat tata letak atau layout apartemen terlihat dan terasa luas dan renovasi yang dilakukan tentu akan memperbaharui tahun dibangunnya sehingga akan memaksimalkan profit bagi pemilik aset untuk dijual.

dengan rekomendasi ini diharapakan dapat menyerap potensi besarnya target pasar di kota Daegu serta pemilik aset bisa mendapatkan keuntungan setinggi-tingginya sesuai perubahan/renovasi fitur dalam memprediksi harga jual.
