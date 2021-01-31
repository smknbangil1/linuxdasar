# Cara Backup database (export)
```bash
mysqldump -u root -p namadb > nama-file-backupnya.sql
```

# Cara Restore Database
```bash
mysql -uroot -p
USE namadatabasenya;
SOURCE /foldernya/namafile-yg-akan-di-import.sql;
```
