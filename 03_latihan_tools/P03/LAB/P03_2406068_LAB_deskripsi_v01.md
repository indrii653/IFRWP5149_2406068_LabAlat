|   Elemen                |  LAB-UC03   — Ajukan peminjaman                       |
|-----------------------------------------------------------------------------------------|
|   Tujuan                |Menghasilkan pengajuan peminjaman yang tersimpan               |
|   Aktor      utama      |Mahasiswa                                                      |
|   Sumber    kebutuhan   |LAB-R03 dan LAB-R04                                            |
|   Pemicu                |Mahasiswa memilih fungsi pengajuan peminjaman                  |
| Prasyarat               |Mahasiswa telah terautentikasi; data peralatan tersedia        |
|Pascakondisi  berhasil   |Pengajuan tersimpan dengan nomor dan status Menunggu keputusan |
|Pascakondisi   gagal     |Tidak ada pengajuan baru yang berhasil tersimpan               |
|  Include                |LAB-UC04- Periksa ketersediaan                                 |
| Extension     point     |Bukti pengajuan tersedia, pada langkah 6                       |
|   Extend                |LAB-UC05-jika [mahasiswa memilih cetak]                        |

<!-- Alur Utama : -->
| Langkah | Tindakan Mahasiswa | Respons Sistem |
| :---: | :--- | :--- |
| **1** | Membuka pengajuan | Menampilkan formulir |
| **2** | Memilih alat, jumlah, rentang waktu, dan tujuan | Menampung isian |
| **3** | Mengirim pengajuan | Memeriksa kelengkapan data |
| **4** | — | — |
| **5** | — | Menjalankan LAB-UC04. Jika tersedia, menyimpan pengajuan dan memberikan nomor |
| **6** | Melihat konfirmasi | Menampilkan nomor dan status; mencapai extension point |
| **7** | Mengakhiri pengajuan | Menutup proses pengajuan |