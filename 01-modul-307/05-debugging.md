 [Modul 307 / Tag 1](/ilv.307/01-modul-307)

# Debugging mit xDebug
## Visual Studio Code & xDebug installieren
 
- Ein gutes Videotutorial finden Sie hier:
[https://www.youtube.com/watch?v=LNIvugvmCyQ](https://www.youtube.com/watch?v=LNIvugvmCyQ)
<!--[https://ekiwi.de/index.php/198/php-debugging-in-xampp-und-uestudio-einrichten/](https://ekiwi.de/index.php/198/php-debugging-in-xampp-und-uestudio-einrichten/)-->

*Die Anleitung ist für Windows & XAMPP, sollte grundlegend aber auch mit MAMP funktionieren. Der Ablauf ist derselbe.*  
- Weitere Nützliche Links:
	- xDebug & MAMP: [https://joshbuchea.com/enable-xdebug-in-mamp-for-mac/](https://joshbuchea.com/enable-xdebug-in-mamp-for-mac/)
	- xDebug & XAMPP: [http://www.sintesisdigital.com.mx/dashboard/docs/activate-use-xdebug.html](http://www.sintesisdigital.com.mx/dashboard/docs/activate-use-xdebug.html)

### Wizard

[https://xdebug.org/wizard](https://xdebug.org/wizard)

### php.ini

```
[xdebug]
xdebug.remote_enable=1
xdebug.remote_autostart=1
zend_extension = ...
````
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ2NDQ0NDY2LDc2NTg5MTQ1NiwtMTE0OT
E2MDkzOSwxMzUxMzYzNTY2LDQzMzc1MTczNF19
-->