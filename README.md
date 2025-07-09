# AIBRARY - AI Tools Library

AIBRARY adalah perpustakaan AI tools yang dilengkapi dengan sistem autentikasi untuk mengelola akses pengguna.

## Fitur

- 🏠 **Halaman Utama**: Landing page dengan informasi tentang AIBRARY
- 🔍 **Pencarian AI Tools**: Halaman pencarian yang memerlukan login
- 🔐 **Sistem Autentikasi**: Login dan registrasi pengguna
- 🛡️ **Proteksi Halaman**: Halaman search hanya bisa diakses setelah login
- 👤 **Manajemen Session**: Session management dengan Express Session
- 🔒 **Password Hashing**: Password di-hash menggunakan bcryptjs

## Struktur Project

```
AIbrary/
├── server.js          # Server Node.js dengan Express
├── userService.js     # Service untuk mengelola user dengan JSON
├── users.json         # File penyimpanan data user
├── package.json       # Dependensi dan konfigurasi project
├── README.md          # Dokumentasi project
└── website/           # Folder frontend
    ├── index.html     # Halaman utama (landing page)
    ├── search.html    # Halaman pencarian (memerlukan login)
    ├── auth.html      # Halaman login/registrasi
    ├── admin.html     # Halaman admin panel
    ├── script.js      # JavaScript untuk animasi dan interaksi
    ├── style.css      # Styling CSS
    └── aiToolsData.js # Data AI tools
```

## Instalasi dan Menjalankan

### Prerequisites
- Node.js (versi 14 atau lebih baru)
- npm (Node Package Manager)

### Langkah Instalasi

1. **Clone atau download project**
   ```bash
   cd AIbrary
   ```

2. **Install dependensi**
   ```bash
   npm install
   ```

3. **Jalankan server**
   ```bash
   npm start
   ```
   
   Atau untuk development dengan auto-reload:
   ```bash
   npm run dev
   ```

4. **Akses aplikasi**
   - Buka browser dan kunjungi: `http://localhost:3000`

## Penggunaan

### Halaman Utama (index.html)
- Halaman pertama yang diakses pengguna
- Menampilkan informasi tentang AIBRARY
- Tombol "Start Searching AI Tools" akan mengarahkan ke halaman login jika belum login
- Menampilkan status login/logout di navbar

### Halaman Autentikasi (auth.html)
- **Login**: Masuk dengan email dan password
- **Sign Up**: Registrasi dengan username, email, dan password
- Setelah login berhasil, pengguna akan diarahkan ke halaman search

### Halaman Pencarian (search.html)
- Hanya bisa diakses setelah login
- Jika belum login, akan diarahkan ke halaman auth
- Fitur pencarian AI tools (placeholder untuk pengembangan selanjutnya)

### Halaman Admin (admin.html)
- Hanya bisa diakses oleh user dengan role admin
- Menampilkan daftar semua user yang terdaftar
- Fitur edit dan delete user
- Statistik jumlah user berdasarkan role

## Kredensial Default

### Admin Account
- **Email**: admin@aibrary.com
- **Password**: password

## API Endpoints

### Autentikasi
- `POST /api/register` - Registrasi pengguna baru
- `POST /api/login` - Login pengguna
- `POST /api/logout` - Logout pengguna
- `GET /api/user` - Mendapatkan informasi user yang sedang login

### Admin (Admin Only)
- `GET /api/users` - Mendapatkan daftar semua user
- `GET /api/users/:id` - Mendapatkan detail user tertentu
- `PUT /api/users/:id` - Update data user
- `DELETE /api/users/:id` - Hapus user

### Halaman
- `GET /` - Halaman utama (index.html)
- `GET /auth.html` - Halaman autentikasi
- `GET /search.html` - Halaman pencarian (memerlukan login)
- `GET /admin.html` - Halaman admin panel (admin only)

## Teknologi yang Digunakan

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **Express Session** - Session management
- **bcryptjs** - Password hashing
- **body-parser** - Request body parsing

### Frontend
- **HTML5** - Markup
- **CSS3** - Styling
- **JavaScript (ES6+)** - Interaktivitas
- **Bootstrap 5** - UI framework
- **Font Awesome** - Icons
- **Animate.css** - Animasi

## Keamanan

- Password di-hash menggunakan bcryptjs dengan salt rounds 10
- Session management untuk menjaga status login
- Middleware autentikasi untuk melindungi halaman tertentu
- Validasi input di sisi server
- Role-based access control (RBAC)
- Admin user tidak bisa dihapus

## Pengembangan Selanjutnya yang disarankan oleh Lead Developer : Sean Richard Lawrence

- [ ] Integrasi database (MySQL/PostgreSQL/MongoDB)
- [ ] Fitur pencarian AI tools yang sebenarnya
- [ ] Sistem rating dan review
- [ ] Kategori AI tools
- [ ] Fitur bookmark/favorit
- [ ] Admin panel untuk mengelola tools
- [ ] Email verification
- [ ] Password reset functionality
- [ ] OAuth integration (Google, GitHub, dll.)

## Troubleshooting

### Port sudah digunakan
Jika port 3000 sudah digunakan, ubah port di `server.js`:
```javascript
const PORT = process.env.PORT || 3001; // atau port lain
```

### Error "Module not found"
Pastikan semua dependensi sudah terinstall:
```bash
npm install
```

### Session tidak tersimpan
Pastikan cookie settings sesuai dengan environment (HTTP/HTTPS)

## Lisensi

MIT License - bebas digunakan untuk keperluan komersial maupun non-komersial.

## Kontribusi

Silakan berkontribusi dengan membuat pull request atau melaporkan issues.

---

**AIBRARY Team** - 2025 