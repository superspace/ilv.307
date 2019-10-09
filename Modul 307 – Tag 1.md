
### Tag 1

# Einführung in das Modul

 - Vorstellung Coach / Schüler, Anwesenheitskontrolle
 - ==ACHTUNG: Bis 08:30 an Christa melden!==
 - Start der Installation von Windows 10 auf dem Labor-PC
	 - Hinweis: Es darf auch ein eigenes Device verwendet werden!
 - Vorstellung des Moduls
   - Nach statischen Webseiten im Modul 101 folgen nun dynamische Webseiten
   - Dafür die "Dynamik" verwenden wir PHP
 - Kursprogramm vorstellen:
   - Tag 1: Setup der Umgebung, Grundlagen Webserver mit PHP, erste Schritte mit PHP
   - Tag 2: Repetition HTML Forms, PHP POST/GET, File-Handling und Datenhaltung
   - Tag 3: Objektorientierte Anwendung von PHP, MVC Design Pattern
   - Tag 4: Einbindung von API's, Umsetzung eines Mini-Projekts als praktische Vertiefung
   - Tag 5: MC-Test, Umsetzung eines Mini-Projekts als KNW
 - Das Schreiben einer Kurs-Dokumentation ist freiwillig. Jedoch muss der Code im KNW sauber und professionell Dokumentiert sein!  


# Was ist PHP
## Statik vs Dynamik
- Was ist der Unterschied zwischen einer statischen und einer dynamischen Webseite?
- Was ist der Unterschied zwischen Server- und Client-seitiger Programmierung? (Jeweils Technologie-Beispiele erarbeiten) 
- Vorteile und Nachteile von Client- und Server-seitig.

## Dynamischer Webserver
- Repetition: Wie funktioniert ein reiner Webserver? (aus älteren Modulen bekannt)
- Erweitern durch PHP Engine und DB:
![enter image description here](https://lh3.googleusercontent.com/sZjkvR1uJTgqbkFdIFxy4hADIob1n5qiAnYQtMolOmGNL_h7GFs_jz5auWqbEiE7hlJPMJRXXRST "PHP Webserver")
- Genau diese Kombination bietet XMAP oder MAMP (Kennen Sie schon aus früheren Modulen, wissen aber meistens nicht genau, was es ist.)
  - Hinweis: XAMP/MAMP ist für die Entwicklung, nicht für Produktivsysteme!

# Arbeitsumgebung
- Labor-PC dient als Entwicklungsumgebung
	- An Stelle des Labor-PC darf auch ein eigenes Device verwendet werden.
- Dokumentations-PC zum Dokumentieren und Recherchieren
- Windows sollte mittlerweile installiert sein: Es empfiehlt sich die automatischen Updates zu deaktivieren!

## Einrichten der Arbeitsumgebung
#### Komponenten
- `XAMP` oder `MAMP`als "Server" :
	- `XAMP`: [https://www.apachefriends.org/download.html](https://www.apachefriends.org/download.html)
	- `MAMP`: [https://www.mamp.info/de/downloads/](https://www.mamp.info/de/downloads/)
- Quellcode Editor:
	- `Visual Studio Code`: [https://code.visualstudio.com/](https://code.visualstudio.com/) (empfohlen)
		- Mit Extension `PHP IntelliSense`
	- oder ein anderer nach Wunsch  (kein Support vom Coach)
- Browser nach belieben

#### Arbeitsauftrag
- Selbstständiges Herunterladen und Installieren der Umgebung
- Zielvorgabe: **Im Quellcode Editor ein `Hello World` in PHP programmieren und über `XAMP`/`MAMP` im Browser anzeigen.**

#### Nachbesprechung
- Wo liegt das Root, und wieso?
- Dateiendungen von PHP-Dateien. Wieso geht es nicht mit `.html`?
- `Hello World` zeigen
- Kurze Einführung in `Visual Studio Code` und `PHP IntelliSense`

# Erste Schritte mit PHP
- Die Übung "Erste Schritte mit PHP" selbstständig lösen. (Hilfe untereinander ist erlaubt.)
- Auf Nachschlagewerke verweisen:
	- [https://www.w3schools.com/php/](https://www.w3schools.com/php/)
	- [https://developer.hyvor.com/tutorials/php](https://developer.hyvor.com/tutorials/php)
	- [https://www.php.net/](https://www.php.net/)
- Diese Übung soll bis zum Schluss des Tages 1 laufen. Zwischendurch wird das selbstständige Arbeiten nach Gutdünken unterbrochen zwecks:
	- Erklärungen und Erläuterungen zu den Übungen
	- Abhandlung aller folgenden Themen


# php.ini & Error Reporting
Über die php.ini-Datei lässt sich die PHP-Instanz global konfigurieren. Der Speicherort der Datei hängt von der Installation ab.  
```ini
error_reporting   = E_ALL & ~E_NOTICE
display_errors = off
error_logs     = /Applications/MAMP/logs/php_error.log
```
Die aktuellen Einstellungen können die Funktion `phpinfo()` ausgegeben werden.

Die Einstellungen können aber auch direkt im PHP-Script angepasst werden:

```php
ini_set('error_reporting', E_ALL);
ini_set('display_errors', true);
```
https://www.php.net/manual/de/function.error-reporting.php

==Demo Fehlermeldung==

# Debugging
## XDebug aktivieren
*MAMP*
https://joshbuchea.com/enable-xdebug-in-mamp-for-mac/

*XAMP*
http://www.sintesisdigital.com.mx/dashboard/docs/activate-use-xdebug.html

==Demo Debugging==
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5NjIyOTY0MDksLTE4MzIzMTkzNTMsMT
MxMDU0ODYzNiwxMDE2OTE5NzU5LDU2MzU4NTc1MiwxMTMwODgx
MjE3LDEwNjQxOTUyMDcsLTI0NzMxNzU1NF19
-->