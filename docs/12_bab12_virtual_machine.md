NAMA :ERWAN AFFIF HIDAYAT
NIM;250202935
KELAS:1IKRA
Tugas Praktikum Minggu 12
Topik: Virtualisasi Menggunakan Virtual Machine

A. Deskripsi Singkat
Pada praktikum minggu ini, mahasiswa akan mempelajari konsep virtualisasi sistem operasi dengan menggunakan Virtual Machine (VM).
Mahasiswa diarahkan untuk menginstal dan menjalankan sistem operasi guest di atas host OS menggunakan perangkat lunak virtualisasi seperti VirtualBox atau VMware.

Praktikum ini menekankan pemahaman hubungan antara host OS, guest OS, dan hypervisor, serta bagaimana konfigurasi resource (CPU, memori, dan storage) memengaruhi kinerja dan isolasi sistem.

B. Tujuan
Setelah menyelesaikan tugas ini, mahasiswa mampu:

Menginstal perangkat lunak virtualisasi (VirtualBox/VMware).
Membuat dan menjalankan sistem operasi guest di dalam VM.
Mengatur konfigurasi resource VM (CPU, RAM, storage).
Menjelaskan mekanisme proteksi OS melalui virtualisasi.
Menyusun laporan praktikum instalasi dan konfigurasi VM secara sistematis.
C. Ketentuan Teknis
Virtualisasi dapat menggunakan VirtualBox atau VMware.
Sistem operasi guest bebas (Linux Ubuntu direkomendasikan).
Praktikum dapat dilakukan secara kelompok kecil (2–3 orang).
Struktur folder (sesuaikan dengan template repo):

praktikum/week12-virtual-machine/
├─ code/
│  └─ catatan_konfigurasi.txt (opsional)
├─ screenshots/
│  ├─ instalasi_vm.png
│  ├─ konfigurasi_resource.png
│  └─ os_guest_running.png
└─ laporan.md
D. Langkah Pengerjaan
Instalasi Virtual Machine

Instal VirtualBox atau VMware pada komputer host.
Pastikan fitur virtualisasi (VT-x / AMD-V) aktif di BIOS.
Pembuatan OS Guest

Buat VM baru dan pilih OS guest (misal: Ubuntu Linux).
Atur resource awal:
CPU: 1–2 core
RAM: 2–4 GB
Storage: ≥ 20 GB
Instalasi Sistem Operasi

Jalankan proses instalasi OS guest sampai selesai.
Pastikan OS guest dapat login dan berjalan normal.
Konfigurasi Resource

Ubah konfigurasi CPU dan RAM.
Amati perbedaan performa sebelum dan sesudah perubahan resource.
Analisis Proteksi OS

Jelaskan bagaimana VM menyediakan isolasi antara host dan guest.
Kaitkan dengan konsep sandboxing dan hardening OS.
Dokumentasi

Ambil screenshot setiap tahap penting.
Simpan di folder screenshots/.
Commit & Push

git add .
git commit -m "Minggu 12 - Virtual Machine"
git push origin main
E. Tugas & Quiz
Tugas
Instal dan jalankan OS guest menggunakan VM.
Konfigurasikan resource VM sesuai instruksi.
Dokumentasikan proses instalasi dan konfigurasi.
Tulis laporan praktikum pada laporan.md.
Quiz
Jawab pada bagian Quiz di laporan:

Apa perbedaan antara host OS dan guest OS?
Apa peran hypervisor dalam virtualisasi?
Mengapa virtualisasi meningkatkan keamanan sistem?
F. Output yang Diharapkan
Screenshot instalasi dan konfigurasi VM.
Laporan lengkap instalasi dan analisis VM di laporan.md.
Semua hasil telah di-commit ke GitHub.
G. Referensi
Silberschatz, A., Galvin, P., Gagne, G. Operating System Concepts, 10th Ed.
Tanenbaum, A. Modern Operating Systems, 4th Ed.
Oracle VirtualBox Documentation.
OSTEP – Virtualization.
