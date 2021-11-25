 [Modul 307 / Tag 1](/ilv.307/01-modul-307)

# Debugging mit xDebug
## Visual Studio Code & xDebug installieren
 
- Ein gutes Videotutorial finden Sie hier:
[https://www.youtube.com/watch?v=LNIvugvmCyQ](https://www.youtube.com/watch?v=LNIvugvmCyQ)
<!--[https://ekiwi.de/index.php/198/php-debugging-in-xampp-und-uestudio-einrichten/](https://ekiwi.de/index.php/198/php-debugging-in-xampp-und-uestudio-einrichten/)-->

*Die Anleitung ist für Windows & XAMPP, sollte grundlegend aber auch mit MAMP funktionieren. Der Ablauf ist derselbe.*  

### Download

[https://xdebug.org/files/php_xdebug-3.0.0-8.0-vs16-x86_64.dll](https://xdebug.org/files/php_xdebug-3.0.0-8.0-vs16-x86_64.dll)

- Das dll-file hierhin bewegen: `C:\xampp\php\ext`
- Das dll-file umbenennen: `php_xdebug.dll`

<!-- ### Wizard

[https://xdebug.org/wizard](https://xdebug.org/wizard) -->

### php.ini

Den Abschnitt `[xdebug]` bearbeiten oder erstellen:

```
[xdebug]
xdebug.mode = debug
xdebug.start_with_request = yes
xdebug.idekey = VSCODE
xdebug.client_port = 9003
xdebug.client_host = "127.0.0.1"
xdebug.discover_client_host  = 1
xdebug.log="/tmp/xdebug.log"
xdebug.cli_color = 1
```


### Weitere Nützliche Links:
- xDebug & MAMP: [https://joshbuchea.com/enable-xdebug-in-mamp-for-mac/](https://joshbuchea.com/enable-xdebug-in-mamp-for-mac/)
- xDebug & XAMPP: [http://www.sintesisdigital.com.mx/dashboard/docs/activate-use-xdebug.html](http://www.sintesisdigital.com.mx/dashboard/docs/activate-use-xdebug.html)

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1NDcxMzUwMDgsNzY1ODkxNDU2LC0xMT
Q5MTYwOTM5LDEzNTEzNjM1NjYsNDMzNzUxNzM0XX0=
-->