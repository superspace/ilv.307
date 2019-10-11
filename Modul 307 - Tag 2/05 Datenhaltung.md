
# Datenhaltung

In diesem Modul behandeln wir ausschliesslich **Datei-basierte Datenhaltung**. *Die Anbindung an eine Datenbank wird in einem späteren Modul behandelt.*

## Formate

### JSON
JSON (*JavaScript Object Notation*) hat sich in der Webenwticklung als qQuasiStandard für Speicherung und Austausch von strukturierten Daten etabliert. Die Syntax entspricht *JavaScript* und erlaubt die Abbildung von diversen Datentypen wie String, Number, Boolean, Array Object etc. Mehrere Einträge werden immer in einem Gefäss (Array oder Object) gefasst.

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

### XML

Historisch immer noch relevant ist das XML-Format (*Extensible Markup Languauge*), mit welchem ebenfalls strukturierte Daten abgebildet werden können.

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

### CSV
Mit CSV (*Comma separated Values*) können tabellarische Informationen erfasst werden. 

### YAML
YAML (*Yet another Markup Language*) eignet sich für die Definition von Schlüssel-Wert-Paaren und wird gerne für Konfigurations-Dateien verwendet.

## Parsen in PHP

### JSON

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
eyJoaXN0b3J5IjpbLTM5NzgwMTMwNSwzNjA3MDQ0M119
-->