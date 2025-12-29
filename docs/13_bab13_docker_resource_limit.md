NAMA:ERWAN AFFIF HIDAYAT
NIM:250202935
KELAS:1IKRA
Tugas Praktikum Minggu 13
Topik: Docker – Resource Limit (CPU & Memori)

A. Deskripsi Singkat
Pada praktikum minggu ini, mahasiswa mempelajari konsep containerization menggunakan Docker, serta bagaimana sistem operasi membatasi pemakaian sumber daya proses melalui mekanisme isolasi dan kontrol resource (mis. cgroups pada Linux).

Fokus praktikum adalah:

Membuat Dockerfile sederhana untuk menjalankan aplikasi/skrip.
Menjalankan container dengan pembatasan resource (CPU dan memori).
Mengamati dampak pembatasan resource melalui output program dan monitoring sederhana.
B. Tujuan
Setelah menyelesaikan tugas ini, mahasiswa mampu:

Menulis Dockerfile sederhana untuk sebuah aplikasi/skrip.
Membangun image dan menjalankan container.
Menjalankan container dengan pembatasan CPU dan memori.
Mengamati dan menjelaskan perbedaan eksekusi container dengan dan tanpa limit resource.
Menyusun laporan praktikum secara runtut dan sistematis.
C. Ketentuan Teknis
Sistem operasi host bebas (Windows/macOS/Linux). Disarankan memakai Docker Desktop (atau Docker Engine di Linux).
Program berbasis terminal.
Fokus penilaian pada keberhasilan build & run container, penerapan resource limit, serta kualitas analisis.
Struktur folder (sesuaikan dengan template repo):

praktikum/week13-docker-resource-limit/
├─ code/
│  ├─ Dockerfile
│  └─ app.*
├─ screenshots/
│  └─ hasil_limit.png
└─ laporan.md
D. Langkah Pengerjaan
Persiapan Lingkungan

Pastikan Docker terpasang dan berjalan.
Verifikasi:
docker version
docker ps
Membuat Aplikasi/Skrip Uji

Buat program sederhana di folder code/ (bahasa bebas) yang:

Melakukan komputasi berulang (untuk mengamati limit CPU), dan/atau
Mengalokasikan memori bertahap (untuk mengamati limit memori).
Membuat Dockerfile

Tulis Dockerfile untuk menjalankan program uji.
Build image:
docker build -t week13-resource-limit .
Menjalankan Container Tanpa Limit

Jalankan container normal:
docker run --rm week13-resource-limit
Catat output/hasil pengamatan.
Menjalankan Container Dengan Limit Resource

Jalankan container dengan batasan resource (contoh):

docker run --rm --cpus="0.5" --memory="256m" week13-resource-limit
Catat perubahan perilaku program (mis. lebih lambat, error saat memori tidak cukup, dll.).

Monitoring Sederhana

Jalankan container (tanpa --rm jika perlu) dan amati penggunaan resource:
docker stats
Ambil screenshot output eksekusi dan/atau docker stats.
Commit & Push

git add .
git commit -m "Minggu 13 - Docker Resource Limit"
git push origin main
E. Tugas & Quiz
Tugas
Buat Dockerfile sederhana dan program uji di folder code/.
Build image dan jalankan container tanpa limit.
Jalankan container dengan limit CPU dan memori.
Sajikan hasil pengamatan dalam tabel/uraian singkat di laporan.md.
Quiz
Jawab pada bagian Quiz di laporan:

Mengapa container perlu dibatasi CPU dan memori?
Apa perbedaan VM dan container dalam konteks isolasi resource?
Apa dampak limit memori terhadap aplikasi yang boros memori?
F. Output yang Diharapkan
File Dockerfile dan kode program uji di praktikum/week13-docker-resource-limit/code/.
Screenshot hasil eksekusi/monitoring di praktikum/week13-docker-resource-limit/screenshots/.
Laporan lengkap pada praktikum/week13-docker-resource-limit/laporan.md.
Semua hasil telah di-commit ke GitHub.
G. Referensi
Docker Documentation – Resource constraints (CPU/Memory).
Linux Kernel Docs – Control Groups (cgroups) dan namespaces.
OSTEP – Virtualization / Resource Management
