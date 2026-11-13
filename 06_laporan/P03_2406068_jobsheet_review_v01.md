Uji konsistensi dilakukan untuk memastikan bahwa diagram *use case* dan deskripsi *use case* memberikan hasil yang sesuai pada setiap kondisi pengajuan KRS.

| No. | Situasi yang Diuji | Hasil Pengujian | Status |
|:---:|---|---|:---:|
| a | Validasi berhasil, mahasiswa tidak mengunduh bukti. | Pengajuan KRS tersimpan dengan status **Menunggu persetujuan dosen wali**. Pengajuan tetap berhasil tanpa mengunduh bukti. | Konsisten |
| b | Validasi gagal. | Sistem menampilkan pesan kegagalan karena data tidak lengkap, prasyarat tidak terpenuhi, atau jadwal bentrok. Pengajuan tidak berhasil disimpan. | Konsisten |
| c | Validasi berhasil, mahasiswa mengunduh bukti. | Pengajuan KRS tersimpan dengan status **Menunggu persetujuan dosen wali**, lalu bukti pengajuan dapat diunduh. | Konsisten |

**Kesimpulan**

Berdasarkan ketiga situasi yang diuji, diagram *use case* dan deskripsi *use case* sudah konsisten. Relasi `«include»` antara *Ajukan KRS* dan *Validasi KRS* menunjukkan bahwa validasi wajib dilakukan dalam proses pengajuan. Sementara itu, relasi `«extend»` antara *Unduh Bukti Pengajuan KRS* dan *Ajukan KRS* menunjukkan bahwa pengunduhan bukti hanya dilakukan apabila mahasiswa memilihnya.

Dengan demikian, pengajuan KRS tetap berhasil jika validasi berhasil meskipun mahasiswa tidak mengunduh bukti. Jika validasi gagal, pengajuan tidak berhasil disimpan. Jika validasi berhasil dan mahasiswa memilih mengunduh bukti, pengajuan disimpan dan bukti dapat diunduh. Pengajuan yang tersimpan juga belum berarti KRS telah disetujui oleh dosen wali.
