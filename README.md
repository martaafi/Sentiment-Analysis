# Sentiment-Analysis
### Author: Marta Afifah

## Studi Kasus
Dalam beberapa tahun terakhir, pemerintah telah mengeluarkan berbagai kebijakan untuk mendorong penggunaan mobil listrik sebagai salah satu upaya mengurangi emisi karbon dan meningkatkan keberlanjutan lingkungan. Kebijakan ini menimbulkan berbagai reaksi dari masyarakat, yang diekspresikan melalui media sosial, termasuk Twitter.

Sebagai seorang Data Scientist, Anda ditugaskan untuk melakukan analisis sentimen terhadap tweet-tweet terkait kebijakan mobil listrik. Anda akan menggunakan dataset yang berisi tweet hasil scraping dari Twitter yang menyebutkan kata kunci seperti `mobil listrik`, `kebijakan mobil listrik`, dan istilah terkait lainnya.

## Tujuan 
- Mengetahui sentimen masyarakat terhadap kebijakan mobil listrik.
- Mengidentifikasi berbagai pendapat yang diungkapkan dalam tweet terkait.
- Melakukan analisis klasifikasi sentimen terhadap tweet-tweet tersebut.

## Informasi Dataset
- EV Data: Dataset ini digunakan untuk pelatihan model, terdiri dari 500 tweet mengenai kebijakan mobil listrik yang dikumpulkan dari media sosial X.
- Data Validasi: Dataset ini digunakan untuk evaluasi performa model yang telah dibentuk.

## Attribute
- `username`: username yang unik dari setiap pengguna twitter
- `tweet_url`: sumber tweet diperoleh
- `full_text`: isi dari tweet
- `label`: variabel target sentimen, yaitu `-1`: sentimen negatif, `0`: sentimen netral, `1`: sentimen positif.

## Langkah Analisis
- Scraping data tweet dengan kata kunci `mobil listrik`, `kebijakan mobil listrik`, dan istilah terkait lainnya.
- Labelling data secara manual, dengan definisi:
    - Positif: Tweet berisi dukungan atau persetujuan terkait kebijakan mobil listrik
    - Negatif: Tweet bersifat skeptis atau menyatakan ketidaksetujuan terkait kebijakan mobil listrik
    - Netral: Tidak positif dan tidak negatif, bersifat questioning kebijakan mobil listrik tanpa ada tendensi kalimat penolakan/persetujuan.
- Text cleaning: menghapus username, tag, url, whitespace, tanda baca, dan karakter yang tidak diperlukan, serta case folding.
- Text preprocessing: mengubah kata-kata slang menjadi kata baku dalam bahasa indonesia, menghapus kata-kata yang tidak dibutuhkan dalam analisis (contoh: yang).
- Exploratory data analysis
- Visualisasi data dengan wordcloud
- Splitting data train (`EV data`) menjadi `train` dan `val` dengan proporsi `80:20`.
- Modelling dengan algoritma `Logistic Regression`, `Linear SVM`, `Random Forest`, `Bernoulli Naive Bayes`, `Multinomial Naive Bayes`, dan `Decision Tree`.
- Hyperparameter tuning pada 3 algoritma yang memiliki akurasi tertinggi.
- Pemilihan model terbaik dengan metrik evaluasi F1 Score mengingat data label yang tidak seimbang.
- Evaluasi model pada `Data Validasi`.
  
## Tools
- Python

## Proporsi label target
![image](https://github.com/user-attachments/assets/da98b407-5b2b-48bc-a99f-e75d611b00fd)

Sebagian besar tweet memiliki sentimen netral, diikuti oleh sentimen negatif, dan yang paling sedikit adalah sentimen positif.

## WordCloud
![image](https://github.com/user-attachments/assets/b121bf13-8934-4b5a-aa9d-d425c8f71998)
![image](https://github.com/user-attachments/assets/9cd144a8-ea62-4393-9261-5b455308faaa)
![image](https://github.com/user-attachments/assets/4fe82e2d-c672-4e91-96d9-d601746da5b5)

Dari hasil visualisasi word cloud di atas, dapat diketahui bahwa top 3 kata yang paling sering muncul pada sentimen negatif adalah mobil (64), listrik (52), dan subsidi (32). Top 3 kata yang paling sering muncul pada sentimen netral adalah listrik (185), mobil (174), dan baterai (70). Top 3 kata yang paling sering muncul pada sentimen positif adalah mobil (22), listrik (16), dan harga (11). Beberapa topik yang sering diperbincangkan oleh masyarakat adalah mengenai kebijakan pemerintah tentang **subsidi** mobil listrik, **harga** mobil listrik, **baterai** mobil listrik, **spklu** yang ditambah oleh pemerintah, dan beberapa jenis atau merek mobil listrik.

## Model Terbaik
![image](https://github.com/user-attachments/assets/e0b13273-6de7-4bf3-a073-47d3ff28fb13)

Model terbaik yang diperoleh adalah `Logistic Regression` dengan nilai `F1 Score macro avg` sebesar 0,56 dan `F1 score weighted avg` sebesar 0,81.

## Evaluasi model
![image](https://github.com/user-attachments/assets/fca8013f-272e-4613-8864-856c08850749)

Hasil evaluasi model dengan `Data Validasi` diperoleh nilai F1 Score sebesar 0,32 (`macro avg`) dan 0,33 (`weighted avg`).

## Kesimpulan
Dari analisis sentimen twitter terhadap kebijakan mobil listrik yang telah dilakukan sebelumnya, diperoleh bahwa tweet masyarakat lebih banyak yang mengekspresiken sentimen netral dibanding sentimen positif atau negatif. Adapun jika dibandingkan antara tweet sentimen negatif dan tweet sentimen positif, tweet dengan sentimen negatif lebih banyak dibanding sentimen positif. Dari hasil visualisasi word cloud, beberapa topik yang sering diperbincangkan oleh masyarakat adalah mengenai kebijakan pemerintah tentang **subsidi** mobil listrik, **harga** mobil listrik, **baterai** mobil listrik, **spklu** yang ditambah oleh pemerintah, dan beberapa jenis atau merek mobil listrik.

## Rekomendasi:
Meskipun sebagian besar tweet bernada netral, jumlah tweet dengan sentimen negatif lebih banyak dibandingkan dengan sentimen positif. Hal ini menunjukkan adanya kekhawatiran atau ketidakpuasan masyarakat terhadap kebijakan mobil listrik. Oleh karena itu, pemerintah disarankan untuk meninjau ulang kebijakan yang diterapkan, khususnya terkait subsidi, harga, infrastruktur SPKLU, dan aspek teknis seperti baterai.


