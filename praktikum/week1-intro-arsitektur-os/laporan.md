
# Laporan Praktikum Minggu [1]
Topik: [Tuliskan judul topik, misalnya "Arsitektur Sistem Operasi dan Kernel"]

---

## Identitas
- **Nama**  : [Miftah Raihan Hidayat]  
- **NIM**   : [250202950]  
- **Kelas** : [1IKRA]

---

## Tujuan
Tuliskan tujuan praktikum minggu ini.  
Tujuan praktikum Operating System (OS) adalah untuk:

1. *Memahami konsep dasar sistem operasi*: Praktikum OS membantu mahasiswa memahami konsep dasar sistem operasi, seperti proses manajemen, manajemen memori, sistem file, dan lain-lain.
2. *Mengenal sistem operasi yang digunakan*: Praktikum OS memungkinkan mahasiswa untuk mengenal sistem operasi yang digunakan, seperti Windows, Linux, atau macOS.
3. *Mengembangkan keterampilan teknis*: Praktikum OS membantu mahasiswa mengembangkan keterampilan teknis dalam menggunakan sistem operasi, seperti menginstal, mengkonfigurasi, dan mengelola sistem operasi.
4. *Memahami manajemen proses*: Praktikum OS membantu mahasiswa memahami bagaimana sistem operasi mengelola proses, termasuk pembuatan, penjadwalan, dan penghentian proses.
5. *Memahami manajemen memori*: Praktikum OS membantu mahasiswa memahami bagaimana sistem operasi mengelola memori, termasuk alokasi, deallokasi, dan manajemen memori virtual.
6. *Mengembangkan keterampilan troubleshooting*: Praktikum OS membantu mahasiswa mengembangkan keterampilan troubleshooting dalam mengidentifikasi dan menyelesaikan masalah yang terkait dengan sistem operasi.
7. *Meningkatkan kemampuan analisis*: Praktikum OS membantu mahasiswa meningkatkan kemampuan analisis dalam memahami bagaimana sistem operasi bekerja dan bagaimana mengoptimalkan kinerjanya.

Dengan demikian, praktikum OS sangat penting bagi mahasiswa yang ingin memahami sistem operasi dan mengembangkan keterampilan teknis dalam bidang ini.

---

## Dasar Teori
Sistem operasi adalah perangkat lunak utama yang mengelola semua sumber daya perangkat keras dan perangkat lunak pada komputer serta bertindak sebagai perantara antara pengguna dan mesin. Tanpa sistem operasi, komputer tidak dapat menjalankan program apa pun, sehingga sangat penting untuk mengoptimalkan kinerja dan memungkinkan interaksi pengguna dengan perangkat. Contohnya termasuk Microsoft Windows, macOS, dan Linux, yang semuanya mengelola memori, proses, dan perangkat input/output. 
.

---

## Langkah Praktikum
langkah-langkah yang dilakukan oleh sistem operasi:

1. *Bootstrapping*
2. *Inisialisasi*
3. *Manajemen proses
4. *Manajemen Memori*
5. *Manajemen File*
6. *Manajemen Input/Output*
7. *Penjadwalan*
8. *Keamanan*
9. *Pengelolaan Sumber Daya
10. *Pengelolaan Jaringan*

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
https://photos.app.goo.gl/r853wurdjkLFrM3N7

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
1. 1. Sebutkan tiga fungsi utama sistem operasi.
  - Tiga fungsi utama sistem operasi (SO) adalah:
​Manajemen Sumber Daya (Resource Management): Mengelola dan mengalokasikan semua sumber daya perangkat keras (hardware) dan perangkat lunak (software) komputer, seperti CPU, memori, perangkat I/O (input/output), dan berkas/file. Fungsinya adalah memastikan bahwa sumber daya digunakan secara efisien dan adil oleh berbagai program dan pengguna.
​Antarmuka Pengguna (User Interface - UI): Menyediakan cara bagi pengguna untuk berinteraksi dengan komputer, baik melalui antarmuka baris perintah (Command Line Interface - CLI) maupun antarmuka grafis (Graphical User Interface - GUI). Ini memungkinkan pengguna untuk menjalankan program dan mengelola berkas.
​Manajemen Proses dan Berkas (Process and File Management):
​Manajemen Proses: Mengatur siklus hidup program yang sedang berjalan (proses), termasuk penjadwalan, sinkronisasi, dan komunikasi antar-proses.
​Manajemen Berkas: Mengorganisir, menyimpan, mengambil, memberi nama, dan melindungi data dalam bentuk berkas dan direktori pada media penyimpanan sekunder.
.

2. Jelaskan perbedaan antara kernel mode dan user mode.
   - kernel memiliki akses penuh dan tanpa batas ke perangkat keras dan memori untuk menjalankan fungsi inti sistem operasi, sementara mode pengguna hanya memiliki akses terbatas untuk menjalankan aplikasi dan mendelegasikan permintaan yang memerlukan hak istimewa ke mode kernel melalui API.
  
3. Sebutkan contoh OS dengan arsitektur monolithic dan microkernel.
 - Contoh sistem operasi (OS) dengan arsitektur monolitik adalah Linux dan Unix, sementara contoh OS dengan arsitektur mikrokernel adalah QNX, MINIX, dan L4. Perbedaan utamanya terletak pada bagaimana layanan inti dan non-inti dikelola; arsitektur monolitik menggabungkan semua layanan dalam satu ruang alamat tunggal, sedangkan arsitektur mikrokernel memisahkan layanan dasar di inti dan menjalankan layanan lainnya sebagai proses terpisah di ruang alamat berbeda. 

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
