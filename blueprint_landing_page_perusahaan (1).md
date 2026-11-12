# Blueprint Pembuatan Landing Page Perusahaan

Dokumen ini berisi panduan struktur konten, arsitektur folder, sistem desain (UI/UX), dan rekomendasi *tech stack* modern menggunakan **Astro** atau **Next.js** dengan **Tailwind CSS**.

## 1. Struktur Section (Urutan dari Atas ke Bawah)

### A. Above the Fold (Tampilan Pertama)

* **Navbar (Header):**

  * Logo perusahaan di sisi kiri.

  * Maksimal 4–5 tautan navigasi (*Tentang Kami*, *Layanan*, *Portofolio*, *Testimoni*, *FAQ*).

  * 1 Tombol **CTA (Call to Action)** utama yang kontras (contoh: *"Hubungi Kami"* atau *"Konsultasi Gratis"*).

* **Hero Section:**

  * **Headline:** Kalimat utama yang singkat, kuat, dan menjelaskan nilai jual (*Unique Value Proposition*).

  * **Sub-headline:** 1–2 kalimat penjelas solusi yang ditawarkan kepada klien.

  * **Tombol CTA Utama & Sekunder:** Ajakan bertindak (contoh: *"Mulai Proyek"* dan *"Lihat Portofolio"*).

  * **Visual:** Foto tim profesional, produk unggulan, atau ilustrasi modern.

### B. Membangun Kepercayaan & Penjelasan

* **Social Proof Awal:** Deretan logo klien, partner resmi, atau sertifikasi yang dimiliki.

* **Tentang Kami (About Us):** Ringkasan profil perusahaan, visi/misi, dan pencapaian dalam angka (contoh: `10+ Tahun Pengalaman`, `200+ Klien Puas`).

* **Layanan / Produk Utama:** Penjelasan singkat 3–4 layanan inti dalam format *card* dengan ikon yang jelas dan fokus pada manfaat bagi klien.

* **Keunggulan Kami (Why Choose Us):** Poin pembeda dibandingkan kompetitor (contoh: garansi layanan, dukungan 24/7, harga transparan).

### C. Validasi & Konversi

* **Portofolio / Studi Kasus:** Bukti hasil kerja nyata (gambar proyek, tautan demo, atau studi kasus).

* **Testimoni Klien:** Ulasan jujur dari klien beserta nama, jabatan, dan nama perusahaan mereka.

* **FAQ (Frequently Asked Questions):** Daftar pertanyaan yang sering diajukan beserta jawabannya untuk menghilangkan keraguan calon klien.

### D. Bagian Penutup

* **Final CTA Banner:** Ajakan bertindak terakhir sebelum pengunjung keluar dari halaman.

* **Footer:** Alamat lengkap kantor, nomor WhatsApp/telepon, email resmi, tautan media sosial, peta lokasi, dan hak cipta.

## 2. Panduan Sistem Desain (UI/UX)

Agar implementasi ke Tailwind CSS konsisten dan terlihat profesional, terapkan standar desain berikut:

### A. Palet Warna (Color Palette)

Gunakan aturan proporsi **60-30-10**:

* **60% Warna Dominan (Background):** Putih bersih (`#FFFFFF`) atau abu-abu sangat terang (`#F8FAFC` / `slate-50`) untuk memberi kesan luas dan modern.

* **30% Warna Sekunder (Teks & Permukaan):** Biru gelap/hitam arang (`#0F172A` / `slate-900`) untuk judul agar kontras tajam, dan abu-abu sedang (`#475569` / `slate-600`) untuk paragraf.

* **10% Warna Aksen (Brand & CTA):** Warna utama identitas perusahaan (contoh: Biru Korporat `#2563EB` / `blue-600` atau Hijau Zamrud `#059669` / `emerald-600`) khusus untuk tombol CTA, tautan aktif, dan sorotan penting.

### B. Tipografi (Typography)

* **Font Utama:** Gunakan font *sans-serif* modern dan mudah dibaca seperti **Inter**, **Plus Jakarta Sans**, atau **DM Sans** (dapat dimuat via Google Fonts atau `@fontsource`).

* **Hierarki Ukuran (Tailwind Scale):**

  * **Hero Headline (H1):** `text-4xl md:text-6xl font-bold tracking-tight`

  * **Section Title (H2):** `text-3xl md:text-4xl font-bold`

  * **Card Title (H3):** `text-xl font-semibold`

  * **Body Text:** `text-base md:text-lg leading-relaxed`

### C. Tata Letak & Ruang Kosong (Layout & Spacing)

* **Container:** Batasi lebar maksimal konten di tengah layar dengan `max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`.

* **Jarak Antar Section:** Berikan ruang napas (*whitespace*) yang lega antar bagian menggunakan `py-16 md:py-24`.

* **Border & Shadow:** Gunakan sudut membulat yang konsisten (`rounded-xl` atau `rounded-2xl`) dan bayangan halus (`shadow-sm` dengan `border border-slate-200`) pada komponen kartu.

## 3. Arsitektur Folder Proyek

Pisahkan setiap bagian ke dalam komponen modular agar mudah dirawat dan dikembangkan:

```
src/
├── components/
│   ├── Navbar.astro          # atau .tsx untuk Next.js
│   ├── Hero.astro
│   ├── ClientLogos.astro
│   ├── About.astro
│   ├── Services.astro
│   ├── WhyChooseUs.astro
│   ├── Portfolio.astro
│   ├── Testimonials.astro
│   ├── FAQ.astro
│   ├── CTA.astro
│   └── Footer.astro
├── layouts/
│   └── MainLayout.astro      # Meta tag SEO, font, struktur HTML dasar
├── styles/
│   └── global.css            # Konfigurasi Tailwind CSS
└── pages/
    └── index.astro           # Halaman utama yang menggabungkan semua komponen

```

## 4. Panduan Inisialisasi Proyek

### Opsi A: Menggunakan Astro + Tailwind CSS

Direkomendasikan jika web fokus pada kecepatan maksimal (*zero JS by default*) dan konten statis.

```
# 1. Buat proyek Astro baru
npm create astro@latest company-landing-page

# 2. Masuk ke direktori proyek
cd company-landing-page

# 3. Tambahkan integrasi Tailwind CSS
npx astro add tailwind

# 4. Install library ikon (Lucide)
npm install lucide-astro

# 5. Jalankan server lokal
npm run dev

```

### Opsi B: Menggunakan Next.js + Tailwind CSS

Direkomendasikan jika ke depannya web akan dikembangkan menjadi aplikasi interaktif yang lebih kompleks.

```
# 1. Buat proyek Next.js baru (pilih Tailwind CSS saat prompt muncul)
npx create-next-app@latest company-landing-page

# 2. Masuk ke direktori proyek
cd company-landing-page

# 3. Install library ikon & animasi
npm install lucide-react framer-motion

# 4. Jalankan server lokal
npm run dev

```

## 5. Ekosistem & Layanan Pendukung

| Kebutuhan | Rekomendasi Tools / Layanan | Keterangan | 
| ----- | ----- | ----- | 
| **Ikon UI** | Lucide Icons (`lucide-astro` / `lucide-react`) | Ringan, konsisten, dan mudah dikustomisasi ukurannya. | 
| **Formulir Kontak** | Web3Forms / Formspree / Resend | Mengirim pesan dari form web langsung ke email tanpa membuat *backend* sendiri. | 
| **Animasi Ringan** | Tailwind CSS Animate / AOS / Framer Motion | Memberikan efek transisi *scroll* yang profesional. | 
| **Hosting & Deploy** | Vercel / Cloudflare Pages / Netlify | Gratis untuk situs statis, otomatis terhubung ke GitHub, dan sudah mendukung SSL. | 

## 6. Checklist Sebelum Rilis (Go-Live)

* \[ \] **Konsistensi Desain:** Palet warna, ukuran font, dan jarak (*padding/margin*) sudah sesuai dengan panduan sistem desain.

* \[ \] **Responsivitas:** Tampilan rapi di layar *mobile* (360px), *tablet* (768px), dan *desktop* (1280px+).

* \[ \] **Optimasi Gambar:** Semua gambar sudah dikompresi dan menggunakan format modern (`.webp` atau `.avif`).

* \[ \] **SEO Dasar:** Tag `<title>`, `<meta name="description">`, Open Graph (untuk pratinjau tautan WhatsApp/sosmed), dan `favicon` sudah terpasang.

* \[ \] **Fungsionalitas Tombol:** Semua tombol CTA dan tautan WhatsApp/formulir kontak berfungsi dengan benar.

* \[ \] **Performa:** Skor Google PageSpeed Insights minimal 90+ untuk perangkat *mobile* dan *desktop*.