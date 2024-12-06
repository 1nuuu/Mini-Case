# Mini Case - Pengujian Sistem Pemesanan Online FoodFast

## Deskripsi Masalah
FoodFast adalah aplikasi pemesanan online yang memungkinkan pengguna memesan makanan dari berbagai restoran. Sebagai freshgraduate yang berminat bergabung menjadi bagian dari tim Quality Control, saya diminta untuk melakukan pengujian pada fitur utama, yaitu proses pemesanan makanan. 

---

## Test Case
Sebagai lulusan baru, saya telah mempelajari siklus pengembangan perangkat lunak (Software Development Life Cycle - SDLC) termasuk tahap pengujian software seperti functional testing dan user acceptance testing (UAT). Saya percaya bahwa kualitas aplikasi sangat dipengaruhi oleh proses pengujian yang sistematis dan menyeluruh. Berikut adalah daftar test case untuk fitur pemesanan makanan:

| **No** | **Test Case**                   | **Tujuan Pengujian**                                                                 | **Langkah-langkah Uji Coba**                                                                                                         | **Data yang Diperlukan**                               | **Hasil yang Diharapkan**                                      |
|--------|---------------------------------|-------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------|----------------------------------------------------------------|
| 1      | Verifikasi Login                | Memastikan pengguna dapat login dengan kredensial valid.                            | 1. Buka aplikasi FoodFast. <br> 2. Masukkan username dan password valid. <br> 3. Klik "Login".                                      | Username: `testuser` <br> Password: `test123`          | Pengguna berhasil login dan diarahkan ke halaman utama.        |
| 2      | Verifikasi Pencarian Restoran   | Memastikan fitur pencarian restoran berfungsi dengan baik berdasarkan kata kunci.   | 1. Login ke aplikasi. <br> 2. Masukkan nama restoran pada kolom pencarian. <br> 3. Klik "Cari".                                     | Kata kunci: `Nasi Goreng`                                | Restoran sesuai kata kunci muncul di hasil pencarian.          |
| 3      | Verifikasi Penambahan Makanan   | Memastikan pengguna dapat menambahkan makanan ke keranjang.                         | 1. Login ke aplikasi. <br> 2. Cari restoran. <br> 3. Pilih makanan dan klik "Tambah ke Keranjang".                                 | Makanan: `Nasi Goreng`| Makanan berhasil ditambahkan ke keranjang belanja.             |
| 4      | Verifikasi Checkout             | Memastikan pengguna dapat menyelesaikan proses checkout dengan sukses.              | 1. Tambahkan makanan ke keranjang. <br> 2. Klik "Checkout". <br> 3. Pilih metode pembayaran.                                       | Metode: `E-Wallet`                                     | Pesanan berhasil diproses dan notifikasi muncul.               |
| 5      | Verifikasi Notifikasi Pesanan   | Memastikan notifikasi muncul setelah pesanan berhasil dibuat.                       | 1. Selesaikan checkout. <br> 2. Periksa notifikasi di aplikasi.                                                                  | -                                | Notifikasi muncul dengan pesan "Pesanan Anda berhasil dibuat." |

---

## Analisis Potensi Bug

Berikut adalah tiga potensi bug yang mungkin terjadi pada fitur pemesanan makanan:

| **No** | **Deskripsi Bug**                      | **Penyebab**                                                                                 | **Dampak**                                                                              | **Saran Perbaikan**                                                                                  |
|--------|----------------------------------------|---------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| 1      | Login Tidak Berfungsi untuk Kredensial Valid | - Logika validasi login tidak sesuai. <br> - Masalah komunikasi antara aplikasi dan server. | - Pengguna valid tidak dapat login, menyebabkan pengalaman buruk.                     | - Lakukan pengujian unit pada fungsi login. <br> - Periksa koneksi API antara aplikasi dan server.     |
| 2      | Restoran Tidak Muncul di Pencarian      | - Algoritma pencarian tidak mendukung kesalahan ejaan. <br> - Data restoran tidak terindeks dengan baik. | - Pengguna tidak menemukan restoran yang dicari.                                       | - Terapkan algoritma pencarian yang tepat dan benar, misalnya algoritma fuzzy. <br> - Pastikan data restoran terindeks di database dengan benar. |
| 3      | Checkout Gagal Karena Waktu Habis       | - API pembayaran lambat atau terjadi kesalahan teknis.                                      | - Pesanan pengguna gagal diproses, menimbulkan frustrasi.                             | - Tambahkan retry otomatis untuk API pembayaran. <br> - Tampilkan pesan error yang informatif.         |

---
