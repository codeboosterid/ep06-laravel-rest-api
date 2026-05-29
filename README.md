# 🚀 EP06 — REST API Laravel + Claude Code

> Source code resmi untuk tutorial YouTube **CodeBoosterID EP06**  
> **"Setup Laravel + Claude Code - REST API dalam 10 Menit!"**

📺 **[Tonton Tutorial di YouTube →](https://youtube.com/@codeboosterid)**  
🌐 **[codebooster.id](https://codebooster.id)**

---

## 📋 Tentang Project

REST API Laravel lengkap yang dibangun dalam 10 menit menggunakan **Vibe Coding** dengan Claude Code. Cocok untuk pemula backend yang ingin belajar cara membangun API yang benar dan efisien.

**Yang akan kamu pelajari:**
- ✅ Setup Laravel project dari 0
- ✅ Database migration dengan best practice
- ✅ Eloquent Model dengan scope & casts
- ✅ Form Request untuk validasi
- ✅ API Resource untuk format response konsisten
- ✅ Controller CRUD dengan search & pagination
- ✅ REST API routes

---

## 🛠️ Tech Stack

| Tool | Versi |
|------|-------|
| PHP | 8.2+ |
| Laravel | 11.x |
| MySQL | 8.0+ |
| Composer | 2.x |

---

## ⚡ Quick Start

### 1. Clone repo

```bash
git clone https://github.com/codeboosterid/ep06-laravel-rest-api.git
cd ep06-laravel-rest-api
```

### 2. Install dependencies

```bash
composer install
```

### 3. Setup environment

```bash
cp .env.example .env
php artisan key:generate
```

Edit `.env`:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=toko_api
DB_USERNAME=root
DB_PASSWORD=
```

### 4. Jalankan migration

```bash
php artisan migrate
```

### 5. Jalankan server

```bash
php artisan serve
```

API berjalan di `http://localhost:8000`

---

## 📡 API Endpoints

| Method | Endpoint | Deskripsi |
|--------|----------|-----------|
| `GET` | `/api/products` | List semua produk (paginate 10) |
| `GET` | `/api/products?search=laptop` | Search produk by nama |
| `POST` | `/api/products` | Buat produk baru |
| `GET` | `/api/products/{id}` | Detail 1 produk |
| `PUT` | `/api/products/{id}` | Update produk |
| `DELETE` | `/api/products/{id}` | Hapus produk |

---

## 🧪 Contoh Request & Response

### Create Product
```bash
curl -X POST http://localhost:8000/api/products \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Laptop Gaming",
    "description": "Laptop untuk gaming dan coding",
    "price": 15000000,
    "stock": 5
  }'
```

**Response:**
```json
{
  "data": {
    "id": 1,
    "name": "Laptop Gaming",
    "description": "Laptop untuk gaming dan coding",
    "price": 15000000.00,
    "stock": 5,
    "is_active": true,
    "created_at": "2026-06-06 10:00:00"
  },
  "message": "Produk berhasil dibuat",
  "status": true
}
```

### Get All Products (with pagination)
```bash
curl http://localhost:8000/api/products
```

### Search Products
```bash
curl http://localhost:8000/api/products?search=laptop
```

---

## 📁 Struktur Project

```
app/
├── Http/
│   ├── Controllers/
│   │   └── ProductController.php
│   ├── Requests/
│   │   └── StoreProductRequest.php
│   └── Resources/
│       └── ProductResource.php
├── Models/
│   └── Product.php
database/
└── migrations/
    └── xxxx_create_products_table.php
routes/
└── api.php
```

---

## 🎯 Validasi Request

| Field | Rule |
|-------|------|
| `name` | required, string, max 255 |
| `description` | nullable, string |
| `price` | required, numeric, min 0.01 |
| `stock` | required, integer, min 0 |
| `is_active` | boolean |

---

## 📺 Tutorial Series CodeBoosterID

| Episode | Topik | Link |
|---------|-------|------|
| EP01 | Kenapa Developer 2026 HARUS Pakai Vibe Coding? | Coming soon |
| **EP06** | **Setup Laravel + Claude Code - REST API dalam 10 Menit** | **Video ini** |
| EP07 | CRUD API Laravel Otomatis - Tanpa Nulis Code Manual | Coming soon |
| EP08 | Authentication JWT Laravel - Cara yang Benar | Coming soon |

---

## 🤝 Kontribusi

Issue dan pull request sangat diterima! Kalau ada pertanyaan, komen di video YouTube atau buka issue di repo ini.

---

## 📄 Lisensi

MIT License — bebas digunakan untuk belajar dan project pribadi.

---

<div align="center">

**Dibuat dengan ❤️ oleh [Faizal Harwin](https://codebooster.id)**  
**Founder CodeBooster | Full Stack Developer | Backend + Vibe Coding**

[![YouTube](https://img.shields.io/badge/YouTube-CodeBoosterID-red?style=flat&logo=youtube)](https://youtube.com/@codeboosterid)
[![Website](https://img.shields.io/badge/Website-codebooster.id-blue?style=flat)](https://codebooster.id)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-faizalharwin-blue?style=flat&logo=linkedin)](https://linkedin.com/in/faizalharwin)

</div>
