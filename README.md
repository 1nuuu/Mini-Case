# Jawaban Mini Case - FoodFast  

## Test Case  

| No  | Test Case                     | Tujuan Pengujian                                            | Langkah-langkah Uji Coba                                                                                           | Data yang Diperlukan          | Hasil yang Diharapkan                               |
|-----|-------------------------------|------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|-------------------------------|----------------------------------------------------|
| 1   | Verifikasi Login              | Memastikan pengguna dapat login dengan kredensial valid    | 1. Buka aplikasi FoodFast. <br> 2. Masukkan username dan password valid. <br> 3. Klik tombol "Login".              | Username: `testuser` <br> Password: `password123` | Pengguna berhasil login dan diarahkan ke halaman utama. |
| 2   | Verifikasi Pencarian Restoran | Memastikan pengguna dapat mencari restoran menggunakan kata kunci tertentu | 1. Login ke aplikasi. <br> 2. Ketikkan nama restoran pada kolom pencarian. <br> 3. Klik tombol "Cari".            | Kata kunci: `Pizza House`    | Restoran yang sesuai dengan kata kunci muncul di hasil pencarian. |
| 3   | Verifikasi Penambahan Makanan ke Keranjang | Memastikan pengguna dapat menambahkan makanan ke keranjang belanja | 1. Login ke aplikasi. <br> 2. Cari restoran. <br> 3. Pilih makanan. <br> 4. Klik tombol "Tambahkan ke Keranjang".  | Makanan: `Spaghetti`         | Makanan berhasil ditambahkan ke keranjang belanja. |
| 4   | Verifikasi Proses Checkout    | Memastikan pengguna dapat menyelesaikan proses checkout    | 1. Login ke aplikasi. <br> 2. Tambahkan makanan ke keranjang. <br> 3. Klik "Checkout". <br> 4. Pilih metode pembayaran. <br> 5. Konfirmasi pesanan. | Metode pembayaran: `E-Wallet`| Pesanan berhasil diproses dan pengguna diarahkan ke halaman konfirmasi. |
| 5   | Verifikasi Notifikasi Pesanan | Memastikan pengguna menerima notifikasi setelah pesanan dibuat | 1. Selesaikan proses checkout. <br> 2. Periksa notifikasi di aplikasi.                                            | Tidak ada data tambahan       | Notifikasi pesanan berhasil muncul di aplikasi.    |  

---

## Analisis Potensi Bug  

### Bug 1: Sistem Tidak Mencocokkan Kredensial Login dengan Benar  
- **Penyebab**: Validasi kredensial yang salah di sisi server.  
- **Dampak**: Pengguna yang valid tidak dapat login ke aplikasi.  
- **Saran Perbaikan**:  
  1. Periksa logika validasi pada back-end.  
  2. Gunakan metode hashing dan verifikasi password yang sesuai standar keamanan.  

### Bug 2: Hasil Pencarian Tidak Akurat  
- **Penyebab**: Algoritma pencarian tidak optimal atau data restoran tidak terindeks dengan benar.  
- **Dampak**: Pengguna kesulitan menemukan restoran yang dicari.  
- **Saran Perbaikan**:  
  1. Implementasikan algoritma pencarian fuzzy untuk meningkatkan relevansi hasil pencarian.  
  2. Optimalkan indexing database restoran.  

### Bug 3: Proses Pembayaran Gagal  
- **Penyebab**: API pembayaran lambat atau tidak merespons.  
- **Dampak**: Pesanan gagal diproses, yang dapat menyebabkan ketidakpuasan pengguna.  
- **Saran Perbaikan**:  
  1. Implementasikan mekanisme retry untuk koneksi API.  
  2. Berikan pesan error yang informatif kepada pengguna, seperti "Pembayaran gagal, coba metode lain".  

---  
