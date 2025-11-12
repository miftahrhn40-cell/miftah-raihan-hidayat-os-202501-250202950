
# Laporan Praktikum Minggu [X]
Topik: [Tuliskan judul topik, misalnya "Arsitektur Sistem Operasi dan Kernel"]

---

## Identitas
- **Nama**  : [Miftah Raihan Hidayat]  
- **NIM**   : [250202950]  
- **Kelas** : [1-IKRA]

---

## Tujuan
1. Menjelaskan konsep proses dan user dalam sistem operasi Linux.
2. Menampilkan daftar proses yang sedang berjalan dan statusnya. 
3. Menggunakan perintah untuk membuat dan mengelola user.
4. Menghentikan atau mengontrol proses tertentu menggunakan PID. 
5. Menjelaskan kaitan antara manajemen user dan keamanan sistem.
---

## Dasar Teori
- Proses adalah program yang sedang dijalankan oleh sistem. Setiap proses memiliki ID sendiri (PID), status, dan menggunakan sumber daya seperti memori dan CPU. Sistem operasi bertugas membuat, menjalankan, dan menghentikan proses agar semua tugas di komputer bisa berjalan dengan baik.

- Sistem operasi juga mengatur bagaimana proses berjalan secara bergantian, berkomunikasi, dan bisa dikontrol. Proses dapat berada dalam keadaan berjalan, menunggu, atau sudah berhenti. Untuk melihat dan mengatur proses, dapat digunakan perintah seperti ps, top, dan kill.

- Linux merupakan sistem multiuser, artinya banyak pengguna bisa memakai sistem yang sama. Setiap pengguna memiliki ID dan group tertentu. Pengaturan user dan group dilakukan agar setiap pengguna hanya bisa mengakses file atau sumber daya yang sesuai dengan haknya.

- User root adalah pengguna dengan hak tertinggi. Karena bisa mengubah semua bagian sistem, penggunaan root perlu hati-hati. Linux menggunakan sistem izin atau permission agar keamanan tetap terjaga dan pengguna lain tidak bisa sembarangan mengubah data penting.

- Saat Linux dinyalakan, proses pertama yang dijalankan adalah init atau systemd. Proses ini akan menyalakan layanan lain dan menjadi induk bagi semua proses lainnya. Hubungan antarproses ini bisa dilihat menggunakan perintah pstree.



---

## Langkah Praktikum
1. Mempersiapkan lingkungan Linux (Ubuntu/WSL)
2. Melakukan Eksperimen 1 untuk mengidentifikasi user yang sedang aktif menggunakan whoami, id, dan groups, kemudian screenshots hasilnya dan letakan di screenshots/user.png
3. Melakukan Eksperimen 2 untuk memonitor proses yang berjalan menggunakan ps aux dan top, kemudian screenshots hasilnya dan letakan di screenshots/top.png
4. Melakukan Eksperimen 3 untuk mengontrol proses dengan menjalankan sleep di latar belakang, mencari PID-nya, dan menghentikannya dengan kill , kemudian screenshots hasilnya dan letakan di screenshots/sleep.png
5. Melakukan Eksperimen 4 untuk menganalisis hierarki proses menggunakan pstree, kemudian screenshots hasilnya dan letakan di screenshots/pstree.png
6. Mendokumentasikan seluruh hasil dan analisis dalam file laporan.md.
7. Melakukan commit dan push hasil praktikum ke repositori GitHub dengan pesan commit yang sesuai.
git add .
git commit -m "Minggu 4 - Manajemen Proses & User"
git push origin main
---

## Kode / Perintah
Setup Environment

Gunakan Linux (Ubuntu/WSL).
Pastikan Anda sudah login sebagai user non-root.
Siapkan folder kerja:
praktikum/week4-proses-user/
Eksperimen 1 – Identitas User Jalankan perintah berikut:

whoami
id
groups
Jelaskan setiap output dan fungsinya.
Buat user baru (jika memiliki izin sudo):
sudo adduser praktikan
sudo passwd praktikan
Uji login ke user baru.
Eksperimen 2 – Monitoring Proses Jalankan:

ps aux | head -10
top -n 1
Jelaskan kolom penting seperti PID, USER, %CPU, %MEM, COMMAND.
Simpan tangkapan layar top ke:
praktikum/week4-proses-user/screenshots/top.png
Eksperimen 3 – Kontrol Proses

Jalankan program latar belakang:
sleep 1000 &
ps aux | grep sleep
Catat PID proses sleep.
Hentikan proses:
kill <PID>
Pastikan proses telah berhenti dengan ps aux | grep sleep.
Eksperimen 4 – Analisis Hierarki Proses Jalankan:

pstree -p | head -20
Amati hierarki proses dan identifikasi proses induk (init/systemd).
Catat hasilnya dalam laporan.
Commit & Push

git add .
git commit -m "Minggu 4 - Manajemen Proses & User"
git push origin main

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
1. User dan Grup = Setiap pengguna punya ID unik dan grup untuk mengatur hak akses.
2. Perintah penting = whoami, id, groups untuk cek info user : adduser, passwd untuk menambah dan mengubah user/password.
3. Proses sistem = ps dan top untuk memantau proses, CPU, dan memori.

---

## Quiz
Apa fungsi dari proses init atau systemd dalam sistem Linux?
jawaban: Menginisialisasi sistem, yaitu memulai semua proses penting seperti layanan (service), daemon, dan konfigurasi sistem.
Apa perbedaan antara kill dan killall?
jawaban: kill digunakan untuk menghentikan proses berdasarkan PID (Process ID). Contoh: kill 1463 menghentikan proses dengan PID 1463. killall digunakan untuk menghentikan semua proses dengan nama yang sama. Contoh: killall firefox menghentikan semua proses bernama firefox.
Mengapa user root memiliki hak istimewa di sistem Linux?
jawaban: User root memiliki hak istimewa karena merupakan administrator utama sistem Linux. Akun ini memiliki akses penuh ke semua file, perintah, dan konfigurasi sistem, sehingga dapat mengelola pengguna lain, menginstal atau menghapus software, serta mengubah pengaturan sistem.


---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
