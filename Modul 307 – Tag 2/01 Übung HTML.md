### Tag 2

# PHP Konkret

## Repetition HTML

### Grundgerüst
```html
<html>
    <head>
        <title>Hello World</title>
        <meta  charset="utf-8">
    </head>
    <body>
        <h1>Hello World</h1>
    </body>
</html>
```
### Formulare
```html
<form action="index.php" method="post">
    <input type="text" name="field1" value="" />
    <button type="submit">Senden</button>
</form>
```
action
: Ziel-URL der Datenübertragung

method
: POST | GET

*POST:* Datenübermittlung an Server

*GET:* Datenanfrage an Server. 

Die Daten können auch als URL-Parameter übergeben werden: 

 `https://www.google.com/search?q=Suchbegriff`

 ist dasselbe wie:
```html
<form action="https://www.google.com/search" method="get">
    <input type="text" name="q" value="Suchbegriff" />
    <button type="submit">Senden</button>
</form>
```

#### Input-Felder
```html
<input type="text" name="field1" value="" />
```

type
: Feld-Typ, z.B. text, email, number, datetime

name 
: Feld-Name, eindeutiger Wert für die Übermittlung des Wertes

value 
: Der Eingabe-Wert, kann auch vorausgefüllt werden

```html
<!-- Text -->
<input type="text" name="field1" value="" />

<!-- Zahl -->
<input type="number" name="field1" value="" min="" max="" />

<!-- E-Mail -->
<input type="email" name="field1" value="" />

<!-- Datum -->
<input type="datetime" name="field1" value="" />

<!-- Unsichtbar -->
<input type="hidden" name="field1" value="" />

<!-- Mehrzeiliger Text -->
<textarea name="field1"></textarea>

<!-- Checkbox -->
<input type="checkbox" name="field1" value="1" />

<!-- Radio-Button -->
<input type="radio" name="field1" value="1" />

<!-- Dropdown -->
<select name="field1">
    <option value="value1">Wert 1</option>
</select>
```
#### Validierung mit HTML5
HTML5 erlaubt die Feld-Validierung im Browser. Die Implementierung der verschiedenen Hersteller variiert jedoch stark, weshalb man sich nicht voll und ganz darauf verlassen darf.
```html
<input type="email" name="field1" value="" required />
```
type
: Bestimmt das zu akzeptierende Format 

required
: Zwingende Eingabe




####  Sicherheit (Filter/Sanitize)

Damit keine falschen oder schädlichen Daten auf dem Server verarbeitet werden, müssen diese erst einer Prüfung unterzogen werden. 

- Unnötige Leerschläge, Tabs etc. entfernen

Mit der Funktion `trim()` werden unnötige Leerschläge entfernt.

- Cross-site Scripting (XSS) verhindern

Mit der Funktion `htmlspecialchars()` werden Sonderzeichen  in die entsprechenden HTML-Codes umgewandelt.

https://www.php.net/manual/de/function.htmlspecialchars.php

*SQL-Injections wird in einem späteren Modul behandelt.*

####  Validierung in PHP

Bevor die Daten auf dem Server weiterverarbeitet werden, müssen diese einer inhaltlichen Validierung unterzogen werden.

Zwingende Felder werden mit `empty()` darauf überprüft, ob ein Wert vorhanden ist.

https://www.php.net/manual/de/function.empty.php

Spezielle Formate wie z.B. eine E-Mail-Adresse kann über PHP Filter validiert werden:

```php
filter_var($email, FILTER_VALIDATE_EMAIL);
```


https://www.php.net/manual/de/function.filter-var.php
    
####   Error-Handling
    
   *TODO*

### File-Handling

#### Lesen und Schreiben von Dateien
Mit PHP können Dateien auf dem Filesystem erstellt, gelesen und modifiziert werden. *VORSICHT* Diese Funktionen sind irreversibel und können auch grossen Schaden auf dem System anrichten!

##### Datei lesen

Mit `readfile()` wird eine Datei gelesen und direkt ausgegeben. Wir haben aber keine Möglichkeit, den Inhalt zu verarbeiten.

Die Funktionen `fopen()` ,  `fread()` und `fclose()` geben uns mehr Kontrolle bei der Verarbeitung der Datei. So können beispielsweise sehr grosse Dateien als Stream gelesen werden und es ist auch möglich, Dateien über ein Netzwerk (z.B. http://) zu öffnen.

https://www.php.net/manual/de/function.fopen.php

Mit  `file_get_contents()` lassen sich Dateien lokal wie auch im Netzwerk öffnen. Die Funktion übergibt den Inhalt der Datei in einen String. Diese Funktion ist ein sogenannte Wrapper, im Hintergrund wird `fopen()` und `fread()` ausgeführt.

https://www.php.net/manual/de/function.file-get-contents.php

##### Datei schreiben

Ach hier können `fopen()`, `fwrite()` und `fclose()` verwendet werden.

Die Funktion `file_put_contents()` ist ein Wrapper für die oben genannten Funktionen und erledigt die Aufgabe mit einem Funktionsaufruf. 

https://www.php.net/manual/de/function.file-put-contents.php

##### Datei erstellen

Neue Dateien können mit der Funktion `fopen()` erzeugt werden.

`file_put_contents()` erstellt automatisch fehlende Dateien.
    
### Datenhaltung

Wir behandeln ausschliesslich datei-basierte Datenhaltung in. Die Anbindung an eine Datenbank wird in einem späteren Modul behandelt.

#### Formate

##### JSON
JSON (JavaScript Object Notation) hat sich als quasi Standard für die Haltung und Übergabe von strukturierten Daten etabliert. Die Syntax entspricht JavaScript und erlaubt die Abbildung von diversen Datentypen wie String, Number, Boolean, Array Object etc. Mehrere Einträge werden immer in einem Gefäss (Array oder Object) gefasst.

*Ein einzelner Eintrag:*

```javascript
"Eintrag A"
```
*Mehrere Einträge:*

```javascript
[
	"Eintrag A",
	"Eintrag B",
	"Eintrag C"
]
```
*Mehrere Einträge mit Schlüssel-Wert-Paaren:*
```javascript
[
	{
		"name": "User A",
		"email": "user-a@email.com",
		"alter": 32
	},
	{
		"name": "User B",
		"email": "user-b@email.com",
		"alter": 27
	}
]
```

https://wiki.selfhtml.org/wiki/JSON

##### XML

Historisch immer noch relevant ist das XML-Format (Extensible Markup Langauge), mit welchem ebenfalls strukturierte Daten abgebildet werden können.

```xml
<?xml version="1.0" encoding="utf-8"?>
<users>
	<user name="User A" email="user-a@email.com">
		<age>32</age>
	</user>
	<user name="User B" email="user-b@email.com">
		<age>27</age>
	</user>
</users>
```

##### CSV
Mit CSV (Comma separated Values) können tabellarische Informationen erfasst werden. 

##### YAML
YAML (Yet another Markup Language) eignet sich für die Definition von Schlüssel-Wert-Paaren und wird gerne für Konfigurations-Daten verwendet.

#### Parsen

##### JSON

Mit den Funktionen `json_decode()` und `json_encode()` können Daten aus PHP direkt in das JSON-Format und andersrum umgewandelt werden. Dabei werden die Datentypen String, Boolean, Number, Array etc. berücksichtigt.

Daten aus einem JSON-File auslesen und als assoziativer Array zurückgeben:

```php
$meinArray = json_decode('relativer/pfad/zum/file.json', true);
```

Einen Array aus PHP im JSON-Format ausgeben:

```php
$meinJsonString = json_encode($meinArray);`
```
https://www.php.net/manual/de/function.json-decode.php
https://www.php.net/manual/de/function.json-encode.php

==Aufgabe zu JSON/PHP==

*Zugriff auf bestimmte Einträge über eine eindeutige Id*

```javascript
{
	"89570283457283485": {
		"name": "Urs Beyeler",
		"email" : "dev@superspace.ch"
	},
	"98708778778978787": {
		"name": "Hans Dampf",
		"email": "hans@dampf.ch"
	}
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY4MDgxNjA0NV19
-->