# Product Requirements Document (PRD)

## 1. Informasi Project

| Item | Keterangan |
|---|---|
| **Nama Produk** | Solusi Halaman Pembayaran Otomatis |
| **Jenis Dokumen** | Product Requirements Document (PRD) |
| **Versi Dokumen** | 1.0 |
| **Tanggal** | 2 September 2026 |
| **Disusun oleh** | Muhammad Ibrohim |
| **Status Dokumen** | Draft — Final Review |
| **Tech Stack** | Next.js, Prisma, PostgreSQL, Better Auth, Vercel Blob Platform |
| **Target** | Web Components / Embeddable SaaS Widget (Responsive, Mobile-First) |

---

## 2. Latar Belakang

Banyak perusahaan besar (*enterprise*) yang menjalankan bisnis dalam skala internasional kehilangan potensi keuntungan finansial (omzet) yang sangat besar justru pada tahap akhir pembelian.

Ketika sebuah bisnis berekspansi ke luar negeri, website utama mereka sering kali gagal menangani kerumitan transaksi lintas negara. Pencatatan data pajak, konversi mata uang, dan integrasi metode pembayaran lokal sering kali dilakukan secara terpisah atau bahkan dihitung secara manual melalui sistem yang kaku.

Akibatnya, calon pembeli global sering membatalkan pesanan mereka karena:

- Proses pembayaran yang membingungkan.
- Tidak mendukung mata uang lokal.
- Tidak mendukung metode pembayaran lokal.
- Biaya pajak tersembunyi yang baru muncul di akhir proses checkout.

Membangun infrastruktur pembayaran global dari nol membutuhkan biaya tim IT internal yang sangat besar dan waktu pengembangan yang lama.

Produk ini hadir sebagai solusi infrastruktur siap pakai berupa komponen halaman pembayaran otomatis yang dapat ditempelkan langsung pada website bisnis *enterprise* apa pun untuk mengotomatiskan seluruh kerumitan transaksi internasional secara instan.

---

## 3. Problem Statement

> **Perusahaan besar berskala internasional kehilangan banyak calon pembeli di halaman pembayaran (*cart abandonment*) karena alur transaksi lintas negara yang rumit, tidak mendukung mata uang dan metode pembayaran lokal, serta sistem perhitungan pajak yang tidak otomatis, sehingga menurunkan efisiensi konversi penjualan global.**

### Masalah Spesifik

- Alur pengisian data halaman pembayaran (*checkout*) terlalu panjang dan berbelit-belit sehingga membuat pembeli jenuh.
- Tidak adanya konversi mata uang otomatis yang dinamis berdasarkan lokasi pembeli.
- Rumitnya penyelarasan regulasi pajak internasional, seperti **VAT** di Eropa atau *Sales Tax* di Amerika, yang berbeda di tiap negara.
- Tingginya biaya dan waktu yang harus dikeluarkan perusahaan jika harus membangun sistem pembayaran global kustom sendiri.

---

## 4. Tujuan Produk

- Menyediakan komponen halaman pembayaran otomatis (*checkout widget*) yang siap pakai dan mudah diintegrasikan ke platform web bisnis apa pun.
- Mengotomatiskan deteksi lokasi pengguna untuk menyesuaikan mata uang, bahasa, dan aturan hukum pajak setempat secara instan.
- Meningkatkan angka konversi penjualan internasional dengan memotong waktu alur transaksi menjadi di bawah 10 detik.
- Menjamin keamanan data transaksi dengan standarisasi enkripsi keuangan internasional.
- Menyediakan produk infrastruktur dengan tingkat kerumitan pengembangan sistem yang medium-rendah, tetapi memberikan dampak keuntungan finansial yang besar bagi pengusaha.

---

## 5. Target User

- Perusahaan skala besar (*enterprise*) yang menjual produk atau layanannya ke pasar internasional/global.
- Pengusaha atau pemilik bisnis e-commerce internasional yang ingin meningkatkan performa halaman pembayaran tanpa merombak total website utama.
- Tim pengembang web (*developer* agensi) yang membutuhkan modul pihak ketiga untuk menangani sistem pembayaran global klien mereka.

---

## 6. User Persona

### Persona 1 — *Marcus, Direktur Operasional E-Commerce Global*

- **Usia:** 42 tahun
- **Karakteristik:** Mengelola toko retail pakaian berskala besar yang berbasis di London, dengan target pasar Amerika Serikat dan Asia Tenggara.
- **Kebutuhan:** Membutuhkan sistem halaman pembayaran yang secara otomatis dapat menghitung pajak impor pembeli di Asia dan menampilkan mata uang lokal tanpa membuat tim IT menulis ulang kode website dari awal.

### Persona 2 — *Siti, Pemilik SaaS Bisnis Internasional*

- **Usia:** 34 tahun
- **Karakteristik:** Menjual software berlangganan untuk perusahaan di berbagai belahan dunia.
- **Kebutuhan:** Membutuhkan infrastruktur pembayaran yang dapat langsung menerima kartu kredit internasional, PayPal, dan Stripe dengan alur konfirmasi transaksi yang sangat cepat agar pembeli tidak membatalkan langganan di detik-detik terakhir.

---

## 7. Scope Project

### In-Scope (MVP)

- Komponen widget halaman pembayaran yang responsif dan mengutamakan tampilan HP (*mobile-first*).
- Deteksi lokasi otomatis (*Geo-IP*) untuk mengubah mata uang dan bahasa.
- Kalkulator pajak internasional otomatis (**VAT / Sales Tax**) yang terintegrasi berdasarkan alamat pembeli.
- Integrasi **API** dengan gerbang pembayaran global utama (**Stripe & PayPal**).
- Dashboard ringkasan laporan transaksi untuk pemilik bisnis.

### Out-of-Scope (MVP)

- Fitur kecerdasan buatan (**AI**) untuk memprediksi perilaku belanja konsumen.
- Integrasi dengan sistem manajemen gudang fisik (*omnichannel inventory synchronization*).
- Fitur *Family Sharing* atau multi-akun dalam satu perusahaan.

---

## 8. Daftar Fitur

| No. | Fitur | Deskripsi Singkat |
|---:|---|---|
| 1 | **Deteksi Geo-IP Otomatis** | Mengenali lokasi negara pengunjung secara *real-time* untuk menyesuaikan bahasa dan mata uang utama. |
| 2 | **Alur Pembayaran Satu Halaman (Single-Page Checkout)** | Menyediakan antarmuka ringkas yang menyatukan pengisian data pengiriman dan pembayaran dalam satu tampilan untuk menekan angka *cart abandonment*. |
| 3 | **Kalkulator Pajak Global Dinamis** | Menghitung tarif pajak internasional seperti VAT, GST, atau Sales Tax secara otomatis berdasarkan alamat tujuan yang dimasukkan pembeli. |
| 4 | **Integrasi Multi-Gerbang Pembayaran (Global Payment Gateways)** | Menghubungkan sistem secara instan ke Stripe, PayPal, dan metode pembayaran lokal terkemuka di berbagai negara. |
| 5 | **Dasbor Analitik Pemilik Bisnis** | Menyediakan metrik performa halaman pembayaran, tingkat konversi, serta laporan pendapatan lintas negara bagi pemilik usaha. |
| 6 | **Penyesuaian Komponen Visual (White-Label Widget Customizer)** | Memungkinkan pemilik bisnis mengubah warna, logo, dan font komponen pembayaran agar selaras dengan desain website utama. |
| 7 | **Notifikasi & Faktur Otomatis** | Mengirimkan bukti pembayaran dan rincian transaksi multibahasa ke email pembeli secara instan setelah transaksi sukses. |

---

## 9. Prioritas Fitur — MoSCoW Method

| Fitur | Prioritas |
|---|---|
| Alur Pembayaran Satu Halaman (Single-Page Checkout) | **Must Have** |
| Deteksi Geo-IP Otomatis | **Must Have** |
| Integrasi Multi-Gerbang Pembayaran (Stripe & PayPal) | **Must Have** |
| Kalkulator Pajak Global Dinamis | **Should Have** |
| Dasbor Analitik Pemilik Bisnis | **Should Have** |
| Notifikasi & Faktur Otomatis | **Should Have** |
| Penyesuaian Komponen Visual (White-Label) | **Could Have** |
| Rekomendasi Produk Berbasis Kecerdasan Buatan (AI) | **Won't Have** |

---

## 10. User Flow

### Flow Utama: Melakukan Pembayaran Internasional Cepat

1. Pembeli global menekan tombol *Bayar* atau *Checkout* di website utama pemilik bisnis.
2. Komponen Halaman Pembayaran Otomatis muncul dengan bahasa dan mata uang yang sudah menyesuaikan lokasi Geo-IP pembeli.
3. Pembeli memasukkan alamat pengiriman mereka.
4. Sistem secara otomatis menghitung dan menampilkan biaya pajak yang berlaku di negara tujuan secara transparan.
5. Pembeli memilih metode pembayaran internasional, seperti kartu kredit atau PayPal, kemudian menekan tombol *Bayar Sekarang*.
6. Sistem memproses transaksi melalui gerbang pembayaran global, menyimpan status sukses di basis data, lalu memperbarui dasbor analitik pemilik bisnis.
7. Pembeli menerima halaman konfirmasi sukses di layar dan menerima faktur otomatis melalui email.

---

## 11. Functional Requirements

- **FR01:** Sistem harus mampu mendeteksi IP Address pengguna secara *real-time* dan mencocokkannya dengan database geografis internasional untuk menentukan negara asal.
- **FR02:** Sistem harus menyediakan komponen antarmuka yang menyatukan kolom data pengiriman, pemilihan kurir, dan opsi pembayaran dalam satu halaman tanpa proses *reload*.
- **FR03:** Sistem harus melakukan kalkulasi nilai nominal mata uang asing secara dinamis berdasarkan kurs terbaru saat transaksi dilakukan.
- **FR04:** Sistem harus memiliki integrasi **API** yang valid dengan penyedia kalkulator pajak eksternal untuk menarik data persentase pajak (**VAT / GST / Sales Tax**) sesuai kode pos atau negara bagian tujuan pengiriman.
- **FR05:** Sistem harus memproses enkripsi token pembayaran dengan aman melalui gerbang Stripe atau PayPal tanpa menyimpan data kartu kredit mentah di database internal.
- **FR06:** Sistem harus menyediakan dasbor analitik yang menampilkan:
  - Grafik garis pendapatan harian.
  - Diagram lingkaran persentase metode pembayaran favorit.
  - Angka rasio konversi sukses.
- **FR07:** Sistem harus memicu pengiriman email otomatis yang berisi berkas lampiran faktur berformat **PDF** ke alamat email pembeli setelah status transaksi berubah menjadi sukses.

---

## 12. Non-Functional Requirements

| Aspek | Requirement |
|---|---|
| **Performance** | Waktu respons loading halaman komponen pembayaran wajib di bawah 1,5 detik di seluruh wilayah akses global utama dengan optimasi **CDN** (*Content Delivery Network*). |
| **Security** | Wajib menggunakan enkripsi **HTTPS/TLS 1.3**, mematuhi standar keamanan data kartu pembayaran internasional (**PCI-DSS**), serta menerapkan isolasi data ketat pada database multi-tenant pemilik bisnis. |
| **Scalability** | Arsitektur database PostgreSQL dan server **REST API** dirancang untuk mampu menangani lonjakan transaksi serentak (*concurrent transactions*) hingga **50.000 transaksi per menit** tanpa penurunan performa. |
| **Usability** | Antarmuka komponen didesain dengan pendekatan *mobile-first*, intuitif, memiliki kontras warna teks yang tinggi untuk aksesibilitas, serta ukuran tombol minimal **44 × 44 piksel** agar mudah ditekan di layar HP. |
| **Reliability** | Target tingkat uptime sistem pembayaran berada pada angka **99,99%** untuk menjamin kelancaran bisnis sepanjang waktu. |
| **Data Retention** | Data riwayat transaksi finansial wajib disimpan secara aman minimal selama **10 tahun** untuk keperluan audit hukum dan pembukuan perusahaan, sekalipun status akun merchant dinonaktifkan. |

---

## 13. UI/UX Design

- Desain komponen pembayaran mengadopsi prinsip *clean layout* dan *mobile-first*, mengingat mayoritas pembeli bertransaksi menggunakan perangkat seluler.
- Struktur halaman web wajib menempatkan elemen navigasi internal (`<nav>`) di dalam bagian kepala halaman (`<header>`) untuk menjaga konsistensi struktur dan navigasi halaman.
- Formulir input didesain dengan fitur pengisian otomatis (*auto-fill*) yang cerdas untuk meminimalkan beban ketik pengguna, seperti deteksi otomatis kota dan provinsi setelah pembeli memasukkan kode pos.
- Menggunakan animasi indikator loading (*skeleton screen*) yang halus saat sistem sedang menghitung biaya pajak global agar memberikan kepastian visual kepada pengguna bahwa proses sedang berjalan di latar belakang.

---

## 14. Technical Requirements

### Frontend Layer

- Next.js (App Router)
- TypeScript
- Tailwind CSS

### Backend Layer

- Next.js API Routes
- Server Actions

### Database & ORM

- PostgreSQL
- Prisma ORM

Prisma digunakan untuk pemetaan skema data yang terstruktur dan kokoh.

### Autentikasi

- Better Auth

Digunakan untuk manajemen sesi login pengusaha ke dalam dasbor analitik.

### Penyimpanan Berkas

- Vercel Blob Platform

Digunakan untuk menyimpan aset statis seperti:

- Logo kustom perusahaan pengguna.
- Salinan digital faktur **PDF**.

### Sistem Otomatisasi

- Vercel Cron

Digunakan untuk menjalankan fungsi pengecekan rekonsiliasi data keuangan harian secara otomatis.

---

## 15. Business Rules

- Satu akun perusahaan (*enterprise merchant*) dapat mengintegrasikan komponen pembayaran ke beberapa domain website eksternal mereka tanpa batasan jumlah platform.
- Penyesuaian persentase pajak global harus mengikuti hukum wilayah berdasarkan alamat pembeli. Namun, pemilik bisnis diberikan hak akses untuk menambahkan biaya admin flat kustom di luar komponen pajak.
- Setiap transaksi yang berhasil diproses akan dikenakan biaya potongan platform SaaS sebesar **1,5% per transaksi** sebagai model monetisasi produk.
- Notifikasi email faktur tidak akan dikirimkan kepada pembeli jika status respons transaksi dari gerbang pembayaran global (Stripe/PayPal) dinyatakan gagal atau ditolak oleh bank terkait.

---

## 16. Manajemen Kegagalan & Penanganan Error

### ER01 — Pembayaran Ditolak

Jika gerbang pembayaran internasional menolak transaksi karena saldo tidak cukup atau kendala fraud, sistem harus:

- Mendeteksi kode error secara *real-time*.
- Menampilkan pesan petunjuk yang jelas kepada pembeli.
- Tidak melakukan *reload* halaman.

### ER02 — API Kalkulator Pajak Tidak Tersedia

Jika koneksi **API** ke kalkulator pajak pihak ketiga terputus, sistem otomatis beralih menggunakan basis data tarif pajak cadangan (*fallback offline tax table*) yang disimpan di server internal agar pembeli tetap dapat melakukan pembayaran.

### ER03 — Alamat Pengiriman Tidak Dikenali

Jika alamat pengiriman tidak dikenali oleh sistem kurir internasional:

- Kolom input memberikan indikasi visual berwarna merah.
- Sistem menyarankan perbaikan alamat secara dinamis.
- Tombol pembayaran tidak dapat ditekan sampai alamat diperbaiki.

---

## 17. Skema Basis Data & Keamanan Data

### DB01 — Isolasi Data Merchant

Seluruh data transaksi finansial dari perusahaan besar dipisahkan secara logis menggunakan pengenal unik (`merchant_id`) pada setiap baris tabel database PostgreSQL untuk mencegah kebocoran data antarperusahaan.

### DB02 — Tokenisasi Data Pembayaran

Database internal tidak diizinkan menyimpan:

- Nomor kartu kredit.
- Kode keamanan (**CVV**).

Sistem hanya diperbolehkan menyimpan *payment token* yang dihasilkan secara aman oleh Stripe atau PayPal untuk keperluan referensi seperti pengembalian dana (*refund*).

### DB03 — Audit Log

Setiap kali terjadi perubahan status transaksi, sistem mencatat log aktivitas secara otomatis yang mencakup:

- Stempel waktu hingga milidetik.
- Jenis aktivitas.
- Alamat IP sistem yang memicu perubahan tersebut.

---

## 18. Alur Kerja Pengembalian Dana

### RF01 — Refund Penuh atau Sebagian

Melalui Dasbor Analitik Pemilik Bisnis, pengusaha dapat memicu pengembalian dana penuh atau sebagian (*partial refund*) kepada pembeli internasional hanya dengan satu klik.

Sistem kemudian:

1. Mengirimkan perintah refund ke **API** Stripe/PayPal.
2. Memproses status refund.
3. Menghitung kembali pembatalan potongan pajak yang sebelumnya terjadi.

### RF02 — Nilai Tukar Saat Refund

Proses pengembalian uang wajib menggunakan nilai kurs mata uang asing yang sama persis dengan nilai kurs saat pembeli melakukan transaksi awal.

Tujuannya adalah melindungi pembeli maupun pemilik bisnis dari kerugian akibat fluktuasi nilai tukar mata uang global.

---

## 19. Pengujian Sistem & Jaminan Kualitas

### QA01 — Cross-Browser & Responsive Testing

Komponen halaman pembayaran wajib diuji dan dipastikan berfungsi tanpa cacat visual pada browser utama dunia, baik dalam versi desktop maupun tampilan seluler.

### QA02 — Load Testing

Tim penjamin kualitas wajib melakukan uji beban (*load testing*) secara berkala untuk mensimulasikan kondisi ketika **50.000 pembeli global** menekan tombol *Bayar Sekarang* secara bersamaan.

Pengujian harus memastikan server Next.js tidak mengalami *crash* atau mati total.

---

## 20. Glosarium Istilah Teknis Bisnis Global

| Istilah | Definisi |
|---|---|
| **Enterprise Merchant** | Perusahaan skala besar yang memanfaatkan platform Solusi Halaman Pembayaran Otomatis untuk menerima transaksi dari konsumen mereka. |
| **Cart Abandonment** | Kondisi ketika calon pembeli sudah memasukkan barang ke keranjang belanja dan masuk ke halaman pembayaran, tetapi membatalkan pembelian di detik-detik terakhir karena alur transaksi yang rumit. |
| **Geo-IP Detection** | Teknologi yang membaca alamat IP internet pembeli untuk mengetahui negara tempat mereka mengakses halaman web. |
| **White-Label** | Fitur yang memungkinkan pemilik bisnis menghapus logo platform penyedia dan menggantinya dengan merek, warna, serta identitas visual mereka sendiri agar terlihat kustom dan profesional. |
| **PCI-DSS** | Standar keamanan internasional yang wajib dipenuhi oleh sistem digital yang mengolah, menyimpan, atau mentransmisikan data kartu kredit. |
