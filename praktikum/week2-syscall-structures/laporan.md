
# Laporan Praktikum Minggu [X]
Topik: [Tuliskan judul topik, misalnya "Arsitektur Sistem Operasi dan Kernel"]

---

## Identitas
- **Nama**  : [Miftah Raihan Hidayat]  
- **NIM**   : [250202950]  
- **Kelas** : [1IKRA]

---

## Tujuan
Tuliskan tujuan praktikum minggu ini.  
1. Menjelaskan konsep dan fungsi system call dalam sistem operasi.
2. Mengidentifikasi jenis-jenis system call dan fungsinya.
3. Mengamati alur perpindahan mode user ke kernel saat system call terjadi.
4. Menggunakan perintah Linux untuk menampilkan dan menganalisis system call

---

## Dasar Teori
Dasar teori mengenai System Call dan Fungsi Kernel adalah inti dari bagaimana sebuah Sistem Operasi (SO) bekerja untuk mengelola sumber daya komputer dan menyediakan layanan kepada program aplikasi.
​1. Kernel (Inti Sistem Operasi)
​Kernel adalah inti atau landasan dasar dari sebuah Sistem Operasi (SO). Ia merupakan lapisan penghubung antara perangkat keras (hardware) komputer dengan perangkat lunak (software) yang bekerja di atasnya. Kernel memiliki kontrol penuh atas segala sesuatu dalam sistem dan bekerja pada mode yang paling istimewa (kernel mode atau supervisor mode), yang memberikannya akses langsung ke semua sumber daya sistem.
​Fungsi Utama Kernel
​Tugas utama kernel adalah mengelola sumber daya sistem dan menyediakan layanan yang aman dan terstruktur bagi program.
​Manajemen Proses:
​Mengatur pembuatan, penjadwalan, dan pengakhiran proses.
​Menentukan proses mana yang akan dijalankan oleh CPU (CPU scheduling).
​Menyediakan mekanisme komunikasi antar-proses (Inter-Process Communication - IPC).
​Manajemen Memori:
​Mengalokasikan dan mendealokasikan memori untuk proses-proses.
​Mengimplementasikan memori virtual (misalnya, paging atau swapping) untuk memberikan ilusi memori yang lebih besar dari yang sebenarnya.
​Manajemen Perangkat Keras (I/O Management):
​Bertindak sebagai perantara antara program dengan perangkat keras I/O (seperti hard disk, keyboard, mouse, kartu jaringan).
​Mengelola device driver yang diperlukan untuk berkomunikasi dengan perangkat tertentu.
​Manajemen Sistem File:
​Mengatur penyimpanan, pengorganisasian, dan pengambilan data pada media penyimpanan (seperti disk).
​Menyediakan struktur direktori dan mekanisme izin akses.
​2. System Call (Panggilan Sistem)
​System Call (panggilan sistem) adalah cara terprogram di mana sebuah program komputer yang berjalan di ruang pengguna (user space) meminta layanan dari Kernel (yang berada di kernel space) dari sistem operasi yang sedang dijalankan.
​Peran dan Mekanisme System Call
​Antarmuka SO: System call adalah antarmuka yang ditentukan dan terkontrol antara program aplikasi dengan layanan inti sistem operasi. Ini adalah satu-satunya cara bagi program di user mode untuk mengakses sumber daya sistem yang diproteksi (seperti file, I/O, memori).
​Keamanan dan Stabilitas: Program aplikasi berjalan di user mode dengan hak akses terbatas. Hal ini mencegah program yang salah atau berbahaya untuk secara langsung merusak sistem atau perangkat keras. System call memastikan akses ke sumber daya yang sensitif dilakukan di bawah pengawasan ketat Kernel.
​Proses Kerja:
​Permintaan: Program aplikasi biasanya memanggil fungsi pustaka standar (standard library function), misalnya printf() atau fopen(), yang kemudian akan memanggil system call wrapper function.
​Transisi Mode: Fungsi wrapper ini akan memicu instruksi khusus (software interrupt atau trap) yang menyebabkan CPU beralih dari User Mode ke Kernel Mode.
​Eksekusi Kernel: Kernel mengambil kendali, mengidentifikasi system call yang diminta (melalui nomor system call), dan menjalankan fungsi kernel yang terkait untuk memenuhi permintaan tersebut.
​Pengembalian: Setelah layanan selesai, Kernel mengembalikan kontrol ke program aplikasi dan beralih kembali ke User Mode.Singkatnya, System Call adalah pintu gerbang terkontrol bagi program di user space untuk mengakses layanan dan sumber daya yang dikelola oleh Kernel di kernel space.


---

### **Hubungan System Call dan Kernel:**

1. Antarmuka Layanan
System call (panggilan sistem) bertindak sebagai gerbang atau API (Application Programming Interface) antara program yang berjalan di user space (ruang pengguna) dan kernel space (ruang kernel).

Program aplikasi tidak dapat mengakses sumber daya perangkat keras atau layanan sistem operasi (seperti manajemen berkas, memori, atau proses) secara langsung karena alasan keamanan dan stabilitas.

Untuk melakukan operasi ini, program harus memanggil fungsi system call yang sesuai.

2. Mode Eksekusi (Mode Switching)
Kernel adalah inti dari sistem operasi, berjalan dalam mode privileged (mode kernel/supervisor), yang memberikannya hak penuh untuk mengakses semua perangkat keras dan memori.

Program aplikasi berjalan dalam mode unprivileged (mode pengguna).

Ketika sebuah system call dipanggil, terjadi mode switching atau context switch: eksekusi berpindah dari mode pengguna ke mode kernel.

3. Eksekusi Layanan
Setelah beralih ke mode kernel, kernel memeriksa dan mengeksekusi permintaan layanan yang spesifik yang diwakili oleh system call tersebut.

Kernel menangani semua operasi penting, seperti:

I/O (Input/Output): Membaca/menulis berkas.

Manajemen Proses: Membuat proses baru (fork, exec).

Manajemen Memori: Mengalokasikan memori (malloc atau sbrk).

Komunikasi Antar-Proses (IPC).

Setelah layanan selesai, kernel mengembalikan hasilnya kepada program aplikasi dan melakukan mode switching kembali ke mode pengguna, melanjutkan eksekusi program.

Kesimpulan
System call adalah mekanisme yang diatur oleh kernel untuk memfasilitasi komunikasi yang aman dan terstruktur antara program aplikasi dan inti sistem operasi (kernel), memungkinkan program untuk menggunakan sumber daya perangkat keras dan layanan sistem.

---

### **Ilustrasi Sederhana:**

```plaintext
[Aplikasi Pengguna]
     |
     |----> System Call (misalnya, write())
     |
[Kernel OS] <-- Menangani permintaan, lalu kembali ke aplikasi
```

---


---

## Langkah Praktikum.
1. Langkah-langkah yang dilakukan:Menyiapkan Lingkungan Percobaan
Menggunakan sistem operasi Linux (bisa via mesin virtual atau dual boot).

Membuka terminal dan memastikan hak akses root/sudo tersedia.

Menyediakan compiler (seperti gcc) untuk menyusun program C.

Membuat Program yang Memanggil System Call

Menulis program C sederhana yang menggunakan system call, seperti:

write() untuk mencetak ke layar,

getpid() untuk mendapatkan ID proses,

fork() untuk membuat proses baru,

open(), read(), close() untuk manajemen file.
2. Perintah yang dijalankan: 1.Menulis dan Menyusun Program C dengan System Call 2.Menjalankan Program 3.Melacak System Call yang Digunakan (dengan strace) 3. File dan kode yang dibuat: 💻 File kode (C / C++) yang berisi struktur system call dan fungsi di dalam kernel (misalnya untuk OS seperti Linux)?

📄 Diagram / dokumen penjelasan tentang struktur sistem call dan fungsi kernel (misalnya untuk laporan atau kuliah sistem operasi)?

⚙️ Template proyek yang memperlihatkan bagaimana menambahkan system call baru di kernel Linux (file .c, .h, dan Makefile)? 4. Commit message yang digunakan:ika menambahkan struktur dan fungsi kernel baru:

feat(kernel): add system call structure and kernel function implementation

Menjelaskan bahwa kamu menambahkan fitur baru (struktur dan fungsi kernel).

2. Jika memperbaiki atau mengubah sistem call yang sudah ada:
fix(syscall): correct parameter handling and update kernel function logic

Fokus pada perbaikan bug atau pembaruan logika fungsi.

3. Jika hanya merapikan atau menambahkan dokumentasi:
docs(kernel): add documentation for system call structure and kernel functioJika menambahkan file awal untuk struktur sistem call:
chore(kernel): create initial files for system call structure and kernel function stubs

Jika membuat commit spesifik untuk tugas kuliah / laporan praktikum:

---

## Kode / Perintah
Tuliskan potongan kode atau perintah utama:
```bash
uname -a
lsmod | head
dmesg | head
```

---

## Hasil Eksekusi
Sertakan screenshot hasil percobaan atau diagram:
![https://photos.app.goo.gl/DHLf6gbJPBK2Jau6A)

---

## Analisis
Analisis
- Jelaskan makna hasil percobaan:User Program (User Space)

Merupakan program atau aplikasi yang dijalankan oleh pengguna (misalnya ls, cat, atau program C buatan sendiri).

Program ini tidak memiliki akses langsung ke perangkat keras demi keamanan dan stabilitas sistem.

Ketika butuh layanan dari sistem (misalnya membaca file, membuat proses, atau mengakses memori), program akan memanggil system call.

2. System Call Interface

Ini adalah lapisan perantara antara user space dan kernel space.

Fungsinya menerjemahkan permintaan dari program pengguna menjadi operasi yang bisa dijalankan oleh kernel.

Contohnya: read(), write(), fork(), open(), close() — semuanya melewati system call interface.

Pada tahap ini, CPU berpindah mode dari user mode ke kernel mode.

3. Kernel Function

Di sinilah fungsi inti kernel dijalankan untuk mengeksekusi permintaan system call.

Kernel memiliki hak akses penuh ke perangkat keras dan memori.

Misalnya, ketika user memanggil write(), kernel function akan mengatur penulisan data ke buffer I/O atau driver perangkat. 
- Hubungkan hasil dengan teori (fungsi kernel, system call, arsitektur OS): Hubungan dengan Teori Fungsi Kernel

Dalam teori sistem operasi, kernel adalah inti sistem operasi yang mengelola seluruh sumber daya komputer — seperti CPU, memori, dan perangkat I/O.

Pada hasil percobaan (diagram), bagian “Kernel Function” menunjukkan bagaimana kernel menangani permintaan yang datang dari user program melalui system call.

Fungsi kernel meliputi:

Manajemen proses: membuat, menjadwalkan, dan mengakhiri proses.

Manajemen memori: mengalokasikan dan mengatur memori antar proses.

Manajemen perangkat I/O: melalui driver untuk membaca/menulis data.

Artinya, diagram tadi mencerminkan bagaimana fungsi kernel berperan sebagai pengendali utama antara aplikasi dan perangkat keras. 
- Apa perbedaan hasil di lingkungan OS berbeda (Linux vs Windows)? Perbedaan Arsitektur Sistem
Aspek	Linux	Windows
Tipe arsitektur	Monolithic kernel	Hybrid kernel
Deskripsi	Semua komponen inti (scheduler, memory manager, file system, driver) berada di dalam satu ruang kernel.	Kombinasi antara microkernel dan monolithic, dengan sebagian layanan kernel dijalankan sebagai modul terpisah (misalnya Windows Executive, HAL, dll).
Implikasi pada hasil percobaan	System call langsung berinteraksi dengan kernel, sehingga lebih cepat namun berisiko bila bug terjadi.	System call melalui beberapa lapisan (napi.dll → kernel32.dll → ntoskrnl.exe), sedikit lebih lambat namun lebih stabil dan modular.
 Perbedaan Mekanisme System Call
Aspek	Linux	Windows
Interface system call	Langsung melalui tabel sys_call_table di kernel.	Melalui Windows API (user mode) → Native API (kernel mode).
Contoh pemanggilan	write(), read(), open() — langsung menuju fungsi kernel (sys_write, sys_read, dll).	WriteFile(), ReadFile() — dipanggil melalui kernel32.dll → ntdll.dll → ntoskrnl.exe.
Jumlah system call	Lebih terbuka (ratusan system call dapat dilihat via strace atau /usr/include/syscall.h).	Lebih tertutup (API tidak semua didokumentasikan secara publik).
Akses developer	Open source — tabel dan implementasi system call bisa dimodifikasi dan dipelajari.	Closed source — hanya API level yang bisa digunakan, implementasi internal kernel disembunyikan.
 
---
---

## Kesimpulan
​Poin-Poin Utama:
​System Call sebagai Antarmuka SO: Praktikum menunjukkan bahwa system call adalah satu-satunya mekanisme terstruktur dan aman bagi program yang berjalan di user mode untuk mengakses layanan-layanan penting yang disediakan oleh SO, seperti manajemen file (open, read, write), manajemen proses (fork, exec), dan kontrol perangkat keras.
​Pentingnya Dual Mode Operasi: Praktikum memvalidasi konsep dual mode operasi (User Mode dan Kernel Mode). Setiap kali system call dipanggil, terjadi transisi mode dari User Mode ke Kernel Mode melalui mekanisme trap atau interrupt. Transisi ini penting untuk:
​Keamanan (Proteksi): Mencegah program aplikasi merusak atau mengakses sumber daya sistem yang sensitif secara langsung.
​Stabilitas: Memastikan bahwa kegagalan satu program aplikasi tidak akan menyebabkan seluruh sistem (kernel) crash.
​Abstraksi oleh Pustaka Standar: Dalam praktikum (misalnya, menggunakan bahasa C), programer jarang memanggil system call secara langsung. Sebaliknya, digunakan fungsi pustaka standar (seperti fopen() atau printf()). Pustaka ini bertindak sebagai wrapper yang mempermudah pemrogram dan menangani detail teknis pemanggilan system call (seperti menyiapkan parameter dan memicu trap).
​Implementasi Layanan Kernel: Hasil dari system call adalah eksekusi fungsi yang sesuai di dalam Kernel. Praktikum memperlihatkan bagaimana Kernel, setelah mengambil kendali, menjalankan tugas inti (misalnya, menjadwalkan proses baru, atau memindahkan data antara buffer memori dan perangkat keras disk).
​Secara keseluruhan, praktikum system call memberikan pemahaman praktis bahwa system call adalah fondasi arsitektur Sistem Operasi modern yang memastikan efisiensi, keamanan, dan manajemen sumber daya yang terpusat dan teratur.

---

## Quiz
1. Apa yang dimaksud dengan system call dalam sistem operasi?
Jawaban: System call adalah mekanisme yang digunakan oleh program aplikasi (user space) untuk meminta layanan dari kernel (kernel space). Melalui system call, aplikasi dapat melakukan operasi yang memerlukan hak akses tinggi, seperti membaca file, membuat proses baru, atau berkomunikasi dengan perangkat keras. Contoh system call pada Linux: read(), write(), open(), fork().

2. Apa peran utama fungsi kernel dalam sistem operasi?
Jawaban: Fungsi kernel berperan sebagai pengelola utama sumber daya sistem. Kernel bertanggung jawab atas manajemen proses, memori, sistem file, serta perangkat I/O. Ketika system call dipanggil, kernel mengeksekusi fungsi tertentu (misalnya sys_read atau sys_write) untuk melaksanakan permintaan aplikasi secara aman dan efisien.

3. Bagaimana alur kerja system call dari aplikasi hingga kembali ke aplikasi?
Jawaban:

Aplikasi di user space memanggil fungsi library (misalnya printf() → write() system call).

Permintaan diteruskan ke System Call Interface melalui trap ke kernel mode.

Kernel menjalankan fungsi kernel yang sesuai untuk menangani permintaan (misalnya menulis ke file atau perangkat).

Jika perlu, kernel berkomunikasi dengan device driver untuk mengakses perangkat keras.

Setelah selesai, hasil dikembalikan ke aplikasi di user space. 

---

## Refleksi Diri
 Tuliskan secara singkat:

-mungkin karna saya belum begitu mengerti tentang aplikasi baru
-saya akan terus belajar dan menanyakan kepada teman yg sudah bisa

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
