# TripWell – Wisata Inklusif Bandung Barat

Platform wisata inklusif untuk semua kalangan di Bandung Barat, dibangun dengan **Next.js 14 App Router + React**.

## 🚀 Quick Start

```bash
cd frontend
npm install
npm run dev
```

Buka [http://localhost:3000](http://localhost:3000) di browser.

---

## 📁 Struktur Folder

```
frontend/
├── app/
│   ├── layout.js          # Root layout (fonts, providers)
│   ├── page.js            # Main page (routing antar halaman)
│   └── globals.css        # CSS global, variabel warna, dark mode
│
├── components/
│   ├── Navbar.jsx          # Navigasi top dengan dark mode toggle
│   ├── Hero.jsx            # Halaman beranda + featured destinations
│   ├── DestinationCard.jsx # Card reusable untuk destinasi
│   ├── DestinationList.jsx # Halaman daftar destinasi + filter
│   ├── Detail.jsx          # Halaman detail destinasi + reviews
│   ├── Dashboard.jsx       # Halaman dashboard
│   ├── TeamSection.jsx     # Halaman tim pengembang
│   ├── Footer.jsx          # Footer reusable
│   └── Modal.jsx           # Login, Review, dan Gallery modal
│
├── context/
│   ├── ThemeContext.jsx    # Dark/light mode state (React Context)
│   └── AuthContext.jsx    # Auth state (login/logout)
│
├── data/
│   └── destinations.js    # Data dummy destinasi, team, reviews
│
├── styles/
│   └── components/        # CSS Modules per komponen
│       ├── Navbar.module.css
│       ├── Hero.module.css
│       ├── DestinationCard.module.css
│       ├── DestinationList.module.css
│       ├── Detail.module.css
│       ├── Dashboard.module.css
│       ├── TeamSection.module.css
│       └── Modal.module.css
│
├── public/
│   └── assets/
│       ├── images/        # Tempatkan gambar lokal di sini
│       └── icons/
│
├── package.json
├── next.config.js
└── README.md
```

---

## ✨ Fitur

- **Dark Mode** – Toggle dengan React Context + localStorage persistence
- **Multi-page SPA** – Navigasi antar halaman tanpa reload (state-based routing)
- **Filter Destinasi** – Filter by aksesibilitas & AI label
- **AI Review Classifier** – Integrasi endpoint BiLSTM, fallback ke local classification
- **Modals** – Login, tulis ulasan dengan preview foto
- **Responsive** – Mobile-friendly di semua ukuran layar
- **CSS Modules** – Semua styling terpisah per komponen, tidak ada inline CSS

---

## 🔌 Konfigurasi API Model

Di halaman Detail destinasi, masukkan URL endpoint model BiLSTM Anda:

```
http://localhost:5000/predict
```

Format request:
```json
{ "text": "ulasan pengguna..." }
```

Format response yang diharapkan:
```json
{ "label": "positif" }
// atau
{ "prediction": 1 }
```

---

## 🛠 Tech Stack

- **Next.js 14** (App Router)
- **React 18** (Hooks, Context API)
- **CSS Modules** (scoped styling)
- **Google Fonts** (Plus Jakarta Sans, DM Serif Display)

---

## 👥 Tim Capstone CC26-PSU116

Dikembangkan untuk Dicoding × DBS Foundation Capstone Project.
