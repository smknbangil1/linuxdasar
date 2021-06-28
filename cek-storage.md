cek keseluruhan disk
```bash
df -h
```

cek size per directory
```bash
du -sh /* | sort -n -r
```

cek free memory dan swap 
```bash
free -h
```

cek unalocated space
```bash 
fdisk -l /dev/sda
```
perhatikan end pada sda1 dan start pada sda2
jika tidak urut end sda1 dan start sda2 berarti ada space yg hilang (unalocated), 
maka pertisi perlu di resize, 
selengkapnya baca di https://linoxide.com/find-allocated-space-linux/
