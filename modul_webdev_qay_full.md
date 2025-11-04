# Modul Pemrograman Dasar Website HTML, CSS, JavaScript, Node.js, dan Express.js

_Disusun oleh GPT-5 Plus_

---

## 📘 Daftar Isi
1. **Pengantar Website dan Linux**  
2. **Persiapan Lingkungan (Ubuntu & CentOS)**  
3. **HTML Dasar**  
4. **CSS & Layout Modern**  
5. **JavaScript Dasar**  
6. **Mini Project: Portfolio Statis**  
7. **Node.js & NPM**  
8. **Express.js (Routing dan Server Web)**  
9. **REST API & JSON**  
10. **Database MySQL & PostgreSQL**  
11. **Session & Login Dasar**  
12. **Deployment di Ubuntu & CentOS**  
13. **Git & GitHub Deployment**  
14. **Final Project: MyShop Web App**  
15. **Lampiran: Cheat Sheet, Troubleshooting, Tips VS Code**

---

# **Bab 1 – Pengantar Website dan Linux**

### 🎯 Tujuan Pembelajaran
- Memahami konsep dasar website.
- Mengenal perbedaan frontend, backend, dan database.
- Memahami cara kerja client–server.
- Menjalankan perintah dasar Linux.

### 1.1 Apa Itu Website
Website adalah kumpulan halaman web yang diakses melalui internet menggunakan browser seperti Chrome atau Firefox. Website dibangun dari tiga bagian utama:

| Komponen | Fungsi |
|-----------|--------|
| **Frontend** | Tampilan yang dilihat pengguna, dibuat dengan HTML, CSS, dan JavaScript. |
| **Backend** | Logika server, diatur dengan Node.js, PHP, atau Python. |
| **Database** | Tempat menyimpan data (MySQL atau PostgreSQL). |

### 1.2 Cara Kerja Website
1. Pengguna membuka browser dan mengetik alamat web.  
2. Browser mengirimkan *request* ke server.  
3. Server memproses data dan mengirimkan *response*.  
4. Browser menampilkan hasil ke layar.

### 1.3 Linux Sebagai Server
Contoh perintah:
```
$ lsb_release -a
$ cat /etc/redhat-release
```

### 1.4 Tes Akses Web via Terminal
```
$ curl https://example.com
```

### 💡 Tips VS Code
Gunakan ekstensi **Remote - SSH** agar bisa coding langsung di server Linux.

---

# **Bab 2 – Persiapan Lingkungan (Ubuntu & CentOS)**

### 🎯 Tujuan
Menyiapkan Git, Node.js, Nginx, dan database (MySQL/PostgreSQL).

### 2.1 Update Sistem
```
# Ubuntu
sudo apt update && sudo apt upgrade -y

# CentOS
sudo dnf update -y
```

### 2.2 Instalasi Tools Dasar
```
sudo apt install -y curl wget git nano build-essential
```

### 2.3 Instal Node.js via NVM
```
curl -fsSL https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
source ~/.nvm/nvm.sh
nvm install --lts
```

### 2.4 Instal Database
```
sudo apt install -y mysql-server postgresql postgresql-contrib
```

### 💡 Tips VS Code
Gunakan **terminal internal VS Code** (``Ctrl+` ``) untuk menjalankan semua perintah di atas.

---

# **Bab 3 – HTML Dasar**

### 🎯 Tujuan
Mengenal struktur HTML dan membuat halaman pertama.

### Contoh
```html
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8">
  <title>Halo Dunia!</title>
</head>
<body>
  <h1>Halo Dunia!</h1>
  <p>Ini halaman pertamaku menggunakan HTML.</p>
</body>
</html>
```

### 💡 Tips VS Code
Ketik `!` lalu tekan **Tab** untuk membuat template HTML5 otomatis (fitur Emmet).

---

# **Bab 4 – CSS & Layout Modern**

### 🎯 Tujuan
Menambahkan tampilan menarik menggunakan Flexbox dan Grid.

```css
body {
  font-family: Arial, sans-serif;
  margin: 0;
  background: #f7f7f7;
}
header {
  background: #1e90ff;
  color: #fff;
  padding: 10px;
}
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 16px;
}
```

### 💡 Tips VS Code
Gunakan `Alt + Klik` untuk multi-cursor editing — ubah banyak baris sekaligus.

---

# **Bab 5 – JavaScript Dasar**

### 🎯 Tujuan
Menambahkan interaktivitas di halaman web.

```js
const tombol = document.querySelector("#klik");
tombol.addEventListener("click", () => {
  alert("Tombol diklik!");
});
```

### 💡 Tips VS Code
Gunakan **Console.log Snippet**: ketik `clg` lalu Tab → otomatis jadi `console.log()`.

---

# **Bab 6 – Mini Project: Portfolio Statis**
Gabungkan HTML + CSS + JS untuk membuat portfolio sederhana.

### Struktur Folder
```
portfolio/
├── index.html
├── style.css
└── script.js
```

Gunakan Live Server (`Alt+L, Alt+O`) untuk preview langsung.

---

# **Bab 7 – Node.js & NPM**

### 🎯 Tujuan
Mengenal Node.js dan manajemen paket menggunakan NPM.

```bash
mkdir hello-node && cd hello-node
npm init -y
echo "console.log('Halo dari Node.js!')" > index.js
node index.js
```

### 💡 Tips VS Code
Gunakan shortcut **Ctrl+Shift+B** untuk menjalankan task otomatis.

---

# **Bab 8 – Express.js**

### 🎯 Tujuan
Membangun server web pertama dengan Express.

```js
const express = require('express');
const app = express();

app.get('/', (req, res) => res.send('Halo dari Express!'));
app.listen(3000, () => console.log('Server di http://localhost:3000'));
```

### 💡 Tips VS Code
Gunakan ekstensi **REST Client** untuk mengetes API langsung di editor.

---

# **Bab 9 – REST API & JSON**

### 🎯 Tujuan
Membuat API dengan method GET, POST, PUT, DELETE.

```js
let users = [];
app.use(express.json());
app.get('/users', (req,res)=>res.json(users));
app.post('/users',(req,res)=>{users.push(req.body);res.json(req.body);});
```

### 💡 Tips VS Code
Gunakan **Thunder Client** extension untuk test API tanpa Postman.

---

# **Bab 10 – Database MySQL & PostgreSQL**

### 🎯 Tujuan
Menghubungkan Express dengan database.

```js
const {Client} = require('pg');
const db = new Client({user:'postgres',password:'123',database:'belajar'});
db.connect();
```

### 💡 Tips VS Code
Gunakan ekstensi **SQLTools** untuk cek tabel langsung dari editor.

---

# **Bab 11 – Session & Login Dasar**

### 🎯 Tujuan
Menambah login sederhana menggunakan session.

```js
const session = require('express-session');
app.use(session({secret:'qaysecret',resave:false,saveUninitialized:false}));
```

### 💡 Tips VS Code
Gunakan `Shift+Alt+↓` untuk duplikasi baris kode login cepat.

---

# **Bab 12 – Deployment di Linux**

### 🎯 Tujuan
Menjalankan aplikasi Node.js di server dengan PM2 & Nginx.

```bash
sudo npm install -g pm2
pm2 start server.js --name myshop
pm2 save && pm2 startup systemd
```

### 💡 Tips VS Code
Gunakan ekstensi **SSH FS** untuk edit file langsung di server.

---

# **Bab 13 – Git & GitHub Deployment**

### 🎯 Tujuan
Menyimpan kode dan melakukan deploy otomatis.

```bash
git init
git add .
git commit -m "Inisialisasi proyek"
git remote add origin https://github.com/qay/myshop.git
git push -u origin main
```

### 💡 Tips VS Code
Gunakan panel **Source Control (Ctrl+Shift+G)** untuk commit cepat.

---

# **Bab 14 – Final Project: MyShop Web App**

### 🎯 Tujuan
Membangun web app lengkap CRUD + Auth + Database + Deploy.

### Fitur Utama
- Login dan Logout.  
- CRUD Produk.  
- Database PostgreSQL.  
- Template EJS.  
- Deploy via Nginx + PM2.

```js
app.get('/produk', async(req,res)=>{
  const data = await db.query('SELECT * FROM produk');
  res.render('dashboard',{produk:data.rows});
});
```

### 💡 Tips VS Code
Gunakan ekstensi **Bookmarks** untuk tandai fungsi penting di file besar.

---

# **Lampiran – Cheat Sheet & Troubleshooting**

### 🧱 Perintah Umum Linux
```
ls, cd, mkdir, rm, nano, chmod, systemctl status, tail -f logs
```

### 🔧 Error Umum
| Error | Penyebab | Solusi |
|-------|-----------|--------|
| EADDRINUSE | Port sudah digunakan | ganti port atau stop proses lama |
| ECONNREFUSED | DB belum jalan | jalankan `sudo systemctl start postgresql` |

### 💡 Tips VS Code Akhir
Gunakan **Settings Sync** agar konfigurasi dan snippet tersimpan di akun GitHub kamu.

---

📘 **Selesai – Modul Pemrograman Dasar Website Q-ay (Full 14 Bab)**

