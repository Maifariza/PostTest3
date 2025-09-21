 # POST-TEST 3 PRAKTIKUM PBO

### **Disusun Oleh**

===========================================================================

                                                                

**Maifariza Aulia Dyas - 2409116032**                         

                                                                

   Sistem Informasi - A - 2024                                  

                                                               

===========================================================================
 
### **SISTEM MANAJEMEN KOLEKSI BARANG ANTIK**

  <h1 align="center">AntikAesthetic 🔎⏳</h1>
    
 -------------------------------------------------------------------------
 

   AntikAesthetic adalah program sederhana berbasis Java untuk menyimpan dan mengelola koleksi barang antik. Tujuannya adalah agar data dapat lebih tertata, mudah dicari, dan tidak ribet.  Dengan aplikasi ini, pencatatan yang biasanya dilakukan secara manual kini bisa dilakukan otomatis sehingga dapat mengurangi salah input.
   
   Program ini menyediakan fitur utama berupa CRUD (Create, Read, Update, Delete) dan pencarian. Melalui fitur tersebut, pengguna dapat menambahkan barang baru ke dalam koleksi, menampilkan seluruh data barang dalam bentuk tabel, memperbarui data tertentu berdasarkan ID, hingga menghapus barang yang sudah tidak diperlukan. 
   
   Fitur pencarian tersedia untuk memudahkan pengguna menemukan barang tertentu hanya dengan memasukkan kata kunci, baik dari nama, kategori, maupun asal barang. 

   Setiap barang antik yang disimpan dalam sistem digambarkan sebagai sebuah objek dengan atribut yang cukup lengkap, mulai dari ID unik, nama barang, kategori, asal, tahun pembuatan, material, kondisi, sumber perolehan, hingga harga perolehan. Seluruh data ini dikelola menggunakan struktur ArrayList, sehingga penyimpanan menjadi lebih fleksibel dan juga memudahkan proses manipulasi data seperti menambah, menampilkan, memperbarui, maupun menghapus.

---


<h1 align="center">Penerapan MVC dan Struktur Packages Program</h1>

1. Package model (Model)
   
    Package ini berisi class Model yang merepresentasikan data barang antik. Class ini memiliki beberapa properti seperti id, nama, kategori, asal, tahun, material, kondisi, sumber, dan hargaPerolehan. Semua properti dibuat dengan access modifier private untuk menjaga prinsip enkapsulasi. Data diakses dan diubah melalui getter dan setter, serta diinisialisasi menggunakan konstruktor. Dengan adanya package ini, semua data barang antik tersimpan rapi dalam bentuk objek.

2. Package service (Controller)

    Package ini berisi class Service yang mengatur logika bisnis program. Semua operasi CRUD (Create, Read, Update, Delete) dijalankan di sini, termasuk juga fitur pencarian data dan validasi input. Controller ini menerima perintah dari View (Main), memprosesnya dengan memanfaatkan data dari Model, lalu mengembalikan hasilnya kembali ke View. Dengan cara ini, logika program terpusat di satu tempat dan tidak tercampur dengan tampilan.

3. Package main (View)
   
    Package ini berisi class Main yang menjadi entry point program. Class ini berfungsi sebagai View, yaitu menampilkan menu utama kepada user dan menerima input pilihan. Setelah menerima input, class ini akan memanggil fungsi yang sesuai di Controller (Service). Karena hanya berfungsi sebagai antarmuka pengguna, class ini tidak diwajibkan memiliki properti maupun konstruktor.

---

<h1 align="center">Struktur Program</h1>

Program yang saya buat terdiri dari beberapa kelas yang memiliki peran masing-masing.

 1. Main.java

    <img width="884" height="781" alt="image" src="https://github.com/user-attachments/assets/bee6126e-1e87-47b4-a9c0-98c24bf7d428" />

    Kelas utama berada di Main.java yang berfungsi sebagai entry point program. Di dalam kelas ini terdapat menu interaktif yang digunakan pengguna untuk menambah, menampilkan,       memperbarui, menghapus, dan mencari data barang. Main juga menjadi penghubung langsung dengan kelas Service agar logika program dapat berjalan sesuai perintah pengguna.
    
 2. Service.java

    <img width="898" height="776" alt="image" src="https://github.com/user-attachments/assets/1b5ee6ad-eade-4cf9-b527-030031e069bc" />

     Selanjutnya ada kelas Service.java yang berada di dalam package service. Kelas ini bertanggung jawab mengelola data barang, mulai dari penyimpanan, penambahan data baru, penghapusan, pencarian, hingga menampilkan seluruh data. Dengan kata lain, Service menjadi pusat logika bisnis program.

 3. Model (Barang)

    <img width="890" height="835" alt="image" src="https://github.com/user-attachments/assets/dd39d5fd-9bd1-40a3-8d4c-f9c375420642" />

    Untuk data inti, saya menggunakan package model. Di dalamnya terdapat kelas Barang sebagai superclass. Kelas Barang menyimpan semua properti umum, seperti id, nama, kategori, asal, tahun, material, kondisi, sumber, dan hargaPerolehan. Semua atribut dibuat private dan diakses menggunakan getter dan setter, sehingga konsep encapsulation diterapkan.

    Dari kelas Barang, saya membuat dua subclass, yaitu barangLelang dan barangWarisan. Kedua kelas ini mewarisi semua atribut yang ada di kelas Barang, tapi punya cara kerja khusus karena saya menggunakan method overriding pada method infoSingkat().

    a. Subclass barangLelang.java

    <img width="844" height="238" alt="image" src="https://github.com/user-attachments/assets/b9e21e51-9eff-483b-ad47-62ac99cd50f1" />

     Saat objek barangLelang dipanggil, program akan menambahkan keterangan “tipe: LELANG”.

    b. Subclass baranngWarisan.java

    <img width="851" height="232" alt="image" src="https://github.com/user-attachments/assets/5ee49e4e-6bf5-406a-ba59-e074cf7199b5" />

    sedangkan jika objek barangWarisan dipanggil, keterangan yang muncul adalah “tipe: WARISAN”.

  
---
# Penjelasan Program

1. Encapsulation (Getter dan Setter)

   <img width="720" height="213" alt="image" src="https://github.com/user-attachments/assets/77820a0e-344b-4313-b538-48370a406f25" />

   Pada kelas Barang, semua atribut didefinisikan dengan akses private, misalnya private int id, private String nama, dan seterusnya. Kata kunci private berarti variabel tersebut tidak bisa dipanggil atau diubah secara langsung dari luar kelas. Jadi, kalau ada kode di luar kelas Barang yang mencoba mengakses barang.id secara langsung, program akan error.
   
   Untuk memberikan akses, dibuatlah getter dan setter:
   
   <img width="784" height="590" alt="image" src="https://github.com/user-attachments/assets/e0ee01a3-cb76-4500-97b3-067164af989c" />

   Getter adalah method yang dipakai untuk membaca nilai, contohnya getNama() untuk mengambil nilai dari atribut nama. Sedangkan setter adalah method yang dipakai untuk mengubah nilai, contohnya setNama(String nama) untuk mengganti nama barang.

   Dengan cara ini, kita bisa menambahkan aturan validasi di dalam setter, misalnya memastikan harga tidak boleh bernilai negatif, atau tahun tidak boleh lebih kecil dari nol. Jadi, selain melindungi data, encapsulation juga memberi kendali penuh kepada programmer agar data yang masuk tetap konsisten dan valid.

2. Inheritance

   a. Superclass Barang

      <img width="302" height="220" alt="image" src="https://github.com/user-attachments/assets/bc702751-1b07-4461-8873-70d7208efe00" />

      Kelas Barang adalah superclass atau kelas induk. Di kelas ini didefinisikan semua atribut umum yang dimiliki setiap barang, misalnya id, nama, kategori, asal, tahun, material, kondisi, sumber, dan hargaPerolehan.

      Selain atribut, kelas Barang juga memiliki method infoSingkat() yang berfungsi untuk menampilkan data inti barang. Karena sifatnya umum, semua subclass bisa langsung mewarisi atribut maupun method yang ada di Barang tanpa perlu menuliskannya lagi. Dengan begitu, Barang menjadi pondasi utama yang menyediakan struktur dasar bagi objek-objek turunan.

   b. Subclass barangLelang
   
   <img width="797" height="91" alt="image" src="https://github.com/user-attachments/assets/70262dc2-52d3-444b-b156-ad38d36e5468" />
   
   Kelas BarangLelang adalah turunan dari Barang. Karena mewarisi semua atribut dari kelas induk, BarangLelang otomatis punya id, nama, kategori, hingga infoSingkat().
   
   Bedanya, di kelas ini method infoSingkat() ditimpa (override). Hasilnya, setiap kali objek BarangLelang dipanggil, output akan menambahkan label khusus "tipe: LELANG". Dengan begitu, meskipun struktur datanya sama dengan Barang, objek lelang bisa dibedakan lewat tampilan informasinya.

   c. Subclass barangWarisan
   
   <img width="790" height="97" alt="image" src="https://github.com/user-attachments/assets/7dcba63a-9c14-49de-bf6d-9cd574d74c46" />

   Kelas BarangWarisan juga merupakan turunan dari Barang. Sama seperti BarangLelang, ia mewarisi seluruh atribut dan method dari kelas induk.

   Di dalamnya, method infoSingkat() juga dioverride, tetapi dengan tambahan label "tipe: WARISAN". Jadi, ketika objek BarangWarisan dipanggil, output akan menampilkan keterangan berbeda, menegaskan bahwa barang tersebut berasal dari warisan.


# Penjelasan Overriding

1. Method di Super Class (Barang)

   <img width="546" height="109" alt="image" src="https://github.com/user-attachments/assets/cc08e63a-4e99-4d41-8144-7deb76c4344c" />

     Method infoSingkat() didefinisikan dalam kelas Barang sebagai method default untuk menampilkan informasi barang. Isi yang ditampilkan meliputi id, nama, kategori, asal, dan sumber. Method ini akan dipanggil secara langsung ketika objek berasal dari kelas Barang tanpa perubahan tambahan.
   
2. Overriding di Subclass barangLelang

   <img width="485" height="85" alt="image" src="https://github.com/user-attachments/assets/7b7f4335-57bc-4df1-9c4e-7886d30f67d9" />

   Pada kelas BarangLelang, method infoSingkat() dioverride. Keyword @Override menunjukkan bahwa method ini menimpa method yang sama dari superclass. Bedanya, pada subclass ini ditambahkan dengan keterangan khusus "tipe: LELANG". Dengan begitu, saat objek BarangLelang dipanggil, hasil yang ditampilkan berbeda dari superclass.
   
3. Overriding di Subclass barangWarisan

   <img width="493" height="101" alt="image" src="https://github.com/user-attachments/assets/3655f49a-f67a-4e64-becb-f648cbb85620" />

   Hal serupa juga dilakukan di kelas BarangWarisan. Method infoSingkat() ditimpa (override) sehingga output memiliki tambahan "tipe: WARISAN". Perbedaan ini menunjukkan bahwa meskipun kedua subclass mewarisi atribut dan method dari kelas induk, masing-masing dapat menyesuaikan perilakunya sendiri.

---

<h1 align="center">Alur Program AntikAesthetic</h1>

  Saat pertama kali dijalankan, sistem langsung menyiapkan data awal berupa beberapa barang antik yang otomatis dimasukkan ke dalam koleksi. Setelah itu, pengguna langsung dibawa ke menu utama yang berisi enam pilihan, yaitu tambah barang, tampilkan barang, perbarui barang, hapus barang, cari barang, dan keluar program.

1. **Mulai dan tampilkan menu utama**
   
   Setiap kali program berjalan, menu utama akan selalu pertama ditampilkan. Dari sini, pengguna bisa memilih fitur apa yang ingin dilakukan dengan memasukkan angka 1 hingga 6.

2. **Tambah barang baru**
   
   Jika pengguna memilih menu tambah barang, sistem akan meminta data barang satu per satu, seperti nama, kategori, asal, tahun pembuatan, material, kondisi, sumber perolehan, dan harga.

   Input yang diberikan akan divalidasi agar sesuai dengan aturan (misalnya tahun harus angka antara 0–3000, harga tidak boleh negatif). Setelah semua data diisi dengan benar, barang akan ditambahkan ke koleksi dan ditampilkan pesan bahwa barang berhasil disimpan.

3. **Menampilkan semua barang**
   
   Pada menu ini, sistem menampilkan daftar lengkap koleksi barang antik dalam bentuk tabel yang rapi. Jika belum ada barang sama sekali, program akan memberi tahu bahwa data masih kosong.

4. **Memperbarui barang berdasarkan ID**
   
   Jika pengguna ingin mengubah data barang, pengguna diminta memasukkan ID barang yang ada. Jika ID ditemukan, setiap data lama akan ditampilkan dalam tanda kurung, dan pengguna bisa memilih untuk menggantinya atau membiarkannya tetap sama.

   Misalnya, jika kolom nama dikosongkan, maka nama lama akan tetap dipakai. Setelah diperbarui, program menegaskan bahwa perubahan berhasil dilakukan.

5. **Menghapus barang berdasarkan ID**
   
   Di menu hapus, pengguna juga perlu memasukkan ID barang. Kalau ID tidak ditemukan, akan muncul pesan bahwa data tidak ada. Jika ID valid, sistem meminta konfirmasi terlebih dahulu. Hanya jika pengguna mengetik “y”, barang benar-benar akan dihapus dari koleksi.

6. **Mencari barang**
   
   Fitur ini memungkinkan pengguna mencari barang dengan kata kunci tertentu, baik berdasarkan nama, kategori, atau asal barang. Jika kata kunci ditemukan pada salah satu barang, hasilnya ditampilkan dalam tabel.

   Jika tidak ada yang cocok, program menampilkan pesan bahwa tidak ada hasil yang sesuai.

7. **Keluar dari program**
   
   Menu terakhir digunakan untuk menutup aplikasi. Sebelum benar-benar keluar, sistem meminta konfirmasi. Kalau pengguna mengetik “y”, program berhenti dengan ucapan terima kasih. Jika tidak, pengguna kembali ke menu utama.
   
---

<h1 align="center">⏳ Menu Utama AntikAesthetic ⏳</h1>

<img width="776" height="289" alt="image" src="https://github.com/user-attachments/assets/02a777fb-04ed-43ee-86f5-5dc2a5298a12" />


Pada awal program, pengguna akan langsung diarahkan ke Menu Utama AntikAesthetic. Menu ini berfungsi sebagai menu utama untuk mengakses seluruh fitur yang tersedia. Terdapat enam pilihan utama yang bisa dipilih sesuai kebutuhan.

   1. Tambah Barang, digunakan untuk menambahkan data barang antik baru dengan mengisi atribut seperti nama, kategori, asal, tahun pembuatan, material, kondisi, sumber perolehan, dan harga perolehan.

   2. Tampilkan Semua Barang, menampilkan seluruh koleksi barang antik yang tersimpan dalam bentuk tabel agar mudah dibaca.

   3. Perbarui Barang, memungkinkan pengguna memperbarui data barang tertentu dengan memasukkan ID barang yang ingin diubah.

   4. Hapus Barang, menghapus data barang dari koleksi berdasarkan ID barang yang ingin dihapus.

   5. Cari Barang, memudahkan pengguna menemukan data barang tertentu dengan memasukkan kata kunci pencarian seperti nama/kategori/asal barang yang ingin dicari.
   
   6. Keluar, digunakan untuk menutup program. Sebelum benar-benar keluar, sistem akan menampilkan konfirmasi agar tidak terjadi kesalahan.

--------------------------------------------------------------------------------------------------------------------------------------------------------------

# **Jika memilih opsi 1 maka akan diarahkan ke Tambah Barang**

<img width="511" height="298" alt="image" src="https://github.com/user-attachments/assets/aa1a8488-abe5-4c84-ab4b-7b8d7d74c4f1" />


Ketika pengguna memilih opsi 1 pada menu utama, maka program akan diarahkan ke fitur Tambah Barang. Pada bagian ini, sistem meminta pengguna untuk mengisi informasi detail mengenai barang antik baru yang ingin ditambahkan ke dalam koleksi AntikAesthetic.

Pada saat pengguna memilih opsi 1 (Tambah Barang), program akan menampilkan form input untuk menambahkan data barang antik baru ke dalam sistem.

Seperti pada gambar, user ingin menambah barang Patung Ganesha. Setelah itu, user diminta mengisi informasi lainnya secara berurutan, mulai dari kategori barang, asal, tahun pembuatan, material, kondisi barang, sumber perolehan, hingga harga perolehan.


### Pemberitahuan Jika Berhasil

<img width="464" height="54" alt="image" src="https://github.com/user-attachments/assets/408ffe7a-4b6d-4956-aac9-fba391e5e2f2" />


Setelah semua data selesai diisi, sistem akan otomatis memberikan ID unik untuk barang baru tersebut dan menambahkannya ke dalam koleksi. 

### Pengecekan Ulang

<img width="1297" height="689" alt="image" src="https://github.com/user-attachments/assets/82f5227c-8690-4b8f-b3ba-f64144f73549" />


Lalu untuk melihat daftar koleksi yang telah ditambahkan, user ketik 2. Di bagian akhir, program menampilkan instruksi “Tekan Enter untuk melanjutkan…” agar pengguna bisa kembali ke menu utama dan melanjutkan ke fitur lain sesuai kebutuhan.

## **Validasi Input**

### Jika Inputan tahun tidak di antara 0 - 3000

<img width="427" height="147" alt="image" src="https://github.com/user-attachments/assets/ebe9b2cd-cf44-43ca-8d08-f4a26d90b381" />

Ketika pengguna mengisi data barang baru, setiap input akan dicek dulu apakah sesuai dengan aturan yang berlaku. Pada contoh di atas, pengguna mencoba memasukkan tahun pembuatan dengan nilai -200. Karena sistem sudah diberi aturan bahwa tahun harus berada dalam rentang 0 sampai 3000, maka input tersebut dianggap tidak valid.

Program kemudian langsung menampilkan pesan peringatan “Harus di antara 0 dan 3000.”. Setelah itu, pengguna diminta kembali untuk mengisi nilai tahun yang benar. 

### Jika Inputan Kosng

<img width="292" height="97" alt="Screenshot 2025-09-08 162201" src="https://github.com/user-attachments/assets/9363c488-0979-4736-81bd-35b5cea66035" />

Apabila pengguna mencoba menambahkan barang baru namun tidak mengisi data pada kolom yang diminta, maka program akan menampilkan pesan peringatan. 

Misalnya, ketika pengguna menekan Enter tanpa mengetikkan nama barang, sistem akan menampilkan pesan “Input tidak boleh kosong”.

--------------------------------------------------------------------------------------------------------------------------------------------------------------

# **Jika memilih opsi 2 maka akan diarahkan ke Tampilkan Barang**

<img width="1279" height="629" alt="image" src="https://github.com/user-attachments/assets/baebb6d6-729f-4a91-a8e5-9ddef25e8309" />


  Jika pengguna memilih opsi 2 pada menu utama, maka program akan diarahkan ke fitur Tampilkan Semua Barang. Pada bagian ini, sistem akan menampilkan seluruh koleksi barang dari AntikAesthetic yang sudah tersimpan dalam database program. Data ditampilkan dalam bentuk tabel agar lebih terstruktur dan mudah dipahami.

  Tabel tersebut berisi informasi penting yang dibagi ke dalam beberapa kolom, yaitu ID, Nama, Kategori, Asal, Tahun Pembuatan, Material, Kondisi, Sumber Perolehan, dan Harga. Setiap baris dalam tabel mewakili satu objek barang antik, sementara ID berfungsi sebagai penanda unik sehingga data dapat dengan mudah diidentifikasi saat ingin diperbarui atau dihapus.

  Melalui tampilan ini, pengguna dapat dengan mudah melihat keseluruhan koleksi barang antik hanya dalam satu layar. Format tabel yang rapi membuat data lebih mudah dibaca, dipahami, dan dibandingkan antar barang. Hal ini membantu pengguna ketika ingin menilai kondisi, harga, atau asal-usul barang tertentu secara cepat.

  Setelah seluruh data ditampilkan, program akan memberikan instruksi kepada pengguna untuk menekan tombol Enter agar dapat melanjutkan ke langkah berikutnya. Tekanan tombol Enter ini akan mengembalikan pengguna ke menu utama, sehingga pengguna dapat memilih kembali menu yang lain sesuai kebutuhan, misalnya menambah barang, memperbarui, menghapus, atau keluar dari program.
  
--------------------------------------------------------------------------------------------------------------------------------------------------------------

# **Jika memilih opsi 3 maka akan diarahkan ke Update Barang**


<img width="552" height="311" alt="Screenshot 2025-09-08 134932" src="https://github.com/user-attachments/assets/e332eafe-cdc4-4199-9ef0-b3d102827924" />

Ketika pengguna memilih opsi 3 pada menu utama, maka program akan diarahkan ke fitur Update Barang.

<img width="608" height="375" alt="image" src="https://github.com/user-attachments/assets/8403e627-b6ea-4a12-a71d-640c33f34931" />


Pada bagian ini, sistem meminta pengguna untuk memasukkan ID dari barang yang ingin diperbarui. ID ini digunakan sebagai penanda unik setiap barang dalam koleksi.

Setelah ID dimasukkan, program akan menampilkan form dengan data lama sebagai referensi. Pengguna dapat mengosongkan input (menekan Enter) jika ingin mempertahankan nilai lama, atau mengetikkan data baru untuk mengganti informasi.

Program akan menampilkan data lama seperti nama barang, kategori, asal, tahun pembuatan, material, kondisi, sumber perolehan, dan harga. Pengguna bisa mengubah salah satu atau beberapa data. Seperti pada gambar diatas, pengguna ingin memperbarui data pada barang dengan ID 1 (Vas Dinasti Ming). Namun, ia hanya ingin merubah data kondisi pada ID 1 saja yang tadinya kondisi "Rusak" menjadi "Baik". Setelah menekan Enter, program akan menyimpan perubahan tersebut dan menampilkan pesan “Data ID 1 berhasil diperbarui” yang menandakan bahwa perubahan data sudah berhasil dilakukan.

### Pengecekan Ulang

<img width="1057" height="517" alt="image" src="https://github.com/user-attachments/assets/965531cc-8cb4-417c-8cf0-92d5ff813f4e" />


Setelah memperbarui data, pilih menu 2 (Tampilkan Semua Barang) untuk mengecek hasilnya. Daftar koleksi akan menampilkan informasi terbaru—termasuk perubahan pada nama, kategori, kondisi, dan kolom lainnya sehingga pengguna bisa memastikan update yang telah dilakukan sebelumnya sudah tersimpan dengan benar.

## **Validasi Input**

### Jika Input ID yang tidak terdaftar

<img width="1023" height="687" alt="image" src="https://github.com/user-attachments/assets/129d39d7-6b7d-4912-92a7-78627e0f3129" />

Apabila pengguna memasukkan ID yang tidak ada di dalam koleksi, maka program akan memberikan pesan peringatan seperti pada gambar diatas. 

Pesan ini berfungsi sebagai validasi agar pengguna mengetahui bahwa ID yang dimasukkan salah atau tidak tersedia.

### Jika Input huruf

<img width="1021" height="680" alt="image" src="https://github.com/user-attachments/assets/c3e9e9bb-d86a-430b-9ca2-e378fdee1def" />


Saat pengguna mencoba mengetik "iya" di kolom ID, program menolak input tersebut dan menampilkan peringatan “Harus berupa angka".

--------------------------------------------------------------------------------------------------------------------------------------------------------------
 
# **Jika memilih opsi 4 maka akan diarahkan ke Hapus Barang**

<img width="336" height="138" alt="Screenshot 2025-09-08 133604" src="https://github.com/user-attachments/assets/90911f05-750a-45dc-865a-bf06fb226e9f" />

etika pengguna mengetik angka 4 pada menu utama, sistem akan langsung mengarahkan ke fitur Hapus Barang. Pada tahap ini, program meminta pengguna untuk memasukkan ID barang yang ingin dihapus. ID ini berfungsi sebagai identitas unik setiap data, sehingga sistem tahu data mana yang dituju.

Setelah ID dimasukkan, sistem akan melakukan pengecekan apakah ID tersebut benar-benar ada di dalam daftar koleksi barang atau tidak. Jika ID ditemukan, sistem tidak akan langsung menghapus data barangnya, melainkan akan memberikan konfirmasi tambahan berupa pertanyaan "Yakin hapus ID... (y/n)?". Konfirmasi ini dibuat untuk menghindari kesalahan pengguna, misalnya jika tanpa sengaja salah mengetik ID.

### Jika Input "n"

<img width="326" height="192" alt="Screenshot 2025-09-08 133622" src="https://github.com/user-attachments/assets/46f0c34a-7f09-476b-a2ca-face02704ecc" />

Apabila pengguna mengetik n, artinya proses penghapusan dibatalkan. Program akan menampilkan pesan bahwa data tidak jadi dihapus, lalu pengguna diminta menekan Enter untuk kembali ke menu utama. Dengan begitu, data tetap aman dan tidak berubah sedikit pun.

### Jika Input "y"

<img width="359" height="168" alt="Screenshot 2025-09-08 133649" src="https://github.com/user-attachments/assets/70f77aae-ba2d-493c-9a63-7b00666220d7" />

Sebaliknya, jika pengguna mengetik y, maka sistem akan benar-benar menghapus data dengan ID yang tadi dimasukkan. Setelah itu, muncul pesan bahwa data berhasil dihapus. Sama seperti sebelumnya, pengguna kemudian menekan Enter untuk kembali ke menu utama.

## **Validasi Input**

### Jika Input ID yang tidak terdaftar

<img width="329" height="130" alt="Screenshot 2025-09-08 133959" src="https://github.com/user-attachments/assets/280c8281-eecf-4156-ba4f-b9b1d97c000b" />

Jika ID tidak terdaftar, sistem menampilkan “Data dengan ID .. tidak ditemukan.”. 

### Jika Input ID selain angka


<img width="334" height="183" alt="Screenshot 2025-09-08 134318" src="https://github.com/user-attachments/assets/c5db5fce-efd5-487f-a161-bdeacda6c84b" />

Jika yang dimasukkan bukan berupa angka tapi huruf, sistem menolak dengan pesan “Harus berupa angka”. Setelah itu, tekan Enter untuk kembali ke menu utama.


--------------------------------------------------------------------------------------------------------------------------------------------------------------

# **Jika memilih opsi 5 maka akan diarahkan ke Cari Barang**

<img width="344" height="71" alt="Screenshot 2025-09-09 151206" src="https://github.com/user-attachments/assets/b4a9184a-472e-4655-a79b-e7dfdfc68fd1" />

Fitur ini dipakai untuk menemukan data dengan cepat. Cukup ketik kata kunci di kolom input, lalu sistem akan mencari yang mengandung kata tersebut pada Nama, Kategori, atau Asal. 


### Cari Berdasarkan Nama Barang

<img width="985" height="160" alt="Screenshot 2025-09-08 135635" src="https://github.com/user-attachments/assets/c4ed5f05-4cb8-4bc5-b222-006758a175b3" />

Pengguna ingin mencari barang berdasarkan nama. Pada kolom Kata kunci, pengguna mengetik “Gucci” lalu menekan Enter. Sistem kemudian menampilkan semua barang yang namanya mengandung kata tersebut.



### Cari Berdasarkan Kategori

<img width="982" height="164" alt="Screenshot 2025-09-08 140013" src="https://github.com/user-attachments/assets/1bf6b9e3-8601-4e41-b86a-86120259a3b4" />

Pengguna ingin mencari berdasarkan kategori. Pada kolom Kata kunci, pengguna mengetik “Patung” lalu menekan Enter. Sistem akan menampilkan semua barang dengan kategori yang mengandung kata tersebut.


### Cari Berdsarkan Asal

<img width="983" height="160" alt="Screenshot 2025-09-08 140157" src="https://github.com/user-attachments/assets/fd2e8cac-0609-4615-a806-3ff43b1d94de" />

Pengguna ingin mencari berdasarkan asal barang. Di kolom Kata kunci, pengguna mengetik “Jepang” lalu menekan Enter. Sistem akan menampilkan semua barang yang asalnya dari Jepang.

## **Validasi Input**

### Input Kata Kunci yang tidak terdaftar

<img width="388" height="119" alt="Screenshot 2025-09-08 140255" src="https://github.com/user-attachments/assets/c3013074-2505-4453-ab92-17a4e1cbfbc2" />

Jika pengguna mengetik kata kunci yang tidak cocok dengan data apa pun, sistem akan menampilkan pesan “Oops.. Tidak ada hasil untuk: ...”

### Inputan Kosong

<img width="341" height="113" alt="Screenshot 2025-09-09 094143" src="https://github.com/user-attachments/assets/a0f53bdb-25e3-42ca-841c-effd5c0cdc83" />

Jika kolom Kata kunci dibiarkan kosong, sistem akan menolak dan menampilkan pesan “Input tidak boleh kosong”.

Setelah itu, pengguna akan diminta mengetik ulang sampai mengisi kata kunci yang valid.

--------------------------------------------------------------------------------------------------------------------------------------------------------------

# **Jika memilih opsi 6 maka akan diarahkan Keluar Program AntikAesthetic**


### Jika memilih "y"

<img width="462" height="294" alt="Screenshot 2025-09-09 130258" src="https://github.com/user-attachments/assets/a97dda3e-362e-4a05-ad42-5d8d46a551bd" />

Saat pengguna memilih menu 6 lalu mengetik y pada konfirmasi, maka program akan tertutup dan menampilkan pesan “Terima kasih Telah Menggunakan Program AntikAesthetic!!”.

### Jika memilih "n"

<img width="469" height="283" alt="Screenshot 2025-09-09 130223" src="https://github.com/user-attachments/assets/7b4a8cb2-1fb8-4a97-a604-6ede66c4fb95" />

Proses keluar dibatalkan. Program akan menampilkan pesan “<< Kembali ke menu utama AntikAesthetic >>” dan pengguna kembali ke menu utama.

## **Validasi Input**

### Jika memilih selain "y" dan "n"

<img width="470" height="282" alt="Screenshot 2025-09-09 130125" src="https://github.com/user-attachments/assets/85249312-528a-48ab-a541-6b516fda71d6" />

Setelah pengguna memilih menu 6, sistem akan meminta konfirmasi (y/n). Jika yang diketik bukan y atau n (misalnya i), input dianggap tidak valid dan proses keluar dibatalkan. 

Program menampilkan pesan “<< Kembali ke menu utama AntikAesthetic >>” lalu meminta pengguna menekan Enter untuk kembali ke menu utama.

--------------------------------------------------------------------------------------------------------------------------------------------------------------

# **Jika user input selain opsi 1-6. Menginputkan menu menggunakan huruf dan mengosongkan inputan**

**Menginputkan Huruf**

<img width="729" height="332" alt="image" src="https://github.com/user-attachments/assets/e88a4486-3e27-4b5a-b503-c91fade6e99b" />

Apabila pengguna tidak mengetikkan angka 1–6, tetapi justru memasukkan huruf (misalnya hai atau abc), sistem akan langsung menganggap input tersebut tidak valid. Hal ini karena program hanya dirancang untuk menerima input berupa angka sesuai opsi yang tersedia pada menu utama.

Setelah mendeteksi input huruf, program akan menampilkan pesan “Pilihan tidak valid.”. Pesan ini dimaksudkan sebagai peringatan agar pengguna tahu bahwa yang dimasukkan tidak sesuai format yang benar. Setelah itu, program meminta pengguna menekan tombol Enter untuk kembali, lalu menampilkan kembali menu utama. 

Pengguna juga diarahkan untuk memperbaiki kesalahannya dan memasukkan angka yang sesuai dengan daftar pilihan menu.

**Mengosongkan Inputan**

<img width="457" height="254" alt="Screenshot 2025-09-09 125912" src="https://github.com/user-attachments/assets/67ec9884-670c-462b-8dd6-cbb210c67051" />

Jika pengguna tidak mengetikkan apa pun (input kosong) lalu langsung menekan Enter pada saat diminta memilih menu, maka sistem akan membaca input tersebut sebagai tidak valid. Dalam kondisi ini, program tidak akan mengeksekusi perintah apa pun, melainkan langsung menampilkan pesan peringatan dan membawa pengguna kembali ke menu utama. Dengan begitu, alur program tetap aman, tidak terjadi error, dan pengguna diberi kesempatan untuk memilih ulang opsi yang benar.
