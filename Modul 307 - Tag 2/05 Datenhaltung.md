
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

## JSON und PHP

Mit den Funktionen `json_decode()` und `json_encode()` lassich Daten aus PHP direkt nach und aus dem JSON-Format umwandeln . Dabei werden die Datentypen String, Boolean, Number, Array etc. berücksichtigt.

Daten aus einem JSON-File auslesen und als assoziativen Array (Parameter *assoziative* auf *true*) zurückgeben. 

```php
$meinArray = json_decode($meinJsonString, true);
```

Einen Array aus PHP im JSON-Format ausgeben:

```php
$meinJsonString = json_encode($meinArray);`
```
https://www.php.net/manual/de/function.json-decode.php
https://www.php.net/manual/de/function.json-encode.php

==DEMO: JSON-String zu PHP==

### Datenstruktur

#### Identifikation einzelner Einträge

Um den Zugriff auf einzelne Einträge sicherzustellen, sollte jeder Eintrag eine eindeutige ID aufweisen. In JSON können wir diese ID als Schlüssel für den direkten Zugriff verwenden. Dies vereinfacht es uns, einzelne Einträge zu bearbeiten oder zu löschen. 

```json
{
	"ee716009417de64432d6f7195425ed18": {
		"name": "Urs Beyeler",
		"email" : "dev@superspace.ch"
	},
	"02621484d917cd47eaa125b12249d4b3": {
		"name": "Hans Dampf",
		"email": "hans@dampf.ch"
	}
}
```
Zugriff auf einen spezifischen Eintrag:

```php
$values = json_decode($meinJSONString, true);
$value = $values['ee716009417de64432d6f7195425ed18'];
```

Die ID kann per Hash-Funktion mit einem zufälligen Wert und beispielswiese dem aktuellen Zeitpunkt erstellt werden:

```php
$id = hash('md5', time() .  rand(1000,9999));
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk5NzY5ODI2NywyMDM5ODkxMjU2LDM2MD
cwNDQzXX0=
-->