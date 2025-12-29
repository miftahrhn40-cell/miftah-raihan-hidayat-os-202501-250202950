NAMA:ERWAN AFFIF HIDAYAT
NIM:250202935
KELAS:1IKRA
Tugas Praktikum Minggu 14
Topik: Penyusunan Laporan Praktikum Format IMRAD

A. Deskripsi Singkat
Pada pertemuan ini, mahasiswa menyusun laporan praktikum ilmiah secara sistematis menggunakan format IMRAD (Introduction, Methods, Results, and Discussion) yang ditutup dengan Kesimpulan.

Laporan IMRAD digunakan untuk merangkum praktikum-praktikum sebelumnya (mis. scheduling, page replacement, deadlock detection, VM/Docker) agar hasil uji dapat dipahami, direplikasi, dan dievaluasi secara akademik.

B. Tujuan
Setelah menyelesaikan tugas ini, mahasiswa mampu:

Menyusun laporan praktikum dengan struktur ilmiah (Pendahuluan–Metode–Hasil–Pembahasan–Kesimpulan).
Menyajikan hasil uji dalam bentuk tabel dan/atau grafik yang jelas.
Menuliskan analisis hasil dengan argumentasi yang logis.
Menyusun sitasi dan daftar pustaka dengan format yang konsisten.
Mengunggah draft laporan ke repositori dengan rapi dan tepat waktu.
C. Ketentuan Teknis
Laporan ditulis dalam Markdown pada file laporan.md.
Topik laporan boleh memilih salah satu dari praktikum sebelumnya:
Scheduling (FCFS/SJF)
Page Replacement (FIFO/LRU)
Deadlock Detection
VM/Docker (resource management)
Wajib menyertakan minimal:
1 tabel hasil (atau lebih)
1 gambar (screenshot, diagram, atau grafik)
sitasi dan daftar pustaka
Struktur folder (sesuaikan dengan template repo):

praktikum/week14-laporan-imrad/
├─ code/
│  └─ (opsional) file kode/data pendukung
├─ screenshots/
│  ├─ (wajib) bukti hasil uji
│  └─ (opsional) grafik/diagram
└─ laporan.md
D. Langkah Pengerjaan
Menentukan Topik Laporan

Pilih 1 topik dari praktikum sebelumnya (mis. Minggu 9/10/11/13) dan tetapkan tujuan eksperimen yang ingin disampaikan.

Menyiapkan Bahan

Kode/program yang digunakan.
Dataset/parameter uji (jika ada).
Bukti hasil eksekusi (screenshot) dan/atau grafik.
Menulis Laporan dengan Struktur IMRAD

Tulis praktikum/week14-laporan-imrad/laporan.md dengan struktur minimal berikut:

Pendahuluan (Introduction): latar belakang, rumusan masalah/tujuan.
Metode (Methods): lingkungan uji, langkah eksperimen, parameter/dataset, cara pengukuran.
Hasil (Results): tabel/grafik hasil uji, ringkasan temuan.
Pembahasan (Discussion): interpretasi hasil, keterbatasan, perbandingan teori/ekspektasi.
Kesimpulan: 2–4 poin ringkas menjawab tujuan.
Menyajikan Tabel/Grafik

Tabel harus diberi judul/keterangan singkat.
Jika menggunakan grafik: jelaskan sumbu dan arti grafik.
Sitasi dan Daftar Pustaka

Cantumkan referensi minimal 2 sumber.
Gunakan format konsisten (mis. daftar bernomor).
Commit & Push Draft

git add .
git commit -m "Minggu 14 - Draft Laporan IMRAD"
git push origin main
E. Tugas & Quiz
Tugas
Susun laporan praktikum format IMRAD di praktikum/week14-laporan-imrad/laporan.md.
Sertakan minimal 1 tabel dan 1 gambar (screenshot/grafik).
Sertakan sitasi dan daftar pustaka.
Pastikan struktur folder rapi sesuai ketentuan.
Quiz
Jawab pada bagian Quiz di laporan:

Mengapa format IMRAD membantu membuat laporan praktikum lebih ilmiah dan mudah dievaluasi?
Apa perbedaan antara bagian Hasil dan Pembahasan?
Mengapa sitasi dan daftar pustaka penting, bahkan untuk laporan praktikum?
F. Output yang Diharapkan
File praktikum/week14-laporan-imrad/laporan.md berisi laporan format IMRAD.
Bukti hasil uji (screenshot/grafik) tersimpan di praktikum/week14-laporan-imrad/screenshots/.
(Opsional) kode/data pendukung di praktikum/week14-laporan-imrad/code/.
Semua perubahan telah di-commit dan di-push.
G. Referensi
Silberschatz, A., Galvin, P., Gagne, G. Operating System Concepts, 10th Ed.
Tanenbaum, A. Modern Operating Systems, 4th Ed.
OSTEP – referensi sesuai topik praktikum yang dipilih.
