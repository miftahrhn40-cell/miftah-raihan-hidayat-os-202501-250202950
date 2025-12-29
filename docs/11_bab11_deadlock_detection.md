nama:erwan affif hidayat
nim:250202935
kelas:1ikra
Tugas Praktikum Minggu 11
Topik: Simulasi dan Deteksi Deadlock

A. Deskripsi Singkat
Pada praktikum minggu ini, mahasiswa akan mempelajari mekanisme deteksi deadlock dalam sistem operasi.
Berbeda dengan Minggu 7 yang berfokus pada pencegahan dan penghindaran deadlock, pada minggu ini mahasiswa diarahkan untuk mendeteksi deadlock yang telah terjadi menggunakan pendekatan algoritmik.

Mahasiswa akan membuat program simulasi sederhana deteksi deadlock, menjalankan dataset uji, serta menyajikan hasil analisis dalam bentuk tabel dan interpretasi logis.

B. Tujuan
Setelah menyelesaikan tugas ini, mahasiswa mampu:

Membuat program sederhana untuk mendeteksi deadlock.
Menjalankan simulasi deteksi deadlock dengan dataset uji.
Menyajikan hasil analisis deadlock dalam bentuk tabel.
Memberikan interpretasi hasil uji secara logis dan sistematis.
Menyusun laporan praktikum sesuai format yang ditentukan.
C. Ketentuan Teknis
Bahasa pemrograman bebas (Python / C / Java / lainnya).
Program berbasis terminal, tidak memerlukan GUI.
Fokus penilaian pada logika algoritma deteksi deadlock, bukan kompleksitas bahasa.
Struktur folder (sesuaikan dengan template repo):

praktikum/week11-deadlock-detection/
├─ code/
│  ├─ deadlock_detection.*
│  └─ dataset_deadlock.csv
├─ screenshots/
│  └─ hasil_deteksi.png
└─ laporan.md
D. Langkah Pengerjaan
Menyiapkan Dataset

Gunakan dataset sederhana yang berisi:

Daftar proses
Resource Allocation
Resource Request / Need
Contoh tabel:

Proses	Allocation	Request
P1	R1	R2
P2	R2	R3
P3	R3	R1
Implementasi Algoritma Deteksi Deadlock

Program minimal harus:

Membaca data proses dan resource.
Menentukan apakah sistem berada dalam kondisi deadlock.
Menampilkan proses mana saja yang terlibat deadlock.
Eksekusi & Validasi

Jalankan program dengan dataset uji.
Validasi hasil deteksi dengan analisis manual/logis.
Simpan hasil eksekusi dalam bentuk screenshot.
Analisis Hasil

Sajikan hasil deteksi dalam tabel (proses deadlock / tidak).
Jelaskan mengapa deadlock terjadi atau tidak terjadi.
Kaitkan hasil dengan teori deadlock (empat kondisi).
Commit & Push

git add .
git commit -m "Minggu 11 - Deadlock Detection"
git push origin main
E. Tugas & Quiz
Tugas
Buat program simulasi deteksi deadlock.
Jalankan program dengan dataset uji.
Sajikan hasil analisis dalam tabel dan narasi.
Tulis laporan praktikum pada laporan.md.
Quiz
Jawab pada bagian Quiz di laporan:

Apa perbedaan antara deadlock prevention, avoidance, dan detection?
Mengapa deteksi deadlock tetap diperlukan dalam sistem operasi?
Apa kelebihan dan kekurangan pendekatan deteksi deadlock?
F. Output yang Diharapkan
Kode program deteksi deadlock di folder code/.
Dataset uji di code/dataset_deadlock.csv.
Screenshot hasil eksekusi di folder screenshots/.
Laporan lengkap di laporan.md.
Semua hasil telah di-commit ke GitHub.
G. Referensi
Silberschatz, A., Galvin, P., Gagne, G. Operating System Concepts, 10th Ed.
Tanenbaum, A. Modern Operating Systems, 4th Ed.
OSTEP – Deadlock Detection
