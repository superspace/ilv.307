### Tag 1

# PHP Einführung

## Setup PHP

### php.ini
Über die php.ini-Datei lässt sich die PHP-Instanz global konfigurieren. Der Speicherort der Datei hängt von der Installation ab.  
```ini
error_reporting   = E_ALL & ~E_NOTICE
display_errors = off
error_logs     = /Applications/MAMP/logs/php_error.log
```
Die aktuellen Einstellungen können über die Funktion `phpinfo()` ausgegeben werden.

Die Einstellungen können aber auch direkt im PHP-Script angepasst werden:

```php
ini_set('error_reporting', E_ALL);
ini_set('display_errors', true);
```
https://www.php.net/manual/de/function.error-reporting.php

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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MzIzMTkzNTMsMTMxMDU0ODYzNiwxMD
E2OTE5NzU5LDU2MzU4NTc1MiwxMTMwODgxMjE3LDEwNjQxOTUy
MDcsLTI0NzMxNzU1NF19
-->