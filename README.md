# Form Login dengan Menggunakan JPA
Pada pertemuan ke 13 ini merupakan implementasi form login berbasis Java yang menggunakan Java Persistence API (JPA) untuk melakukan proses autentikasi pengguna secara terstruktur dan efisien. Aplikasi ini menghubungkan antarmuka grafis (GUI) berbasis Java Swing dengan database melalui konsep Object Relational Mapping (ORM). Dengan memanfaatkan Entity dan EntityManager, proses verifikasi username dan password dilakukan secara otomatis tanpa penulisan query SQL secara manual.

# Fitur Utama
- Login menggunakan username dan password <br>
- Validasi data ke database menggunakan EntityManager <br>
- Pesan hasil login: ✔ Berhasil → diarahkan ke halaman utama (Dashboard), ❌ Gagal → pesan kesalahan (username/password salah
- 
# Mekanisme Login Menggunakan JPA
Berikut adalah alur proses login: <br>
- Pengguna memasukkan username dan password. <br>
- Aplikasi mengirim permintaan query ke database melalui EntityManager. <br>
- JPA melakukan pencarian data dengan JPQL (Java Persistence Query Language). <br>
- Jika data cocok → Akses diberikan. <br>
- Jika tidak ditemukan → Pesan error ditampilkan.
  
# jFrame Login
•	Desain frame Login <br>
 <img width="368" height="246" alt="image" src="https://github.com/user-attachments/assets/ee652d7b-dfd5-41ec-986d-77feb267a7fd" />
 
•	Code Button Masuk berfungsi sebagai proses login menggunakan JPA. Saat tombol Masuk ditekan, program memeriksa apakah username dan password terisi, lalu mencari data pengguna di database. Jika username tidak ditemukan, muncul pesan “Data tidak ditemukan”; jika password sesuai, tampil pesan “Selamat datang, [username]” dan form Dashboard dibuka; namun jika salah, muncul pesan “Password salah”. Setelah itu, transaksi diselesaikan dan koneksi database ditutup.
 <img width="609" height="384" alt="image" src="https://github.com/user-attachments/assets/35c1dc78-8c03-4972-99fd-a3b29d3249ef" />
 
•	Code Label Lupa password berfungsi untuk membuka form ResetPassword saat label “Lupa Password” diklik. Program akan menampilkan form reset password (r.setVisible(true)) dan menutup form login yang sedang aktif (this.dispose()).
 <img width="554" height="90" alt="image" src="https://github.com/user-attachments/assets/172c57a7-c5ab-42cf-852d-ed19d56e5768" />
 
•	Code Label Daftar berfungsi untuk membuka form Daftar ketika label “Daftar” diklik. Program akan membuat objek form Daftar, menampilkannya di layar, lalu menutup form yang sedang aktif agar dapat langsung melakukan proses pendaftaran akun baru.
 <img width="554" height="94" alt="image" src="https://github.com/user-attachments/assets/62e16d95-bbd1-40e1-aaea-1bb3b5b9e9d2" />
 
# jFrame Reset Password
•	Desain frame ResetPassword <br>
 <img width="375" height="214" alt="image" src="https://github.com/user-attachments/assets/72702551-e532-4697-abf8-201327a125bb" />

•	Code Button Cari berfungsi untuk mencari data pengguna berdasarkan username saat tombol Cari ditekan. Program terlebih dahulu memeriksa apakah kolom username sudah diisi. Jika belum, muncul pesan peringatan. Jika sudah, program menggunakan JPA untuk mencari data pengguna di database. Jika data tidak ditemukan, muncul pesan “Data tidak ditemukan”. Namun jika ditemukan, form akan menampilkan kolom dan tombol untuk mengganti password, mengunci input username agar tidak diubah, dan memfokuskan kursor ke kolom password baru. Setelah itu, transaksi diselesaikan dan koneksi database ditutup.
 <img width="560" height="288" alt="image" src="https://github.com/user-attachments/assets/ae2e9283-f538-46e7-a219-5f94e0f22bb7" />

•	Code Button Simpan berfungsi untuk menyimpan perubahan password saat tombol Simpan ditekan. Program terlebih dahulu memeriksa apakah kolom password sudah diisi. Jika belum, muncul pesan peringatan. Jika sudah, program menggunakan JPA untuk mengambil data pengguna berdasarkan username, kemudian memperbarui password di database dengan nilai baru. Setelah transaksi disimpan (commit), sistem menampilkan pesan “Berhasil diubah”, menutup form saat ini, dan membuka kembali form Login agar pengguna dapat masuk menggunakan password yang baru diperbarui.
 <img width="606" height="336" alt="image" src="https://github.com/user-attachments/assets/600a29c6-6f7d-4ea2-8ad3-c728eb6dc870" />

•	Code Label Back berfungsi untuk kembali ke form Login saat label “Back” diklik. Program membuka objek form Login, menampilkannya di layar, lalu menutup form yang sedang aktif agar dapat kembali ke halaman login dengan mudah.
 <img width="563" height="89" alt="image" src="https://github.com/user-attachments/assets/4877212e-bdd1-431f-87e9-9dd4aa919335" />



