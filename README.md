**Project Overview**

Tujuan dari proyek ini adalah untuk melakukan analisis data ekstensif terhadap ulasan produk Tokopedia guna memahami perilaku konsumen dan mengidentifikasi peluang bisnis. Latar belakang proyek ini didasari oleh pentingnya ulasan pelanggan sebagai cerminan langsung dari kepuasan, yang dapat memberikan wawasan berharga bagi penjual, pembeli, dan platform e-commerce itu sendiri. Permasalahan spesifik yang coba dijawab adalah:

1. Bagaimana distribusi rating dan sentimen dari ulasan produk?

2. Kategori dan produk apa yang paling laku dan paling tidak laku?

3. Pola-pola umpan balik seperti apa yang muncul dari ulasan positif dan negatif?

4. Bagaimana rekomendasi produk terbaik untuk dijual berdasarkan kombinasi penjualan dan rating?

Pendekatan yang digunakan adalah analisis data eksploratif (EDA) untuk memeriksa rating dan penjualan, serta analisis sentimen untuk mengkategorikan ulasan, dan diakhiri dengan pemodelan sederhana untuk memberikan rekomendasi produk.

**Analysis Process**

Analisis data dilakukan secara sistematis melalui beberapa langkah utama:

1. Pengumpulan Data: Dataset ulasan produk Tokopedia yang berjumlah 40.607 baris dari berbagai kategori diunduh dari Kaggle.

2. Pembersihan dan Pra-pemrosesan Data:

3. Pengecekan Data Hilang dan Duplikasi: Dataset diperiksa untuk data yang hilang (NaN) dan duplikasi. Kolom sold ditemukan memiliki 14 nilai yang hilang, yang kemudian diisi dengan 0. Tidak ada duplikasi baris yang ditemukan.

4. Pembersihan Teks: Teks ulasan dibersihkan dari URL, tanda baca, dan diubah menjadi huruf kecil (case folding).
5. Normalisasi Data Numerik: Kolom rating dan sold dinormalisasi menggunakan MinMaxScaler untuk memungkinkan perbandingan yang adil dalam perhitungan recommendation_score.

Analisis dan Pemodelan:

1. Analisis Kepuasan Pelanggan: Distribusi rating dianalisis menggunakan histogram dan frekuensi untuk memahami sentimen umum.

2. Analisis Penjualan: Produk dan kategori terlaris serta yang paling tidak laku diidentifikasi dengan mengelompokkan data berdasarkan kolom sold.

3. Analisis Sentimen: Model TextBlob digunakan untuk mengkategorikan ulasan menjadi 'Positive', 'Neutral', dan 'Negative' berdasarkan polaritasnya. Metode ini dipilih karena kemudahannya dan kemampuannya memberikan hasil yang cepat untuk volume data yang besar.

4. Analisis Kata Kunci: WordCloud digunakan untuk memvisualisasikan kata-kata yang paling sering muncul di seluruh ulasan, memberikan gambaran umum tentang hal-hal yang paling sering dibahas konsumen.

5. Pemodelan Rekomendasi: Sebuah skor sederhana (recommendation_score) dihitung dengan mengalikan rating yang telah dinormalisasi dengan sold yang telah dinormalisasi. Skor ini digunakan untuk mengidentifikasi produk terbaik yang memiliki kombinasi penjualan tinggi dan rating yang baik.

**Insight & Findings**
Dari analisis yang telah dilakukan, beberapa wawasan kunci dapat ditemukan:

1. Kepuasan Pelanggan Sangat Tinggi: Rata-rata rating produk adalah 4.64, menunjukkan tingkat kepuasan yang sangat tinggi secara keseluruhan. Distribusi rating menunjukkan mayoritas ulasan (30.311) memberikan rating 5. Hal ini menunjukkan bahwa Tokopedia memiliki ekosistem yang relatif sehat.

2. Sentimen Ulasan Cenderung Netral: Analisis sentimen menunjukkan bahwa sebagian besar ulasan (32.273) bersifat Netral. Ini bisa jadi karena banyak ulasan singkat seperti "barang sudah sampai" yang tidak mengandung sentimen eksplisit. Ulasan Positif (8.116) jauh lebih banyak daripada ulasan Negatif (218).

3. Ada Produk Terlaris yang Sering Dikritik: Menariknya, produk seperti Gamepad single Usb M-Tech dan Headset Bluetooth Mini S530 muncul di daftar produk dengan ulasan positif terbanyak sekaligus ulasan negatif terbanyak. Ini menunjukkan bahwa meskipun produk-produk ini populer dan banyak terjual, ada isu-isu kualitas atau harapan yang tidak terpenuhi yang sering dikeluhkan oleh sebagian kecil pembeli.

4. Kategori 'Elektronik' Memiliki Rating Rata-Rata Tertinggi: Kategori elektronik memiliki rata-rata rating tertinggi (4.76), diikuti oleh fashion dan pertukangan. Sementara itu, kategori handphone memiliki rata-rata rating terendah (4.38). Ini mengindikasikan bahwa konsumen cenderung lebih ketat dalam menilai produk handphone dibandingkan kategori lainnya.

**Conclusion & Recommendation**
Berdasarkan wawasan di atas, berikut adalah rekomendasi yang konkret dan dapat ditindaklanjuti:

1. Untuk Penjual Produk Populer (Elektronik & Olahraga): Penjual harus memantau ulasan negatif dengan cermat, terutama untuk produk yang terbukti laris namun juga memiliki banyak keluhan. Misalnya, untuk produk seperti Gamepad single Usb M-Tech, penjual dapat meningkatkan deskripsi produk, memberikan panduan penggunaan yang lebih jelas, atau memperbaiki kontrol kualitas untuk mengurangi ulasan negatif. Hal ini akan meningkatkan rating dan kepuasan pelanggan, serta mempertahankan volume penjualan yang tinggi.

2. Untuk Penjual Produk dengan Rating Rendah (Handphone): Penjual di kategori ini harus berinvestasi lebih banyak dalam layanan purna jual dan deskripsi produk yang transparan. Mengingat konsumen handphone lebih kritis, respons cepat terhadap pertanyaan dan garansi yang jelas dapat menjadi nilai tambah yang signifikan.

3. Untuk Platform Tokopedia: Pertimbangkan untuk menambahkan fitur di dashboard penjual yang secara otomatis menyoroti produk yang memiliki volume ulasan negatif tinggi, meskipun penjualan produk tersebut baik. Fitur ini akan membantu penjual proaktif dalam menangani masalah dan meningkatkan kualitas produk di seluruh platform.
