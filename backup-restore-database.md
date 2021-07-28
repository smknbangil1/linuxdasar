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
