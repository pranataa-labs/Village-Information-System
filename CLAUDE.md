# Sistem Informasi Desa (SID) Modern — Portal Pelayanan Publik

**Tech Stack:** Next.js 16 (App Router), TypeScript, Tailwind CSS, Prisma ORM, MySQL.  
**Standards & Operating Workflow:** Terintegrasi penuh dengan [Workflow Master](.workflow/README.md).

---

## 1. Operating Discipline & Engineering Workflow
Semua pekerjaan rekayasa pada repositori ini WAJIB mematuhi 9 tahapan alur kerja di `.workflow/workflows/00-engineering-workflow-ai-coding.md`:
1. **Triage:** Pahami tujuan, klasifikasikan tipe tugas dan tingkat risiko (Low / Medium / High).
2. **Discover:** Periksa skema Prisma (`prisma/schema.prisma`), server actions / API routes, dan komponen UI.
3. **Design:** Rancang acceptance criteria, flow data Server Component vs Client Component, dan validasi schema Zod.
4. **Plan:** Tentukan file dan urutan modifikasi; hindari overengineering.
5. **Implement:** Tulis kode TypeScript yang strictly-typed, aman dari XSS/injection, dan modular.
6. **Verify:** Jalankan typecheck (`npm run build` atau `npx tsc --noEmit`) dan linter (`npm run lint`).
7. **Review:** Periksa diff, verifikasi server-side validation (jangan percaya input form client), dan otorisasi RBAC admin desa vs warga.
8. **Release:** Verifikasi migrasi skema Prisma (`npx prisma migrate status`).
9. **Report:** Laporkan hasil verifikasi nyata dengan jujur (Passed / Failed / Skipped).

---

## 2. Aturan Khusus Ekosistem Next.js & Desa
- **Privasi Data Kependudukan (PII):** NIK, nomor KK, dan data pribadi warga WAJIB dienkripsi atau dilindungi dari kebocoran public endpoint.
- **Server Action & Validation:** Seluruh form pengajuan surat online WAJIB divalidasi menggunakan skema Zod di sisi server sebelum disimpan via Prisma.
- **Accessibility & Mobile-First:** Portal layanan warga wajib ramah perangkat mobile dan mematuhi WCAG 2.2 AA (Rule 01 Frontend).
