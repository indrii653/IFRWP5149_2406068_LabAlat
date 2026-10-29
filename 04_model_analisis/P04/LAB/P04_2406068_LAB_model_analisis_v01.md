| Sumber                                    |           Hubungan           | Tujuan                                                            |
| :---------------------------------------- | :--------------------------: | :---------------------------------------------------------------- |
| **Peminjam**                              |         Association          | LAB-UC01 Lihat Ketersediaan Peralatan                             |
| **Peminjam**                              |         Association          | LAB-UC03 Ajukan Peminjaman                                        |
| **Mahasiswa**                             |         Association          | LAB-UC05 Cetak Bukti Pengajuan _(khusus, tetap dari Pertemuan 3)_ |
| **Mahasiswa**                             | Generalization $\rightarrow$ | Peminjam                                                          |
| **Dosen**                                 | Generalization $\rightarrow$ | Peminjam                                                          |
| **Petugas Laboratorium**                  |         Association          | LAB-UC02 Kelola Data Peralatan                                    |
| **Petugas Laboratorium**                  |         Association          | LAB-UC06 Proses Keputusan Peminjaman                              |
| **Petugas Laboratorium**                  |         Association          | LAB-UC11 Catat Pengembalian Peralatan                             |
| **Kepala Laboratorium**                   |         Association          | LAB-UC07 Lihat Laporan Peminjaman                                 |
| **LAB-UC03 Ajukan Peminjaman**            |          «include»           | LAB-UC04 Periksa Ketersediaan _(tetap dari Pertemuan 3)_          |
| **LAB-UC05 Cetak Bukti Pengajuan**        |           «extend»           | LAB-UC03 Ajukan Peminjaman _(tetap dari Pertemuan 3)_             |
| **LAB-UC08 Tambah Data Peralatan**        | Generalization $\rightarrow$ | LAB-UC02 Kelola Data Peralatan                                    |
| **LAB-UC09 Ubah Data Peralatan**          | Generalization $\rightarrow$ | LAB-UC02 Kelola Data Peralatan                                    |
| **LAB-UC10 Hapus Data Peralatan**         | Generalization $\rightarrow$ | LAB-UC02 Kelola Data Peralatan                                    |
| **LAB-UC11 Catat Pengembalian Peralatan** |          «include»           | LAB-UC12 Periksa Kondisi Peralatan                                |
| **LAB-CO01 (collaboration)**              |  Realization $\rightarrow$   | LAB-UC03 Ajukan Peminjaman                                        |
| **LAB-CO02 (collaboration)**              |  Realization $\rightarrow$   | LAB-UC11 Catat Pengembalian Peralatan                             |
