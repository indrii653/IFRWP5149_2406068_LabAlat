<!-- Deskripsi -->
Mahasiswa mengajukan KRS dengan memilih mata kuliah.Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS dan memberikan catatan keputusan.

<!-- Tabel Kebutuhan -->

|  ID   |                             Kebutuhan Tugas                              |
|-------|--------------------------------------------------------------------------|
|SIA-R01|                  Mahasiswa dapat melihat jadwal kuliah                   |
|SIA-R02|               Admin akademik dapat mengelola jadwal kuliah               |
|SIA-R03|                      Mahasiswa dapat mengajukan KRS                      |
|SIA-R04|             Sistem memvalidasi KRS sebagai bagian pengajuan              |
|SIA-R05|Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
|SIA-R06|        Dosen wali dapat memproses persetujuan atau penolakan KRS         |

<!-- Batas Sistem dan Aturan -->
Batas dan asumsi: 
• Pengguna telah terautentikasi. 
• Data mata kuliah, prasyarat, dan jadwal tersedia. 
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan. 
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan. 
• KRS tersimpan belum berarti disetujui. 
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar 
tugas.

<!-- Identifikasi Aktor -->
|ID-Kebutuhan|      Aktor   |            Fungsi            |
|------------|--------------|------------------------------|
|  SIA-R01   |  Mahasiswa   |      Ajukan mata kuliah      |
|  SIA-R02   |  Admin       |akademik Kelola jadwal kuliah |
|  SIA-R03   |  Dosen Wali  |akademik Kelola mata kuliah   |

<!-- Tabel Katalog Use Case -->
|   ID   | Nama       use        case   |           Peran dalam model           |
|--------|------------------------------|---------------------------------------|
|SIA-UC01|Lihat jadwal kuliah           | Fungsi utama Mahasiswa                |
|SIA-UC02|Kelola jadwal kuliah          | Fungsi utama Admin                    |
|SIA-UC03|Ajukan  KRS                   | Fungsi utama Mahasiswa                |
|SIA-UC04|Validasi pengajuan KRS        | Perilaku yang disertakan UC03         |
|SIA-UC05|Unduh    bukti    pengajuan   | Fungsi utama Mahasiswa                |
|SIA-UC06|Proses  keputusan  peminjaman | Tambahan bersyarat pada UC03          |
|SIA-UC07|Proses persetujuan/penolakan  | Fungsi utama Dosen Wali               |

<!-- Relasi Include -->
SIA-UC03 «include» SIA-UC04 
Alasan: pemeriksaan menjadi bagian validasi pengajuan.

<!-- Relasi Extends -->
SIA-UC05 «extend» SIA-UC03 
Extension point: Bukti pengajuan tersedia. 
Kondisi: [mahasiswa memilih cetak]. 
Alasan: pengajuan tetap berhasil tanpa pencetakan.