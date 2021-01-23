# linux dasar
dasar-dasar command line di linux
## SSH
### Melihat log ssh
tail -20 /var/log/auth.log | grep ssh

### Melihat yg berhasil login
last

### Memeriksa seluruh user yg berhasil login, kita, atau ada peretas?
lastlog

### Melihat yg gagal masuk
lastb -n 20
