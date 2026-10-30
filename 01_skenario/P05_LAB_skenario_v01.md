<!-- Tabel Skenario -->
| ID         | Nama Use Case                    |
|------------|----------------------------------|
| LAB-UC01   | Lihat Ketersediaan Peralatan     |
| LAB-UC02   | Ajukan Peminjaman                |
| LAB-UC03   | Periksa Ketersediaan             |
| LAB-UC04   | Cetak Bukti Pengajuan            |
| LAB-UC05   | Kelola Data Peralatan            |
| LAB-UC06   | Proses Keputusan Peminjaman      |
| LAB-UC07   | Lihat Laporan Peminjaman         |
| LAB-UC09   | Ubah Data Peralatan              |
| LAB-UC10   | Hapus Data Peralatan             |
| LAB-UC11   | Catat Pengembalian Peralatan     |
| LAB-UC12   | Periksa Kondisi Peralatan        |

<!-- Tabel 5.3 Skenario Use Case LAB-UC01 Lihat Ketersediaan Peralatan -->
| Elemen  |                                            Deskripsi                                             |
|---------|--------------------------------------------------------------------------------------------------|
|  Nama   |                          Use Case LAB-UC01 Lihat Ketersediaan Peralatan                          |
|  Aktor  |                           Peminjam (berlaku untuk Mahasiswa dan Dosen)                           |
| Tujuan  |         Peminjam dapat mengetahui peralatan yang tersedia sebelum mengajukan peminjaman.         |
|Deskripsi|Peminjam membuka fungsi ketersediaan dan melihat daftar peralatan beserta status ketersediaannya. |


|Kegiatan|                             Respon Sistem                             |
|--------|-----------------------------------------------------------------------|
|                              Skenario   Normal                                 |
|   1.   |         Peminjam membuka fungsi Lihat Ketersediaan Peralatan.         |
|   2.   |  Sistem menampilkan daftar peralatan beserta status ketersediaannya.  |
|                         Skenario      Alternatif                               |
|   3.   |Tidak ada peralatan yang tersedia pada daftar (cabang dari langkah 2). |
|   4.   |      Sistem menampilkan pesan tidak ada peralatan yang tersedia.      |
Skenario Akhir
Use case selesai jika daftar peralatan beserta status ketersediaannya ditampilkan; jika tidak ada peralatan yang tersedia, use case selesai dengan pesan tersebut.

<!-- Tabel 5.4 Skenario Use Case LAB-UC04 Periksa Ketersediaan  -->
| Elemen  |               Deskripsi                                                                                                  |
|---------|---------------------------------------------------------------------------------- ---------------------------------------|
|  Nama   |     Use Case LAB-UC04 Periksa Ketersediaan                                                                               |
|  Aktor  |     Peminjam (berjalan di dalam LAB-UC03 Ajukan Peminjaman)                                                              |
| Tujuan  |     Ketersediaan peralatan yang dipilih terperiksa sebelum pengajuan disimpan.                                           |
|Deskripsi|Sistem memeriksa jumlah dan status peralatan yang dipilih peminjam dan menyampaikan hasilnya kepada alur pengajuan. Use case ini berjalan di dalam UC03 dan tidak mempunyai interaksi langsung dengan aktor. |

|Kegiatan|                                Respon Sistem                                 |
|--------|------------------------------------------------------------------------------|
|                                 Skenario    Normal                                    |
|   1.   | Alur pengajuan memanggil Periksa Ketersediaan dengan peralatan yang dipilih. |
|   2.   |            Sistem memeriksa jumlah dan status peralatan tersebut.            |
|   3.   |                    Sistem menyatakan peralatan tersedia.                     |
|   4.   |              Alur pengajuan melanjutkan penyimpanan pengajuan.               |
|                                 Skenario  Alternatif                                  |
|   5.   |Peralatan tidak tersedia atau jumlah tidak mencukupi (cabang dari langkah 2). |
|   6.   |  Sistem menyampaikan hasil tidak tersedia sehingga alur pengajuan berhenti.  |
Skenario Akhir
Use case selesai jika hasil pemeriksaan tersampaikan kepada alur pengajuan; hasil tersedia melanjutkan pengajuan, hasil tidak tersedia menghentikan pengajuan.

<!-- Tabel 5.5 Skenario Use Case LAB-UC05 Cetak Bukti Pengajuan -->
| Elemen  | Deskripsi                                                                                                             |
|---------|-----------------------------------------------------------------------------------------------------------    --------|
|  Nama   | Use Case LAB-UC05 Cetak Bukti Pengajuan                                                                               |
|  Aktor  | Mahasiswa (asosiasi khusus)                                                                                           |
| Tujuan  | Bukti pengajuan tercetak sebagai tambahan bersyarat pada pengajuan.                                                   |
|Deskripsi|Mahasiswa yang memilih cetak pada konfirmasi pengajuan menerima bukti pengajuan dengan nomor pengajuan. Cabang ini berlaku dengan condition [mahasiswa memilih cetak] dan extension point Bukti pengajuan tersedia pada LAB-UC03. |
|Kegiatan|                                      Respon Sistem                                      |
|--------|-----------------------------------------------------------------------------------------|
|                                               Skenario Normal                                    |
|   1.   |                Mahasiswa memilih cetak bukti pada konfirmasi pengajuan.                 |
|   2.   |Sistem menampilkan bukti pengajuan dengan nomor pengajuan dan status Menunggu Keputusan. |
|   3.   |                           Mahasiswa mengonfirmasi pencetakan.                           |
|   4.   |                            Sistem mencetak bukti pengajuan.                             |
|                                               Skenario Alternatif                                |
|   5.   |                 Mahasiswa tidak memilih cetak (cabang dari langkah 1).                  |
|   6.   |      Sistem menutup konfirmasi tanpa mencetak bukti dan pengajuan tetap tersimpan.      |
Skenario Akhir
Use case selesai jika bukti pengajuan tercetak; jika mahasiswa tidak memilih cetak, pengajuan tetap selesai tanpa bukti cetak.

<!-- Tabel 5.6 Skenario Use Case LAB-UC02 Kelola Data Peralatan  -->
| Elemen  |          Deskripsi                                                                                       |
|---------|-----------------------------                                                                             |
|  Nama   |Use Case LAB-UC02 Kelola Data Peralatan                                                                   |
|  Aktor  |Petugas Laboratorium                                                                                      |
| Tujuan  |Data peralatan terkelola melalui satu fungsi pengelolaan bersama.                                         |
|Deskripsi|Petugas membuka fungsi pengelolaan data peralatan, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khususnya masing-masing. |
|Kegiatan|                           Respon Sistem                            |
|--------|--------------------------------------------------------------------|
|                               Skenario Normal                               |
|   1.   |           Petugas membuka fungsi Kelola Data Peralatan.            |
|   2.   |             Sistem menampilkan daftar data peralatan.              |
|   3.   |Petugas memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus. |
|   4.   |Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih. |
|   5.   |              Petugas mengisi atau mengonfirmasi data.              |
|   6.   |          Sistem memeriksa kelengkapan dan keabsahan data.          |
|   7.   |                    Petugas menyimpan perubahan.                    |
|   8.   |       Sistem menyimpan perubahan dan menampilkan konfirmasi.       |
|                             Skenario Alternatif                             |
|   9.   |     Data tidak lengkap atau tidak sah (cabang dari langkah 6).     |
|  10.   |  Sistem menolak penyimpanan dan menampilkan pesan kesalahan data.  |
Skenario Akhir
Use case selesai jika perubahan data peralatan tersimpan; jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan.

<!-- Tabel 5.7 Skenario Use Case LAB-UC08 Tambah Data Peralatan  -->
| Elemen  |                                                     Deskripsi                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------|
|  Nama   |                                      Use Case LAB-UC08 Tambah Data Peralatan                                       |
|  Aktor  |                                                Petugas Laboratorium                                                |
| Tujuan  |                Data peralatan baru tersimpan sebagai bentuk khusus dari pengelolaan data peralatan.                |
|Deskripsi|Petugas mengisi data peralatan baru dan menyimpan data tersebut; langkah bersama mengikuti Tabel skenario LAB-UC02. |
|Kegiatan|                          Respon Sistem                          |
|--------|-----------------------------------------------------------------|
|                                   Skenario Normal                        |
|   1.   |          Petugas membuka fungsi Tambah Data Peralatan.          |
|   2.   |        Sistem menampilkan formulir data peralatan baru.         |
|   3.   |              Petugas mengisi data peralatan baru.               |
|   4.   |               Sistem memeriksa kelengkapan data.                |
|   5.   |                     Petugas menyimpan data.                     |
|   6.   |Sistem menyimpan data peralatan baru dan menampilkan konfirmasi. |
|                               Skenario Alternatif                        |
|   7.   |           Data tidak lengkap (cabang dari langkah 4).           |
|   8.   | Sistem menolak penyimpanan dan meminta petugas melengkapi data. |
Skenario Akhir
Use case selesai jika data peralatan baru tersimpan; jika data tidak lengkap, data tidak tersimpan.

<!-- Tabel 5.8 Skenario Use Case LAB-UC09 Ubah Data Peralatan -->
| Elemen  |                                                          Deskripsi                                                           |
|---------|------------------------------------------------------------------------------------------------------------------------------|
|  Nama   |                                            Use Case LAB-UC09 Ubah Data Peralatan                                             |
|  Aktor  |                                                     Petugas Laboratorium                                                     |
| Tujuan  |                        Data peralatan berubah sebagai bentuk khusus dari pengelolaan data peralatan.                         |
|Deskripsi|Petugas memilih data peralatan, mengubah datanya, dan menyimpan perubahan; langkah bersama mengikuti Tabel skenario LAB-UC02. |




