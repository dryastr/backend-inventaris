# Backend - Inventory Management API

Proyek ini adalah API backend untuk sistem manajemen inventaris sederhana, dibangun dengan Laravel dan menggunakan Laravel Sanctum untuk autentikasi.

## Persyaratan Sistem

- PHP versi 8.1 atau yang lebih baru
- Composer untuk manajemen dependencies
- MySQL atau database lain yang didukung Laravel

## Cara Menjalankan Backend

1. Pastikan Anda berada di folder backend: `cd backend`
2. Install dependencies PHP: `composer install`
3. Salin file konfigurasi environment: `cp .env.example .env`
4. Generate application key: `php artisan key:generate`
5. Konfigurasi database di file `.env` (default menggunakan MySQL dengan database `db_inventory`, username `root`, tanpa password)
6. Jalankan migration database: `php artisan migrate`
7. Jalankan server development: `php artisan serve`

Server akan berjalan di `http://localhost:8000`.

## API Endpoints

### Autentikasi
- `POST /api/register` - Registrasi user baru
- `POST /api/login` - Login dan mendapatkan token akses
- `GET /api/user` - Mendapatkan informasi user saat ini (memerlukan autentikasi)

### Produk
- `GET /api/products` - Mendapatkan daftar produk (akses publik)
- `POST /api/products` - Membuat produk baru (memerlukan autentikasi)
- `GET /api/products/{id}` - Mendapatkan detail produk (memerlukan autentikasi)
- `PUT /api/products/{id}` - Memperbarui produk (memerlukan autentikasi)
- `DELETE /api/products/{id}` - Menghapus produk (memerlukan autentikasi)

## Credentials untuk Testing

Untuk menguji endpoint yang memerlukan autentikasi:

1. Registrasi user baru melalui `POST /api/register` dengan data:
   - name: (nama Anda)
   - email: (email yang valid)
   - password: (password minimal 6 karakter)

2. Login melalui `POST /api/login` dengan email dan password yang didaftarkan untuk mendapatkan token.

3. Gunakan token tersebut di header request: `Authorization: Bearer {token}`

Contoh credentials test sederhana:
- Email: test@example.com
- Password: password123

Anda dapat mendaftarkan user baru untuk keperluan testing.
