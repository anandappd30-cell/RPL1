# SaveIt - Aplikasi Manajer Finansial & Prioritas Pengeluaran Harian (Metode SAW)

> **Tugas Akhir Rekayasa Perangkat Lunak (RPL) / SPK**  
> **Judul:** APLIKASI MANAJER FINANSIAL DAN PRIORITAS PENGELUARAN HARIAN MENGGUNAKAN METODE SAW BERBASIS MOBILE (SaveIt)

Aplikasi *Decision Support System* (SPK) berbasis mobile untuk membantu pengguna memprioritaskan rencana pengeluaran harian dan mencegah pembelian impulsif menggunakan algoritma **Simple Additive Weighting (SAW)** yang terintegrasi dengan sisa pagu anggaran harian (*daily budget thresholding*).

---

## 🚀 Cara Menjalankan di VS Code (Lokal di Laptop/PC)

Aplikasi ini dibangun menggunakan **React 19 + TypeScript + Vite + Tailwind CSS**. Sangat mudah dijalankan di VS Code dengan langkah berikut:

### 1. Prasyarat (Prerequisites)
Pastikan laptop Anda sudah terinstal:
- **Node.js** (Versi 18 ke atas / LTS disarankan): Unduh gratis di [https://nodejs.org](https://nodejs.org) jika belum ada.
- **Visual Studio Code (VS Code)**: Unduh di [https://code.visualstudio.com](https://code.visualstudio.com).

### 2. Buka Folder Proyek di VS Code
1. Ekstrak file zip / clone repositori ini ke laptop Anda.
2. Buka aplikasi **VS Code**.
3. Pilih menu **File** > **Open Folder...**, lalu pilih folder proyek ini (`SaveIt`).

### 3. Buka Terminal di VS Code
Di VS Code, tekan tombol pintasan:
- **Windows / Linux:** `Ctrl + \`` (tombol backtick di atas tombol Tab) atau menu **Terminal** > **New Terminal**.
- **macOS:** `Cmd + \``

### 4. Install Dependencies
Ketik perintah berikut di terminal lalu tekan **Enter**:
```bash
npm install
```
*Tunggu proses instalasi package selesai (membuat folder `node_modules`).*

### 5. Jalankan Server Pengembangan (Dev Server)
Ketik perintah:
```bash
npm run dev
```

Terminal akan menampilkan link:
```
  VITE v8.x.x  ready in xxx ms

  ➜  Local:   http://localhost:3000/
  ➜  Network: http://192.168.x.x:3000/
```

### 6. Buka di Browser
- Tekan `Ctrl + klik` link **`http://localhost:3000`** di terminal, atau buka Google Chrome / Edge lalu ketik `http://localhost:3000`.
- **Ingin dibuka langsung dari HP Android / iPhone Anda?**
  Pastikan laptop dan HP Anda tersambung ke jaringan Wi-Fi yang sama (atau Hotspot HP), lalu ketik alamat **Network** (contoh: `http://192.168.1.10:3000`) di browser Chrome/Safari pada HP Anda!

---

## 🛠️ Perintah Berguna Lainnya

| Perintah | Fungsi |
|---|---|
| `npm run dev` | Menjalankan server lokal (pengembangan) |
| `npm run build` | Melakukan kompilasi kode siap produksi ke folder `dist` |
| `npm run lint` | Memeriksa apakah ada error sintaks TypeScript |

---

## 📁 Struktur Direktori Penting

```text
├── index.html                 # Entry point HTML & konfigurasi font Plus Jakarta Sans
├── package.json               # Konfigurasi dependensi (React 19, Lucide, Tailwind v4)
├── vite.config.ts             # Konfigurasi bundler Vite
├── src/
│   ├── main.tsx               # Inisialisasi React DOM
│   ├── App.tsx                # Layout utama (Mode Simulasi HP & Mode Layar Penuh)
│   ├── types/
│   │   └── index.ts           # Definisi data model (Transaksi, Alternatif, Kriteria SAW)
│   ├── utils/
│   │   └── sawEngine.ts       # Algoritma matematis Simple Additive Weighting (SAW)
│   ├── context/
│   │   └── AppContext.tsx     # State management & LocalStorage persistensi
│   ├── data/
│   │   ├── sampleData.ts      # Data uji coba realistis untuk demo dosen
│   │   └── academicDoc.ts     # Naskah lengkap Laporan TA (BAB I - BAB V & Tanya Jawab)
│   └── components/
│       ├── layout/            # Header, Phone Mockup, Bottom Nav, Desktop Side Panel
│       ├── dashboard/         # Halaman Beranda & ringkasan kuota harian
│       ├── saw/               # Kalkulator SAW & transparansi tabel matriks X, R, V
│       ├── transactions/      # Buku kas pencatatan pemasukan & pengeluaran
│       ├── reports/           # Laporan distribusi kategori & efisiensi penghematan
│       ├── academic/          # Pembaca naskah TA siap salin & cetak PDF
│       └── common/            # Modal catat transaksi, alternatif belanja & profil
```

---

## 💡 Fitur Unggulan untuk Sidang Tugas Akhir RPL
1. **Transparansi Matematis Penuh (Tab Langkah Matematis):** Dosen dapat memeriksa langsung Matriks Keputusan $X$, Matriks Ternormalisasi $R$, dan Vektor $V_i$.
2. **Budget Threshold Cutoff:** Tidak hanya meranking, sistem juga membatasi belanja berdasarkan sisa kuota pagu harian pengguna.
3. **Eksekusi 1-Klik:** Item prioritas #1 yang disetujui dapat langsung dicatat menjadi transaksi nyata di buku kas.
4. **Naskah TA Siap Salin:** Tab Dokumen TA menyediakan naskah BAB I s.d BAB V dan bank tanya jawab sidang penguji.
