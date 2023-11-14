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

# TUGAS 8
### 1. IMPLEMENTASI CHECKLIST
- **Membuat halaman formulir tambah item baru**
  1. Membuat berkas baru pada direktori lib dengan nama saleslist_form.dart
  2. Tambahkan widget SalesFormPage yang memungkinkan pengguna untuk memasukkan detail item yang ingin mereka jual
  3. Tambahkan widget Scaffold untuk membuat struktur dasar halaman termasuk AppBar dan body
  4. Membuat variabel baru bernama _formKey untuk ditambahkan ke dalam atribut key milik widget Form
  5. Membuat variabel untuk menyimpan input dari masing-masing field, yaitu _name, _amount, _price, dan _description 
  6. Membuat widget TextFormField di dalam Column yang memungkinkan pengguna memasukkan informasi masing-masing field
- **Mengarahkan pengguna ke halaman form ketika tombol Tambah Item ditekan**
  1. Pada widget InventoryItem pada berkas menu.dart, di bawah kode ScaffoldMessenger, tambahkan kode untuk melakukan navigasi ke MaterialPageRoute yang mencakup SalesFormPage menggunakan Navigator.push
- **Memunculkan data sesuai isi dari formulir dalam sebuah pop-up setelah menekan tombol Save**
  1. Pada saleslist_form.dart, tambahkan tombol save dengan ElevatedButton
  2. Lalu, tambahkan showDialog untuk menampilkan dialog ketika data item berhasil disimpan
- **Membuat sebuah drawer pada aplikasi**
  1. Membuat berkas baru bernama left_drawer.dart
  2. Tambahkan widget LeftDrawer untuk menampilkan drawer kiri pada aplikasi
  3. Tambahkan widget Drawer untuk membuat tampilan drawer yang memiliki ListView yang berisi daftar item
  4. Tambahkan widget DrawerHeader untuk menampilkan judul dan deskripsi singkat aplikasi. Pada tugas ini, saya menambahkan judul "BeSeller" dan deskripsi "Catat list product jualanmu di sini!" di bagian header
  5. Tambahkan widget ListTile untuk menampilkan item-item menu dalam drawer di mana setiap ListTile memiliki leading (ikon), title (judul item), dan onTap (aksi saat item tersebut ditekan)
  6. Tambahkan Routing untuk melakukan navigasi antar halaman dalam aplikasi menggunakan widget Navigator dan MaterialPageRoute
  7. Lalu, masukkan drawer ke halaman menu.dart
  8. Impor untuk menambahkan navigasi ke halaman MyHomePage dan SalesFormPage

### 2. PERBEDAAN Navigator.push() & Navigator.pushReplacement()
1. **Navigator.push()**: Method untuk menambahkan route baru ke dalam stack route yang dikelola oleh Navigator. Method ini menyebabkan route baru ditumpuk di atas rute sebelumnya sehingga pengguna dapat kembali ke rute sebelumnya
   - contoh:
   ```
   Navigator.push(
     context,
     MaterialPageRoute(
       builder: (context) => SalesFormPage(),
     ),
   );
   ```
2. **Navigator.pushReplacement()**: Method untuk mengganti rute saat ini dengan rute baru. Method ini mengganti halaman yang sedang ditampilkan tanpa menambahkannya ke dalam tumpukan rute sehingga tidak mengubah kondisi elemen stack yang berada di bawahnya
   - contoh:
   ```
   onTap: () {
     Navigator.pushReplacement(
       context,
       MaterialPageRoute(
         builder: (context) => MyHomePage(),
       ));
   },
   ```

### 3. LAYOUT WIDGET
1. **Scaffold**: Sebagai kerangka dasar untuk sebuah halaman, menyediakan struktur dasar seperti AppBar, Drawer, dan sebagainya
2. **Container**: Untuk menentukan layout, padding, dan dekorasi
3. **Column & Row**: Untuk menyusun widget secara vertikal (Column) atau horizontal (Row)
4. **Stack**: Untuk menumpuk widget satu di atas yang lain
5. **ListView**: Untuk menampilkan daftar item dalam tata letak bergulir

### 4. ELEMENT INPUT
1. **TextField**: Untuk memungkinkan pengguna memasukkan teks
2. **Checkbox**: Untuk pilihan opsi biner
3. **DropdownButton**: Untuk memilih salah satu opsi dari daftar
4. **DatePicker**: Untuk memilih tanggal

### 5. CLEAN ARCHITECTURE
Clean Architecture adalah pendekatan pengembangan perangkat lunak yang menekankan pemisahan kode menjadi lapisan-lapisan yang berbeda untuk mempermudah pemeliharaan dan pengujian
