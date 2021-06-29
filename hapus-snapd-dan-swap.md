###Hapus snapd
Menampilkan aplikasi yg terkait snapd
```
snap list
```
hapus nama package-nya
```
snap remove --purge package-name
```
lanjut, 
```
apt autoremove --purge snapd
```
next, hapus folder2 snap
```
rm -rf ~/snap
sudo rm -rf /snap
sudo rm -rf /var/snap
sudo rm -rf /var/lib/snapd
```
### Hapus /SWAP
menampilkan nilai swappiness
```
cat /proc/sys/vm/swappiness
```
next, set to 10 or 0
```
sysctl vm.swappiness=0
```
next, melihat ukuran partisi swap
```
free -h
```
cek swap yg aktif
```
swapon --show
```
next, disable swap
```
swapoff -a
```
hapus swap.img
```
rm /swap.img
```
edit dengan nano /etc/fstab
beri tanda pagar depannya /swap.img
