# **E-commerce Customer Analytics: Predicting Churn**
### Created By : Fauzi Achmad, Hilmi Tito, M Rizky Bayu Aji

Overview Project

## Business Problem Understanding
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


**Limitasi**


Model bisa memprediksi churn berdasarkan definisi churn diatas 6 bulan, menggunakan terutama 10 parameter terbaik dengan batasan/limit sbb:

1. Tenure: 0 sd 31 month
2. Cashback amount: 37 sd 324 Rupiah
3. Warehouse to home: 5 sd 36 KM
4. Complain: customer yang ada dan tidak ada kompalain
5. Number of Adress: 1 sd 11
6. Order Amount Hike from last Year: 11% sd 26%
7. Satisfaction Score: 1 sd 5
8. Preferred payment mode: Virtual account, ewallet, debit card, credit card dab CoD.
9. Marital Status: Single, Married dan Divorced
10. Number of device registered: 1 sd 6 device

### Error Analytics


Dari hasil analisis error pada variabel Actual dan Predicted, terlihat bahwa model salah memprediksi sejumlah besar data. Berikut adalah beberapa poin penting dari analisis terhadap fitur-fitur yang paling berkontribusi terhadap kesalahan prediksi:

- Feature Tenure:

Tenure tertinggi yang salah diprediksi adalah 1.0 dengan jumlah 72, diikuti oleh 0.0 sebanyak 40. Hal ini menunjukkan bahwa pengguna dengan masa aktif yang sangat pendek (Tenure rendah) sering salah diprediksi oleh model, kemungkinan karena perilaku pengguna baru yang berbeda dengan pengguna lama belum cukup terdeteksi dengan baik oleh model.
- Feature PreferredLoginDevice:

Pengguna yang menggunakan perangkat login tertentu, khususnya kategori 1 atau Mobile Phone (dengan 123 kasus), tampaknya lebih sering salah diprediksi. Perangkat login mungkin memengaruhi pola penggunaan yang tidak sepenuhnya dikenali oleh model, sehingga perlu analisis lebih lanjut untuk mengidentifikasi device-specific behavior.
- Feature CityTier:

Salah prediksi paling banyak terjadi di CityTier 1 dan 3, yang mencakup kota besar dan kota menengah. Ini mengindikasikan kemungkinan adanya perbedaan perilaku belanja yang tidak sepenuhnya dimodelkan, seperti aksesibilitas ke layanan atau preferensi pengguna yang bervariasi berdasarkan lokasi.
- Feature WarehouseToHome:

Pengiriman dari jarak tertentu seperti 9.0 (dengan 35 kesalahan) sering salah diprediksi. Hal ini bisa menunjukkan ketidaktepatan model dalam mengakomodasi dampak jarak pengiriman terhadap perilaku pembelian atau kepuasan pengguna.
- Feature PreferredPaymentMode:

Pembayaran yang paling sering salah diprediksi adalah mode pembayaran dengan kode 2 dan 1 atau Debit Card dan Credit Card. Mungkin ada bias yang belum sepenuhnya dimengerti model terkait pilihan pembayaran ini, misalnya, apakah diskon atau cashback lebih sering memicu pembelian berulang.
- Feature HourSpendOnApp:

Pengguna yang menghabiskan 3 jam di aplikasi (110 kesalahan) tampaknya sering salah diprediksi. Ini menunjukkan bahwa durasi penggunaan aplikasi mungkin memiliki pola perilaku yang rumit, dan mungkin perlu eksplorasi lebih lanjut mengenai aktivitas selama waktu tersebut.
- Feature NumberOfDeviceRegistered:

Registrasi perangkat terbanyak di kategori 4 (80 kasus) menunjukkan kesalahan prediksi yang cukup besar. Ini mungkin mengindikasikan bahwa pengguna dengan banyak perangkat memiliki pola interaksi yang kompleks atau berbeda dari rata-rata pengguna.
- Feature SatisfactionScore:

Skor kepuasan 3 (65 kasus) sering salah diprediksi. Hal ini menunjukkan bahwa pengguna dengan tingkat kepuasan sedang cenderung memiliki perilaku yang sulit ditebak oleh model, mungkin karena mereka berada di titik peralihan antara puas dan tidak puas.
- Feature Complain:

Jumlah kesalahan prediksi cukup merata antara yang memiliki komplain dan tidak. Ini menandakan bahwa model mungkin kurang sensitif terhadap indikasi ketidakpuasan yang diwakili oleh variabel komplain.
- Feature OrderAmountHikeFromlastYear:

Peningkatan jumlah order tertinggi pada angka 14.0 dan 12.0 menunjukkan kesalahan signifikan, menunjukkan bahwa model kesulitan memprediksi pengguna dengan perubahan pola pembelian yang signifikan dibandingkan tahun sebelumnya.
- Feature CouponUsed:

Penggunaan kupon 1.0 (83 kasus) menjadi sumber kesalahan terbesar, mungkin karena dampak promosi yang belum diantisipasi secara tepat dalam model prediksi.
- Feature Actual dan Predicted:

Kesalahan prediksi terutama terjadi pada pengguna yang sebenarnya Churn (Actual 1) tetapi diprediksi tidak Churn (Predicted 0), sebanyak 145 kasus. 


Analisis error ini menunjukkan bahwa fitur-fitur seperti Tenure, PreferredLoginDevice, dan jarak pengiriman dari gudang ke rumah memiliki pengaruh signifikan terhadap kesalahan prediksi. Akan tetapi, model ini hanya mengalami kesalahan 181 dari 1076. Pendekatan yang lebih baik untuk menangani variabel-variabel ini, misalnya dengan memasukkan fitur tambahan atau menggunakan algoritma yang lebih kompleks, dapat membantu mengurangi kesalahan prediksi model.

# Conclusion & Recommendation

Berdasarkan hasil classification report dari model RF yang sudah dituning, kita dapat menyimpulkan bahwa jika model ini digunakan untuk menyaring pelanggan yang mungkin akan churn, maka model ini dapat mengurangi 99% pelanggan yang tidak akan churn untuk tidak kita beri perhatian lebih (berdasarkan recall untuk kelas 0.0). Selain itu, model ini juga dapat mengidentifikasi 79% dari seluruh pelanggan yang benar-benar akan churn (berdasarkan recall untuk kelas 1.0).

Ketepatan prediksi model kita untuk pelanggan yang akan churn adalah 97% (precision untuk kelas 1.0), yang berarti setiap kali model memprediksi bahwa seorang pelanggan akan churn, sekitar 97% prediksi tersebut benar. Namun, perlu dicatat bahwa ada sekitar 1% dari pelanggan yang tidak akan churn namun diprediksi oleh model sebagai pelanggan yang akan churn, yang dapat mempengaruhi efisiensi strategi retensi.

Secara keseluruhan, model ini memiliki akurasi sebesar 96%, dan performanya dapat dilihat dari weighted average f1-score sebesar 96%, menunjukkan bahwa model seimbang dalam menangani kedua kelas, meskipun ada peluang untuk peningkatan lebih lanjut, khususnya dalam mengurangi kesalahan prediksi untuk pelanggan yang tidak akan churn.


Dari Context diperoleh bahwa
- Marketplace besar di Indonesia memiliki CAC yang lebih rendah, di kisaran Rp 100.000 hingga Rp 300.000 per pelanggan.
- Marketplace kecil atau niche cenderung memiliki CAC yang lebih tinggi, yaitu sekitar Rp 300.000 hingga Rp 1.000.000 per pelanggan.
- Untuk strategi organik, CAC bisa diturunkan ke Rp 50.000 hingga Rp 150.000 jika kampanye pemasaran organik dijalankan dengan baik.

Bila seandainya biaya untuk screening/menyaring data per kandidat itu Rp 300.000, dan andaikan jumlah pelanggan yang kita miliki untuk suatu kurun waktu sebanyak 200 orang (dimana andaikan 100 orang akan Churn, dan 100 orang tidak akan Churn), maka hitungannya kurang lebih akan seperti ini :

Tanpa Model (semua kandidat diperiksa dan ditawarkan):

- Total Biaya => 200 x Rp 300.000 = Rp 60.000.000
- Total Pelanggan yang akan Churn => 100 orang (karena semua ditawarkan)
- Total Pelanggan yang akan Tidak Churn => 0 orang (karena semua ditawarkan)
- Biaya yang Terbuang => 100 x Rp 300.000 = Rp 30.000.000 (karena 100 orang Churn dan menjadi sia-sia)
- Jumlah Penghematan => Rp 0
Dengan Model (hanya pelanggan yang diprediksi Churn (100) oleh model yang diperiksa dan ditawarkan):

- Total Biaya => (79 x Rp 300.000) + (1 x Rp 300.000) = Rp 23.700.000 + Rp 300.000 = Rp 24.000.000
- Total Pelanggan yang akan Churn => 79 orang (berdasarkan recall untuk kelas churn yaitu 79%)
- Total Pelanggan yang akan Tidak Churn => 21 orang (karena recall untuk kelas non churn adalah 79%)
- Biaya yang Terbuang => 1 x Rp 300.000 = Rp 300.000 (berdasarkan recall untuk kelas non churn, sebanyak 1 orang yang tidak Churn tetapi tetap ditawarkan)
- Jumlah Penghematan: Perhitungan penghematan dihitung sebagai selisih antara biaya tanpa model dan dengan model => Rp60.000.000−Rp24.000.000=Rp36.000.000

Berdasarkan contoh hitungan tersebut, terlihat bahwa dengan menggunakan model prediksi, perusahaan akan dapat menghemat biaya yang signifikan tanpa mengorbankan banyak jumlah pelanggan Tidak Churn. Model ini membantu dalam menyaring pelanggan dengan lebih efisien, mengurangi biaya yang terbuang karena menawarkan pada pelanggan yang tidak tertarik, dan secara keseluruhan meningkatkan efektivitas strategi pemasaran.
#### Recommendation
Hal-hal yang bisa dilakukan untuk mengembangkan project dan modelnya lebih baik lagi :
- Menambahkan fitur-fitur atau kolom baru yang berpotensi berkaitan dengan ketertarikan pelanggan terhadap produk, seperti jumlah biaya transaksi, parameter demografi, dan lainnya, untuk memperkaya analisis dan meningkatkan akurasi prediksi model.
- Mencoba algorithm ML yang lain terutama neural network, mencoba hyperparameter tuning kembali, dan menggunakan metode Grid Search untuk tuning, serta coba gunakan teknik oversampling yang berbeda juga selain Random Over Sampling, seperti SMOTENC, dll.
- Menganalisa data-data yang model kita masih salah tebak lebih dalam untuk mengetahui alasannya dan karakteristiknya bagaimana.


Untuk dashboard e-commerce, bisa diakses pada link dibawah ini:
https://public.tableau.com/views/Final_Project_ecommerce_Alpha/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link
