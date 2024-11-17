Berikut adalah langkah-langkah untuk membuat aturan iptables yang akan **redirect trafik dari IP 141.11.17.243 pada port 9001 ke IP 10.123.0.2 pada port 8291**.

---

### 1. **Tambahkan Aturan NAT untuk Redirect**
Gunakan table `nat` dan chain `PREROUTING` untuk mengarahkan trafik dari IP publik ke IP internal:

```bash
sudo iptables -t nat -A PREROUTING -d 141.11.17.243 -p tcp --dport 9001 -j DNAT --to-destination 10.123.0.2:8291
sudo iptables -t nat -A PREROUTING -d 141.11.17.243 -p udp --dport 9001 -j DNAT --to-destination 10.123.0.2:8291
```

### 2. **Tambahkan Aturan Forwarding**
Agar trafik diteruskan dari mesin Anda ke target internal, Anda perlu mengizinkan forwarding pada table `filter` dan chain `FORWARD`:

```bash
sudo iptables -A FORWARD -p tcp -d 10.123.0.2 --dport 8291 -j ACCEPT
sudo iptables -A FORWARD -p udp -d 10.123.0.2 --dport 8291 -j ACCEPT
```

---

### 3. **Aktifkan IP Forwarding**
Pastikan kernel diatur untuk mengizinkan IP forwarding. Jalankan:

```bash
sudo sysctl -w net.ipv4.ip_forward=1
```

Untuk membuat perubahan ini permanen, tambahkan atau ubah di file `/etc/sysctl.conf`:
```bash
net.ipv4.ip_forward=1
```

Kemudian reload:
```bash
sudo sysctl -p
```

---

### 4. **Simpan Aturan**
Agar aturan tetap berlaku setelah reboot, Anda harus menyimpannya:

#### a. Install iptables-persistent (jika belum)
```bash
sudo apt update
sudo apt install iptables-persistent -y
```

#### b. Simpan Aturan
```bash
sudo netfilter-persistent save
sudo netfilter-persistent reload
```

---

### 5. **Verifikasi Aturan**
Untuk memverifikasi apakah aturan berhasil diterapkan:

#### a. Cek Aturan NAT
```bash
sudo iptables -t nat -L PREROUTING -v -n
```

#### b. Cek Aturan Forwarding
```bash
sudo iptables -L FORWARD -v -n
```

---

### Penjelasan
- **PREROUTING**: Mengubah tujuan (destination) dari paket sebelum routing.
- **DNAT**: Mengarahkan destination address ke IP dan port tertentu.
- **FORWARD**: Mengizinkan paket yang diteruskan dari satu jaringan ke jaringan lain.
- **sysctl**: Mengaktifkan forwarding di tingkat kernel untuk memastikan paket dapat melewati server.

Dengan konfigurasi ini, semua trafik ke IP `141.11.17.243:9001` akan diarahkan ke IP `10.123.0.2:8291`.
