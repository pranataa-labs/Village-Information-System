# 🏛️ Desa Muer - Sistem Informasi Desa (SID) & E-Layanan Publik

![Next.js](https://img.shields.io/badge/Next.js-16.3-black?style=for-the-badge&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React-19.2-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-v4-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma_ORM-5.11-2D3748?style=for-the-badge&logo=prisma&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![NextAuth](https://img.shields.io/badge/NextAuth.js-v4-purple?style=for-the-badge&logo=auth0&logoColor=white)
![Shadcn UI](https://img.shields.io/badge/Shadcn_UI-Components-000000?style=for-the-badge)

**Desa Muer** adalah platform **Sistem Informasi Desa (SID) dan Portal E-Layanan Publik** terintegrasi yang dirancang untuk mendigitalisasi tata kelola administrasi desa dan mempercepat pelayanan masyarakat. Dibangun dengan meta-framework **Next.js 16 (App Router)**, **TypeScript**, **Tailwind CSS v4**, dan **Prisma ORM**, sistem ini memadukan portal informasi publik yang interaktif dengan *backoffice dashboard* berperforma tinggi untuk aparatur desa.

---

## ✨ Fitur Utama (Key Features)

### 👥 Sisi Warga & Pengunjung (Public-Facing Portal)
* **E-Layanan Surat Mandiri Berbasis NIK (`/layanan/pengajuan`):** Warga dapat mengajukan permohonan surat keterangan (Surat Keterangan Domisili, SKU, SKTM, dan Pengantar SKCK) secara mandiri. Cukup dengan menginput NIK, sistem secara cerdas melakukan verifikasi silang ke basis data kependudukan desa untuk mengautofill identitas pemohon.
* **Tracking Resi Surat Real-Time (`/layanan/cek-status`):** Setiap pengajuan menghasilkan nomor resi/tiket unik. Warga dapat memantau progres permohonan melalui indikator tahapan (*Menunggu Validasi $\rightarrow$ Diproses $\rightarrow$ Selesai / Ditolak*).
* **Transparansi Anggaran APBDes (`/data/apbdes`):** Infografis interaktif rincian Pendapatan Desa, Belanja Desa, dan Pembiayaan disertai persentase penyerapan anggaran untuk mewujudkan akuntabilitas publik.
* **Infografis Kependudukan Interaktif (`/data/penduduk`):** Visualisasi data demografi desa menggunakan **Recharts** (piramida rentang usia, rasio gender, sebaran pekerjaan, pendidikan, dan agama).
* **Kanal Pengaduan Warga / Lapor Warga! (`/pengaduan`):** Saluran partisipasi warga untuk melaporkan kendala infrastruktur, ketertiban, kebersihan, atau sosial lengkap dengan deskripsi dan lampiran bukti foto.
* **Profil & Potensi Desa (`/profil`, `/potensi`, `/lembaga`):** Dokumentasi sejarah desa, visi-misi, bagan struktur organisasi aparatur desa, peta wilayah, kelembagaan masyarakat (BPD, LPMD, PKK), dan direktori potensi ekonomi/wisata daerah.
* **CMS Berita & Pengumuman (`/berita`):** Media publikasi resmi seputar agenda kegiatan, sosialisasi kebijakan, dan informasi terkini pemerintah desa.

### 🛡️ Sisi Aparatur Desa (Admin Dashboard & Backoffice)
* **Autentikasi Aman & RBAC:** Sistem autentikasi berbasis **NextAuth.js (Auth.js)** dengan proteksi *middleware* dan pembagian hak akses (*Role-Based Access Control*): `SUPERADMIN` (Sekdes/Administrator IT) dan `STAFF` (Kaur Pelayanan).
* **Buku Induk Kependudukan (`/admin/penduduk`):** Manajemen basis data penduduk terpusat dengan dukungan pencarian multi-parameter (NIK/Nama), filter wilayah dusun/RT/RW, dan mutasi status kependudukan (*Tetap, Pindah, Meninggal*).
* **Meja Kerja Layanan Surat (`/admin/layanan`):** Validasi berkas pemohon dengan antarmuka *split-screen* (data pemohon berdampingan langsung dengan foto lampiran KTP/KK asli). Dilengkapi aksi pemrosesan, input alasan penolakan, serta fitur cetak surat resmi.
* **Manajemen Anggaran APBDes (`/admin/apbdes`):** Panel dinamis untuk mencatat pagu anggaran dan pemutakhiran realisasi per pos belanja.
* **Moderasi Aspirasi & Pengaduan (`/admin/pengaduan`):** Manajemen siklus laporan masuk warga dari status `UNREAD` $\rightarrow$ `READ` $\rightarrow$ `RESOLVED`.
* **CMS Pengelolaan Berita (`/admin/konten`):** Editor konten terpadu untuk menerbitkan atau mengarsipkan artikel dan pengumuman desa.

---

## 🛠️ Tech Stack & Arsitektur Sistem

| Layer / Kebutuhan | Teknologi yang Digunakan |
| :--- | :--- |
| **Meta-Framework** | [Next.js 16](https://nextjs.org/) (App Router Architecture, React Server Components) |
| **Bahasa Pemrograman** | [TypeScript 5](https://www.typescriptlang.org/) (Strict Type Safety) |
| **Frontend Library** | [React 19](https://react.dev/) |
| **Styling & Theme** | [Tailwind CSS v4](https://tailwindcss.com/) dengan palet Emerald Modern |
| **UI Components** | [Shadcn UI](https://ui.shadcn.com/) + Base UI + Lucide React |
| **Database & ORM** | [MySQL](https://www.mysql.com/) terintegrasi via [Prisma ORM v5](https://www.prisma.io/) |
| **Autentikasi & Keamanan** | [NextAuth.js v4](https://next-auth.js.org/) + `bcryptjs` (Password Hashing) |
| **Form & Validasi** | [React Hook Form](https://react-hook-form.com/) + [Zod Schema Validation](https://zod.dev/) |
| **Data Visualization** | [Recharts](https://recharts.org/) (Demographic Charts & Financial Progress) |
| **Toast Notifications** | [Sonner](https://sonner.emilkowal.ski/) |

---

## 📁 Struktur Direktori (Source Code Overview)

```text
web-desa-muer/
├── prisma/
│   ├── schema.prisma         # Skema basis data relasional (User, Penduduk, PengajuanSurat, APBDes, Pengaduan, Berita)
│   └── seed.js               # Seeder default akun administrator
├── public/                   # Aset gambar statis, ikon, dan vektor
├── src/
│   ├── app/
│   │   ├── (public)/         # Rute antarmuka portal publik warga
│   │   │   ├── berita/       # Halaman direktori & detail berita
│   │   │   ├── data/         # Grafik demografi kependudukan & transparansi APBDes
│   │   │   ├── layanan/      # E-Layanan pengajuan surat & tracking nomor resi
│   │   │   ├── lembaga/      # Informasi BPD, LPMD, PKK, dsb.
│   │   │   ├── pengaduan/    # Formulir aspirasi & Lapor Warga!
│   │   │   ├── potensi/      # Potensi ekonomi, pertanian, & wisata desa
│   │   │   ├── profil/       # Sejarah, Visi Misi, dan Struktur Aparatur Desa
│   │   │   └── page.tsx      # Beranda utama (Hero, Quick Stats, Sambutan Kades)
│   │   ├── admin/            # Rute antarmuka khusus Aparatur Desa (Dashboard Backoffice)
│   │   │   ├── apbdes/       # Pengelolaan data keuangan desa
│   │   │   ├── dashboard/    # Metrik ringkasan operasional desa
│   │   │   ├── konten/       # Manajemen CMS artikel & berita
│   │   │   ├── layanan/      # Verifikasi & pemrosesan surat warga
│   │   │   ├── penduduk/     # Buku Induk Kependudukan desa
│   │   │   └── pengaduan/    # Tindak lanjut laporan aduan warga
│   │   ├── api/              # Endpoint API backend (NextAuth, REST handler)
│   │   ├── login/            # Halaman login administrator & staf
│   │   ├── globals.css       # Konfigurasi Tailwind CSS v4 & theme variables
│   │   └── layout.tsx        # Root layout HTML & font loading
│   ├── components/
│   │   ├── forms/            # Komponen form terisolasi (pengajuan surat, penduduk, dsb.)
│   │   ├── layout/           # Navbar, Footer publik, dan Sidebar dashboard
│   │   └── ui/               # Koleksi komponen UI atomik (Button, Dialog, Select, Card, dsb.)
│   ├── lib/
│   │   ├── auth.ts           # Konfigurasi NextAuth Provider & JWT callback
│   │   ├── utils.ts          # Helper class utilities (clsx & twMerge)
│   │   └── validations/      # Skema validasi Zod (NIK 16 digit, form surat, dll.)
│   └── middleware.ts         # Route guarding untuk mengamankan path `/admin/*`
├── package.json
└── tsconfig.json
```

---

## 🚀 Panduan Menjalankan Proyek (Local Development)

### 1. Prasyarat Sistem
* [Node.js](https://nodejs.org/) versi 18.18+ atau versi 20+
* [MySQL Database Server](https://dev.mysql.com/downloads/) (XAMPP / Laragon / Docker)

### 2. Kloning Repositori
```bash
git clone https://github.com/pranataa-labs/village.git
cd village
```

### 3. Instalasi Dependensi
```bash
npm install
```

### 4. Konfigurasi Environment (`.env`)
Buat atau sesuaikan file `.env` di direktori *root*:
```env
# Koneksi Database MySQL
DATABASE_URL="mysql://root:@localhost:3306/db_desa_muer"

# Konfigurasi NextAuth
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="ganti_dengan_random_secret_string_32_karakter"
```

### 5. Setup Skema Database & Seeder
Jalankan migrasi Prisma dan seed akun administrator default:
```bash
# Push skema tabel ke MySQL
npx prisma db push

# Eksekusi seeder akun admin
node prisma/seed.js
```

### 6. Jalankan Server Development
```bash
npm run dev
```
Buka peramban Anda di [http://localhost:3000](http://localhost:3000).

---

## 🔐 Kredensial Demo Akun Administrator

| Role | Username | Password Default | Akses Menu |
| :--- | :--- | :--- | :--- |
| **Superadmin (Kaur IT / Sekdes)** | `admin` | `admin123` | Seluruh fitur Backoffice (`/admin`) |

---

## 💡 Nilai Strategis Portofolio

Proyek ini merefleksikan penguasaan mendalam dalam rekayasa perangkat lunak berskala institusi publik:
1. **Arsitektur Meta-Framework Modern:** Pemanfaatan *React Server Components* (RSC) Next.js 16 untuk kecepatan rendering optimal dan SEO pada halaman publik, dipadukan dengan *Client Components* dinamis untuk interaktivitas formulir dan charting.
2. **Integritas Data Relasional:** Pemodelan skema kependudukan, pengajuan surat, transaksi APBDes, dan relasi data menggunakan Prisma ORM dengan *strict data types*.
3. **Standar Keamanan Sektor Publik:** Penerapan validasi input komprehensif (Zod) untuk mencegah anomali data NIK/KK, enkripsi kata sandi berbasis *bcrypt*, serta otorisasi berbasis sesi JWT yang kokoh.
4. **Desain UI/UX Berpusat pada Pengguna (Citizen-Centric):** Desain visual ramah pengguna dengan nuansa *emerald*, tata letak responsif di perangkat seluler, serta keterbacaan data yang memudahkan seluruh lapisan masyarakat.

---

<p align="center">
  Dikelola dengan ❤️ oleh <b><a href="https://github.com/pranataa-labs">pranataa-labs</a></b>
</p>
