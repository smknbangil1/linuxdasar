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
## Upload SSH Key dari Putty
copy pub key dari puttygen, 
paste ke file authorized_keys
```bash
mkdir ~/.ssh
cd ~/.ssh
nano authorized_keys
```
## Upload SSH Key dari Linux PC Local
Generate dulu
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@domain.com"
```
Upload ke server yg mau diremote
```bash
ssh-copy-id root@ip_remote
```

## =========================
## SSH KEY - Disable password on login ===
## =========================
```bash
nano /etc/ssh/sshd_config
```
Cari directive berikut dan modifikasi seperti berikut:
```bash
PasswordAuthentication no
ChallengeResponseAuthentication no
UsePAM no
```
Kemudian simpan dan restart service SSH
```bash
systemctl restart ssh
```
