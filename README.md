# Analisis Isu Lansia 2045

## Ringkasan Proyek

Tujuan proyek ini melakukan analisis terhadap kumpulan artikel berita terkait isu lansia di Indonesia dalam konteks persiapan menghadapi Indonesia Emas 2045 (Bonus Demografi Kedua). Dengan menggunakan model bahasa besar, artikel-artikel tersebut diringkas, diklasifikasikan berdasarkan topik, dan diidentifikasi pemangku kepentingan beserta fokus dan inisiatif mereka. Tujuannya adalah untuk mendapatkan pemahaman komprehensif mengenai lanskap isu lansia, tantangan yang dihadapi, serta upaya-upaya yang sedang dan akan dilakukan oleh berbagai pihak.

## Metodologi

Analisis dilakukan melalui beberapa tahapan otomatis menggunakan Python dan library `langchain_community` serta model dari Replicate:

1.  **Pengumpulan Data**: Data artikel dikumpulkan dalam format CSV.
2.  **Pemuatan Data**: Artikel dimuat ke dalam Pandas DataFrame.
3.  **Ringkasan Artikel**: Model bahasa besar digunakan untuk membuat ringkasan singkat (1-3 kalimat) untuk setiap artikel, fokus pada temuan atau argumen utama.
4.  **Klasifikasi Topik**: Setiap ringkasan artikel diklasifikasikan ke dalam satu atau lebih kategori yang relevan (Kesehatan Lansia, Kebijakan Pemerintah, Ekonomi, Sosial Budaya, Inovasi Teknologi, Lainnya) beserta penjelasan singkat.
5.  **Identifikasi Pemangku Kepentingan**: Model bahasa besar digunakan untuk mengekstraksi pemangku kepentingan yang disebutkan dalam artikel, mengklasifikasikan mereka berdasarkan kategori organisasi (Pemerintah Pusat, Pemerintah Daerah, Sektor Swasta, Akademisi & Peneliti, Organisasi Masyarakat Sipil & Komunitas), serta mengidentifikasi fokus utama, rencana/inisiatif, dan masalah yang mereka tangani.

## Temuan Utama

Berdasarkan analisis artikel:

*   **Isu Utama**: Isu utama terkait lansia di Indonesia meliputi kesehatan, kesiapan ekonomi, peran pemerintah dalam kebijakan, serta adaptasi sosial dan teknologi dalam menghadapi peningkatan populasi lansia menuju 2045.
*   **Klasifikasi Topik**: Topik yang paling sering dibahas adalah **Kesehatan Lansia**, **Kebijakan Pemerintah**, dan **Ekonomi**.
*   **Pemangku Kepentingan Kunci**: **Pemerintah** (pusat dan daerah) adalah pemangku kepentingan yang paling dominan. **Institusi Pendidikan**, **Sektor Swasta**, dan **Organisasi Masyarakat Sipil** juga berperan penting.
*   **Rencana & Inisiatif**: Berbagai program dan kebijakan sedang dijalankan atau direncanakan, fokus pada peningkatan layanan kesehatan, pemberdayaan ekonomi, kebijakan pendukung, dan pemanfaatan teknologi untuk lansia.
*   **Tantangan**: Tantangan signifikan mencakup kesiapan infrastruktur, pembiayaan, literasi digital lansia, dan koordinasi antar pemangku kepentingan.

## Struktur Notebook

Notebook ini disusun sebagai berikut:

*   **Instalasi Library**: Menginstal library Python yang dibutuhkan (`langchain_community`, `replicate`, `requests`).
*   **Inisialisasi Model**: Mengatur API token dan menginisialisasi model bahasa besar dari Replicate.
*   **Pemuatan Data**: Memuat data artikel dari file CSV.
*   **Ringkasan Artikel**: Kode untuk melakukan summarisasi artikel menggunakan model.
*   **Klasifikasi Artikel**: Kode untuk mengklasifikasikan ringkasan artikel ke dalam kategori yang ditentukan.
*   **Pemetaan Pemangku Kepentingan (Pendekatan 1 - Manual)**: Kode untuk mengidentifikasi pemangku kepentingan berdasarkan kata kunci dan menampilkan data terkait (fokus dan inisiatif) yang telah ditentukan sebelumnya.
*   **Pemetaan Pemangku Kepentingan (Pendekatan 2 - Terstruktur)**: Kode untuk mengekstrak pemangku kepentingan dan detail terkait (kategori, fokus, inisiatif, masalah) secara terstruktur menggunakan model bahasa besar dan skema JSON.
*   **Kesimpulan Analisis**: Ringkasan temuan dari keseluruhan analisis.
*   **Tabel Hasil**: Menampilkan tabel ringkasan dan klasifikasi artikel, serta tabel pemetaan pemangku kepentingan.

## Persyaratan

*   Python 3.7+
*   Library yang terdaftar di `requirements.txt` (atau diinstal melalui `pip install` di notebook).
*   Akses API Replicate dengan token yang valid dan cukup kredit untuk menjalankan model.

## Cara Menjalankan

1.  Pastikan file CSV artikel (`Kumpulan Artikel Lansia 2045(Sheet1).csv`) berada di path yang sesuai (`/content/`).
2.  Masukkan token API Replicate Anda ke dalam Colab Secrets dengan nama `api_token`.
3.  Jalankan setiap sel kode di notebook secara berurutan.
4.  Hasil ringkasan, klasifikasi, dan pemetaan pemangku kepentingan akan ditampilkan dalam bentuk tabel Pandas DataFrame.
