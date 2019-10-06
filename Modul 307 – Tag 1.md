### Tag 1

# PHP Einführung

## Setup PHP

### php.ini
Über die php.ini-Datei lässt sich die PHP-Instanz global konfigurieren. Der Speicherort der Datei hängt von der Installation ab.  
```ini
memory_limit   = 128MB
display_errors = off
error_logs     = /Applications/MAMP/logs/php_error.log
```
Die aktuellen Einstellungen können über die Funktion `phpinfo()` ausgegeben werden.

Die Einstellungen können aber auch direkt im PHP-Script angepasst werden:

```php
ini_set('display_errors', true);
```

==Demo Fehlermeldung==

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

###
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY2MDI2MDY4MCwtMjQ3MzE3NTU0XX0=
-->