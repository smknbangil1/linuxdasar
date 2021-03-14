# Cara menggunakan TMUX
Manfaat TMUX:
1. digunakan untuk menjalan proses yg butuh sesi panjang, misalnya backup file besar antar server
2. digunakan untuk multi tasking terminal

intall tmux di centos 7
```bash
yum install -y tmux
```
intall tmux di debian
```bash
apt install -y tmux
```
cek versi tmux
```bash
tmux -V 
```
menjalankan tmux
```bash
tmux new 
atau, diberi nama sesi
tmux new -s [session_name] 
tmux new -s backup-database
```

kembali ke sesi tertentu
```bash
tmux attach -t namasesinya
```
## backup database
```bash
 mysqldump -u root -p namadb_nya > database.sql
```
