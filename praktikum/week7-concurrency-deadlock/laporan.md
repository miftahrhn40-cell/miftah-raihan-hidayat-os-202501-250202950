9
# Laporan Praktikum Minggu [X]
Topik: [Tuliskan judul topik, misalnya "Arsitektur Sistem Operasi dan Kernel"]

---

## Identitas
- **Nama**  : [MIFTAH RAIHAN HIDAYAT]  
- **NIM**   : [250202950]  
- **Kelas** : [1-IKRA]

---

## Tujuan
Tuliskan tujuan praktikum minggu ini.  
Mengidentifikasi empat kondisi penyebab deadlock Mahasiswa mampu mengenali dan menjelaskan empat kondisi dasar yang menyebabkan deadlock terjadi, yaitu:

Mutual Exclusion

Hold and Wait

No Preemption

Circular Wait

Menjelaskan mekanisme sinkronisasi menggunakan semaphore atau monitor Mahasiswa memahami bagaimana semaphore dan monitor digunakan untuk mengontrol akses ke sumber daya bersama sehingga deadlock dapat dicegah.

Menganalisis dan memberikan solusi untuk kasus deadlock Mahasiswa dapat menganalisis penyebab deadlock pada suatu program dan merancang solusi sinkronisasi yang efektif untuk menghilangkan atau mencegah deadlock.

Berkolaborasi dalam tim untuk menyusun laporan analisis Mahasiswa bekerja sama dalam kelompok untuk melakukan eksperimen, berdiskusi, dan menyusun laporan hasil analisis secara komprehensif

---

## Dasar Teori
1.Sinkronisasi Proses Proses yang berjalan secara bersamaan (concurrent) harus disinkronkan agar tidak saling mengganggu saat mengakses sumber daya bersama. Tanpa sinkronisasi, dapat terjadi race condition dan deadlock.

2.Deadlock dan Empat Kondisinya Deadlock adalah kondisi di mana proses saling menunggu tanpa akhir. Deadlock hanya terjadi jika empat kondisi tercapai secara bersamaan:

Mutual Exclusion

Hold and Wait

No Preemption

Circular Wait

3.Semaphore sebagai Mekanisme Sinkronisasi Semaphore digunakan untuk mengatur jumlah proses yang dapat mengakses sumber daya. Dengan operasi wait() dan signal(), semaphore mencegah proses masuk critical section bersamaan dan dapat digunakan untuk mencegah deadlock.

4.Dining Philosophers Problem sebagai Model Deadlock Masalah ini menggambarkan bagaimana proses (filosof) dapat saling menunggu sumber daya (garpu) hingga terjadi deadlock. Ini digunakan sebagai studi kasus utama untuk memahami konflik akses sumber daya.

5.Pencegahan Deadlock dengan Aturan Akses Deadlock dapat dihindari dengan mengubah pola akses sumber daya, misalnya dengan membatasi jumlah proses yang boleh mengakses (semaphore), atau mengubah urutan pengambilan sumber daya sehingga circular wait tidak terbentuk.

---

## Langkah Praktikum
1. Langkah-langkah yang dilakukan.  
2. Perintah yang dijalankan.  
3. File dan kode yang dibuat.  
4. Commit message yang digunakan.

---

## Kode / Perintah
Persiapan Tim

Bentuk kelompok beranggotakan 3–4 orang.
Tentukan ketua dan pembagian tugas (analisis, implementasi, dokumentasi).
Eksperimen 1 – Simulasi Dining Philosophers (Deadlock Version)

Implementasikan versi sederhana dari masalah Dining Philosophers tanpa mekanisme pencegahan deadlock.
Contoh pseudocode:
while true:
  think()
  pick_left_fork()
  pick_right_fork()
  eat()
  put_left_fork()
  put_right_fork()
Jalankan simulasi atau analisis alur (boleh menggunakan pseudocode atau diagram alur).
Identifikasi kapan dan mengapa deadlock terjadi.
Eksperimen 2 – Versi Fixed (Menggunakan Semaphore / Monitor)

Modifikasi pseudocode agar deadlock tidak terjadi, misalnya:
Menggunakan semaphore (mutex) untuk mengontrol akses.
Membatasi jumlah filosof yang dapat makan bersamaan (max 4).
Mengatur urutan pengambilan garpu (misal, filosof terakhir mengambil secara terbalik).
Analisis hasil modifikasi dan buktikan bahwa deadlock telah dihindari.
Eksperimen 3 – Analisis Deadlock

Jelaskan empat kondisi deadlock dari versi pertama dan bagaimana kondisi tersebut dipecahkan pada versi fixed.

Sajikan hasil analisis dalam tabel seperti contoh berikut:

Kondisi Deadlock	Terjadi di Versi Deadlock	Solusi di Versi Fixed
Mutual Exclusion	Ya (satu garpu hanya satu proses)	Gunakan semaphore untuk kontrol akses
Hold and Wait	Ya	Hindari proses menahan lebih dari satu sumber daya
No Preemption	Ya	Tidak ada mekanisme pelepasan paksa
Circular Wait	Ya	Ubah urutan pengambilan sumber daya
Eksperimen 4 – Dokumentasi

Simpan semua diagram, screenshot simulasi, dan hasil diskusi di:
praktikum/week7-concurrency-deadlock/screenshots/
Tuliskan laporan kelompok di laporan.md (format IMRaD singkat: Pendahuluan, Metode, Hasil, Analisis, Diskusi).
Commit & Push

git add .
git commit -m "Minggu 7 - Sinkronisasi Proses & Deadlock"
git push origin main
forks = [threading.Lock() for _ in range(5)]

def philosopher(i): left = forks[i] right = forks[(i + 1) % 5]

while True:
    print(f"Philosopher {i} sedang berpikir...")
    time.sleep(1)

    left.acquire()     # Ambil garpu kiri
    print(f"Philosopher {i} mengambil garpu KIRI")

    right.acquire()    # Ambil garpu kanan → bisa menyebabkan deadlock
    print(f"Philosopher {i} mengambil garpu KANAN")

    print(f"Philosopher {i} mulai makan...")
    time.sleep(1)

    left.release()
    right.release()
```
```

---

## Hasil Eksekusi
Sertakan screenshot hasil percobaan atau :
forks = [threading.Lock() for _ in range(5)]

def philosopher(i): left = forks[i] right = forks[(i + 1) % 5]

while True:
    print(f"Philosopher {i} sedang berpikir...")
    time.sleep(1)

    left.acquire()     # Ambil garpu kiri
    print(f"Philosopher {i} mengambil garpu KIRI")

    right.acquire()    # Ambil garpu kanan → bisa menyebabkan deadlock
    print(f"Philosopher {i} mengambil garpu KANAN")

    print(f"Philosopher {i} mulai makan...")
    time.sleep(1)

    left.release()
    right.release()

---

## Analisis

1.Analisis Eksperimen Versi 1 (Tanpa Mekanisme Pencegah Deadlock)
Pada percobaan pertama, semua filsuf bekerja tanpa aturan tambahan — mereka langsung mengambil garpu kiri terlebih dahulu. Dari hasil output, seluruh filsuf memang sukses memegang garpu kiri, tetapi tidak ada satu pun yang berhasil mengambil garpu kanan. Akhirnya, tidak ada proses makan yang terjadi.

Pada titik ini, setiap filsuf terjebak karena garpu yang ia butuhkan sedang digunakan oleh tetangganya. Terbentuklah rantai tunggu seperti berikut:

F0 → menunggu garpu 1
F1 → menunggu garpu 2
F2 → menunggu garpu 3
F3 → menunggu garpu 4
F4 → menunggu garpu 0 (membuat lingkaran lengkap)

Situasi tersebut memenuhi keempat kondisi deadlock menurut Coffman. Yang paling terlihat adalah circular wait, karena kelima filsuf saling menunggu dalam urutan melingkar tanpa jalan keluar.

Tidak ada mekanisme: untuk mengubah urutan pengambilan garpu, membatasi siapa yang boleh makan, atau memaksa pelepasan garpu.

Akibatnya, sistem berhenti total dan tidak satu filsuf pun dapat melanjutkan. Eksperimen ini menunjukkan bahwa desain Dining Philosophers versi dasar secara alami mengarah pada deadlock.

2.Analisis Eksperimen Versi 2 (Semaphore + Urutan Garpu Dibalik) Pada versi kedua, dua metode pencegahan deadlock dimasukkan:

3.Semaphore max_eaters = 4 Hanya empat filsuf yang boleh mencoba makan dalam satu waktu.

4.Filsuf terakhir mengambil garpu dengan urutan terbalik Ia mengambil garpu kanan dulu, baru garpu kiri, untuk memecahkan pola pengambilan sumber daya yang identik.

Setelah modifikasi ini dijalankan, output menunjukkan bahwa:

Proses makan terjadi secara bergantian tanpa kebuntuan. Tidak ada lima filsuf yang menunggu selamanya. Selalu ada filsuf yang berhasil makan dan kemudian melepas garpu.

Dengan maksimum empat filsuf di zona makan, tidak pernah terbentuk kondisi di mana kelima garpu terkunci sekaligus.

Penerapan urutan terbalik pada filsuf terakhir juga menghilangkan pola permintaan resource yang membentuk lingkaran sempurna. Dengan begitu, kondisi circular wait terputus, sehingga deadlock tidak mungkin muncul.

Secara keseluruhan, kedua mekanisme ini terbukti efektif menghilangkan salah satu syarat utama deadlock. Karena kondisi Coffman keempat tidak terpenuhi, maka sistem dapat berjalan bebas deadlock.
---

## Kesimpulan
Deadlock pada Dining Philosophers terjadi karena semua kondisi Coffman terpenuhi, terutama circular wait.

Dengan membatasi akses menggunakan semaphore serta mengubah urutan pengambilan garpu, circular wait dapat dihilangkan.

Versi perbaikan berjalan lebih stabil dan tidak menunjukkan tanda deadlock.

Praktikum ini menunjukkan bahwa pengaturan resource sangat menentukan apakah sistem concurrency aman atau tidak.


---

## Quiz
1.Sebutkan empat kondisi utama penyebab deadlock.
2.Mengapa sinkronisasi diperlukan dalam sistem operasi?
3.Jelaskan perbedaan antara semaphore dan monitor.
3
## jawaban
>>Eksperimen 1 – Versi Deadlock

Pada eksperimen pertama, program menunjukkan bahwa tanpa mekanisme sinkronisasi, para filosof akan saling menunggu garpu yang tidak pernah dilepas. Semua proses berhenti dan tidak ada filosof yang dapat makan.
Kesimpulan: Deadlock terjadi karena semua kondisi deadlock terpenuhi (mutual exclusion, hold and wait, no preemption, circular wait).

>>Eksperimen 2 – Versi Fixed (Dengan Sinkronisasi)

Pada eksperimen kedua, penggunaan semaphore membatasi jumlah filosof yang boleh mengambil garpu secara bersamaan. Hal ini memutus rantai circular wait sehingga proses dapat berjalan dengan lancar.
Kesimpulan: Deadlock berhasil dicegah, dan seluruh filosof dapat makan secara bergantian. Program berjalan stabil dan tidak macet.

>>Eksperimen 3 – Analisis Kondisi Deadlock

Eksperimen ini menunjukkan perbedaan mendasar antara versi deadlock dan versi fixed. Versi deadlock memenuhi semua kondisi penyebab deadlock, sedangkan versi fixed berhasil menghilangkan beberapa di antaranya (terutama hold and wait dan circular wait).
Kesimpulan: Dengan menghilangkan minimal satu kondisi deadlock, sistem dapat mencegah kebuntuan dan memastikan proses berjalan aman serta efisien.
 

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
