### cli enable maintenance moodle
```bash
php patch/moodle/admin/cli/maintenance.php --enable
```
### setting php untuk moodle 3.9 | 3.10 | 3.11 | keatasnya
```bash
max_input_vars = 5000
```
### cronjob moodle
```bash
* * * * * /usr/bin/php /var/www/moodle/admin/cli/cron.php >/dev/null 2>&1
```
