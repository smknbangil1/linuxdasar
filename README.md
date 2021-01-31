# linuxdasar
dasar-dasar command line di linux
## edit ip/network di centos 7
```bash
nano /etc/sysconfig/network-scripts/ifcfg-eth0
```bash
### Restart service network
```
systemctl restart network
```

## perintah dan pengaturan ssh
[a relative link](README1-SSH.md)

## Transfer File/Folder
```bash
scp -r /foldernya/moodledata/ root@IP_ServerB:/tujuan/moodledata
```
