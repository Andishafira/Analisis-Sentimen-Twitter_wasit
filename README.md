
# 🧠 Analisis Sentimen Twitter: Kasus Kekalahan Timnas Indonesia di Piala Asia U-23 2024

## 📌 Deskripsi Proyek
Proyek ini merupakan bagian dari tugas Ujian Tengah Semester mata kuliah **Kecerdasan Bisnis** pada Program Magister Teknologi Informasi UGM. Analisis ini dilakukan terhadap sentimen publik di Twitter terkait **wasit** dalam pertandingan **Indonesia vs Uzbekistan (29 April 2024)** pada semifinal **Piala Asia U-23 2024**.

## 🎯 Tujuan
- Mengambil data dari media sosial (Twitter) menggunakan API.
- Melakukan preprocessing teks.
- Melabeli data menggunakan pendekatan **Lexicon-Based Sentiment Analysis**.
- Membangun model klasifikasi sentimen menggunakan algoritma **Naïve Bayes** (Multinomial, Bernoulli, Complement).
- Mengevaluasi model dan menguji prediksi terhadap input baru.

---

## 🔧 Tools dan Teknologi
- Python (Google Colab)
- Library: `pandas`, `re`, `sklearn`, `Sastrawi`, `matplotlib`, `wordcloud`
- Tweet-Harvest v2.6.0
- Lexicon Sentiment Dictionary (manual)
- Scikit-learn: MultinomialNB, BernoulliNB, ComplementNB

---

## 🛠️ Tahapan Proyek

### 1. 🐦 Data Crawling
- Data diambil dari Twitter menggunakan keyword: **"wasit"**
- Waktu pengambilan: 29 - 30 April 2024
- Total tweet terkumpul: **250 tweet berbahasa Indonesia**

### 2. 📊 Eksplorasi Data
- Visualisasi WordCloud
- Frekuensi kata
- Pemeriksaan nilai null dan duplikat

### 3. ✨ Preprocessing Teks
- Lowercasing
- Pembersihan simbol & karakter
- Tokenizing
- Stemming (`Sastrawi`)
- Stopword removal

### 4. 🏷️ Sentiment Labeling - Lexicon Based
- Kamus kata positif & negatif digunakan untuk memberikan skor sentimen.
- Kategori: `Positif`, `Netral`, `Negatif`
- Visualisasi hasil label

### 5. 🤖 Modeling
Model klasifikasi yang digunakan:
- **Multinomial Naive Bayes**
- **Bernoulli Naive Bayes**
- **Complement Naive Bayes**

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

## 👩‍🎓 Penulis
**Andi Shafira Dyah Kurniasari**  
NIM: 22/509347/PTK/14898  
Magister Teknologi Informasi – Universitas Gadjah Mada

---

## 📌 Catatan
> Proyek ini bersifat akademik dan tidak mewakili pendapat resmi terhadap pertandingan atau pihak tertentu.

---
