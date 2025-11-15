# 🍳 Belajar Masak — Chatbot
Chatbot resep masakan Indonesia yang dibangun menggunakan **n8n**, **Telegram Bot**, dan teknik **Retrieval-Augmented Generation (RAG)**. Chatbot ini mampu memberikan resep lengkap berupa:

- **Judul masakan**
- **Daftar bahan**
- **Langkah-langkah memasak**
- **Informasi tambahan**
  
Seluruh jawaban dihasilkan berdasarkan dataset resep Indonesia yang telah diproses menjadi **vector embeddings** dan disimpan dalam **Supabase Vector Store**, sehingga hasilnya lebih **relevan, akurat, dan terstruktur**.

---

## 📦 Dataset

Dataset utama berasal dari:

📌 **Kaggle — Indonesian Food Recipes Dataset**  
https://www.kaggle.com/datasets/wawansuwandi/resep-makanan-indonesia

Pada proyek ini, digunakan **500 resep** yang dipilih dan dibersihkan agar optimal untuk proses embedding dan pencarian vektor.

📌 **Proses ekstraksi dataset via Google Colab:**  
https://colab.research.google.com/drive/1omHO6WNUz5lqCnw7MCTTCYOk2BExDOT5?usp=sharing

Dataset kemudian disimpan dalam format yang siap dipakai dalam workflow RAG.

---

## 🔧 Teknologi yang Digunakan

| Komponen | Teknologi |
|---------|-----------|
| Workflow otomasi | **n8n.cloud** |
| Platform chat | **Telegram Bot API** |
| Embedding model | **Gemini Embeddings** |
| Vector database | **Supabase Vector Store** |
| Large Language Model (LLM) | **Gemini** |
| Memory | **Postgres Chat Memory** |
| Dataset | **Kaggle** |

---

## 🧠 Arsitektur RAG Workflow

Berikut alur kerja chatbot:

User (Telegram)

↓

Telegram Trigger → menerima pesan dari user

↓

Chat Query Embedding → mengubah pertanyaan user menjadi vektor

↓

Supabase Vector Store → mencari resep paling relevan dari database

↓

RAG Context Builder → menggabungkan hasil pencarian + pertanyaan

↓

LLM (Gemini Chat Model) → menghasilkan jawaban terstruktur

↓

Telegram Send Message → mengirim jawaban ke user


---

## 🤖 Kemampuan Chatbot

Chatbot **Belajar Masak** dapat membantu:

✔️ Mencari resep masakan Indonesia  
✔️ Mengambil bahan & langkah secara lengkap  
✔️ Menjelaskan proses memasak langkah demi langkah  
✔️ Membuat format resep yang rapi & konsisten  
✔️ Membuat langkah improvisasi jika data tidak lengkap  
✔️ Menjawab pertanyaan seputar bahan atau cara memasak  

---

## 📱 Cara Menggunakan Chatbot

1. Buka aplikasi **Telegram**  
2. Cari bot: **@rumusmemasak_bot**  
3. Klik **Start**  
4. Tanyakan resep masakan Indonesia apa pun!  

---

## 🚀 Cara Menjalankan Workflow di n8n

### **A. Import Workflow**
1. Buka n8n  
2. Klik **Import Workflow**  
3. Pilih file `.json` dari repository  

### **B. Siapkan Credential**
Isi API Key untuk:
- Telegram Bot  
- Supabase  
- Gemini  

### **C. Aktifkan Workflow**
Klik tombol **Activate** agar bot berjalan otomatis.

---

## 🧩 Kesimpulan

Project **Belajar Masak** adalah implementasi lengkap RAG menggunakan n8n dengan:

- Telegram sebagai antarmuka pengguna  
- Supabase sebagai vector store  
- Gemini sebagai LLM  
- Dataset Indonesia dari Kaggle  

Chatbot ini membantu pengguna menemukan dan memahami resep masakan Indonesia dengan cepat, akurat, dan terstruktur.

---
