# Mengaktifkan akses remote database MySQL
## agar database bisa diakses dari luar jaringan
### buka/edit file konfigurasi my.ini atau my.cnf
Geser kebawah sampai anda menemukan bagian [mysqld] dan hilangkan simbol komentar (#) di awal kode – kode dibawah:
```bash
bind-address        = 127.0.0.1    
bind-address        = 192.168.8.18
```
Dimana baris pertama adalah setting agar kita bisa masuk ke MySQL dari localhost dan baris kedua menentukan alamat IP servernya.
Setelah itu mari kita berikan hak akses user MySQL agar bisa terhubung dari luar VPSnya:
```bash
GRANT ALL PRIVILEGES ON *.* TO 'nama_user'@'%' IDENTIFIED BY 'kata_sandi' WITH GRANT OPTION;
```
atau
```bash
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'password' WITH GRANT OPTION;
```
lalu flush hak akses database
```bash
FLUSH PRIVILEGES;
```
Setelah itu restart MySQL
```bash
service mysql restart
```
Anda bisa mencoba membuka koneksi ke VPS tersebut dengan eksekusi perintah berikut:
```bash
mysql -u nama_user -h 192.168.8.18 -p
```
Kalau gagal harap anda cek setting firewall di VPS asal dan VPS tujuan, kadang diblokir port default MySQL (3306) kalau tidak dikenali dalam aturannya.
