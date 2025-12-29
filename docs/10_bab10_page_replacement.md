NAMA:ERWAN AFFIF HIDAYAT
NIM:250202935
KELAS:1IKRA
Tugas Praktikum Minggu 10
Topik: Manajemen Memori – Page Replacement (FIFO & LRU)

A. Deskripsi Singkat
Pada praktikum minggu ini, mahasiswa akan mempelajari manajemen memori virtual, khususnya mekanisme page replacement.
Fokus utama praktikum adalah memahami bagaimana sistem operasi mengganti halaman (page) di memori utama ketika terjadi page fault, serta membandingkan performa algoritma FIFO (First-In First-Out) dan LRU (Least Recently Used).

Mahasiswa akan mengimplementasikan program simulasi page replacement, menjalankan dataset uji, dan menyajikan hasil dalam bentuk tabel atau grafik.

B. Tujuan
Setelah menyelesaikan tugas ini, mahasiswa mampu:

Mengimplementasikan algoritma page replacement FIFO dalam program.
Mengimplementasikan algoritma page replacement LRU dalam program.
Menjalankan simulasi page replacement dengan dataset tertentu.
Membandingkan performa FIFO dan LRU berdasarkan jumlah page fault.
Menyajikan hasil simulasi dalam laporan yang sistematis.
C. Ketentuan Teknis
Bahasa pemrograman bebas (Python / C / Java / lainnya).
Program berbasis terminal (tidak wajib GUI).
Fokus penilaian pada logika algoritma dan keakuratan hasil simulasi.
Struktur folder (sesuaikan dengan template repo):

praktikum/week10-page-replacement/
├─ code/
│  ├─ page_replacement.*
│  └─ reference_string.txt
├─ screenshots/
│  └─ hasil_simulasi.png
└─ laporan.md
D. Langkah Pengerjaan
Menyiapkan Dataset

Gunakan reference string berikut sebagai contoh:

7, 0, 1, 2, 0, 3, 0, 4, 2, 3, 0, 3, 2
Jumlah frame memori: 3 frame.

Implementasi FIFO

Simulasikan penggantian halaman menggunakan algoritma FIFO.
Catat setiap page hit dan page fault.
Hitung total page fault.
Implementasi LRU

Simulasikan penggantian halaman menggunakan algoritma LRU.
Catat setiap page hit dan page fault.
Hitung total page fault.
Eksekusi & Validasi

Jalankan program untuk FIFO dan LRU.
Pastikan hasil simulasi logis dan konsisten.
Simpan screenshot hasil eksekusi.
Analisis Perbandingan

Buat tabel perbandingan seperti berikut:

Algoritma	Jumlah Page Fault	Keterangan
FIFO	...	...
LRU	...	...
Jelaskan mengapa jumlah page fault bisa berbeda.
Analisis algoritma mana yang lebih efisien dan alasannya.
Commit & Push

git add .
git commit -m "Minggu 10 - Page Replacement FIFO & LRU"
git push origin main
E. Tugas & Quiz
Tugas
Buat program simulasi page replacement FIFO dan LRU.
Jalankan simulasi dengan dataset uji.
Sajikan hasil simulasi dalam tabel atau grafik.
Tulis laporan praktikum pada laporan.md.
Quiz
Jawab pada bagian Quiz di laporan:

Apa perbedaan utama FIFO dan LRU?
Mengapa FIFO dapat menghasilkan Belady’s Anomaly?
Mengapa LRU umumnya menghasilkan performa lebih baik dibanding FIFO?
F. Output yang Diharapkan
Kode program simulasi di folder code/.
Dataset uji di code/reference_string.txt.
Screenshot hasil simulasi di screenshots/.
Laporan lengkap di laporan.md.
Semua hasil telah di-commit ke GitHub.
G. Referensi
Silberschatz, A., Galvin, P., Gagne, G. Operating System Concepts, 10th Ed.
Tanenbaum, A. Modern Operating Systems, 4th Ed.
OSTEP – Virtual Memory & Page Replacement
