# LLM sebagai Market Analyst
**Bisakah AI merangkum sentimen investor dari komentar sosial media secara otomatis?**

Project ini menggunakan Large Language Models (LLM) untuk menganalisis dan membuat ringkasan pasar saham India berdasarkan komentar investor retail di sosial media (Twitter). Project ini menggunakan language model dari IBM, yaitu **IBM granite-3.3-8b-instruct**. Sistem ini dapat mengklasifikasi, menganalisis, dan merangkum insight pasar.

---

## Tujuan Proyek
- Mengambil data komentar sosial media yang berkaitan dengan saham India.
- Mengklasifikasikan sentimen (bullish/bearish) secara otomatis.
- Menggunakan LLM untuk menyusun **ringkasan harian pasar**, insight per saham, dan tren umum.
- Mengevaluasi apakah LLM dapat menggantikan peran analis pasar retail.

---

## Dataset
- sumber: https://www.kaggle.com/datasets/rutviknelluri/tweets-of-indian-stocks-from-stocktwits
- Dataset: Komentar saham dari sosial media (Twitter)
- Format: CSV
- Kolom: `company`, `tweet`, `sentiment`
- Ukuran: {jumlah rows} baris

Contoh:

| company | tweet                             | sentiment |
|---------|-----------------------------------|-----------|
| TCS     | “TCS will breakout soon!”         | bullish   |
| INFY    | “INFY dropping, time to short.”   | bearish   |

---

## Metodologi

### 1. **EDA**
- Hitung proporsi bullish vs bearish
- Mencari saham yang paling banyak / sedikit dibicarakan
- Jumlah komentar bullish/bearish 20 saham paling ramai dibicarakan

### 2. **AI Processing (LLM via Replicate)**
- Model: `ibm-granite/granite-3.3-8b-chat`
- Fungsi: menganalisis komentar dan menghasilkan insight
- Strategi:
  - Sampling 5 komentar per saham
  - Prompt ringan dan fokus
  - Retry + caching untuk keandalan

### 3. **Ringkasan**
- Sentimen pasar secara umum
- Insight tentang indeks $NIFTY50.NSE
- Top 3 saham paling ramai & sepi beserta ringkasannya

---

## Insight & Visualisasi

- **Distribusi sentimen**: Mayoritas komentar adalah bullish (>60%)
- **Top saham dibahas**: TCS, INFY, RELIANCE
- **Polarisasi**: INFY banyak komentar bearish, RELIANCE banyak komentar bullish

Visualisasi:
- Pie chart distribusi sentimen
- Bar chart top saham
- Heatmap sentimen per perusahaan
- Word cloud komentar bullish

---

## Model AI yang Digunakan
- `ibm-granite/granite-3.3-8b-chat` (Replicate)
- Prompt dirancang untuk:
  - Merangkum komentar menjadi 1-2 kalimat
  - Meniru gaya analis pasar
  - Memahami opini dominan dan sentimen umum

---

## Insight Utama
- AI mampu merangkum sentimen pasar secara cukup akurat dan konsisten
- LLM bisa digunakan untuk membangun dashboard insight harian pasar

---

## Kesimpulan & Rekomendasi
- LLM dapat menjadi asisten market analyst berbasis komentar sosial media
- Perlu integrasi dengan data harga saham untuk insight kuantitatif
- Sistem ini cocok untuk dipakai di sektor riset pasar, fintech, dan edukasi investasi

---

## Tools & Library
- Python
- Pandas
- Matplotlib & Seaborn
- Replicate API (LLM)
- LangChain

---

## Next Step
- Integrasi dengan harga saham → prediksi pergerakan
- Gunakan Reddit, StockTwits sebagai sumber tambahan
- Gunakan API Twitter untuk scrapping data real-time sehingga bisa melakukan analisis realtime juga

---

## Kontak
Proyek ini dibuat oleh Steven Andre Gonassis, sebagai bagian dari Capstone Project Hacktiv8: Data Summarization and Classification using IBM Granite.  
