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
- Genau diese Kombination bietet XMAPP oder MAMP (Kennen Sie schon aus früheren Modulen, wissen aber meistens nicht genau, was es ist.)
  - Hinweis: XAMPP/MAMP ist für die Entwicklung, nicht für Produktivsysteme!

# Arbeitsumgebung
- Labor-PC dient als Entwicklungsumgebung
	- An Stelle des Labor-PC darf auch ein eigenes Device verwendet werden.
- Dokumentations-PC zum Dokumentieren und Recherchieren
- Windows sollte mittlerweile installiert sein: Es empfiehlt sich die automatischen Updates zu deaktivieren!

## Einrichten der Arbeitsumgebung
#### Komponenten
- `XAMPP` oder `MAMP`als "Server" :
	- `XAMPP`: [https://www.apachefriends.org/download.html](https://www.apachefriends.org/download.html)
	- `MAMP`: [https://www.mamp.info/de/downloads/](https://www.mamp.info/de/downloads/)
- Quellcode Editor:
	- `Visual Studio Code`: [https://code.visualstudio.com/](https://code.visualstudio.com/) (empfohlen)
		- Mit Extension `PHP IntelliSense`
	- oder ein anderer nach Wunsch  (kein Support vom Coach)
- Browser nach belieben

#### Arbeitsauftrag
- Selbstständiges Herunterladen und Installieren der Umgebung
- Zielvorgabe: **Im Quellcode Editor ein `Hello World` in PHP programmieren und über `XAMPP`/`MAMP` im Browser anzeigen.**

#### Nachbesprechung
- Wo liegt das Root, und wieso?
- Dateiendungen von PHP-Dateien. Wieso geht es nicht mit `.html`?
- `Hello World` zeigen
- Kurze Einführung in `Visual Studio Code` und `PHP IntelliSense`

# Übungen
- Die Übungen 01 "Erste Schritte mit PHP" und 02 "Kontrollstrukturen, Schleifen, Funktionen" werden nacheinander selbsständig gelöst. (Hilfe untereinander ist erlaubt.)
- Auf Nachschlagewerke verweisen:
	- [https://www.w3schools.com/php/](https://www.w3schools.com/php/)
	- [https://developer.hyvor.com/tutorials/php](https://developer.hyvor.com/tutorials/php)
	- [https://www.php.net/](https://www.php.net/)
- Diese Übungen sollen bis zum Schluss des Tages 1 laufen. Zwischendurch wird das selbstständige Arbeiten nach Gutdünken unterbrochen zwecks:
	- Erklärungen und Erläuterungen zu den Übungen
	- Abhandlung aller folgenden Themen


# PHP Konfiguration & Error Reporting
### php.ini
- Über die php.ini-Datei lässt sich die PHP-Instanz global konfigurieren. Der Speicherort der Datei hängt von der Installation ab.  
- Die aktuellen Einstellungen können die Funktion `phpinfo()` ausgegeben werden.
	- `phpinfo()`erklären/erläutern
- Demo an Hand von `date.timezone`:
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
Die Error Reporting Einstellungen erläutern / deminstrieren.
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

# Debugging
## Visual Studio Code & xDebug
- Was ist `xDebug`?
- Debugging Demo durchführen
- Danach installieren und konfigurieren die Schüler xDebig selbstständig:

### xDebug installieren / konfigurieren
- Gutes Tutorial mit Videoanleitung:
[https://ekiwi.de/index.php/198/php-debugging-in-xampp-und-uestudio-einrichten/](https://ekiwi.de/index.php/198/php-debugging-in-xampp-und-uestudio-einrichten/)
*Die Anleitung ist für Windows & XAMPP, sollte grundlegend aber auch mit MAMP funktionieren. Der Ablauf ist derselbe.*  
- Weitere Nützliche Links:
	- xDebug & MAMP: https://joshbuchea.com/enable-xdebug-in-mamp-for-mac/
	- xDebug & XAMPP: http://www.sintesisdigital.com.mx/dashboard/docs/activate-use-xdebug.html

# Datumsfunktionen
to do...

# Multidimenionale Arrays
- Von `multidimensionale Arrays` spricht man, wenn Arrays als Elemente in eines Arrays gespeichert sind.  Die Arrays sind somit ineinander verschachtelt.
- Damit lassen sich einfach hierarchische Strukturen abbilden.
 
 ### Beispiel
 Ein Flugzeug besteht aus verschiedenen Attributen:
 ```php
 $flugzeug = Array('registrierung' => 'HB-ABC','hersteller' => 'Airbus','Typ' => 'A380');
 ```
 Wir können in einem Array mehrere Flugzeuge speichern, in dem wir die einzelnen Flugzeug-Arrays in einen übergeordneten Array verpacken:
   ```php
 $flugzeuge = Array(
		 Array('registrierung' => 'HB-ABC','hersteller' => 'Airbus','typ' => 'A380'),
		 Array('registrierung' => 'HB-CDE','hersteller' => 'Boeing','typ' => 'B777'),
		 Array('registrierung' => 'HB-ZCD','hersteller' => 'Piper','typ' => 'Archer')
		 );
 ```

Der Zugriff auf ein bestimmtes Element in der mehrdimensionalen Struktur erfolgt durch aneinanderreihen von Indices/Keys:
 ```php
print('Hersteller:' . $flugzeuge[0]['hersteller']);  
//1.Dimension: Flugzeug mit Index 0  -  2.Dimension: Key "hersteller"
```
> Hersteller: Airbus

Für die komplette Ausgabe wird der übergerodnete Array `$flugzeuge` mittels `foreach()` geloopt. Innerhalb des Loops stehen nun die einzelnen Flugzeug-Arrays zur Verfügung, aus welchen die Attribute ausgelesen werden können:
```php
foreach ($flugzeuge  as  $flugzeug)
{
	print("Registrierung: $flugzeug[registrierung]<br>\n");
	print("Hersteller: $flugzeug[hersteller]<br>\n");
	print("Typ: $flugzeug[typ]\n");
	print("----------<br>\n");
}
```

 > Registrierung: HB-ABC  
    Hersteller: Airbus  
    Typ: A380
    ----------
    Registrierung: HB-CDE  
    Hersteller: Boeing  
    Typ: B777
    ----------
    Registrierung: HB-ZCD  
    Hersteller: Piper  
    Typ: Archer
    ----------


Alternativ können durch einen weiteren Loop alle Attribute dynamisch ausgelesen werden:
```php
foreach ($flugzeuge as $flugzeug)
{
        foreach($flugzeug AS $attribut => $wert)
        {
            print("$attribut: $wert<br>\n");
        }
        print("----------<br>\n");
}
```
 > registrierung: HB-ABC  
    hersteller: Airbus  
    typ: A380
    ----------
    registrierung: HB-CDE  
    hersteller: Boeing  
    typ: B777
    ----------
    registrierung: HB-ZCD  
    hersteller: Piper  
    typ: Archer
    ----------
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjg0NjE1MDAsLTIxMjIyODk4OTIsMzQ0OT
Q0ODEzLC00ODMxNDczMTddfQ==
-->