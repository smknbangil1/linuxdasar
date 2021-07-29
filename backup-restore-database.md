# Cara Backup database (export)
```bash
mysqldump -u root -p namadb > nama-file-backupnya.sql
```

# extract .sql.gz
```bash 
gzip -d example.sql.gz
```

# Cara Restore Database
```bash
mysql -uroot -p
USE namadatabasenya;
SOURCE /foldernya/namafile-yg-akan-di-import.sql;
```
# Cara membuat database moodle
```bash
CREATE DATABASE moodledb CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```
# Cara melihat user dan hak akses ke database
```bash
SELECT db, host, user FROM mysql.db;
```
# Install NGINX - PHP7.4 FPM - MariaDB
```bash
apt-get install nginx-full -y
```
```bash
apt-get install mariadb-server mariadb-client -y
```
```bash
apt-get install python3.8 -y
```
```bash
apt-get install graphviz aspell ghostscript clamav php7.4-fpm php7.4-common php7.4-mysql php7.4-gmp php7.4-curl php7.4-intl php7.4-mbstring php7.4-soap php7.4-xmlrpc php7.4-gd php7.4-xml php7.4-cli php7.4-zip php7.4-pspell php7.4-gd php7.4-ldap -y
```
