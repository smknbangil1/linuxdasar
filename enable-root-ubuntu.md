cara mengaktifkan root login UBUNTU
```
sudo –i passwd root
```
masukkan passwordnya, setelah itu edit ini...

```
nano /etc/ssh/sshd_config
```
buat baris 
```
PermitRootLogin yes
```
kemudian berilah hak akses 700
```
chmod 700 .ssh
```
restart service ssh
sampai disini ubuntu dah bisa diakses langsung dgn root
supaya aman buat ssh key: id_rsa

Selesai!!!
