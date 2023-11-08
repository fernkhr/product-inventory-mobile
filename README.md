# TUGAS 7

### 1. STATELESS & STATEFUL WIDGET
- **Stateless Widget**:
1. Tidak memiliki keadaan internal yang dapat berubah
2. Widget ini tidak dapat merubah data atau tampilannya setelah dibuat
- **Stateful Widget**:
1. Memiliki keadaan internal yang bisa berubah seiring waktu
2. Widget ini dapat merespons perubahan data dan memperbarui tampilannya sesuai keadaan tersebut

### 2. WIDGET
1. **MyHomePage**: Menampilkan judul aplikasi di app bar dan daftar item inventory dalam bentuk grid
2. **InventoryCard**: Menampilkan card yang berisi ikon dan teks yang merepresentasikan item inventory tertentu
3. **Scaffold**: Membungkus keseluruhan halaman dengan struktur dasar aplikasi, termasuk app bar dan body
4. **AppBar**: Menampilkan app bar di bagian atas halaman dengan judul "BeSeller"
5. **Padding**: Menambahkan padding (ruang kosong) di sekitar konten yang ada
6. **Column**: Menampilkan children (widget lain) secara vertikal, seperti judul "Your Inventory" dan GridView
7. **Material**: Mengatur tampilan latar belakang kartu dengan warna indigo
8. **InkWell**: Membuat area yang responsif terhadap sentuhan user di atas card dan menampilkan pesan SnackBar saat card diklik
9. **Container**: Membungkus ikon dan teks dalam kartu item inventory
10. **MyApp**: Menyediakan konfigurasi dasar aplikasi, seperti judul dan tema

### 3. IMPLEMENTASI CHECKLIST
1. Pada berkas menu.dart, `import 'package:flutter/material.dart'`
2. Mengubah bagian `({super.key, required this.title})` menjadi `({Key? key}) : super(key: key)`
3. Di bawah kode MyHomePage({Key? key}) : super(key: key), menambahkan icon untuk Lihat Item, Tambah Item, dan Logout pada class `final List<InventoryItem> items`
4. Menambahkan widget-widget yang dibutuhkan termasuk `SnackBar` dengan `Text("Kamu telah menekan tombol ${item.name}!")`
