# SP-PPT — Product Requirements Document (PRD)

**Sistem Penilaian Produksi Pementasan Teater (SP-PPT)**
Mata Pelajaran Seni Teater · Kelas IX · SMPN 10 Samarinda

| Atribut | Isi |
|---|---|
| Versi dokumen | 1.0 |
| Bahasa | Indonesia |
| Jenis produk | Aplikasi web progresif (PWA), responsif, berbasis peran |
| Pendekatan | Dibangun dan dirapikan dari nol; seluruh fitur berprioritas sama (semua wajib ada pada rilis 1.0) |
| Pemilik produk | Guru Pembina Seni Teater |

---

## Daftar Isi

1. [Ringkasan Produk](#1-ringkasan-produk)
2. [Latar Belakang dan Masalah](#2-latar-belakang-dan-masalah)
3. [Tujuan dan Indikator Keberhasilan](#3-tujuan-dan-indikator-keberhasilan)
4. [Ruang Lingkup](#4-ruang-lingkup)
5. [Pengguna dan Peran](#5-pengguna-dan-peran)
6. [Struktur Produksi: Tahapan dan Divisi](#6-struktur-produksi-tahapan-dan-divisi)
7. [Model Penilaian](#7-model-penilaian)
8. [Kebutuhan Fungsional](#8-kebutuhan-fungsional)
9. [Fitur per Peran](#9-fitur-per-peran)
10. [Matriks Hak Akses](#10-matriks-hak-akses)
11. [Alur Sistem](#11-alur-sistem)
12. [Kebutuhan Non-Fungsional](#12-kebutuhan-non-fungsional)
13. [Persyaratan Keamanan](#13-persyaratan-keamanan)
14. [Identitas Visual dan UX](#14-identitas-visual-dan-ux)
15. [Model Data (Konseptual)](#15-model-data-konseptual)
16. [Kasus Tepi dan Penanganan](#16-kasus-tepi-dan-penanganan)
17. [Integrasi dan Dependensi](#17-integrasi-dan-dependensi)
18. [Kriteria Penerimaan](#18-kriteria-penerimaan)
19. [Risiko dan Mitigasi](#19-risiko-dan-mitigasi)
20. [Keputusan Default dan Asumsi](#20-keputusan-default-dan-asumsi)

---

## 1. Ringkasan Produk

SP-PPT adalah aplikasi web untuk mengelola sekaligus menilai produksi pementasan teater siswa Kelas IX. Satu produksi melibatkan puluhan siswa dengan peran berbeda, berjalan dalam empat tahapan, dan dinilai oleh tiga pihak. SP-PPT mencatat seluruh proses itu (jadwal, kehadiran, tugas, karya, komunikasi, dan penilaian) sehingga nilai akhir tiap siswa adil, transparan, dan dapat dipertanggungjawabkan.

Aplikasi ini memiliki dua fungsi yang saling terhubung:

1. **Manajemen produksi**: jadwal, absensi, tugas dan deadline, naskah dan dokumen, komunikasi, serta laporan.
2. **Penilaian multi-penilai**: rubrik per peran, penilaian per tahapan, agregasi otomatis, rapor, dan moderasi.

## 2. Latar Belakang dan Masalah

Penilaian produksi teater di kelas bersifat kolaboratif dan sulit diukur karena:

- Peran siswa berbeda-beda (pimpinan, sutradara, pemain, tata rias, tata busana, dan lain-lain) sehingga kriteria nilainya juga berbeda.
- Kontribusi siswa tersebar di empat tahapan dan tidak mudah dicatat oleh satu guru.
- Penilaian dari guru saja rawan subjektif dan tidak melihat kerja sama antar siswa.
- Dokumen, jadwal, dan komunikasi tersebar di banyak grup pesan sehingga sulit dilacak.
- Rekap nilai dan rapor manual memakan waktu dan rawan salah hitung.

## 3. Tujuan dan Indikator Keberhasilan

| Tujuan | Indikator |
|---|---|
| Penilaian adil dan terukur | 100% siswa memiliki nilai akhir yang dihitung otomatis dari rubrik, tanpa hitung manual |
| Transparansi | Siswa dapat melihat nilai, rincian kriteria, dan komentar penilai sendiri |
| Efisiensi guru | Rekap nilai kelas dan rapor PDF dihasilkan dengan satu klik |
| Akuntabilitas proses | Seluruh aktivitas (login, submit, ubah nilai) tercatat di log |
| Koordinasi produksi | Jadwal, absensi, tugas, dan pengumuman berada di satu sistem |
| Aksesibilitas | Dapat dipakai di ponsel, tablet, dan desktop, termasuk saat koneksi lemah |

## 4. Ruang Lingkup

### 4.1 Dalam lingkup (rilis 1.0)

Semua modul berikut dibangun dari nol dan berprioritas sama:

- Autentikasi dan manajemen sesi
- Dashboard per peran
- Manajemen pengguna, kelas, dan peran
- Rubrik dan penilaian multi-penilai (Guru, Ketua, Rekan)
- Rekap nilai, rapor, dan moderasi
- Struktur kerabat kerja
- Jadwal, kalender, dan booking alat
- Absensi terkontrol per peran
- Checklist, tugas, deadline, dan umpan balik
- Notifikasi dan broadcast (termasuk WhatsApp)
- Naskah, dokumen, dan informasi umum
- Fitur khusus per peran (prompt book, casting, desain set, rias, busana, musik, publikasi)
- Aduan, panduan, dan tombol darurat
- Ekspor/impor, backup/restore, dan log sistem
- PWA, mode offline, tema, dan aksesibilitas

### 4.2 Di luar lingkup

- Aplikasi native iOS/Android (digantikan PWA)
- Pembayaran atau transaksi keuangan nyata (modul keuangan hanya pencatatan)
- Integrasi dengan sistem rapor nasional atau Dapodik

## 5. Pengguna dan Peran

Sistem mengenali **17 peran siswa**, ditambah **Guru** dan **Admin**.

### 5.1 Peran siswa (17)

| No | Peran | Kelompok |
|---:|---|---|
| 1 | Pimpinan Produksi | Pengurus inti |
| 2 | Sekretaris | Pengurus inti |
| 3 | Bendahara | Pengurus inti |
| 4 | Sutradara | Artistik |
| 5 | Asisten Sutradara | Artistik |
| 6 | Koordinator Perlengkapan | Koordinator divisi |
| 7 | Koordinator Publikasi & Dokumentasi | Koordinator divisi |
| 8 | Koordinator Tata Panggung | Koordinator divisi |
| 9 | Koordinator Tata Rias | Koordinator divisi |
| 10 | Koordinator Tata Busana | Koordinator divisi |
| 11 | Koordinator Tata Musik & Suara | Koordinator divisi |
| 12 | Anggota Perlengkapan | Anggota divisi |
| 13 | Anggota Publikasi & Dokumentasi | Anggota divisi |
| 14 | Anggota Tata Panggung | Anggota divisi |
| 15 | Anggota Tata Rias | Anggota divisi |
| 16 | Anggota Tata Busana | Anggota divisi |
| 17 | Anggota Tata Musik & Suara | Anggota divisi |

Peran **Pemain (Aktor/Aktris)** adalah peran ke-18 dalam daftar kerja dan dikelola sebagai kelompok **Pemeran**. Jika jumlah 17 peran dihitung sebagai acuan baku, Pemain dihitung sebagai peran tunggal pada divisi Pemeran dan Bendahara dihitung bersama pengurus inti. Tim pengembang wajib mengonfirmasi penghitungan akhir ini dengan guru sebelum skema data dibekukan (lihat bagian 20).

### 5.2 Peran non-siswa

| Peran | Ringkasan wewenang |
|---|---|
| **Guru Pembina** | Pemilik kelas dan penilai utama. Mengelola siswa, rubrik, penilaian semua peran, moderasi, rekap, laporan, jadwal master, absensi, backup |
| **Admin** | Akses penuh seluruh sistem: akun guru, semua kelas, pengaturan global, log sistem, maintenance mode |

### 5.3 Hierarki visual peran

Lencana peran berwarna sesuai hierarki: Pimpinan dan Sutradara emas, Koordinator biru, Anggota dan Pemain abu-abu.

## 6. Struktur Produksi: Tahapan dan Divisi

### 6.1 Empat tahapan

| Tahap | Isi utama |
|---|---|
| Persiapan | Rubrik, data siswa, konsep, desain, casting, rencana anggaran |
| Pelaksanaan | Latihan, pembuatan properti/kostum/set, dokumentasi proses |
| Pertunjukan | Gladi, pementasan, standby cue, touch-up, dokumentasi hari-H |
| Pasca | Evaluasi, refleksi, pengembalian properti/kostum/alat, LPJ |

Guru dapat mengaktifkan atau menonaktifkan tahapan dan mengubah bobot tiap tahapan.

### 6.2 Enam divisi

1. Perlengkapan
2. Publikasi & Dokumentasi
3. Tata Panggung
4. Tata Rias
5. Tata Busana
6. Tata Musik & Suara

Pengurus inti (Pimpinan, Sekretaris, Bendahara), tim artistik (Sutradara, Asisten), dan Pemeran dikelompokkan terpisah dari enam divisi di atas pada tampilan struktur.

## 7. Model Penilaian

### 7.1 Tiga penilai (bobot default)

| Penilai | Bobot default | Siapa |
|---|---:|---|
| Guru Pembina | 50% | Menilai semua peran dan semua aspek |
| Ketua | 30% | Pimpinan Produksi, Sutradara, Koordinator, Asisten Sutradara sesuai garis penilaian |
| Rekan Sejawat | 20% | Sesama anggota divisi atau sesama pemain; boleh anonim |

**Rumus nilai individu:**

```
Nilai Individu = (Nilai Guru × 0.50) + (Nilai Ketua × 0.30) + (Nilai Rekan × 0.20)
```

- Bobot dapat diubah guru di Pengaturan; sistem menyimpan bobot per periode.
- Jika satu penilai belum mengisi, bobot dinormalisasi otomatis dari penilai yang sudah mengisi.

### 7.2 Skala penilaian

| Nilai | Label | Skor |
|---:|---|---:|
| 4 | Sangat Baik | 100 |
| 3 | Baik | 80 |
| 2 | Cukup | 60 |
| 1 | Kurang | 40 |

Setiap level memiliki deskripsi teks per kriteria. Komentar **wajib** jika nilai ≤ 2.

### 7.3 Agregasi

1. **Nilai per tahapan:** jumlah (skor × bobot kriteria) dibagi total bobot.
2. **Nilai akhir per peran:** nilai tiap tahapan dikali bobot tahapan, lalu dijumlah. Bobot tahapan default: Persiapan 20%, Pelaksanaan 35%, Pertunjukan 30%, Pasca 15%.
3. **Predikat:**

| Rentang | Predikat | Makna |
|---|---|---|
| 90–100 | A | Mahir, teladan |
| 80–89 | B | Kompeten, andal |
| 70–79 | C | Memenuhi standar |
| 60–69 | D | Perlu perbaikan |
| < 60 | E | Tidak memenuhi |

### 7.4 Rubrik per peran

**Pemain (6 kriteria):**

| Kriteria | Bobot |
|---|---:|
| Hafalan Dialog | 20% |
| Penjiwaan Karakter | 25% |
| Proyeksi Suara & Intonasi | 15% |
| Blocking & Movement | 15% |
| Interaksi Panggung | 15% |
| Kedisiplinan | 10% |

**Asisten Sutradara (4 kriteria):** Prompt Book, Catatan Harian, Standby Cue, Evaluasi.

**Anggota divisi (4 kriteria, dinilai Koordinator):**

| Divisi | Kriteria dan bobot |
|---|---|
| Perlengkapan | Kerja Sama 30%, Kualitas Kerja 30%, Disiplin 20%, Inisiatif 20% |
| Publikasi & Dokumentasi | Kreativitas 30%, Ketepatan Waktu 25%, Kualitas Visual 25%, Kerja Sama 20% |
| Tata Panggung | Ketepatan Waktu 30%, Kualitas Konstruksi 30%, Kerja Sama 20%, Keselamatan 20% |
| Tata Rias | Kreativitas 30%, Higienitas 25%, Ketepatan Waktu 25%, Kerja Sama 20% |
| Tata Busana | Kreativitas 30%, Kerapian Jahitan 25%, Ketepatan Waktu 25%, Kerja Sama 20% |
| Tata Musik & Suara | Ketepatan Cue 30%, Kualitas Audio 25%, Kerapian 25%, Kerja Sama 20% |

**Penilaian rekan (3 kriteria):**

| Kelompok | Kriteria |
|---|---|
| Anggota Perlengkapan | Kerja Sama, Kontribusi, Disiplin |
| Anggota Publikasi | Kreativitas, Ketepatan Waktu, Kerja Sama |
| Anggota Tata Panggung | Kerja Sama, Keselamatan, Kontribusi |
| Anggota Tata Rias | Kreativitas, Higienitas, Kerja Sama |
| Anggota Tata Busana | Kerapian, Kreativitas, Kerja Sama |
| Anggota Tata Musik | Ketepatan Cue, Kualitas Audio, Kerja Sama |
| Pemain | Penjiwaan, Kerja Sama, Kedisiplinan |

**Pengurus inti dan koordinator:** Guru menyediakan rubrik default (mis. Kerja Sama, Tanggung Jawab, Kehadiran, Kreativitas, Kemampuan Teknis) yang dapat diedit di Manajemen Rubrik.

### 7.5 Siapa menilai siapa

| Yang dinilai | Penilai utama | Penilai pendukung |
|---|---|---|
| Pimpinan Produksi | Guru | Semua Koordinator |
| Sutradara | Guru | Asisten + Pemain |
| Asisten Sutradara | Sutradara | Guru |
| Sekretaris | Pimpinan Produksi | Guru |
| Bendahara | Pimpinan Produksi | Guru |
| Koordinator Divisi | Pimpinan Produksi | Anggota + Guru |
| Anggota Divisi | Koordinator | Rekan Divisi |
| Pemain | Sutradara | Asisten + Rekan |

Guru dapat menilai semua peran.

### 7.6 Aturan penilaian

- Nilai berstatus **Draft** (dapat diedit) atau **Final** (terkunci).
- Perubahan nilai Final menyimpan versi baru; versi lama ditandai *superseded* dan tidak dihapus. Riwayat memuat siapa, kapan, dari-ke berapa, dan alasan.
- Hanya Guru/Admin yang dapat menghapus nilai Final.
- Bobot kriteria ≠ 100% dinormalisasi otomatis (bobot ÷ total × 100).
- Status Alpa otomatis memengaruhi kriteria kedisiplinan/kehadiran.

## 8. Kebutuhan Fungsional

Semua kebutuhan berikut **wajib** pada rilis 1.0. Kode `FR-xx` dipakai untuk pelacakan di issue GitHub.

### 8.1 Autentikasi dan Sesi (FR-AUTH)

| ID | Kebutuhan |
|---|---|
| FR-AUTH-01 | Halaman login memiliki tiga tab: Guru, Siswa, Admin |
| FR-AUTH-02 | Login siswa: pilih kelas, lalu email atau nomor WhatsApp atau NIS (bila diaktifkan guru), dan kata sandi. Sistem membedakan email (mengandung `@`) dan nomor WhatsApp (angka) secara otomatis |
| FR-AUTH-03 | Guru yang mengampu banyak kelas dapat berpindah kelas tanpa login ulang |
| FR-AUTH-04 | Tombol tampilkan/sembunyikan kata sandi, tautan "Lupa Password" (instruksi hubungi guru), dan "Butuh Bantuan" |
| FR-AUTH-05 | Registrasi siswa dengan Kode Kelas (contoh `IXS-2025`), nama lengkap, email unik, nomor WhatsApp unik (min. 10 digit), kata sandi (min. 8 karakter) dengan konfirmasi, dan peran awal (default Pemain) |
| FR-AUTH-06 | Registrasi ditolak jika kode kelas tidak ada atau email/WhatsApp sudah terdaftar |
| FR-AUTH-07 | Sesi aktif 8 jam; auto-logout setelah 30 menit tanpa aktivitas |
| FR-AUTH-08 | Ganti kata sandi dari header; logout dengan konfirmasi |
| FR-AUTH-09 | Verifikasi 2 langkah (OTP via WhatsApp) pada perangkat baru jika diaktifkan guru |
| FR-AUTH-10 | Manajer perangkat: daftar perangkat aktif dan logout jarak jauh |
| FR-AUTH-11 | Riwayat login 30 hari terakhir (waktu, perangkat, peramban, alamat IP) |
| FR-AUTH-12 | Setiap login dan logout tercatat di log sistem |

### 8.2 Dashboard (FR-DASH)

| ID | Kebutuhan |
|---|---|
| FR-DASH-01 | **Dashboard siswa:** kartu profil (foto/inisial, lencana peran dan divisi), aksi cepat sesuai peran, sapaan dan kata motivasi harian, progres produksi per tahapan, 5 notifikasi terbaru, jadwal terdekat dengan konfirmasi hadir, deadline terdekat dengan hitung mundur, aktivitas terbaru, pengumuman (dengan pin), statistik pribadi (kehadiran, nilai, progres tugas) |
| FR-DASH-02 | **Dashboard guru:** statistik kelas dan siswa, daftar kelas (kelas favorit), aksi cepat (rekap, struktur, jadwal, absensi, notifikasi, aktivitas, backup, broadcast, pengumuman, kelola siswa, statistik, ekspor), aktivitas real-time dengan filter, kartu alert (belum dinilai, LPJ masuk, anomali, sering absen, belum submit), kartu broadcast cepat, kelas yang perlu perhatian |
| FR-DASH-03 | **Dashboard admin:** semua fitur guru ditambah kelola akun guru, kelola semua kelas, backup/restore, pengaturan sistem, log sistem, statistik global, kelola admin, maintenance mode |
| FR-DASH-04 | **Dashboard Pimpinan Produksi:** kartu komando (hijau/kuning/merah), progres 6 divisi, alert kritis, broadcast cepat, rapat terdekat |
| FR-DASH-05 | **Dashboard Sutradara:** ringkasan visi artistik, progres latihan per adegan, pemain terbaik (nilai sementara), pemain perlu perhatian, cue sheet mendatang, catatan harian |
| FR-DASH-06 | **Dashboard Sekretaris:** presensi hari ini, jadwal hari ini, dokumen terbaru, akses cepat arsip |
| FR-DASH-07 | **Dashboard Bendahara:** saldo kas, pengeluaran terbaru dengan nota, ringkasan RAB, akses laporan keuangan |
| FR-DASH-08 | **Dashboard Koordinator:** progres divisi, anggota (kehadiran dan progres tugas), tugas divisi, jadwal internal, absensi internal, kebutuhan divisi |
| FR-DASH-09 | Dashboard memperbarui data otomatis (target setiap 30 detik atau lewat pembaruan real-time) |

### 8.3 Manajemen Pengguna, Kelas, dan Peran (FR-USR)

| ID | Kebutuhan |
|---|---|
| FR-USR-01 | Guru/Admin menambah, mengubah, dan menghapus siswa; atur peran lewat dropdown atau seret-lepas |
| FR-USR-02 | Reset kata sandi siswa oleh guru |
| FR-USR-03 | Import siswa dari Excel/CSV dengan template dan validasi |
| FR-USR-04 | Admin mengelola akun guru, hak akses, dan admin lain |
| FR-USR-05 | Siswa mengedit profil (foto, nama panggilan, kontak) |
| FR-USR-06 | Pimpinan Produksi melihat tabel seluruh siswa (nama, kelas, peran, divisi, status penilaian) dengan filter, pencarian, dan ekspor CSV |
| FR-USR-07 | Kode kelas dibuat dan dapat dinonaktifkan oleh guru |

### 8.4 Rubrik dan Penilaian (FR-NIL)

| ID | Kebutuhan |
|---|---|
| FR-NIL-01 | Manajemen rubrik: lihat rubrik master per peran, ubah bobot (auto-normalisasi), tambah kriteria, aktif/nonaktifkan kriteria |
| FR-NIL-02 | Form penilaian: pilih target (satu atau batch), kriteria muncul sesuai peran target, slider 1–4 dengan deskripsi, komentar per kriteria, pratinjau nilai real-time |
| FR-NIL-03 | Aksi **Simpan Draft** dan **Finalisasi**; semua kriteria wajib terisi sebelum finalisasi |
| FR-NIL-04 | Penilaian cepat (quick score) untuk beri nilai sama ke banyak siswa |
| FR-NIL-05 | Template penilaian tersimpan dan riwayat penilaian yang pernah diberikan |
| FR-NIL-06 | Alur guru: pilih Kelas → Siswa → Peran → Tahapan |
| FR-NIL-07 | Pimpinan Produksi menilai Sekretaris, Bendahara, dan 6 Koordinator Divisi |
| FR-NIL-08 | Sutradara menilai Pemain dan Asisten Sutradara; Asisten menilai Pemain (aspek teknis: blocking, interaksi) |
| FR-NIL-09 | Koordinator menilai anggota divisinya |
| FR-NIL-10 | Penilaian rekan sejawat dengan opsi anonim dan deteksi anomali |
| FR-NIL-11 | Bobot multi-penilai dan bobot tahapan dapat diatur guru per periode |
| FR-NIL-12 | Perhitungan nilai akhir, predikat, dan normalisasi bobot otomatis sesuai bagian 7 |
| FR-NIL-13 | Pengingat otomatis ke penilai yang belum submit |
| FR-NIL-14 | Riwayat revisi nilai (versi, alasan, pelaku) |

### 8.5 Nilai Siswa dan Rapor (FR-RPR)

| ID | Kebutuhan |
|---|---|
| FR-RPR-01 | "Nilai Saya": kartu nilai akhir (desimal, 2 angka) dan predikat dengan warna (A emas, B biru, C hijau, D oranye, E merah) serta lencana Lulus/Perlu Perbaikan |
| FR-RPR-02 | Grafik radar 4 tahapan dan grafik batang perbandingan antar tahapan |
| FR-RPR-03 | Rincian per kriteria (nilai dan bobot); pemain mendapat tambahan 6 kriteria pemain dan radar 6 kriteria |
| FR-RPR-04 | Komentar penilai (Guru, Ketua, Rekan) dengan filter komentar positif/semua |
| FR-RPR-05 | Riwayat penilaian dan grafik tren nilai |
| FR-RPR-06 | Perbandingan dengan rata-rata kelas tanpa menyebut nama siswa lain |
| FR-RPR-07 | Rekomendasi perbaikan otomatis berdasarkan nilai terendah |
| FR-RPR-08 | Unduh rapor PDF dengan kop sekolah, logo, dan tanda tangan digital; opsi **Rapor Lengkap** atau **Rapor Ringkas** |
| FR-RPR-09 | Refleksi diri pemain (yang sudah baik, yang perlu diperbaiki, target) dikirim untuk penilaian tahap Pasca; tombol hanya tampil pada tahap Pasca |

### 8.6 Rekap dan Moderasi (FR-REK)

| ID | Kebutuhan |
|---|---|
| FR-REK-01 | Tabel rekap: nama, kelas, peran, nilai 4 tahapan, nilai akhir, predikat; filter, urut, cari |
| FR-REK-02 | Statistik: rata-rata, tertinggi, terendah, distribusi predikat, perbandingan antar kelas |
| FR-REK-03 | Ekspor CSV, XLSX multi-sheet (Rekap, Per Tahapan, Per Kriteria, Statistik), PDF rapor kelas; cetak langsung |
| FR-REK-04 | Moderasi: deteksi anomali (semua 4 atau semua 1, selisih antar penilai > 1,5 poin, pola nilai seragam, pengisian < 10 detik per siswa, di luar jam wajar) |
| FR-REK-05 | Guru memvalidasi atau menolak penilaian, memberi catatan ke penilai, dan dapat membuka identitas penilai anonim; pembukaan identitas dicatat di log |

### 8.7 Struktur Kerabat Kerja (FR-STR)

| ID | Kebutuhan |
|---|---|
| FR-STR-01 | Tampilan "Kerabat Kerja [Kelas]" dikelompokkan per divisi dengan header berwarna |
| FR-STR-02 | Tiap anggota: avatar, nama, lencana peran, lencana "Anda", tombol chat WhatsApp |
| FR-STR-03 | Pencarian, filter (divisi, level, kelas), urut (nama, hierarki) |
| FR-STR-04 | Bagan hierarki, deskripsi tugas tiap peran, kontak darurat, "Lihat Kontak Saya" (atasan dan bawahan langsung) |
| FR-STR-05 | Bagikan struktur ke WhatsApp; guru ekspor ke PDF/XLSX |
| FR-STR-06 | Tombol melayang "Kerabat" dengan animasi pulse |

### 8.8 Jadwal dan Kalender (FR-JDW)

| ID | Kebutuhan |
|---|---|
| FR-JDW-01 | Kartu jadwal: judul, jenis, tanggal, jam, lokasi, PIC; warna per jenis |
| FR-JDW-02 | Hak membuat jadwal umum: Pimpinan, Sekretaris, Sutradara, Asisten, Guru, Admin. Bendahara, Anggota, Pemain tidak berhak |
| FR-JDW-03 | Koordinator membuat jadwal **internal** divisi (tertutup; peserta terkunci ke anggota divisinya; notifikasi hanya ke divisi) |
| FR-JDW-04 | Kalender bulanan dengan penanda warna, detail saat diklik, kalender drag-and-drop untuk edit oleh pembuat |
| FR-JDW-05 | Konfirmasi Hadir/Tidak Hadir yang tampil ke guru |
| FR-JDW-06 | Pengingat otomatis H-1 dan H-1 jam; pengingat susulan bagi yang belum konfirmasi |
| FR-JDW-07 | Sinkronisasi ke Google Calendar atau iCal |
| FR-JDW-08 | Master schedule: garis waktu horizontal (merah → kuning → hijau → biru) |
| FR-JDW-09 | Booking alat (sound system, properti, kostum, alat rias, alat panggung, lainnya) dengan deteksi bentrok otomatis dan persetujuan guru (Pending/Approved/Rejected) |
| FR-JDW-10 | Kategori jadwal berwarna: Rapat biru, Latihan oranye, Gladi merah, Pementasan emas, Evaluasi ungu, Produksi hijau, Fitting pink, Briefing cyan |
| FR-JDW-11 | Kalender konten publikasi (H-30, H-14, H-7, H-1, Hari-H) |

### 8.9 Absensi (FR-ABS)

Absensi adalah alat kontrol produksi, sehingga pembuat sesi dibatasi.

| Pembuat | Jenis kegiatan | Peserta | Edit/hapus |
|---|---|---|---|
| Pimpinan Produksi | Rapat, briefing, konsolidasi, lintas divisi | Semua / Divisi / Peran / Custom | Pembuat, Guru, Admin |
| Sekretaris | Rapat, briefing, administratif | Semua / Divisi / Peran / Custom | Pembuat, Guru, Admin |
| Sutradara | Latihan akting, gladi, evaluasi akting | **Terkunci:** seluruh Pemain + seluruh Tata Musik & Suara | Pembuat, Guru, Admin |
| Asisten Sutradara | Sama dengan Sutradara | **Terkunci:** Pemain + Tata Musik & Suara | Pembuat, Sutradara, Guru, Admin |
| Koordinator Divisi | Rapat, latihan, produksi, fitting, gladi kering, evaluasi, briefing internal | **Terkunci:** anggota divisinya | Pembuat, Guru, Admin |
| Guru / Admin | Semua | Semua / Custom | Semua |

| ID | Kebutuhan |
|---|---|
| FR-ABS-01 | Tombol "Buat Sesi Absensi" hanya tampil untuk peran berhak; tidak untuk Bendahara, Anggota, Pemain |
| FR-ABS-02 | Kolom Peserta berupa dropdown (Pimpinan, Sekretaris, Guru, Admin) atau lencana terkunci (Sutradara, Asisten, Koordinator) |
| FR-ABS-03 | Status: Hadir, Izin, Sakit, Alpa; tombol "Tandai Semua Hadir" untuk input cepat |
| FR-ABS-04 | Kartu sesi: judul, jenis, waktu, lokasi, pembuat, cakupan peserta, progres pengisian, tombol Isi dan Lihat Rekap |
| FR-ABS-05 | Notifikasi hanya ke peserta sesuai cakupan; pengingat H-1 dan H-1 jam; pengingat bagi yang belum mengisi |
| FR-ABS-06 | Pengecualian: Guru dapat mengizinkan Sutradara menambah peserta dari divisi lain (nonaktif secara default); Pimpinan dapat membuat sesi darurat tanpa notifikasi |
| FR-ABS-07 | Rekap: Pimpinan/Sekretaris/Guru/Admin melihat semua; Sutradara dan Asisten hanya sesi latihan buatan sendiri; Koordinator hanya divisinya; siswa hanya dirinya |
| FR-ABS-08 | Statistik per sesi, per siswa (dengan tren), per divisi (paling dan kurang disiplin), per jenis kegiatan |
| FR-ABS-09 | QR code absensi per sesi |
| FR-ABS-10 | Absensi via WhatsApp dengan format tertentu |
| FR-ABS-11 | Batas waktu pengisian; sesi otomatis tertutup setelah batas |
| FR-ABS-12 | Absensi manual oleh guru untuk siswa yang tidak bisa mengakses aplikasi |
| FR-ABS-13 | Opsional per sesi: selfie bukti hadir dan pencatatan lokasi (dengan persetujuan siswa) |
| FR-ABS-14 | Ekspor rekap per sesi, siswa, divisi, jenis kegiatan |
| FR-ABS-15 | Grid presensi siswa × tanggal untuk Sekretaris dan statistik persentase otomatis |

### 8.10 Checklist, Tugas, Deadline, dan Umpan Balik (FR-TGS)

| ID | Kebutuhan |
|---|---|
| FR-TGS-01 | Checklist tugas default per peran (daftar tugas berbeda untuk tiap peran); progres bar otomatis; direset saat ganti tahapan; riwayat tahapan sebelumnya tetap dapat dilihat |
| FR-TGS-02 | Template checklist buatan guru; deadline per tugas; unggah bukti (foto/dokumen) |
| FR-TGS-03 | Verifikasi tugas dan permintaan revisi dengan komentar oleh Koordinator/Guru |
| FR-TGS-04 | Pembuat deadline: Pimpinan, Sekretaris, Sutradara, Asisten, Koordinator, Guru, Admin |
| FR-TGS-05 | Isi deadline: judul, deskripsi, tanggal-jam, prioritas (Rendah/Sedang/Tinggi/Kritis), lampiran, penerima (semua, divisi, peran, custom) |
| FR-TGS-06 | Pengingat otomatis H-3, H-1, H-1 jam, dan notifikasi "Deadline Terlewat" |
| FR-TGS-07 | Status: Belum Dikerjakan, Sedang Dikerjakan, Selesai, Terlewat |
| FR-TGS-08 | Siswa memperbarui status, mengunggah bukti, meminta perpanjangan dengan alasan; Koordinator/Guru menyetujui atau menolak |
| FR-TGS-09 | Umpan balik progres 0–100%, komentar berjenjang, rating 1–5, dan riwayat feedback |
| FR-TGS-10 | Papan kanban (To Do, In Progress, Done, Blocked) dengan seret-lepas |
| FR-TGS-11 | Tombol "Ajukan Bantuan" pada tugas anggota; "Tandai Selesai" |
| FR-TGS-12 | Ekspor checklist per siswa, divisi, atau tahapan (PDF/XLSX) |

### 8.11 Notifikasi dan Broadcast (FR-NTF)

| ID | Kebutuhan |
|---|---|
| FR-NTF-01 | Panel notifikasi geser dari kanan, ikon lonceng dengan lencana angka |
| FR-NTF-02 | Jenis: Tugas (biru), Instruksi (ungu), Info (hijau), Urgent (merah), Reminder (oranye), Feedback (pink), Sistem (abu) |
| FR-NTF-03 | Status baca (latar biru = baru), "Tandai Dibaca" per item, "Tandai Semua Dibaca" dengan sinkronisasi antar perangkat dan stempel waktu |
| FR-NTF-04 | Real-time dengan toast dan suara opsional; filter (Semua, Belum Dibaca, Tugas, Instruksi, Info, Urgent) dan pencarian kata kunci |
| FR-NTF-05 | Notifikasi otomatis untuk: jadwal baru/berubah, deadline mendekat/terlewat, tugas baru/diverifikasi/perlu revisi, nilai masuk/berubah, absensi dibuka/ditutup, pengumuman, aduan dibalas, broadcast |
| FR-NTF-06 | Notifikasi WhatsApp dengan template yang dapat dikustomisasi, log pengiriman, cari dan filter log |
| FR-NTF-07 | Notifikasi per peran sesuai matriks di bagian 10.3 |

**Broadcast per peran:**

| Pengirim | Target |
|---|---|
| Pimpinan Produksi | Semua siswa, semua koordinator, semua pemain, divisi, peran, custom; dapat dijadwalkan; ada riwayat |
| Sekretaris | Semua siswa, divisi, peran, custom |
| Sutradara / Asisten | Pemain, Tata Musik & Suara, atau keduanya (default latihan) |
| Koordinator | Anggota divisinya (dan sub-divisi bila ada) |
| Bendahara | Semua siswa (info keuangan), koordinator (info RAB), custom |
| Guru | Semua kelas, kelas tertentu, semua siswa, peran, custom; templat pesan tersimpan |

Format broadcast: teks, gambar, tautan, atau kombinasi; dapat dikirim juga lewat WhatsApp.

### 8.12 Naskah, Dokumen, dan Informasi Umum (FR-DOK)

| ID | Kebutuhan |
|---|---|
| FR-DOK-01 | Naskah digital: unggah PDF, pratinjau di aplikasi, bookmark, catatan pribadi per halaman, highlight dialog sendiri, pencarian kata, mode baca malam |
| FR-DOK-02 | Arsip dokumen berstruktur folder: Proposal, Surat Izin, Naskah Drama, Notulen Rapat, Dokumentasi, Laporan Keuangan, Laporan Divisi; unggah banyak berkas, pratinjau PDF, cari nama berkas, unduh; hapus hanya oleh Guru |
| FR-DOK-03 | Kompilasi LPJ otomatis dengan template, penggabungan data 6 divisi dan keuangan, sampul dengan logo, ekspor PDF |
| FR-DOK-04 | Pimpinan Produksi mengunggah LPJ (PDF/DOCX) dan mengisi dana masuk, pengeluaran, sisa, catatan evaluasi; Guru memvalidasi |
| FR-DOK-05 | Informasi umum: form (judul, kategori, isi, lampiran, target), pin di dashboard, kategori (Akademik, Teknis, Keuangan, Artistik, Administratif, Umum), jenis (Pengumuman, Instruksi, Informasi, Peringatan, Pengingat, Laporan, Hasil Rapat, Kebijakan), read receipt, komentar, arsip, pencarian |
| FR-DOK-06 | Hak unggah informasi umum: Pimpinan, Sekretaris, Bendahara, Sutradara, Asisten, Koordinator, Guru (Admin juga) |
| FR-DOK-07 | Papan pengumuman digital dengan pin, filter kategori, like, komentar, dan bagikan |

### 8.13 Koordinasi dan Komunikasi (FR-KOM)

| ID | Kebutuhan |
|---|---|
| FR-KOM-01 | Log aktivitas: pengguna, aksi, target, waktu; filter; guru melihat semua, siswa melihat log pribadi |
| FR-KOM-02 | Activity feed real-time dengan ikon per jenis aktivitas |
| FR-KOM-03 | Forum diskusi per divisi, topik, atau kegiatan; kategori Umum, Teknis, Artistik, Keuangan, Administratif; guru memoderasi |
| FR-KOM-04 | Chat internal: antar siswa sekelas, antar koordinator, dengan guru, grup per divisi; teks, gambar, berkas, voice note, read receipt, status online |

### 8.14 Aduan, Panduan, dan Darurat (FR-ADU)

| ID | Kebutuhan |
|---|---|
| FR-ADU-01 | Tombol panduan melayang: cara login, dashboard, nilai, struktur, jadwal, mengisi dan membuat absensi, membuat jadwal, FAQ |
| FR-ADU-02 | Aduan: judul, deskripsi, bukti opsional, kategori (Akademik, Teknis, Sosial, Keamanan, Bullying, Lainnya); status Open / In Progress / Closed; guru membalas; siswa melihat di "Aduan Saya" |
| FR-ADU-03 | Aduan anonim; identitas hanya terlihat oleh guru |
| FR-ADU-04 | Teruskan aduan ke WhatsApp guru: manual (tautan wa.me berisi pesan terisi) atau otomatis lewat API, balasan WhatsApp masuk ke sistem |
| FR-ADU-05 | Templat pesan: "Halo Pak/Bu [Nama Guru], saya [Nama Siswa] dari kelas [Kelas]. Judul: [Judul]. Deskripsi: [Deskripsi]. Terima kasih." |
| FR-ADU-06 | Tombol darurat melayang dengan konfirmasi; mengirim notifikasi urgent ke guru dan pimpinan |
| FR-ADU-07 | Aduan kategori Bullying dan Keamanan diberi prioritas tinggi dan notifikasi segera ke guru |

### 8.15 Ekspor, Impor, Backup (FR-EXP)

| ID | Kebutuhan |
|---|---|
| FR-EXP-01 | Ekspor CSV (rekap nilai), XLSX multi-sheet, PDF (rapor, LPJ, jadwal), DOCX (laporan) |
| FR-EXP-02 | Opsi ekspor untuk nilai, absensi, jadwal, checklist, keuangan, dan dokumen |
| FR-EXP-03 | Impor siswa, nilai, dan jadwal dari Excel/CSV dengan templat dan validasi sebelum simpan |
| FR-EXP-04 | Backup otomatis harian ke Google Drive (`backup_YYYY-MM-DD.xlsx`) dan backup manual per kelas atau semua kelas |
| FR-EXP-05 | Restore semua data, per kelas, atau per jenis data (nilai saja, absensi saja, dan seterusnya) dengan pemilihan tanggal backup |

### 8.16 Pengaturan (FR-SET)

| ID | Kebutuhan |
|---|---|
| FR-SET-01 | Periode penilaian (tahun ajaran) |
| FR-SET-02 | Bobot multi-penilai dan bobot tahapan |
| FR-SET-03 | Aktif/nonaktif tahapan, kriteria, login NIS, verifikasi 2 langkah |
| FR-SET-04 | Pengaturan WhatsApp (API, templat), Google Drive, dan status failover |
| FR-SET-05 | Maintenance mode oleh Admin (halaman "Sedang Maintenance") |
| FR-SET-06 | Analytics: pengguna aktif, fitur terbanyak dipakai, halaman teratas, rata-rata waktu akses |

### 8.17 Tampilan, Aksesibilitas, dan Bahasa (FR-UI)

| ID | Kebutuhan |
|---|---|
| FR-UI-01 | Tema Terang/Gelap/Otomatis (mengikuti OS) dengan toggle di header; preferensi tersimpan |
| FR-UI-02 | Warna aksen pilihan siswa (biru, hijau, ungu, merah, oranye) |
| FR-UI-03 | Responsif: desktop (>1024 px, sidebar), tablet (768–1024 px), ponsel (<768 px, navigasi bawah dan FAB), ponsel kecil (<480 px, layout ringkas); target sentuh minimal 44 px |
| FR-UI-04 | Animasi halus (transisi 0,3 dtk, hover 0,2 dtk, modal, skeleton shimmer, splash screen) dengan opsi menonaktifkan |
| FR-UI-05 | Mode aksesibilitas: font lebih besar, kontras tinggi, navigasi keyboard, dukungan pembaca layar |
| FR-UI-06 | Mode fokus (sembunyikan elemen non-esensial) dan mode cetak (sembunyikan tombol dan menu) |
| FR-UI-07 | Multi-bahasa: Indonesia (default), Inggris, dan bahasa lain yang dapat ditambah (mis. Jawa) |
| FR-UI-08 | Mode hemat data: gambar diperkecil, animasi mati, cache agresif |
| FR-UI-09 | Toast (Sukses hijau, Error merah, Warning kuning, Info biru; hilang setelah 3 dtk), modal (tutup lewat backdrop/ESC, header lengket), empty state dengan tombol aksi, skeleton loading, pesan error ramah dengan tombol "Laporkan Masalah" |

### 8.18 PWA dan Keandalan (FR-PWA)

| ID | Kebutuhan |
|---|---|
| FR-PWA-01 | Dapat diinstal di layar utama (ikon, splash, layar penuh) |
| FR-PWA-02 | Service worker meng-cache halaman utama dan aset statis; halaman tetap terbuka saat offline |
| FR-PWA-03 | Mode offline: siswa mengerjakan tugas, data tersimpan lokal, sinkron otomatis saat daring |
| FR-PWA-04 | Failover: dua proyek backend (primer dan cadangan); otomatis beralih saat kuota primer habis; guru melihat status aktif |

## 9. Fitur per Peran

Setiap peran siswa memperoleh fitur umum (login, profil, dashboard, Nilai Saya, jadwal, notifikasi, berkas) ditambah fitur khusus berikut.

### 9.1 Fitur umum semua siswa

- Profil dan peran yang diampu
- Dashboard dengan ringkasan tahapan, jadwal terdekat, notifikasi, pintasan sesuai peran
- Nilai Saya (bagian 8.5)
- Jadwal dan kalender dengan filter divisi/peran dan konfirmasi hadir
- Notifikasi berkategori
- Berkas dan arsip yang relevan dengan peran

### 9.2 Pimpinan Produksi

- Dashboard produksi: statistik siswa, divisi, progres keseluruhan, progres 6 divisi, linimasa 4 tahapan, alert kritis
- Tombol cepat: Rapat Darurat, Broadcast, Lihat LPJ
- Manajemen tim: tabel seluruh siswa, filter, pencarian, ekspor CSV
- Penilaian Sekretaris, Bendahara, dan 6 Koordinator (komentar wajib jika ≤ 2)
- LPJ akhir: unggah PDF/DOCX, isian keuangan, kirim ke Guru
- Absensi dan jadwal umum, deadline, pengumuman, broadcast

### 9.3 Sekretaris

- Presensi digital (grid siswa × tanggal, status, "Tandai Semua Hadir", statistik %)
- Manajemen jadwal (form, kalender interaktif, notifikasi otomatis, pengingat H-1)
- Arsip dokumen (folder, unggah banyak berkas, pratinjau PDF, pencarian)
- Kompilasi laporan (templat LPJ, gabung data divisi dan keuangan, sampul, PDF)
- Absensi umum, pengumuman administratif

### 9.4 Bendahara

- Pencatatan keuangan, penyusunan RAB, unggah nota, laporan keuangan, rekap pengeluaran
- Dashboard saldo kas, pengeluaran terbaru, ringkasan RAB
- Broadcast info keuangan dan unggah informasi keuangan
- Tidak dapat membuat absensi, jadwal, atau deadline

### 9.5 Sutradara

- Visi artistik: judul, tema, gaya, breakdown adegan, unggah moodboard dan Prompt Book PDF, "Publish Visi"
- Casting: tabel tokoh-pemain-status, form audisi (hafalan, penjiwaan, suara), tukar pemain, cetak call sheet PDF
- Penilaian Pemain (6 kriteria) dan Asisten Sutradara (4 kriteria)
- Catatan evaluasi harian: linimasa per tanggal, tag pemain, status (Baik / Perlu Perbaikan / Kritis), notifikasi ke pemain
- Absensi latihan (peserta terkunci), jadwal latihan, deadline dan broadcast ke pemain

### 9.6 Asisten Sutradara

- Prompt book digital: editor blocking dengan grid panggung 9 area, seret ikon pemain, simpan posisi per adegan, cue sheet (kode, timing, aksi), ekspor PDF
- Catatan harian: tanggal, adegan, pemain hadir, catatan, foto, rating adegan 1–5
- Penilaian pemain aspek teknis dengan komentar konstruktif wajib
- Standby cue mode Live: hitung mundur per cue, tombol panggil pemain ("5 menit lagi tampil"), log cue tepat/telat
- Absensi latihan (peserta terkunci) dan jadwal latihan

### 9.7 Koordinator Perlengkapan

- Manajemen properti (nama, adegan, bahan, status, penanggung jawab, sketsa, checklist bahan, progres)
- To-do anggota, penilaian anggota, inventaris dan pengembalian (Baik / Rusak Ringan / Rusak Berat / Hilang)
- Katalog bahan (kayu, kertas mache, busa poliuretan, kain, logam, plastik, keramik, bambu), estimasi biaya, unggah nota

### 9.8 Koordinator Publikasi & Dokumentasi

- Strategi publikasi: kalender konten H-30/H-14/H-7/H-1/Hari-H, target audiens, platform (Instagram, TikTok, WhatsApp, poster cetak), caption dan hashtag
- Poster dan logo (unggah maks. 5 MB, galeri, voting desain)
- Dokumentasi latihan (foto/video maks. 50 MB, tag, album otomatis per tanggal, editor sederhana)
- Dokumentasi pertunjukan mode Live, backup otomatis ke Google Drive, watermark logo dan tanggal
- Aftermovie: linimasa klip, musik latar, ekspor MP4 720p/1080p, kirim ke guru
- Penilaian anggota

### 9.9 Koordinator Tata Panggung

- Desain set: editor grid panggung (panjang × lebar × tinggi), area (utama, belakang, sayap kiri/kanan), seret elemen, sketsa dan potongan, palet warna
- Kalkulator bahan, tutorial konstruksi, checklist keselamatan
- Gladi kering: timer pasang (target 10 menit) dan bongkar (target 5 menit), log aktual vs target
- To-do dan penilaian anggota

### 9.10 Koordinator Tata Rias

- Desain rias (korektif, karakter, fantasi), face chart digital, moodboard, opsi pembuatan face chart dengan AI dari deskripsi
- Alat dan bahan, status higienis (Bersih / Kotor / Perlu Steril), pengingat sterilisasi
- Uji coba rias: jadwal fitting, foto sebelum-sesudah, rating kenyamanan 1–5
- Touch-up mode Live: timer, checklist pemain, kit darurat
- Penilaian anggota

### 9.11 Koordinator Tata Busana

- Desain kostum (tokoh, jenis Sejarah/Tradisional/Fantasi, warna, tekstur, aksesori, moodboard), data ukuran pemain, estimasi kain
- Proses produksi: Desain → Potong → Jahit → Fitting → Finishing, progres bar dan foto per tahap
- Fitting (jadwal 15 menit per pemain, evaluasi nyaman/sesuai/modifikasi, foto)
- Simulasi quick change (target < 2 menit, log waktu)
- Perawatan dan pengembalian (Cuci, Setrika, Simpan, Kembalikan; status Baik / Rusak / Hilang)
- Penilaian anggota

### 9.12 Koordinator Tata Musik & Suara

- Konsep musik dengan 10 jenis: Pembuka (Overture), Penutup, Pergantian Babak, Ilustrasi, Sound Track, Theme Song, Penokohan, Aksentuasi, Setting, Pelebur Emosi
- Sound cue sheet (adegan, waktu, jenis, volume, durasi), unggah audio MP3/WAV maks. 20 MB, pemutar pratinjau, pengaturan fade in/out
- Inventaris alat (speaker, mixer, mic, kabel, laptop, proyektor) dan status kondisi
- Latihan sound (timer ≤ 1 jam, log timing dan volume)
- Check sound hari-H: checklist 10 menit sebelum (mic 1–4, volume seimbang, kabel rapi, cadangan audio), slider volume
- Penilaian anggota

### 9.13 Anggota Divisi (semua divisi)

Fitur bersama: **Tugas Saya** (nama, deadline, prioritas, status, "Tandai Selesai", "Ajukan Bantuan", unggah bukti), **Penilaian Rekan Sejawat** (3 kriteria, opsi anonim), **Nilai Saya**.

Fitur khusus:

| Divisi | Fitur khusus |
|---|---|
| Perlengkapan | Katalog bahan, tutorial video properti, tips koordinator |
| Publikasi & Dokumentasi | Unggah media (foto maks. 5 MB JPG/PNG, video maks. 50 MB MP4), caption dan tag auto-suggest, pratinjau grid, media library (filter tanggal/jenis/tag, cari, unduh, bagikan) |
| Tata Panggung | Timer pengerjaan, unggah progres per tahap, tutorial konstruksi, checklist keselamatan, daftar alat tukang, gladi kering |
| Tata Rias | Panduan rias (korektif, karakter, fantasi) dan templat face chart, checklist alat, log sterilisasi dan peringatan alat kotor, uji coba rias |
| Tata Busana | Panduan menjahit, referensi kostum, kalkulator bahan, progres jahitan per tahap (Belum/Dikerjakan/Selesai), fitting |
| Tata Musik & Suara | Library audio (kategori, metadata judul/artis/durasi/mood, unggah maks. 20 MB), lihat dan tandai cue sheet, latihan sound, check sound |

### 9.14 Pemain

- Naskah digital dengan highlight, catatan blocking dari Asisten, cue dialog, bookmark adegan
- Jadwal latihan pribadi (hanya yang melibatkan pemain), pengingat H-1 dan H-1 jam, konfirmasi hadir
- Latihan dialog 10 langkah: Pemahaman Karakter, Memahami Naskah, Penekanan Kata & Frase, Intonasi Suara, Latihan Membaca Bersama, Gerakan & Ekspresi Wajah, Latihan Berdialog, Memahami Tujuan Karakter, Latihan Imajinasi, Pementasan Ulang
- Rekam suara: rekam, dengar ulang, timer latihan
- Penilaian rekan pemain (Penjiwaan, Kerja Sama, Kedisiplinan; opsi anonim)
- Nilai Saya: kartu nilai dari Sutradara, Asisten, dan Rekan; radar 6 kriteria; riwayat komentar; unduh rapor PDF
- Refleksi diri untuk tahap Pasca

### 9.15 Guru Pembina

- Dashboard, manajemen pengguna, manajemen rubrik, penilaian semua peran (per siswa atau batch)
- Rekap nilai, moderasi, monitoring progres (per tahapan dan divisi, pengingat otomatis), pengumuman dan broadcast
- Laporan akhir: pembuatan LPJ otomatis, validasi LPJ dari Pimpinan, ekspor rapor dan rekap
- Pengaturan: periode, bobot, backup/restore, jadwal master, absensi, booking alat, aduan

### 9.16 Admin

- Semua kemampuan Guru, ditambah kelola akun guru dan admin, kelola semua kelas, backup dan restore global, pengaturan sistem, log sistem, statistik global, maintenance mode

## 10. Matriks Hak Akses

Simbol: ✅ akses penuh · ✏️ edit/input · 👁️ lihat saja · ❌ tidak ada akses

### 10.1 Fitur umum

| Fitur | Pimprod | Sekret | Bendahara | Sutradara | Asisten | Kor Div | Anggota | Pemain | Guru | Admin |
|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Dashboard | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Lihat Nilai Sendiri | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Beri Nilai | ✏️ | ❌ | ❌ | ✏️ | ✏️ | ✏️ | ✏️ (rekan) | ✏️ (rekan) | ✏️ | ✏️ |
| Buat Absensi Umum | ✏️ | ✏️ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✏️ | ✏️ |
| Buat Absensi Latihan | ❌ | ❌ | ❌ | ✏️ | ✏️ | ❌ | ❌ | ❌ | ✏️ | ✏️ |
| Buat Absensi Internal | ❌ | ❌ | ❌ | ❌ | ❌ | ✏️ | ❌ | ❌ | ✏️ | ✏️ |
| Isi Absensi | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Buat Jadwal Umum | ✏️ | ✏️ | ❌ | ✏️ | ✏️ | ❌ | ❌ | ❌ | ✏️ | ✏️ |
| Buat Jadwal Internal | ❌ | ❌ | ❌ | ❌ | ❌ | ✏️ | ❌ | ❌ | ✏️ | ✏️ |
| Buat Deadline | ✏️ | ✏️ | ❌ | ✏️ | ✏️ | ✏️ | ❌ | ❌ | ✏️ | ✏️ |
| Broadcast | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ | ❌ | ❌ | ✏️ | ✏️ |
| Buat Pengumuman | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ | ❌ | ❌ | ✏️ | ✏️ |
| Upload Informasi Umum | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ | ❌ | ❌ | ✏️ | ✏️ |
| Buat Aduan | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ | ✏️ |
| Balas Aduan | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✏️ | ✏️ |
| Moderasi Penilaian | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✏️ | ✏️ |
| Rekap Nilai | 👁️ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✏️ | ✏️ |
| Kelola Siswa | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✏️ | ✏️ |
| Backup/Restore | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✏️ | ✏️ |
| Log Sistem | 👁️ pribadi | 👁️ pribadi | 👁️ pribadi | 👁️ pribadi | 👁️ pribadi | 👁️ pribadi | 👁️ pribadi | 👁️ pribadi | ✅ | ✅ |

Catatan: semua siswa dapat mengajukan aduan; matriks ini mengoreksi dokumen sumber yang menandai Pimpinan hingga Koordinator tidak dapat membuat aduan.

### 10.2 Fitur modul produksi

| Fitur | Pimprod | Sekret | Sutradara | Asisten | Kor Div | Anggota | Pemain | Guru |
|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Presensi (rekap) | 👁️ | ✏️ | 👁️ | 👁️ | 👁️ | ❌ | 👁️ | ✏️ |
| Jadwal | 👁️ | ✏️ | ✏️ | ✏️ | 👁️ (+internal ✏️) | 👁️ | 👁️ | ✏️ |
| Visi Artistik | 👁️ | ❌ | ✏️ | 👁️ | 👁️ | ❌ | 👁️ | 👁️ |
| Casting | 👁️ | ❌ | ✏️ | 👁️ | ❌ | ❌ | 👁️ | ✏️ |
| Prompt Book | 👁️ | ❌ | 👁️ | ✏️ | ❌ | ❌ | ❌ | 👁️ |
| Properti | 👁️ | ❌ | 👁️ | ❌ | ✏️ (Perlengkapan) | ✏️ (Perlengkapan) | ❌ | 👁️ |
| Poster / Publikasi | 👁️ | ❌ | 👁️ | ❌ | ✏️ (Publikasi) | ✏️ (Publikasi) | ❌ | 👁️ |
| Set Panggung | 👁️ | ❌ | 👁️ | ❌ | ✏️ (Tata Panggung) | ✏️ (Tata Panggung) | ❌ | 👁️ |
| Rias | 👁️ | ❌ | 👁️ | ❌ | ✏️ (Tata Rias) | ✏️ (Tata Rias) | 👁️ | 👁️ |
| Busana | 👁️ | ❌ | 👁️ | ❌ | ✏️ (Tata Busana) | ✏️ (Tata Busana) | 👁️ | 👁️ |
| Musik | 👁️ | ❌ | 👁️ | ❌ | ✏️ (Tata Musik) | ✏️ (Tata Musik) | ❌ | 👁️ |
| Naskah | 👁️ | 👁️ | ✏️ | ✏️ | ❌ | ❌ | 👁️ | 👁️ |
| LPJ | ✏️ | ✏️ | ❌ | ❌ | ❌ | ❌ | ❌ | ✏️ |
| Refleksi | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✏️ | 👁️ |

Aturan: hak edit pada modul divisi hanya berlaku untuk divisi milik pengguna; divisi lain berstatus lihat-saja atau tidak ada akses.

### 10.3 Notifikasi per peran

| Penerima | Notifikasi utama |
|---|---|
| Semua | Pengumuman baru, jadwal baru |
| Pimpinan | Divisi belum submit, laporan masuk |
| Sekretaris | Presensi belum diisi, jadwal besok |
| Sutradara | Pemain belum dinilai, catatan baru |
| Asisten | Cue baru, jadwal standby |
| Koordinator | Tugas anggota belum selesai, deadline dekat |
| Anggota | Tugas baru, pengingat deadline |
| Pemain | Jadwal latihan, feedback dari Sutradara |
| Guru | Siswa belum dinilai, LPJ masuk, anomali terdeteksi |

## 11. Alur Sistem

### 11.1 Siklus produksi

1. **Persiapan:** Guru menyiapkan rubrik dan data siswa → siswa login dan melihat peran → Pimpinan/Koordinator mengisi persiapan → Guru dan Ketua menilai tahap Persiapan.
2. **Pelaksanaan:** Divisi menjalankan tugas → Sutradara dan Asisten melatih pemain → dokumentasi berjalan → Guru dan Ketua menilai.
3. **Pertunjukan:** Semua divisi standby → pementasan → dokumentasi hari-H → Guru, Ketua, dan Rekan menilai.
4. **Pasca:** Evaluasi dan refleksi → pengembalian properti/kostum/alat → penyusunan LPJ → Guru dan Ketua menilai.
5. **Rekap:** Sistem menghitung nilai akhir → Guru memvalidasi → siswa melihat nilai dan mengunduh rapor → Guru mengunduh rekap kelas.

### 11.2 Alur login sampai aksi

Login (pilih tab) → Dashboard → menu atau aksi cepat → fitur terbuka (modal/halaman) → aksi → simpan → notifikasi sukses → kembali ke dashboard → logout.

### 11.3 Alur penilaian

- **Penilai:** Beri Nilai → pilih target → kriteria tampil → geser slider → komentar → pratinjau → Finalisasi.
- **Siswa:** Nilai Saya → kartu dan predikat → radar → rincian → komentar → unduh rapor.

### 11.4 Alur absensi

- **Rapat (Pimpinan/Sekretaris):** Buat Sesi → isi form → simpan → notifikasi ke peserta → peserta mengisi → rekap.
- **Latihan (Sutradara/Asisten):** Buat Sesi Latihan → peserta terkunci → simpan → notifikasi ke Pemain + Tata Musik → rekap.
- **Internal (Koordinator):** Buat Sesi Internal → peserta terkunci → notifikasi ke anggota divisi → rekap.

### 11.5 Alur deadline

Buat Deadline → isi form → simpan → notifikasi → siswa memperbarui status dan mengunggah bukti → Koordinator memverifikasi → feedback.

### 11.6 Alur aduan

Isi form aduan → kirim → sistem menyimpan → tombol "Kirim ke WA Guru" → WhatsApp terbuka dengan pesan terisi (atau terkirim otomatis lewat API) → Guru membalas → siswa melihat balasan di "Aduan Saya".

## 12. Kebutuhan Non-Fungsional

| ID | Kategori | Persyaratan |
|---|---|---|
| NFR-01 | Kinerja | Halaman utama termuat ≤ 3 detik pada jaringan 4G; aksi umum merespons ≤ 1 detik; skeleton loading saat data dimuat |
| NFR-02 | Kapasitas | Mendukung minimal 10 kelas dan 400 pengguna aktif bersamaan |
| NFR-03 | Ketersediaan | Target 99% selama masa produksi; failover otomatis saat kuota primer habis |
| NFR-04 | Real-time | Pembaruan data tampil tanpa muat ulang manual (dashboard maks. 30 detik) |
| NFR-05 | Responsif | Berfungsi pada ponsel layar ≥ 320 px, tablet, dan desktop |
| NFR-06 | Offline | Halaman inti dan pengerjaan tugas tetap berjalan tanpa jaringan; sinkron otomatis |
| NFR-07 | Penghematan data | Mode hemat data mengurangi transfer gambar dan animasi |
| NFR-08 | Aksesibilitas | Mengikuti WCAG 2.1 AA sebagai target: kontras, navigasi keyboard, label pembaca layar |
| NFR-09 | Kompatibilitas | Chrome, Edge, Firefox, Safari (dua versi stabil terakhir), dan WebView ponsel |
| NFR-10 | Pemeliharaan | Kode modular per fitur, konfigurasi (bobot, tahapan, kriteria) disimpan di data, bukan di kode |
| NFR-11 | Auditabilitas | Semua aksi penting masuk log yang tidak dapat diubah pengguna biasa |
| NFR-12 | Pencadangan | Backup harian otomatis; pemulihan dapat diuji per kelas |
| NFR-13 | Lokalisasi | Antarmuka berbahasa Indonesia; zona waktu WITA (UTC+8) sebagai default |
| NFR-14 | Pengujian | Rumus penilaian dan hak akses memiliki uji otomatis dengan cakupan kasus tepi bagian 16 |

## 13. Persyaratan Keamanan

Persyaratan ideal yang harus dipenuhi sistem:

| ID | Persyaratan |
|---|---|
| SEC-01 | Autentikasi berlapis; kata sandi disimpan dalam bentuk hash dengan algoritma modern berlapis garam (mis. bcrypt/Argon2), tidak pernah dalam teks biasa |
| SEC-02 | Otorisasi berbasis peran (RBAC) diterapkan di **sisi server** pada setiap permintaan; pembatasan tampilan di antarmuka hanya pelengkap |
| SEC-03 | Semua komunikasi melalui HTTPS/TLS; cookie sesi bertanda `Secure`, `HttpOnly`, dan `SameSite` |
| SEC-04 | Token sesi kedaluwarsa 8 jam, dapat dicabut, dan terikat perangkat; auto-logout 30 menit tidak aktif |
| SEC-05 | Pembatasan percobaan login (rate limiting) dan penguncian sementara setelah gagal berulang |
| SEC-06 | Verifikasi 2 langkah (OTP WhatsApp) opsional dan dapat diwajibkan guru |
| SEC-07 | Validasi dan sanitasi input di server (nilai hanya 1–4, panjang teks, tipe berkas, ukuran berkas) untuk mencegah injeksi dan XSS |
| SEC-08 | Perlindungan CSRF pada semua aksi pengubah data |
| SEC-09 | Enkripsi data sensitif saat disimpan (nomor WhatsApp, selfie, lokasi, identitas penilai anonim) |
| SEC-10 | Idempotency key pada pengiriman nilai dan absensi untuk mencegah submit ganda |
| SEC-11 | Unggahan berkas dipindai/divalidasi tipe dan ukurannya, disimpan terpisah dari kode aplikasi, dan diakses lewat tautan bertanda tangan sementara |
| SEC-12 | Identitas penilai anonim hanya dapat dibuka oleh Guru/Admin dan setiap pembukaan dicatat |
| SEC-13 | Log audit tidak dapat diubah atau dihapus oleh pengguna biasa; memuat pengguna, aksi, target, waktu, IP, perangkat |
| SEC-14 | Secret dan kunci API (WhatsApp, Google Drive) disimpan di variabel lingkungan atau secret manager, tidak di repositori |
| SEC-15 | Aturan keamanan basis data dengan prinsip hak akses minimum: siswa hanya membaca dan menulis data miliknya atau sesuai perannya |
| SEC-16 | Privasi: data pribadi siswa (anak di bawah umur) hanya dipakai untuk keperluan pembelajaran; ada kebijakan retensi dan penghapusan data setelah periode berakhir |
| SEC-17 | Lokasi dan selfie absensi hanya diambil dengan persetujuan eksplisit dan opsional |
| SEC-18 | Backup dienkripsi dan akses ke penyimpanan backup dibatasi untuk Guru/Admin |
| SEC-19 | Header keamanan (CSP, X-Frame-Options, X-Content-Type-Options) dan dependensi dipantau kerentanannya |
| SEC-20 | Aduan Bullying/Keamanan dan aduan anonim diperlakukan rahasia dan hanya terlihat oleh guru |

## 14. Identitas Visual dan UX

### 14.1 Aset visual

| Aset | Tautan |
|---|---|
| Latar belakang (motif teater samar) | https://iili.io/nJ1Rcj1.png |
| Logo sekolah | https://iili.io/nBiviCX.png |
| Logo mata pelajaran | https://iili.io/nap50AB.png |

Ketentuan penggunaan:

- Halaman login menampilkan splash screen dengan **dua logo** (sekolah dan mapel) di kartu putih semi-transparan di atas latar motif teater.
- Latar diberi overlay warna agar teks terbaca; tampilan terang dan gelap berbeda.
- Kop rapor PDF, sampul LPJ, dan ekspor memuat logo sekolah dan logo mapel.
- Aset sebaiknya diunduh dan disimpan di repositori (`/assets`) dan tidak bergantung pada layanan hosting eksternal, agar tidak hilang saat tautan kedaluwarsa.

### 14.2 Prinsip UX

- Antarmuka ramah ponsel karena sebagian besar siswa memakai HP
- Menu dan aksi cepat menyesuaikan peran (tombol yang tidak berhak tidak ditampilkan)
- Warna bermakna konsisten (jenis jadwal, jenis notifikasi, predikat nilai, hierarki peran)
- Konfirmasi untuk aksi yang tidak dapat dibatalkan (finalisasi nilai, logout, hapus, tombol darurat)
- Empty state ramah dan pesan error yang menjelaskan solusi
- Floating button: Panduan, Aduan, Kerabat, Darurat

## 15. Model Data (Konseptual)

Entitas utama (tanpa skema teknis; tim pengembang menurunkannya sesuai pilihan basis data):

| Entitas | Atribut kunci | Relasi |
|---|---|---|
| Kelas | nama, kode kelas, tahun ajaran, aktif | punya banyak Siswa; dimiliki Guru |
| Pengguna | jenis (guru/siswa/admin), nama, email, WhatsApp, NIS, hash kata sandi, foto | milik Kelas |
| Peran | nama, kelompok, divisi, level hierarki | dipegang Pengguna (per periode) |
| Divisi | nama, koordinator | berisi Anggota |
| Tahapan | nama, urutan, bobot, aktif | memiliki Penilaian |
| Rubrik / Kriteria | peran sasaran, nama, bobot, deskripsi per level, aktif | dipakai Penilaian |
| Penilaian | penilai, target, tahapan, jenis penilai (guru/ketua/rekan), status (draft/final), anonim, versi | berisi Nilai Kriteria |
| Nilai Kriteria | kriteria, skor 1–4, komentar | milik Penilaian |
| Revisi Nilai | versi, nilai lama-baru, alasan, pelaku, waktu | milik Penilaian |
| Jadwal | judul, jenis, waktu, lokasi, PIC, cakupan peserta, internal/umum | punya Konfirmasi Kehadiran |
| Sesi Absensi | judul, jenis, waktu, pembuat, cakupan, batas waktu | punya Catatan Kehadiran |
| Catatan Kehadiran | siswa, status (Hadir/Izin/Sakit/Alpa), metode (manual/QR/WA), bukti | milik Sesi |
| Tugas / Deadline | judul, deskripsi, tenggat, prioritas, penerima, status, bukti, rating | punya Komentar |
| Notifikasi | penerima, jenis, judul, pesan, status baca, waktu | — |
| Broadcast | pengirim, target, format, jadwal | menghasilkan Notifikasi |
| Dokumen | folder, nama, berkas, pengunggah | — |
| Informasi Umum | judul, kategori, jenis, isi, target, pin | punya Komentar dan Read Receipt |
| Aduan | pengirim (atau anonim), kategori, status, balasan | — |
| Booking Alat | alat, waktu mulai-selesai, pemohon, status persetujuan | — |
| Log Aktivitas | pengguna, aksi, target, waktu, IP, perangkat | — |
| Pengaturan | bobot penilai, bobot tahapan, periode, opsi fitur | per Kelas / global |
| Entitas modul peran | properti, casting, prompt book, cue sheet, desain set, face chart, kostum, cue musik, inventaris, media | per divisi |

## 16. Kasus Tepi dan Penanganan

| Kasus | Penanganan |
|---|---|
| Penilai lupa mengisi | Pengingat otomatis; alert di dashboard guru |
| Nilai tidak lengkap | Semua kriteria wajib terisi sebelum finalisasi |
| Penilai tertentu tidak mengisi | Bobot dinormalisasi dari penilai yang mengisi |
| Konflik kepentingan | Penilaian rekan anonim dan dimoderasi guru |
| Submit ganda | Idempotency key di server |
| Nilai di luar rentang | Validasi server: hanya 1–4 |
| Revisi nilai | Versi baru; versi lama tetap tersimpan |
| Total bobot ≠ 100% | Normalisasi otomatis |
| Koneksi lambat / offline | Skeleton loading, optimistic UI, antrean sinkron |
| Kuota backend primer habis | Failover otomatis ke cadangan |
| Siswa Alpa | Mengurangi skor kedisiplinan/kehadiran otomatis sesuai aturan guru |
| Properti/kostum hilang | Wajib isi formulir kehilangan |
| Bentrok booking alat | Ditolak otomatis dengan pesan |
| Email atau WhatsApp ganda saat registrasi | Registrasi ditolak |
| Kode kelas salah | Registrasi ditolak |
| Siswa pindah peran di tengah produksi | Riwayat peran tersimpan; nilai tahap sebelumnya tetap milik peran saat itu |
| Pembuat absensi tidak berhak | Aksi ditolak di server, bukan hanya disembunyikan di UI |
| Sutradara butuh peserta divisi lain | Hanya jika guru mengaktifkan pengecualian; selain itu minta Pimpinan/Sekretaris/Koordinator |
| Siswa tidak punya akses aplikasi | Guru mengisi absensi manual |
| Pengguna lupa kata sandi | Hubungi guru untuk reset |

## 17. Integrasi dan Dependensi

| Integrasi | Fungsi | Catatan |
|---|---|---|
| WhatsApp (tautan `wa.me` dan API opsional) | Notifikasi, pengingat, OTP, broadcast, aduan, absensi via WA | Mode manual wajib ada; API bersifat opsional |
| Google Drive | Backup harian, cadangan dokumentasi pertunjukan | Akses dibatasi akun guru/admin |
| Google Calendar / iCal | Sinkronisasi jadwal | Ekspor satu arah minimum |
| Backend cloud dengan basis data real-time | Penyimpanan, sinkronisasi, autentikasi | Dua proyek (primer dan cadangan) untuk failover |
| Penyimpanan berkas | Foto, video, audio, dokumen | Batas ukuran per jenis berkas (bagian 9) |
| Pustaka grafik dan PDF | Radar, batang, rapor, LPJ | Dapat diganti selama output setara |

## 18. Kriteria Penerimaan

Rilis 1.0 diterima jika seluruh poin berikut terpenuhi:

1. **Autentikasi:** Tiga jenis pengguna dapat login, registrasi siswa tervalidasi, sesi kedaluwarsa sesuai aturan.
2. **Hak akses:** Setiap peran hanya dapat melihat dan melakukan aksi sesuai matriks bagian 10, diuji di sisi server.
3. **Penilaian:** Skenario uji dengan data contoh menghasilkan nilai akhir dan predikat yang sama dengan hitungan manual (termasuk normalisasi bobot dan penilai yang tidak mengisi).
4. **Absensi terkontrol:** Sutradara, Asisten, dan Koordinator tidak dapat mengubah cakupan peserta terkunci; Bendahara, Anggota, dan Pemain tidak dapat membuat sesi.
5. **Rapor dan rekap:** Rapor PDF (lengkap dan ringkas) dan rekap XLSX/CSV dapat diunduh dengan data benar dan memuat kop dan logo.
6. **Moderasi:** Kelima jenis anomali terdeteksi pada data uji; guru dapat memvalidasi, menolak, dan membuka identitas anonim (tercatat di log).
7. **Komunikasi:** Notifikasi, broadcast, deadline dengan pengingat, aduan ke WhatsApp berfungsi sesuai peran.
8. **Offline dan PWA:** Aplikasi dapat diinstal; halaman inti terbuka tanpa jaringan; data offline tersinkron saat daring.
9. **Failover dan backup:** Simulasi kuota habis berpindah ke cadangan tanpa kehilangan data; restore per kelas berhasil.
10. **Tampilan:** Responsif pada empat breakpoint, tema terang/gelap/otomatis, aset visual (latar dan dua logo) tampil sesuai bagian 14.
11. **Keamanan:** Seluruh SEC-01 sampai SEC-20 terverifikasi lewat tinjauan dan uji.
12. **Dokumentasi:** Panduan pengguna ringkas per peran tersedia di dalam aplikasi.

## 19. Risiko dan Mitigasi

| Risiko | Dampak | Mitigasi |
|---|---|---|
| Cakupan sangat besar, semua fitur berprioritas sama | Jadwal molor, kualitas turun | Pecah menjadi milestone teknis (fondasi, penilaian, produksi, komunikasi, penguatan) walau semuanya wajib pada 1.0; setiap `FR-xx` menjadi issue sendiri |
| Siswa memakai HP dengan kuota dan memori terbatas | Aplikasi lambat atau tidak terpakai | Mode hemat data, PWA, offline, kompresi gambar |
| Penilaian rekan dipakai untuk balas dendam atau saling menguntungkan | Nilai tidak adil | Anonim, deteksi anomali, moderasi guru, bobot rekan kecil |
| Kuota layanan cloud gratis habis | Aplikasi berhenti | Failover dua proyek, pemantauan kuota |
| Kehilangan data | Nilai hilang | Backup harian otomatis, riwayat revisi, restore per jenis data |
| Kebocoran data pribadi siswa | Pelanggaran privasi | Bagian 13, minimisasi data, retensi |
| Tautan aset eksternal hilang | Logo/latar tidak tampil | Simpan salinan aset di repositori |
| Ketergantungan API WhatsApp | Notifikasi gagal | Mode manual `wa.me` selalu tersedia |
| Dokumen sumber saling bertentangan | Salah implementasi | Daftar keputusan default (bagian 20) disepakati sebelum pengembangan |

## 20. Keputusan Default dan Asumsi

Dokumen sumber memuat dua versi yang berbeda. PRD ini memilih nilai berikut sebagai **default yang dapat diubah guru** (kecuali jumlah peran dan tahapan yang bersifat struktural). Tim pengembang diminta mengonfirmasi butir bertanda ⚠️ dengan Guru Pembina sebelum pengembangan.

| Topik | Versi A (dokumen fitur per peran) | Versi B (dokumentasi lengkap) | Keputusan PRD |
|---|---|---|---|
| Bobot penilai | Guru 50 / Ketua 30 / Rekan 20 | Guru 60 / Ketua 25 / Rekan 15 | **50 / 30 / 20** ⚠️ (dapat diubah di Pengaturan) |
| Tahapan | 4 (Persiapan, Pelaksanaan, Pertunjukan, Pasca) | 5 (Development, Latihan, Gladi Resik, Pementasan, Evaluasi) | **4 tahapan**; Latihan dan Gladi Resik tercakup dalam Pelaksanaan, Evaluasi sebagai Pasca |
| Divisi | 6 divisi | 7 grup (termasuk Pengurus Inti dan Pemeran) | **6 divisi** + kelompok Pengurus Inti, Artistik, dan Pemeran |
| Peran | 17 peran siswa | 21 peran | **17 peran** ⚠️ konfirmasi penghitungan akhir (bagian 5.1) |
| Bobot tahapan | 20 / 35 / 30 / 15 | tidak dirinci | **20 / 35 / 30 / 15** (dapat diubah) |
| Skala | 1–4 (Sangat Baik 100, Baik 80, Cukup 60, Kurang 40) | sama | Sama |
| Panjang kata sandi | tidak disebut | minimal 6 karakter | **minimal 8 karakter** (keputusan keamanan) |
| Hak Beri Nilai Anggota dan Pemain | hanya penilaian rekan | tanda ✅ pada matriks | **Hanya penilaian rekan sejawat** untuk Anggota dan Pemain |
| Hak aduan | semua siswa | tabel menandai sebagian peran ❌ | **Semua siswa dapat mengajukan aduan** |
| Hak absensi/jadwal | Sekretaris saja | Pimpinan, Sekretaris, Sutradara, Asisten, Koordinator | Mengikuti **bagian 8.8 dan 8.9** |

Asumsi tambahan:

- Satu produksi per kelas per periode; guru dapat mengampu beberapa kelas.
- Tahun ajaran default 2025/2026, dapat diubah.
- Fitur berbasis AI (face chart dari deskripsi) bersifat opsional dan dapat dinonaktifkan; tidak ada data siswa yang dikirim ke layanan eksternal tanpa persetujuan guru.
- Semua fitur diberi prioritas yang sama; urutan pengerjaan ditentukan tim pengembang berdasarkan ketergantungan teknis, bukan nilai bisnis.

---

*Akhir dokumen PRD SP-PPT v1.0.*
