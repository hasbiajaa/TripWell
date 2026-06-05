 <a href="https://ibb.co/pxpCNDc"><img src="https://i.ibb.co.com/MyR1XPQK/Trip-Well.png" alt="icon" border="0"></a>

# TripWell – Inclusive Tourism Accessibility Classification

## Project Overview

TripWell is an AI-powered inclusive tourism platform designed to help users identify whether a tourist destination is accessible for people with mobility limitations, such as wheelchair users, elderly visitors, and families with strollers.

This project focuses on analyzing Indonesian tourism reviews using Deep Learning and Natural Language Processing (NLP) techniques.

The AI system automatically classifies tourism reviews into:

- **Ramah Disabilitas** (Accessible)
- **Akses Terbatas** (Limited Accessibility)

This project was developed for:

> Coding Camp 2026 powered by DBS Foundation

---

# Team Information

## Team ID
CC26-PSU116

## Team Members

| Name | Learning Path | Role |
|---|---|---|
| Laily Khoiriyah Isnaini | AI Engineer | Active |
| Okky Puspa Ningrum | AI Engineer | Active |
| Muhammad Hasbi Ramadhani | Data Science | Active |
| Argama Vanesa Nauli Sijabat | Data Science | Active |
| Rumaisya | Full-Stack Developer | Active |
| Annisa Sahindar | Full-Stack Developer | Active |

---

# Important Link

## Video & Slide

| Presentasi | Demo | PPT |
| :--- | :--- | :--- |
| [Presentation Video](https://youtu.be/q__M4EfqY2U) | [Demo Video](https://youtu.be/lDdIHNFOMr4) | [PPT Slide](https://canva.link/cyd7t8p47910n0a) |

---

# Background

Tourism accessibility information in Indonesia is still limited and difficult to identify clearly from public reviews. Most tourism platforms mix accessibility-related reviews with unrelated information such as price, scenery, or entertainment.

As a result, users with mobility needs often struggle to determine whether a location is safe and accessible before visiting.

TripWell aims to solve this problem by developing an AI-based review classification system using a Bidirectional LSTM model.

---

# Problem Statement

Lack of accessibility-focused filtering systems in tourism reviews causes users with mobility limitations to struggle in assessing whether a destination is accessible and safe.

---

# Main Features

- Accessibility review classification using NLP
- Binary classification:
  - Positive → Ramah Disabilitas
  - Negative → Akses Terbatas
- Deep Learning model using Bidirectional LSTM
- TensorFlow Functional API implementation
- Custom callback implementation
- Model export in `.keras` format
- Simple inference system
- Ready for API integration

---

# Model Architecture

The model uses:

```text
Input Layer
↓
Embedding Layer
↓
SpatialDropout1D
↓
Bidirectional LSTM
↓
Bidirectional LSTM
↓
GlobalMaxPooling1D
↓
Dense Layer
↓
Dropout
↓
Output Layer (Sigmoid)
```
---
# Cara Menjalankan Aplikasi
 
Aplikasi TripWell terdiri dari **3 bagian** yang perlu dijalankan secara terpisah.
 
---
 
### Prasyarat
 
Pastikan perangkat sudah terinstal:
 
| Tool | Versi |
|---|---|
| Python | 3.10+ |
| Node.js | 18+ |
| npm | 9+ |
 
---
 
### 1. AI Engineer – Flask AI API
 
```bash
# Masuk ke folder ai-engineer
cd TripWell/ai-engineer/app
 
# Install dependencies
pip install -r ../requirements.txt
 
# Jalankan Flask API
python predict.py
```
 
AI API akan berjalan di `http://localhost:5000`
 
Endpoint yang tersedia:
- `POST /predict` — mengklasifikasikan teks ulasan
- `GET /health` — mengecek status server
---
 
### 2. Data Science – Streamlit Dashboard
 
```bash
# Masuk ke folder data-science
cd TripWell/data-science
 
# Install dependencies
pip install -r requirements.txt
 
# Jalankan dashboard
streamlit run dashboard.py
```
 
Dashboard akan terbuka di `http://localhost:8501`
 
---
 
### 3. Full-Stack – Next.js Web Application
 
#### Langkah 1 – Setup Environment Variables
 
Buat file `.env.local` di dalam folder `fullstack/`:
 
```env
# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
 
# Google OAuth (via NextAuth)
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
 
# NextAuth
NEXTAUTH_SECRET=your_random_secret_string
NEXTAUTH_URL=http://localhost:3000
 
# URL AI API (arahkan ke Flask server yang sedang berjalan)
NEXT_PUBLIC_API_AI_URL=http://localhost:5000
```
 
#### Langkah 2 – Setup Database
 
1. Buat project baru di [https://supabase.com](https://supabase.com)
2. Buka **SQL Editor** di dashboard Supabase
3. Jalankan script dari file `cloud-database/schema.sql` untuk membuat tabel yang dibutuhkan
#### Langkah 3 – Install dan Jalankan
 
```bash
# Masuk ke folder fullstack
cd TripWell/fullstack
 
# Install dependencies
npm install
 
# Jalankan development server
npm run dev
```
 
Web app akan berjalan di `http://localhost:3000`
 
---
 
### Ringkasan Menjalankan Semua Service
 
Buka **3 terminal terpisah**, lalu jalankan masing-masing:
 
| Terminal | Service | Perintah | Port |
|---|---|---|---|
| Terminal 1 | AI API (Flask) | `cd TripWell/ai-engineer/app && python predict.py` | 5000 |
| Terminal 2 | Dashboard (Streamlit) | `cd TripWell/data-science && streamlit run dashboard.py` | 8501 |
| Terminal 3 | Web App (Next.js) | `cd TripWell/fullstack && npm run dev` | 3000 |
 
> ⚠️ **Pastikan AI API (Terminal 1) sudah berjalan terlebih dahulu sebelum membuka web app**, agar fitur klasifikasi ulasan secara real-time dapat berfungsi dengan baik.
---
## Link Drive Model AI
https://drive.google.com/drive/folders/1cGS-OuZXDVINKzgCbOOyU1Cb-3sqMM38?usp=sharing 

---

# <div align="center">Presented By :</div>

<div align="center">

| <img src="https://i.ibb.co/xGPVFJD/dicoding-logo-white.png" height="60" alt="dicoding-logo-white" border="0"> | <img src="https://i.ibb.co.com/YMTYskf/DBS.png" height="120" alt="dbs-logo" border="0"> |
| :---: | :---: |

</div>


