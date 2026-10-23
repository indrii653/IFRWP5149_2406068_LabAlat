| Aktor | Kedudukan | Tujuan terhadap Sistem |
| --- | --- | --- |
| Peminjam | Umum (general), baru pada Pertemuan 4 | Peran umum bagi peminjam peralatan. Mewariskan fungsinya kepada Mahasiswa dan Dosen. |
| Mahasiswa | Khusus dari Peminjam, tetap dari Pertemuan 3 | Melihat ketersediaan dan mengajukan peminjaman (diwarisi dari Peminjam), ditambah mencetak bukti pengajuan sebagai asosiasi khususnya sendiri. |
| Dosen | Khusus dari Peminjam, baru pada Pertemuan 4 | Melihat ketersediaan dan mengajukan peminjaman (diwarisi dari Peminjam). |
| Petugas Laboratorium | Tetap dari Pertemuan 3 | Mengelola data peralatan, memproses keputusan peminjaman, dan mencatat pengembalian peralatan. |
| Kepala Laboratorium | Tetap dari Pertemuan 3 | Melihat laporan peminjaman. |

<!-- Katalog Use Case -->
|     ID   |          Nama Use Case       |                 Peran dalam Model                  | Sumber Kebutuhan |
|----------|------------------------------|--------------------------------------------------- |------------------|
| LAB-UC01 | Lihat Ketersediaan Peralatan | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam | LAB-R01, LAB-R07 |
| LAB-UC02 | Kelola Data Peralatan        | Tetap dari Pertemuan 3; use case UMUM bagi LAB-UC08, LAB-UC09, LAB-UC10 | LAB-R02, LAB-R08 |
| LAB-UC03 | Ajukan Peminjaman            | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam; menyertakan LAB-UC04; direalisasikan LAB-CO01 | LAB-R03, LAB-R07 |
| LAB-UC04 | Periksa Ketersediaan         | Tetap dari Pertemuan 3; perilaku yang disertakan LAB-UC03 | LAB-R03 |
| LAB-UC05 | Cetak Bukti Pengajuan        | Tetap dari Pertemuan 3; tambahan bersyarat pada LAB-UC03 melalui `«extend»` | LAB-R04 |
| LAB-UC06 | Proses Keputusan Peminjaman  | Tetap dari Pertemuan 3; fungsi utama petugas | LAB-R05 |
| LAB-UC07 | Lihat Laporan Peminjaman     | Tetap dari Pertemuan 3; fungsi utama kepala laboratorium | LAB-R06 |
| LAB-UC08 | Tambah Data Peralatan        | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02 | LAB-R08 |
| LAB-UC09 | Ubah Data Peralatan          | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02 | LAB-R08 |
| LAB-UC10 | Hapus Data Peralatan         | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02 | LAB-R08 |
| LAB-UC11 | Catat Pengembalian Peralatan | Baru pada Pertemuan 4; fungsi utama petugas; direalisasikan LAB-CO02 | LAB-R09 |
| LAB-UC12 | Periksa Kondisi Peralatan    | Baru pada Pertemuan 4; perilaku yang disertakan LAB-UC11 | LAB-R10 |

<!-- Generalization Aktor -->
• Mahasiswa adalah bentuk khusus dari Peminjam, dan Dosen adalah bentuk khusus dari Peminjam. Alasan: keduanya berbagi fungsi yang sama, yaitu melihat ketersediaan peralatan dan mengajukan peminjaman. 
• Asosiasi ke LAB-UC01 dan LAB-UC03 digambar satu kali, yaitu dari Peminjam. Jangan menggambar garis yang sama dari Mahasiswa dan dari Dosen. 
• Asosiasi Mahasiswa ke LAB-UC05 Cetak Bukti Pengajuan tidak ikut dipindahkan dan tidak dihapus, karena fungsi itu khusus mahasiswa. Asosiasi ini menjadi contoh asosiasi tambahan milik aktor khusus. 
• Periksa arah panah pada gambar: ujung segitiga kosong harus menempel pada Peminjam, bukan pada Mahasiswa dan bukan pada Dosen. Karena Peminjam digambar di tengah, panah Mahasiswa mengarah ke bawah dan panah Dosen mengarah ke atas; keduanya berakhir pada Peminjam. 

<!-- generalization use case -->
• LAB-UC08, LAB-UC09, dan LAB-UC10 adalah bentuk khusus dari LAB UC02 Kelola Data Peralatan. Alasan: ketiganya adalah bentuk khusus 
pengelolaan data peralatan. 
• Tuliskan untuk setiap use case khusus satu kalimat perilaku pembedanya. Tambah menghasilkan data peralatan baru. Ubah menghasilkan data peralatan yang berubah. Hapus menghasilkan data peralatan yang terhapus dengan syarat pada aturan studi kasus.


|     ID   | Nama Collaboration (Sama dengan Nama Use Case) |       Use Case yang Direalisasikan     |
|--------- |----------------------------- ------------------|--------------------------------------- |
| LAB-CO01 | Ajukan Peminjaman                              | LAB-UC03: Ajukan Peminjaman            |
| LAB-CO02 | Catat Pengembalian Peralatan                   | LAB-UC11: Catat Pengembalian Peralatan |

|                   Elemen               |              ID dan Nama               |
|--------------------------------------- |--------------------------------------- |
| LAB-UC11: Catat Pengembalian Peralatan | LAB-UC11: Catat Pengembalian Peralatan |
| Elemen                                 | LAB-UC11: Catat Pengembalian Peralatan |
| Sumber kebutuhan                       | LAB-R09 dan LAB-R10                    |
| Tujuan                                 | Pengembalian tercatat dan status peminjaman serta kondisi peralatan terbarui                          |
| Aktor utama                            | Petugas Laboratorium                   |
| Pemicu                                 | Petugas memilih fungsi pencatatan pengembalian dan menentukan peminjaman yang akan dikembalikan       |
| Prasyarat                              | Petugas telah terautentikasi; peminjaman terpilih berstatus Dipinjam                                  |
| Pascakondisi berhasil                  | Pengembalian tercatat dengan tanggal kembali dan kondisi peralatan; status peminjaman menjadi Selesai |
| Pascakondisi gagal                     | Tidak ada pengembalian baru yang tercatat; status peminjaman tidak berubah                            |
| Include                                | LAB-UC12: Periksa Kondisi Peralatan    |
| Collaboration                          | LAB-CO02: Catat Pengembalian Peralatan |

<!-- Alur Utama -->
| Langkah |             Tindakan Petugas                  |                                 Respons Sistem                                     |
|---------|---------------------------------------------- |------------------------------------------------------------------------------------|
|    1    | Memilih peminjaman yang akan dikembalikan     | Menampilkan data peminjaman terpilih dan statusnya                                 |
|    2    | Mengonfirmasi alat yang kembali dan jumlahnya | Menampung konfirmasi petugas                                                       |
|    3    | Tidak ada                                     | Memeriksa status peminjaman harus Dipinjam                                         |
|    4    | Tidak ada                                     | Menjalankan LAB-UC12: memeriksa dan mencatat kondisi peralatan                     |
|    5    | Menyimpan pencatatan pengembalian             | Menyimpan tanggal kembali dan kondisi; mengubah status peminjaman menjadi Selesai  |
|    6    | Melihat konfirmasi                            | Menampilkan ringkasan pengembalian                                                 |

<!-- Alur alternatif atau pengecualian  -->
Menampilkan ringkasan pengembalian 
• A1: Status bukan Dipinjam (pada langkah 3): sistem menolak pencatatan dan menampilkan status peminjaman saat ini. Pascakondisi gagal berlaku; tidak ada data yang disimpan. 
• A2: Kondisi Rusak Ringan atau Rusak Berat (pada langkah 4): sistem tetap menyimpan pencatatan, menandai kondisi tersebut pada data peralatan,dan pengembalian tetap tercatat. Kerusakan tidak otomatis menimbulkan denda pada model ini. 
• A3: Jumlah alat yang kembali tidak sesuai (pada langkah 2): sistem meminta petugas memeriksa kembali isian sebelum penyimpanan; pencatatan tidak disimpan sampai jumlah sesuai atau dikoreksi. 