### Tag 1

# PHP Einführung

## Setup PHP

### php.ini
Über die php.ini-Datei können gewisse Einstellungen an der PHP-Instanz global angepasst werden. 
```ini
memory_limit   = 128MB
display_errors = off
error_logs     = /Applications/MAMP/logs/php_error.log
```
Die Einstellungen können aber auch direkt im PHP-Script angepasst werden:

```php
ini_set('display_errors', true);
```

## Editor/IDE

### Visual Studio Code

#### Extensions
- PHP Intellisense
- PHP Debug

#### Debugging
##### XDebug aktivieren
*MAMP*
https://joshbuchea.com/enable-xdebug-in-mamp-for-mac/

*XAMP*
http://www.sintesisdigital.com.mx/dashboard/docs/activate-use-xdebug.html

==Demo Debugging==


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk2MzkwMTEyMCwtMjQ3MzE3NTU0XX0=
-->