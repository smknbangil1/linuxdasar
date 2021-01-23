# linux dasar
dasar-dasar command line di linux
## SSH
### Melihat log ssh
```bash
tail -20 /var/log/auth.log | grep ssh
```
### Melihat yg berhasil login
```bash
last
```
### Memeriksa seluruh user yg berhasil login, kita, atau ada peretas?
```bash
lastlog
```
### Melihat yg gagal masuk
```bash
lastb -n 20
```
