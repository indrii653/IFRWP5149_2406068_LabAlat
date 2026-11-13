Tugas ini MELANJUTKAN kasus SIA Pertemuan 4, bukan kasus baru. Diagram acuannya adalah diagram SIA Pertemuan 4, dan kebutuhan acuannya adalah SIA-R07 sampai SIA-R12 (lihat Jobsheet Pertemuan 4, Tabel 4.6). Keterampilan baru pada tugas ini adalah penulisan skenario, bukan perancangan kasus baru, sehingga mahasiswa tidak menambah use case, aktor, atau kebutuhan di luar diagram SIA Pertemuan 4. Tidak ada contoh jawaban SIA di dalam jobsheet ini. 


| ID       | Nama Use Case             | Aktor              | Catatan Pemetaan |
|----------|---------------------------|--------------------|------------------|
| SIA-UC07 | Lihat Kalender Akademik  | Civitas Akademika  | Ditulis satu kali atas nama Civitas Akademika; berlaku untuk Mahasiswa dan Dosen |
| SIA-UC08 | Input Nilai Mata Kuliah  | Dosen              | Prasyarat: dosen pengampu mata kuliah; alternatif: nilai di luar rentang yang sah ditolak; direalisasikan SIA-CO01 |
| SIA-UC09 | Lihat KHS                | Mahasiswa          | Hanya nilai yang sudah dipublikasikan yang ditampilkan; direalisasikan SIA-CO02 |
| SIA-UC10 | Kelola Data Mahasiswa    | Admin Akademik     | Skenario umum pengelolaan; langkah-langkah bersama yang dirujuk UC11, UC12, dan UC13 |
| SIA-UC11 | Tambah Data Mahasiswa    | Admin Akademik     | Khusus dari UC10; perilaku pembeda: data mahasiswa baru tersimpan |
| SIA-UC12 | Ubah Data Mahasiswa      | Admin Akademik     | Khusus dari UC10; perilaku pembeda: data mahasiswa berubah |
| SIA-UC13 | Hapus Data Mahasiswa     | Admin Akademik     | Khusus dari UC10; perilaku pembeda: data mahasiswa terhapus; syarat: tidak ada data akademik aktif |