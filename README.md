# 🏛️ Village Information System & Public E-Services Portal

![Next.js](https://img.shields.io/badge/Next.js-16.3-black?style=for-the-badge&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React-19.2-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-v4-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma_ORM-5.11-2D3748?style=for-the-badge&logo=prisma&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![NextAuth](https://img.shields.io/badge/NextAuth.js-v4-purple?style=for-the-badge&logo=auth0&logoColor=white)
![Shadcn UI](https://img.shields.io/badge/Shadcn_UI-Components-000000?style=for-the-badge)

**Village Information System (SID)** is an integrated public e-service and administrative governance platform designed to digitize village administration and expedite citizen services. Engineered with **Next.js 16 (App Router)**, **TypeScript**, **Tailwind CSS v4**, and **Prisma ORM**, this system unites an interactive civic portal with a high-performance backoffice for local government officials.

---

## ✨ Key System Features

### 👥 Citizen-Facing Public Portal
- **Self-Service Letter Application (`/layanan/pengajuan`):** Citizens can apply for certificates (Domicile, Business License, Financial Hardship, and Police Clearance Letters) autonomously. By providing their National Identification Number (NIK), the system verifies data against municipal demographic records to autofill applicant details.
- **Real-Time Ticket & Tracking (`/layanan/cek-status`):** Every submission generates a unique tracking receipt allowing citizens to monitor progress across transparent stages (*Pending Validation &rarr; In Progress &rarr; Approved / Rejected*).
- **Municipal Budget Transparency (`/data/apbdes`):** Interactive financial infographics breaking down Village Revenue, Expenditures, and Financing alongside budget realization percentages.
- **Demographic Infographics (`/data/penduduk`):** Dynamic population visualizations using **Recharts** (age pyramids, gender distribution, occupational breakdown, education, and religion).
- **Public Grievance Channel (`/pengaduan`):** Citizen feedback and incident reporting for infrastructure, sanitation, or social issues with photo evidence attachments.
- **Village Profile & Economic Potential (`/profil`, `/potensi`, `/lembaga`):** Historical archives, municipal apparatus charts, regional maps, civic institutions (BPD, LPMD, PKK), and tourism/economic registries.
- **News CMS & Announcements (`/berita`):** Official communications channel for policy updates, community agendas, and municipal bulletins.

### 🛡️ Administrative Backoffice & Staff Workspace
- **Secure Authentication & RBAC:** Session security via **NextAuth.js (Auth.js)** with middleware route guarding and role segmentation: `SUPERADMIN` (IT Administrator / Village Secretary) and `STAFF` (Public Service Officer).
- **Master Demographic Registry (`/admin/penduduk`):** Centralized citizen database with multi-parameter search (NIK/Name), regional neighborhood filters, and vital status updates (*Permanent, Relocated, Deceased*).
- **Service Desk & Verification (`/admin/layanan`):** Split-screen document verification displaying application data alongside high-resolution ID attachments with one-click approval, rejection explanations, and official document printing.
- **Budget Management (`/admin/apbdes`):** Dynamic ledger management for recording municipal budgets and updating expenditure allocations.
- **Grievance Moderation (`/admin/pengaduan`):** Lifecycle resolution for public reports (*UNREAD &rarr; READ &rarr; RESOLVED*).
- **Integrated News CMS (`/admin/konten`):** Unified content editor for drafting and publishing articles and notices.

---

## 🛠️ Technical Architecture & Technology Stack

| Architecture Layer | Technology Selection |
| :--- | :--- |
| **Meta-Framework** | [Next.js 16](https://nextjs.org/) (App Router Architecture, React Server Components) |
| **Programming Language** | [TypeScript 5](https://www.typescriptlang.org/) (Strict Type Safety) |
| **Frontend Library** | [React 19](https://react.dev/) |
| **Styling & Design System** | [Tailwind CSS v4](https://tailwindcss.com/) with Modern Emerald Palette |
| **UI Components** | [Shadcn UI](https://ui.shadcn.com/) + Base UI + Lucide React |
| **Database & ORM** | [MySQL](https://www.mysql.com/) integrated via [Prisma ORM v5](https://www.prisma.io/) |
| **Authentication & Security** | [NextAuth.js v4](https://next-auth.js.org/) + `bcryptjs` (Password Hashing) |
| **Form & Validation** | [React Hook Form](https://react-hook-form.com/) + [Zod Schema Validation](https://zod.dev/) |
| **Data Visualization** | [Recharts](https://recharts.org/) (Demographic Charts & Financial Progress) |
| **Toast Notifications** | [Sonner](https://sonner.emilkowal.ski/) |

---

## 📁 Source Code Organization

```text
web-desa-muer/
├── prisma/
│   ├── schema.prisma         # Relational database schema (User, Resident, LetterRequest, Budget, Grievance, News)
│   └── seed.js               # Default administrative account seeder
├── public/                   # Static images, icons, and vectors
├── src/
│   ├── app/
│   │   ├── (public)/         # Citizen-facing public routes
│   │   ├── admin/            # Administrative backoffice routes
│   │   ├── api/              # Backend API route handlers (NextAuth, REST)
│   │   ├── login/            # Staff authentication login view
│   │   ├── globals.css       # Tailwind CSS v4 variables & design tokens
│   │   └── layout.tsx        # Root HTML layout and font loading
│   ├── components/
│   │   ├── forms/            # Isolated form components (letter requests, resident mutations)
│   │   ├── layout/           # Public navigation, footer, and admin sidebar
│   │   └── ui/               # Atomic Shadcn UI primitives (Button, Dialog, Card, etc.)
│   ├── lib/
│   │   ├── auth.ts           # NextAuth credentials provider & JWT callbacks
│   │   ├── utils.ts          # Class merging helper utilities (clsx & twMerge)
│   │   └── validations/      # Zod validation schemas
│   └── middleware.ts         # Route guarding for `/admin/*` paths
├── package.json
└── tsconfig.json
```

---

## 🚀 Local Installation & Setup Guide

### 1. System Requirements
- [Node.js](https://nodejs.org/) version 18.18+ or 20+
- [MySQL Database Server](https://dev.mysql.com/downloads/)

### 2. Repository Cloning
```bash
git clone https://github.com/pranataa-labs/Village-Information-System.git
cd Village-Information-System
```

### 3. Dependency Installation
```bash
npm install
```

### 4. Environment Configuration (`.env`)
```env
DATABASE_URL="mysql://root:@localhost:3306/db_desa_muer"
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="your_secure_random_32_character_secret_string"
```

### 5. Database Schema & Seeder
```bash
npx prisma db push
node prisma/seed.js
```

### 6. Run Development Server
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🔐 Administrative Demo Credentials

| Role | Username | Default Password | Menu Access |
| :--- | :--- | :--- | :--- |
| **Superadmin (IT / Municipal Officer)** | `admin` | `admin123` | Complete Backoffice Features (`/admin`) |

---

<p align="center">
  Maintained with ❤️ by <b><a href="https://github.com/pranataa-labs">pranataa-labs</a></b>
</p>
