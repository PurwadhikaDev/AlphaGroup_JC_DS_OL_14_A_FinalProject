Overview Project
**Context**  
Dalam dunia e-commerce yang sangat kompetitif, **e-commerce** Alpha, sebuah platform yang baru didirikan, berupaya menganalisis perilaku pelanggan untuk meningkatkan retensi pelanggan. Dalam banyak penelitian bisnis dan literatur pemasaran, terdapat konsensus umum bahwa biaya untuk mendapatkan pelanggan baru jauh lebih tinggi dibandingkan dengan biaya untuk mempertahankan pelanggan lama. Sering disebut sebagai prinsip "Customer Retention vs. Acquisition", perbandingan ini sangat relevan terutama di industri e-commerce, SaaS, dan layanan berlangganan.

Beberapa Referensi dan Fakta Terkait Biaya Akuisisi vs. Retensi Pelanggan:

- Harvard Business Review:Menyatakan bahwa mendapatkan pelanggan baru bisa 5 hingga 25 kali lebih mahal daripada mempertahankan pelanggan yang sudah ada . Ini menunjukkan bahwa investasi dalam program retensi lebih hemat biaya daripada terus-menerus mencari pelanggan baru.
- Bain & Company:Laporan dari Bain & Company, salah satu konsultan manajemen terkemuka: mengungkapkan bahwa meningkatkan retensi pelanggan sebesar 5% bisa meningkatkan keuntungan sebesar 25% hingga 95%. Ini dikarenakan pelanggan lama cenderung lebih sering berbelanja, berbelanja dalam jumlah yang lebih besar, dan lebih loyal.
- Invesp: Sebuah studi dari Invesp : mendukung bahwa biaya untuk mengakuisisi pelanggan baru adalah sekitar 5 kali lebih tinggi dibandingkan dengan biaya mempertahankan pelanggan yang sudah ada. Mereka juga menemukan bahwa pelanggan setia menyumbang 16% lebih banyak terhadap keuntungan rata-rata perusahaan daripada pelanggan baru .

**Oleh karena itu, Kami menganggap bahwa mempertahankan pelanggan loyal atau yang sudah ada sama pentingnya dengan mendapatkan pelanggan baru**.

**Churn pelanggan** mengacu pada fenomena ketika pelanggan berhenti menggunakan produk atau layanan dari suatu perusahaan. Saat ini, churn merupakan salah satu tantangan utama yang dihadapi oleh bisnis online, khususnya e-commerce. Tingkat churn yang tinggi dapat menyebabkan hilangnya pendapatan, meningkatnya biaya pemasaran untuk memperoleh pelanggan baru, dan melemahnya loyalitas terhadap merek. Oleh karena itu, memprediksi dan mencegah churn sangat penting bagi pertumbuhan bisnis dan peningkatan profitabilitas.

Banyak perusahaan seperti Netflix, Spotify, dan Zoom menggunakan indikator churn pelanggan setelah 30 hari sebagai benchmarking. Alpha e-commerce juga menerapkan indikator churn yang serupa, di mana pelanggan yang tidak melakukan transaksi atau tidak menggunakan layanan dalam 30 hari akan dianggap sebagai churn.

Dengan fokus pada probabilitas churn yang saat ini berada di angka 17%, perusahaan dapat menganalisis berapa persen pelanggan yang berpotensi berhenti menggunakan layanan mereka, sehingga dapat menurunkan angka tersebut di bawah 15%. Penentuan promo juga berperan penting, di mana promo yang diberikan ditujukan untuk menarik kembali pelanggan yang berpotensi churn. Tujuan dari pendekatan ini adalah untuk melakukan langkah-langkah preventif yang dapat mengurangi tingkat churn dan mempertahankan pelanggan setia.

Standar time horizon untuk churn rate dalam suatu bisnis, khususnya di sektor e-commerce atau SaaS (Software as a Service), sangat tergantung pada model bisnis dan siklus penggunaan produk atau layanan. Biasanya, time horizon yang digunakan dapat berupa bulanan atau tahunan, tergantung pada tujuan dan pola interaksi pelanggan.


Bulanan (Monthly Churn Rate):

Kapan digunakan: Time horizon bulanan sering digunakan dalam bisnis dengan siklus penjualan yang cepat, seperti e-commerce, layanan berlangganan bulanan, atau bisnis dengan transaksi yang lebih sering.

Contoh penggunaan: E-commerce yang melakukan kampanye diskon atau promo besar mungkin ingin melihat Monthly Active Users (MAU) dan churn rate bulanan untuk memantau loyalitas pelanggan.

Keuntungan: Analisis bulanan memungkinkan pemantauan churn rate yang lebih cepat dan responsif. kita bisa segera melihat dampak dari marketing campaign yang sedang dilakukan atau isu laiun yang mungkin membuat pelanggan berhenti berbelanja atau menggunakan layanan.

Dengan demikian tingkat churn rate yang akan digunakan adalah bulanan agar dapat menangkap isu lebih cepat dari  customer yang akan berpotensi churn.


Marketplace besar di Indonesia memiliki CAC yang lebih rendah, di kisaran Rp 100.000 hingga Rp 300.000 per pelanggan.

Marketplace kecil atau niche cenderung memiliki CAC yang lebih tinggi, yaitu sekitar Rp 300.000 hingga Rp 1.000.000 per pelanggan.

Untuk strategi organik, CAC bisa diturunkan ke Rp 50.000 hingga Rp 150.000 jika kampanye pemasaran organik dijalankan dengan baik.


Target:

- 0 : Pelanggan tetap menggunakan produk atau layanan.
- 1 : Pelanggan berhenti menggunakan produk atau layanan.

**Problem Statement :**

Dalam industri e-commerce yang sangat kompetitif, e-commerce Alpha menghadapi tantangan utama dalam mempertahankan pelanggan mereka. Meskipun telah berhasil menarik pelanggan baru, tingkat churn yang tinggi, saat ini mencapai 17%, mengancam stabilitas pendapatan dan mengakibatkan meningkatnya biaya akuisisi pelanggan baru. Dengan churn yang tinggi, perusahaan tidak hanya kehilangan pelanggan tetapi juga menghadapi tantangan dalam mempertahankan loyalitas terhadap merek, yang secara langsung berdampak pada profitabilitas jangka panjang.

E-commerce Alpha membutuhkan solusi untuk memprediksi churn pelanggan secara efektif dan mengidentifikasi faktor-faktor utama yang menyebabkan pelanggan berhenti menggunakan produk atau layanan mereka. Dengan mengembangkan model prediksi churn yang akurat, perusahaan dapat mengambil langkah-langkah strategis untuk mencegah churn dan meningkatkan retensi pelanggan, yang pada akhirnya akan meningkatkan pertumbuhan bisnis dan profitabilitas. Diharapkan, dengan implementasi solusi ini, tingkat churn dapat diturunkan dibawah angka 15%

Tujuan dari analisis ini adalah untuk memprediksi apakah pelanggan akan churn atau tetap menggunakan layanan, serta memberikan rekomendasi strategi yang tepat untuk mengurangi churn berdasarkan hasil prediksi tersebut sehingga dapat mengurangi cost dari penarikan pelanggan.

Saat ini rasio churn adalah 17% dimana dengan adanya solusi machine learning yang kami tawarkan, expected penurunan churn sesuai standar bisa di bawah 15%. Dengan adanya machine learning diharapkan terdapat prediksi customer mana yang akan churn berdasarkan parameter tertentu sehingga dapat ditawarkan insentif oleh perusahaan untuk meminimalisir churn. 

Secara deskriptif juga dianalisa variabel-variabel dengan tingkat churn yang lebih tinggi, sehingga dapat diberikan usulan untuk perbaikan kondisi eksisiting.  


**Goals :**

Bangun model prediktif yang dapat mengidentifikasi pelanggan yang berisiko meninggalkan perusahaan (churn) secara akurat berdasarkan variabel yang diberikan. Hal ini dapat membantu perusahaan mengambil langkah proaktif untuk mempertahankan pelanggan tersebut dan mengurangi tingkat churn dari 17% menjadi dibawah 15%

Lakukan analisis eksplorasi menyeluruh terhadap data pelanggan yang diberikan untuk mendapatkan wawasan tentang perilaku dan karakteristik pelanggan. Ini termasuk menganalisis pola dan tren dalam variabel. Analisis ini dapat membantu perusahaan memahami pelanggannya dengan lebih baik dan menginformasikan pengambilan keputusan di masa mendatang. 

**Analytic Approach :**

Jadi yang akan kita lakukan adalah menganalisis data untuk menemukan pola yang membedakan pelanggan yang tetap menggunakan produk/layanan dan yang berhenti menggunakan produk/layanan.

Kemudian kita akan membangun model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi probabilitas pelanggan akan/ingin berhenti menggunakan produk/layanan perusahaan Alpha e-commerce atau tidak.


**User:**
User dari penggunaan model dan solusi data analytics ini adalah Customer Relationship Division, e.g Division Head, Marketing/Relationship Manager agar dapat membantu dalam menentukan strategi yang tepat untuk mengurangi churn dengan biaya yang optimal.

Model digunakan setiap akhir bulan untuk menganalisa potensi customer churn. Limitasi dari model adalah adanya kriteria churn customer yang tidak membeli ulang diatas 6 bulan, serta prediktif parameter yang terbatas pada parameter terpilih pada model kami dengan variasi eksisting. (apabila ada parameter atau variasi baru model belum bisa memprediksi sepenuhnya atau belum memperhitungkan parameter tersebut). 

**Data Understanding**
| Attribute | Description |
| --- |  --- |
| CustomerID | Unique customer ID |
| Churn | Churn Flag |
| Tenure | Tenure of customer in organization |
| PreferredLoginDevice | Preferred login device of customer |
| CityTier | City tier |
| WarehouseToHome | Distance in between warehouse to home of customer |
| PreferredPaymentMode | Preferred payment method of customer |
| Gender | Gender of customer |
| HourSpendOnApp | Number of hours spend on mobile application or website |
| NumberOfDeviceRegistered | Total number of deceives is registered on particular customer |
| PreferedOrderCat | Preferred order category of customer in last month |
| SatisfactionScore | Satisfactory score of customer on service |
| MaritalStatus | Marital status of customer |
| NumberOfAddress | Total number of added added on particular customer |
| Complain | Any complaint has been raised in last month |
| OrderAmountHikeFromlastYear | Percentage increases in order from last year |
| CouponUsed | Total number of coupon has been used in last month |
| OrderCount | Total number of orders has been places in last month |
| DaySinceLastOrder | Day Since last order by customer |
| CashbackAmount | Average cashback in last month |
