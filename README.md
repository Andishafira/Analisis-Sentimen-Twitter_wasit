
# Analisis Sentimen Twitter: Kasus Kekalahan Timnas Indonesia di Piala Asia U-23 2024

## Deskripsi Proyek
Proyek ini merupakan bagian dari tugas Ujian Tengah Semester mata kuliah **Kecerdasan Bisnis** pada Program Magister Teknologi Informasi UGM. Analisis ini dilakukan terhadap sentimen publik di Twitter terkait **wasit** dalam pertandingan **Indonesia vs Uzbekistan (29 April 2024)** pada semifinal **Piala Asia U-23 2024**.

## Tujuan
- Mengambil data dari media sosial (Twitter) menggunakan API.
- Melakukan preprocessing teks.
- Melabeli data menggunakan pendekatan **Lexicon-Based Sentiment Analysis**.
- Membangun model klasifikasi sentimen menggunakan algoritma **Naïve Bayes** (Multinomial, Bernoulli, Complement).
- Mengevaluasi model dan menguji prediksi terhadap input baru.

---

## Tools dan Teknologi
- Python (Google Colab)
- Library: `pandas`, `re`, `sklearn`, `Sastrawi`, `matplotlib`, `wordcloud`
- Tweet-Harvest v2.6.0
- Lexicon Sentiment Dictionary (manual)
- Scikit-learn: MultinomialNB, BernoulliNB, ComplementNB

---

## Tahapan Proyek

### 1. Data Crawling
Sebelum melakukan analisis sentiment twitter, diperlukan crawling dataset menggunakan Application Programming Interface (API) untuk mendapatkan dataset berisi tweet tweet pegguna twitter yang memposting unggahan dengan keyword “wasit”. Tools yang digunakan dalam proses crawling data pada tugas ini adalah Tweet Harvest versi 2.6.0. Tweet-harvest merupakan tools yang digunakan untuk melakukan crawling data pada media sosial Twitter dengan menggunakan API. Tools tersebut memerlukan sebuah token yang digunakan untuk melakukan akses API dari google colab kepada akun twitter yang saya gunakan. Dengan menggunakan tools tersebut, didapatkan 250 data dengan keyword “wasit” yang diunggah melalui postingan pengguna twitter mulai dari 29 April 2024 hingga 30 April 2024.

### 2. 📊 Eksplorasi Data
Pada tahap ini dilakukan peninjauan data null, analisis wordCloud dan analisis frakuensi kata kata yang sering muncul dari data mentah. Pada tahap ini, eksplorasi data difokuskan pada kolom full_text. Hal ini dikarenakan kolom tersebut memuat isi tweet dari dataset. Berdasarkan hasil keluaran yang ditunjukan pada gambar 30, dataset khususnya pada kolom full_text bebas dari nilai null sehingga dapat dilanjutkan ke tahap berikutnya.

### 3. ✨ Preprocessing Teks
- Lowercasing : Mengonversi seluruh teks menjadi lowercase dapat membantu memastikan konsistensi dalam analisis. Sehingga dapat menghindari perbedaan yang tidak perlu akibat perbedaan huruf kapital dan non kapital.
- Pembersihan simbol & karakter : Untuk membantu menghilangkan "noise" atau gangguan dari data teks, seperti karakter khusus, tanda baca, atau simbol yang tidak relevan untuk analisis.
- Tokenizing : Untuk memecah teks (tweet) menjadi unit-unit yang lebih kecil yang disebut "token" atau kata-kata. Tokenisasi mengubah teks menjadi representasi yang lebih terstruktur, di mana setiap token mewakili unit terkecil (kata atau simbol) dalam teks. Tujuan utama dari tokenisasi adalah untuk mempersiapkan teks agar dapat diolah lebih lanjut oleh algoritma text mining.
- Stemming (`Sastrawi`) : Proses stemming data dalam analisis sentimen Twitter digunakan untuk mengubah kata kata menjadi bentuk dasarnya atau bentuk kata yang lebih sederhana, dengan tujuan untuk mengurangi variasi kata yang memiliki akar kata atau makna yang sama. Contohnya, kata-kata seperti "memakan", "dimakan", dan "makanan" akan distem menjadi kata dasar "makan". Stemming membantu dalam normalisasi teks dan menciptakan konsistensi data, sehingga kata kata dengan makna yang sama dianggap sebagai satu entitas dalam analisis
- Stopword removal : Digunakan untuk menghapus kata-kata umum yang tidak memberikan nilai tambah dalam analisis sentimen atau pemrosesan teks. Kata-kata ini disebut "stopwords" karena biasanya tidak memiliki makna khusus atau tidak mempengaruhi sentimen dari teks secara signifikan. Stopwords adalah kata-kata umum seperti "dan", "atau", "di", "yang", dsb., yang banyak muncul dalam teks. Menghapus stopwords dapat membantu dalam fokus pada kata-kata kunci atau makna yang lebih penting dalam teks untuk analisis lebih lanjut. Hal ini dikarenakan proses stopwords menghilangkan noise atau gangguan yang tidak perlu dalam data teks

### 4. 🏷️ Sentiment Labeling - Lexicon Based
Pendekatan Lexicon Based didasarkan pada asumsi bahwa orientasi sentimen kontekstual adalah hasil dari orientasi sentimen masing-masing kata atau frasa dalam teks. Metode ini dapat digunakan untuk mengekstrak sentimen dari blog dengan menggabungkan pengetahuan leksikal dan teknik klasifikasi teks. Lexicon dapat disusun secara manual atau diperluas secara otomatis dari sekumpulan kata kunci (seed words)

### 5. 🤖 Modeling
Naïve bayes dipilih dikarenakan memiliki komputasi yang efisien karena hanya memerlukan perhitungan sederhana dari probabilitas prior dan likelihood. Ini membuatnya cepat dalam melatih model dan melakukan prediksi. Selain itu Naive Bayes cenderung lebih tahan terhadap overfitting dibandingkan dengan model yang lebih kompleks. Hal ini karena model memiliki jumlah parameter yang relatif sedikit.

Evaluasi dilakukan menggunakan:
- **Confusion Matrix**
- **Classification Report** (Accuracy, Precision, Recall, F1-Score)

Hasil evaluasi menunjukkan bahwa model **Complement Naïve Bayes** memiliki performa terbaik untuk dataset ini.

---

## 🧾 Hasil Kesimpulan
- Mayoritas sentimen pengguna terhadap wasit pada pertandingan tersebut **bernuansa negatif**.
- Kombinasi preprocessing teks + lexicon-based labeling cukup efektif untuk data Twitter berbahasa Indonesia.
- Model Complement Naïve Bayes direkomendasikan untuk kasus serupa.

---

## 📌 Catatan
> Proyek ini bersifat akademik dan tidak mewakili pendapat resmi terhadap pertandingan atau pihak tertentu.

---
