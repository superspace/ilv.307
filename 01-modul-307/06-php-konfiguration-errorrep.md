 [Modul 307 / Tag 1](/ilv.307/01-modul-307)

# PHP Konfiguration & Error Reporting
### php.ini
- Über die php.ini-Datei lässt sich die PHP-Instanz global konfigurieren. Der Speicherort der Datei hängt von der Installation ab.  
- Die aktuellen Einstellungen können mit der Funktion `phpinfo()` ausgegeben werden.
```php
print(date("H.i"));
 ```

 ```ini
date.timezone=America/Costa_Rica
  ```
  [https://www.php.net/manual/de/timezones.php](https://www.php.net/manual/de/timezones.php)

### Alternative 1: Konfiguration im PHP-Script
Die Einstellungen können aber auch direkt im PHP-Script angepasst werden:
```php
ini_set("date.timezone", "Asia/Dubai");
print(date("H.i"));
```

### Alternative 2: Konfiguration in der .htaccess
Eine weitere Möglichkeit ist die Konfiguration auf ebene des Apache Moduls über die .htaccess Datei:
```
php_value "date.timezone" "Africa/Tripoli"
``` 

### Einstellungen zu Error Reporting
in der php.ini:
```ini
error_reporting   = E_ALL & ~E_NOTICE
display_errors = off
error_log="C:\xampp\php\logs\php_error_log.log"
```
im PHP Script:
```php
ini_set('error_reporting', E_ALL & ~E_NOTICE);
ini_set('display_errors', 'On');
```
[https://www.php.net/manual/de/function.error-reporting.php](https://www.php.net/manual/de/function.error-reporting.php)
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTcwODA1NDM5XX0=
-->