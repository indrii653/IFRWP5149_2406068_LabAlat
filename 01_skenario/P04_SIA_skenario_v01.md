<!-- Deskripsi -->

Selain mahasiswa, dosen juga meminjam peralatan laboratorium untuk kegiatan praktikum dan penelitian. Mahasiswa dan dosen sama-sama dapat melihat ketersediaan peralatan dan mengajukan peminjaman. Petugas laboratorium mengelola data peralatan: menambah peralatan baru, mengubah data peralatan, dan menghapus data peralatan yang tidak lagi dipakai. Setelah peminjaman disetujui dan alat diambil, petugas mencatat pengembalian peralatan. Pada saat mencatat pengembalian, petugas memeriksa dan mencatat kondisi peralatan.

<!-- Tabel Aktor  -->

| Aktor                    | Kedudukan                                    | Tujuan terhadap Sistem                                                                                                                         |
| :----------------------- | :------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------- |
| **Peminjam**             | Umum (_general_), baru pada Pertemuan 4      | Peran umum bagi peminjam peralatan. Mewariskan fungsinya kepada Mahasiswa dan Dosen.                                                           |
| **Mahasiswa**            | Khusus dari Peminjam, tetap dari Pertemuan 3 | Melihat ketersediaan dan mengajukan peminjaman (diwarisi dari Peminjam), ditambah mencetak bukti pengajuan sebagai asosiasi khususnya sendiri. |
| **Dosen**                | Khusus dari Peminjam, baru pada Pertemuan 4  | Melihat ketersediaan dan mengajukan peminjaman (diwarisi dari Peminjam).                                                                       |
| **Petugas Laboratorium** | Tetap dari Pertemuan 3                       | Mengelola data peralatan, memproses keputusan peminjaman, dan mencatat pengembalian peralatan.                                                 |
| **Kepala Laboratorium**  | Tetap dari Pertemuan 3                       | Melihat laporan peminjaman.                                                                                                                    |

<!-- Tabel Use Case -->

| ID           | Nama Use Case                | Peran dalam Model                                                                                 | Sumber Kebutuhan |
| :----------- | :--------------------------- | :------------------------------------------------------------------------------------------------ | :--------------- |
| **LAB-UC01** | Lihat Ketersediaan Peralatan | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam                                                | LAB-R01, LAB-R07 |
| **LAB-UC02** | Kelola Data Peralatan        | Tetap dari Pertemuan 3; use case UMUM bagi LAB-UC08, LAB-UC09, LAB-UC10                           | LAB-R02, LAB-R08 |
| **LAB-UC03** | Ajukan Peminjaman            | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam; menyertakan LAB-UC04; direalisasikan LAB-CO01 | LAB-R03, LAB-R07 |
| **LAB-UC04** | Periksa Ketersediaan         | Tetap dari Pertemuan 3; perilaku yang disertakan LAB-UC03                                         | LAB-R03          |
| **LAB-UC05** | Cetak Bukti Pengajuan        | Tetap dari Pertemuan 3; tambahan bersyarat pada LAB-UC03 melalui «extend»                         | LAB-R04          |
| **LAB-UC06** | Proses Keputusan Peminjaman  | Tetap dari Pertemuan 3; fungsi utama petugas                                                      | LAB-R05          |
| **LAB-UC07** | Lihat Laporan Peminjaman     | Tetap dari Pertemuan 3; fungsi utama kepala laboratorium                                          | LAB-R06          |
| **LAB-UC08** | Tambah Data Peralatan        | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02                                              | LAB-R08          |
| **LAB-UC09** | Ubah Data Peralatan          | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02                                              | LAB-R08          |
| **LAB-UC10** | Hapus Data Peralatan         | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02                                              | LAB-R08          |
| **LAB-UC11** | Catat Pengembalian Peralatan | Baru pada Pertemuan 4; fungsi utama petugas; direalisasikan LAB-CO02                              | LAB-R09          |
| **LAB-UC12** | Periksa Kondisi Peralatan    | Baru pada Pertemuan 4; perilaku yang disertakan LAB-UC11                                          | LAB-R10          |

<!-- Generalization Aktor -->

• Mahasiswa adalah bentuk khusus dari Peminjam, dan Dosen adalah bentuk khusus dari Peminjam. Alasan: keduanya berbagi fungsi yang sama, yaitu melihat ketersediaan peralatan dan mengajukan peminjaman.
• Asosiasi ke LAB-UC01 dan LAB-UC03 digambar satu kali, yaitu dari Peminjam. Jangan menggambar garis yang sama dari Mahasiswa dan dari Dosen.
• Asosiasi Mahasiswa ke LAB-UC05 Cetak Bukti Pengajuan tidak ikut dipindahkan dan tidak dihapus, karena fungsi itu khusus mahasiswa. Asosiasi ini menjadi contoh asosiasi tambahan milik aktor khusus. • Periksa arah panah pada gambar: ujung segitiga kosong harus menempel pada Peminjam, bukan pada Mahasiswa dan bukan pada Dosen. Karena Peminjam digambar di tengah, panah Mahasiswa mengarah ke bawah dan panah Dosen mengarah ke atas; keduanya berakhir pada Peminjam.
