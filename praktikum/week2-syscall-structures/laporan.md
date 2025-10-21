
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

## Langkah Praktikum
1. Langkah-langkah yang dilakukan.  
2. Perintah yang dijalankan.  
3. File dan kode yang dibuat.  
4. Commit message yang digunakan.

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
![Screenshot hasil](screenshots/example.png)

---

## Analisis
- Jelaskan makna hasil percobaan.  
- Hubungkan hasil dengan teori (fungsi kernel, system call, arsitektur OS).  
- Apa perbedaan hasil di lingkungan OS berbeda (Linux vs Windows)?  

---

## Kesimpulan
Tuliskan 2–3 poin kesimpulan dari praktikum ini.

---

## Quiz
1. [Pertanyaan 1]  
   **Jawaban:**  
2. [Pertanyaan 2]  
   **Jawaban:**  
3. [Pertanyaan 3]  
   **Jawaban:**  

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
