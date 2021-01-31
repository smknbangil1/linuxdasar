# linuxdasar
dasar-dasar command line di linux
## edit ip/network di centos 7
```bash
nano /etc/sysconfig/network-scripts/ifcfg-eth0
```
### Restart service network
```bash
systemctl restart network
```

## perintah dan pengaturan ssh
[a relative link](README1-SSH.md)

## Transfer File/Folder
contoh1:
```bash
scp /root/.ssh/id_rsa root@IP_ServerB:/root/.ssh/
scp /root/.ssh/id_dsa root@IP_ServerB:/root/.ssh/
```
contoh transfer file dan mengganti nama file ketika sampai di tujuan
```bash
scp /users/Edward/desktop/scp.zip root@191.162.0.2:/writing/article/howtoscp.zip
```
contoh 2:
```bash
scp -r /foldernya/moodledata/ root@IP_ServerB:/tujuan/moodledata
```
contoh 3, dengan port selian default 22
```bash
scp -P 9922 -r /foldernya/moodledata/ root@IP_ServerB:/tujuan/moodledata
scp -P 2322 /users/Edward/desktop/scp.zip root@191.162.0.2:/writing/article
```
