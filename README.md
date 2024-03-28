## Model Machine Learning Prediksi Kelayakan Air Minum (Classification Model) ##
#### Created by : Ganeswara Pramudita, Nur Achmey Selgi Harwanti dan Anisa Maulidina ####

- Data Source : [link di sini](https://www.kaggle.com/datasets/adityakadiwal/water-potability)
- Tableau Dashboard : [Klik link ini](https://www.kaggle.com/datasets/adityakadiwal/water-potability)

### Context ### 
Akses yang merata dan aman terhadap air minum adalah tujuan utama dalam menjaga kesehatan masyarakat, sesuai dengan Tujuan Pembangunan Berkelanjutan (SDGs) ke-6. Indonesia berkomitmen mencapai target 100% akses terhadap air minum yang layak pada tahun 2024. Penting bagi penyedia air minum untuk memastikan bahwa sumber air yang disediakan memenuhi standar kualitas yang ditetapkan, seperti tingkat kekeruhan (turbidity), tingkat keasaman (pH), dan konsentrasi zat-zat kimia seperti sulfat dan kloramin. Contohnya, WHO menetapkan batas maksimum 5 NTU untuk kekeruhan dan rentang pH 6.5-8.5. Negara lain memiliki standar yang berbeda, seperti Canada yang menetapkan batas maksimum untuk sulfate hingga 500 mg/l. Pengetahuan tentang standar ini penting untuk menilai keselamatan air minum dan memastikan tindakan yang diperlukan jika ada ketidaksesuaian dengan standar yang ditetapkan, demi kesejahteraan dan kesehatan masyarakat yang lebih baik.
Target:   
0: Air tidak layak minum  
1: Air layak minum  

 ### Problem Statement ###

Pemerintah harus memperhatikan pengelolaan air untuk memastikan keamanan dan kualitas air minum. Tanpa pengetahuan yang memadai, mengelola sumber air bisa memakan waktu dan sumber daya, berpotensi membahayakan kesehatan dan menyebabkan dampak sosial dan ekonomi. Contoh masalah ini terjadi di berbagai negara seperti Kamerun dan Nigeria, di mana urbanisasi mengakibatkan kesulitan akses air minum yang aman. Dengan populasi dan urbanisasi yang terus meningkat, pemahaman tentang kualitas air dan pengelolaannya menjadi krusial untuk menyediakan air minum yang aman bagi masyarakat

### Goals ###

Tujuan dari prediksi ini adalah agar pemerintah dapat mengalokasikan sumber daya dengan lebih efisien, dengan fokus pada sumber air yang memiliki potensi untuk dijadikan sebagai sumber air minum yang layak. Selain itu, pemerintah juga tertarik untuk memahami faktor-faktor atau variabel yang memengaruhi kualitas air minum.

### Analytic Approach ### 

Analisis data kualitas air dan faktor penting, serta pembangunan model prediksi untuk optimalkan pengelolaan air dan keputusan penyediaan air minum aman.

### Metrics Evaluation ###
**True Negative (TN)**: Model memprediksi bahwa sumber air tidak layak dimana kenyataannya sumber air tersebut memang tidak layak
**True Positive (TP)**: Model memprediksi bahwa sumber air layak dimana kenyataannya sumber air tersebut memang layak
**False Negative (FN)**: Model memprediksi bahwa sumber air tidak layak dimana kenyataannya sumber air tersebut ternyata layak
**False Positive (FP)**: Model memprediksi bahwa sumber air layak dimana kenyataannya sumber air tersebut ternyata tidak layak
**Type 1 error**: False Positive  
Konsekuensi: pemerintah akan menggunakan sumber air minum yang tidak layak sehingga akan berbahaya bagi kesehatan konsumen.
**Type 2 error**: False Negative  
Konsekuensi: pemerintah akan kehilangan calon sumber air yang sebenarnya bisa dimanfaatkan untuk air minum.

### Kesimpulan ### 
Kualitas air yang memadai sebagai air minum yang layak adalah air dengan Parameter kimia (pH, Hardness, Chloromines, Solid dan Sulfate) masih di bawah standar index Parameter WHO 
- pH : 6.5 - 8.5
- Chloromines : 0.5 - 2 mg/l
- Hardness : < 300
- Solid : <600 mg/l
- Sulfate : 250
Model Random Forest memiliki tingkat presisi 67% dalam mengidentifikasi air tidak layak dan 73% untuk air layak. Meskipun berhasil memfilter sebagian besar air tidak layak, masih diperlukan peningkatan dalam mengenali air layak. Meskipun demikian, penggunaan model ini dapat membantu mengurangi risiko menerima air tidak layak.

- *Tanpa Model :*
(semua sumber mata air kita lakukan uji) :
- Total Biaya : 1000 x Rp.715.000 = Rp.715.000.000
- Total sumber air layak yang didapatkan  : 500 (karena semua diuji)
- Total sumber air layak yang tidak didapatkan  = 0 (karena semua diuji)
- Biaya yang terbuang : 500 x Rp.715.000 =  Rp.357.500.000 (karena 500 sampel air ternyata tidak layak sehingga menjadi sia -sia)
- jumlah penghematan : 0 Rp

*Dengan Model :*
(hanya sumber air yang dipredisi `layak` oleh model yang kita lakukan pengujian lebih lanjut di lab)
- Total Biaya : (145 x Rp. 715.000) + (35 x Rp.715.000) = Rp. 103.675.000 + Rp. 25.025.000 = Rp.128.700.000
- Total sumber air layak yang didapatkan : 140 sumber (karena recall 1/ yang layak itu 29%)
- Total sumber air tidak layak yang didapatkan : 360 sumber (karena recall 1/yang layak itu 29%)
- Biaya yang terbuang : 35 x Rp. 715.000 = Rp. 25.025.000 (berdasarkan recall 0/yg tidak layak (35 sumber air tidak layak))

Selisih tanpa model dan dengan model:
Rp. 715.000.000 - Rp. 128.700.000 = Rp.586.3000.000

Berdasarkan perhitungan di atas, dapat disimpulkan bahwa dengan menggunakan model yang dibuat, pemerintah dapat mengurangi biaya uji lab dari sumber mata air yang ada.

### Rekomendasi ### 
Hal yang bisa dilakukan dalam mengembangkan model dan project lebih baik lagi :

For Model :
1. Menambahkan fitur `koordinat` untuk mengetahui sebaran titik sumber air yang layak dan tidak layak agar dapat terpetakan secara spasial. Selain itu pentingnya data spasial untuk memperhitungkan faktor-faktor geografis seperti jarak ke sumber pencemaran atau kepadatan populasi di sekitar sumber air. Dalam hal ini berarti juga perlu adanya penambahan fitur `neighbourhood` atau lingkungan sekitar yang berpotensi mencemari sumber mata air seperti : Pabrik, TPA (Tempat Pemakaman Umum) dan sebagainya
2. Mencoba Algoritma ML yang lain dan juga mencoba hyperparameter tuning kembali, coba gunakan teknis resampling yang berbeda selain ke-3 teknik resampling di atas
3. Penambhan fitur `waktu` untuk mengetahui sampel air diambil saat musim kemarau/hujan. karena cuaca juga menentukan tingkat beban pencemar yang akan mencemari sumber mata air
4. Penambahan fitur `Suhu` karena menurut penelitian (Efendi, 2003), suhu merupakan salah satu parameter penting dalam pengujian kelayakan air minum
5. Menggunakan dataset dari observasi nyata agar bisa membuat model yang lebih baik
6.  Menentukan kelayakan air cukup mengukur beberapa parameter yang penting saja seperti pH, hardness dan Chloromines, Sulfate dan Solid

For Business
1. Waktu pengambilan sampel sebaiknya jangan di musim penghujan karna intensitas beban pencemar akan meningkat
2. Model memiliki tingkat presisi yang relatif tinggi dalam mengidentifikasi air yang tidak layak, disarankan untuk meningkatkan pengawasan dan pengujian kualitas air secara berkala.  Memang anjuran dari pemerintah untuk terus dilakukan pengujian secara berkala
3. Optimalisasi sumber-sumber air minum melalul perbaikan kualitas
air dengan memanfaatkan teknologi pengolahan flltrasi, sedimentasi
aerasi, dekootarninasi disinfeksi, dan atau teknologi lain yang dapat
mewujudkan kualitas air memenuhi standar baku mutu air minum

### Limitasi Model ###
1. Standarisasi parameter kualitas air pada model ini tidak sepenuhnya sesuai dengan WHO. Dilihat dari kelas 1 (Kategori air layak minum) yang dimiliki model, ada beberapa yang merepesentasikan nilai pH yang melebihi standar WHO. Beberapa sumber air yang nilai pHnya di atas dan di bawah standara WHO (6.5 - 8.5) dikategorikan 'layak' pada model ini. Sebenarnya, di beberapa negara, rentang standar pH yang dikatakan layak juga ada yang berbeda dengan standar WHO, seperti Singapore yang memiliki pH dengan rentang 6.5 - 9.5, jadi limitasi model ini hanya bisa digunakan di daerah tertentu (tidak dijelaskan data ini untuk daerah mana). Oleh karena itu limitasi model ini hanya bisa digunakan pada negara-negara yang menggunakan standar WHO
  
    Misalkan seperti di Jepang yang memiliki banyak gunung berapi, dan beberapa sumber airnya memiliki tingkat keasaman yang tinggi sebagai akibat dari aktivitas vulkanik . Oleh karena itu, pemerintah Jepang menetapkan rentang pH yang lebih rendah untuk air minum yang dianggap layak (*source : https://www.jica.go.jp , Japan’s Experiences on Water Supply Development*)

2. Kinerja Model mungkin tidak baik/ tidak dapat dipercaya hasil prediksinya jika digunakan untuk kasus nyata karena dataset tidak menggambarkan kondisi sebenernya
