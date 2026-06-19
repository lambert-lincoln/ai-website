# Design.md
### Design Brief — "Rol" Landing Page

Dokumen ini adalah context lengkap buat LLM yang bakal build website-nya. Semua keputusan visual & copy udah final — ikutin persis, jangan improvisasi ke arah default (warm cream + serif, dark + neon accent, atau broadsheet newspaper layout), kecuali emang disebut di bawah.

---

## 1. Brand Overview

**Nama:** Rol
**Apa ini:** Jasa cuci, scan, dan cetak film analog. Bisa drop-off langsung atau kirim roll film via kurir/JNE, hasil scan dikirim digital dalam 24-48 jam.
**Target audience:** Anak muda urban (20-30 tahun) yang lagi explore kamera film — bukan fotografer profesional, tapi orang yang suka proses "nunggu" dan hasil yang nggak instan kayak HP.
**Single job halaman ini:** Convince mereka buat kirim/antar roll film pertama mereka ke Rol. Satu CTA utama: **"Kirim Roll Pertamamu"**.

**Brand story (insight yang dipakai buat angle copy):**
Orang balik ke film bukan karena hasilnya lebih bagus dari kamera HP — tapi karena prosesnya yang lambat itu sendiri yang dicari. Nggak ada preview, nggak ada delete-retake, nggak ada filter. Foto yang jadi adalah foto yang emang terjadi. Rol posisinya sebagai partner yang ngerti ritual itu, bukan cuma "lab cuci film" generic.

---

## 2. Voice & Tone

- Bahasa Indonesia santai, kayak ngomong ke temen yang juga suka motret film — bukan bahasa marketing korporat.
- Hindari kata "solusi", "terdepan", "terpercaya" — kata-kata generic lab/jasa.
- Istilah teknis film (C-41, ISO, push/pull process, contact sheet) dipakai natural, nggak dijelasin berlebihan — audiensnya udah ngerti atau penasaran buat cari tau sendiri.
- Kalimat pendek. Nggak perlu emoji berlebihan di body copy (beda sama caption sosmed).
- Tone: tenang, sedikit nostalgic, percaya diri — bukan hard-selling.

---

## 3. Visual Identity

### Palet Warna (token system)

| Nama | Hex | Peran |
|---|---|---|
| Hitam Kamar Gelap | `#15110D` | Background utama |
| Merah Safelight | `#A8331F` | Accent utama, CTA, highlight |
| Amber Negatif | `#D89A4E` | Accent sekunder, hover state, garis tipis |
| Putih Kertas Foto | `#F1EAD9` | Teks utama di atas background gelap |
| Abu Seluloid | `#7A726A` | Teks sekunder, caption, metadata |
| Hijau Kontak (sangat minim, dipakai dikit aja) | `#3C4A37` | Hanya buat satu elemen signature (lihat bawah), jangan dipake di tempat lain |

Catatan: background BUKAN pure black (`#000`) dan BUKAN warm cream — ini dark, tapi warm dark, kayak ruangan dengan satu lampu merah nyala.

### Tipografi

- **Display (headline):** Serif dengan karakter sedikit quirky/vintage — pakai font yang punya optical sizing/personality kuat (contoh: Fraunces). Dipakai gede di hero, dibatasin cuma buat headline-level, jangan dipake di body.
- **Body:** Sans yang clean & sangat readable di background gelap (contoh: Inter atau IBM Plex Sans). Ukuran nyaman dibaca, line-height lega.
- **Utility/mono:** Monospace (contoh: IBM Plex Mono) — dipakai khusus buat hal yang mimicking timestamp/stempel di film: nomor section, harga, metadata teknis ("ISO 400 · C-41 · 36 EXP"). Ini yang bikin halaman kerasa kayak label di canister film.

### Layout Concept

Single page, scroll vertikal, section-section dengan jeda visual yang jelas (bukan card grid generic). Wireframe kasar:

```
┌─────────────────────────────┐
│  NAV: logo "Rol" · CTA kecil │
├─────────────────────────────┤
│         HERO                 │
│  headline besar (serif)      │
│  frame foto yang "develop"   │  ← signature element ada di sini
│  CTA: Kirim Roll Pertamamu   │
├─────────────────────────────┤
│  INSIGHT/STORY (kenapa film) │
│  teks pendek, 1 kolom, fokus │
├─────────────────────────────┤
│  CARA KERJA (proses)         │
│  01 Kirim/Antar               │
│  02 Kami Develop               │
│  03 Scan + Kirim Digital      │
│  → ini sequence asli, jadi    │
│    numbered marker make sense │
├─────────────────────────────┤
│  LAYANAN & HARGA              │
│  list, gaya label canister    │
├─────────────────────────────┤
│  HASIL (galeri scan)          │
│  grid foto, grain texture      │
├─────────────────────────────┤
│  TESTIMONI                    │
│  2-3 quote, minimal styling   │
├─────────────────────────────┤
│  CTA PENUTUP + LOKASI/KONTAK  │
├─────────────────────────────┤
│  FOOTER                       │
└─────────────────────────────┘
```

### Signature Element

Satu elemen yang bikin halaman ini diingat: **frame foto di hero yang "develop" pas di-scroll.** Mulai dari frame negatif merah-gelap nyaris kosong (kayak film yang baru masuk developer), terus secara bertahap (scroll-triggered) gambar muncul jadi foto penuh — termasuk detail sprocket holes tipis di kiri-kanan frame. Ini satu-satunya tempat animasi "showy" boleh terjadi. Bagian lain halaman tetap tenang & minim motion.

Warna hijau kontak (`#3C4A37`) khusus dipakai di outline frame ini doang pas state "developing" — nggak dipakai di tempat lain di halaman.

### Motion Notes

- Hero: scroll-triggered develop effect (signature element di atas). Sekali aja, orchestrated, bukan diulang-ulang.
- Section lain: fade/slide-up halus pas masuk viewport, durasi singkat, nggak perlu effect tambahan.
- Hover state tombol/CTA: transisi warna ke Amber Negatif, simple.
- Respect `prefers-reduced-motion` — kalau user set itu, signature element langsung tampil full (skip animasi develop), section lain skip fade.

---

## 4. Konten per Section (copy asli, bukan placeholder)

### Hero
- **Headline:** "Roll-mu Belum Selesai Sampai Dicuci"
- **Subheadline:** "Kirim atau antar roll film-mu, kami develop & scan, hasil digital balik ke kamu dalam 24-48 jam."
- **CTA button:** "Kirim Roll Pertamamu"

### Insight/Story
- **Heading:** "Kenapa Repot-Repot Film?"
- **Body:** "Nggak ada preview. Nggak ada delete-retake. Foto yang jadi adalah foto yang emang terjadi. Itu yang bikin orang balik ke film — bukan soal kualitas, tapi soal proses yang nggak instan."

### Cara Kerja (numbered, karena beneran sequence)
- **01 — Kirim atau Antar** — "Drop-off langsung ke studio kami, atau kirim via kurir. Roll apapun, 35mm atau 120."
- **02 — Kami Develop** — "C-41 standard process, dikerjakan harian. Push/pull process tersedia kalau roll-nya butuh treatment khusus."
- **03 — Scan + Kirim Digital** — "Hasil scan resolusi tinggi dikirim ke email/Drive kamu. Cetak fisik opsional."

### Layanan & Harga (gaya label canister, pakai font mono buat angka/spec)
- **Develop + Scan (35mm, 36 exp)** — Rp 65.000 · ISO 100-3200 · 24-48 jam
- **Develop + Scan (120 / medium format)** — Rp 85.000
- **Push/Pull Process** — +Rp 25.000
- **Cetak fisik (4R, per lembar)** — Rp 2.500

(Angka di atas contoh placeholder harga — sesuaikan ke harga asli sebelum publish.)

### Hasil
- **Heading:** "Yang Udah Di-develop Minggu Ini"
- Grid galeri foto hasil scan customer (grain texture kelihatan, jangan di-edit kelewat clean)

### Testimoni
- 2-3 quote singkat dari customer fiktif, gaya santai bukan testimoni korporat. Contoh: *"Baru tau hasil scan-nya pas udah lupa apa yang gue foto. Itu serunya."*

### CTA Penutup + Lokasi
- **Heading:** "Roll Udah Penuh? Saatnya Develop."
- Info drop-off location + opsi kirim, link/CTA kirim roll.

### Footer
- Logo, social link, jam operasional, kontak WA/email.

---

## 5. Technical & Accessibility Notes

- Single HTML page (atau single-file React kalau itu environment build-nya), CSS & JS digabung di file yang sama.
- Responsive penuh sampai mobile width — ini target utama karena audiensnya browsing dari HP.
- Visible keyboard focus di semua interactive element (CTA, link).
- Respect `prefers-reduced-motion` (lihat Motion Notes di atas).
- Semua teks dalam Bahasa Indonesia, termasuk alt-text gambar.
- Hindari numbered marker (01/02/03) di section lain selain "Cara Kerja" — di section itu valid karena emang proses berurutan, di tempat lain jangan dipaksain.

---

## 6. Out of Scope

- Ini single landing page — JANGAN bikin multi-page routing, nav ke halaman lain, atau form booking yang fungsional (cukup CTA visual, belum perlu backend).
- Jangan tambah fitur yang nggak diminta (live chat widget, newsletter popup, dll).