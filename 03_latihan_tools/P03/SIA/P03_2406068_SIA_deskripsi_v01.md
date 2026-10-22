### 1. SIA-UC01 — Ajukan KRS

| Elemen | Deskripsi |
| --- | --- |
| **Tujuan** | Menghasilkan pengajuan Kartu Rencana Studi (KRS) yang tersimpan untuk diproses |
| **Aktor utama** | Mahasiswa |
| **Sumber kebutuhan** | SIA-R01 dan SIA-R02 |
| **Pemicu** | Mahasiswa memilih menu atau fungsi pengajuan KRS |
| **Prasyarat** | Mahasiswa telah terautentikasi; periode pengisian KRS aktif |
| **Pascakondisi berhasil** | Pengajuan KRS tersimpan dengan status Menunggu Persetujuan |
| **Pascakondisi gagal** | Tidak ada data pengajuan KRS baru yang tersimpan dalam sistem |
| **Include** | SIA-UC02 — Validasi KRS |
| **Extension point** | Validasi gagal, pada langkah 3; Bukti pengajuan tersedia, pada langkah 5 |
| **Extend** | SIA-UC03 — Unduh bukti pengajuan SIA jika [mahasiswa memilih unduh bukti] |

---

### 2. SIA-UC02 — Validasi KRS

| Elemen | Deskripsi |
| --- | --- |
| **Tujuan** | Memastikan daftar mata kuliah yang dipilih mahasiswa memenuhi aturan akademik |
| **Aktor utama** | Sistem |
| **Sumber kebutuhan** | SIA-R02 |
| **Pemicu** | Sistem dipanggil oleh use case Ajukan KRS saat pengajuan diproses |
| **Prasyarat** | Data mata kuliah dan batas SKS mahasiswa tersedia di sistem |
| **Pascakondisi berhasil** | Pengajuan KRS tervalidasi dan siap untuk diproses ke tahap persetujuan |
| **Pascakondisi gagal** | Sistem menampilkan pesan kesalahan dan pengajuan KRS dibatalkan |
| **Include** | - |
| **Extension point** | - |
| **Extend** | - |

---

### 3. SIA-UC03 — Unduh Bukti Pengajuan KRS

| Elemen | Deskripsi |
| --- | --- |
| **Tujuan** | Menghasilkan dan mengunduh berkas bukti pengajuan KRS dalam format dokumen |
| **Aktor utama** | Mahasiswa |
| **Sumber kebutuhan** | SIA-R03 |
| **Pemicu** | Mahasiswa memilih tombol atau menu unduh bukti pengajuan KRS |
| **Prasyarat** | Mahasiswa telah menyelesaikan pengajuan KRS dan bukti pengajuan telah tersedia |
| **Pascakondisi berhasil** | Berkas bukti pengajuan KRS berhasil terunduh ke perangkat mahasiswa |
| **Pascakondisi gagal** | Berkas bukti pengajuan KRS gagal diunduh |
| **Include** | - |
| **Extension point** | - |
| **Extend** | - |

---

### 4. SIA-UC04 — Proses Keputusan KRS

| Elemen | Deskripsi |
| --- | --- |
| **Tujuan** | Menentukan dan menyimpan hasil keputusan (disetujui atau ditolak) atas pengajuan KRS |
| **Aktor utama** | Dosen Wali |
| **Sumber kebutuhan** | SIA-R04 |
| **Pemicu** | Dosen memilih data pengajuan KRS mahasiswa yang akan diproses |
| **Prasyarat** | Dosen telah terautentikasi; terdapat pengajuan KRS mahasiswa dengan status Menunggu Persetujuan |
| **Pascakondisi berhasil** | Status pengajuan KRS diperbarui menjadi Disetujui atau Ditolak (dilengkapi alasan penolakan jika ditolak) |
| **Pascakondisi gagal** | Status pengajuan KRS tidak berubah |
| **Include** | - |
| **Extension point** | - |
| **Extend** | - |