 [Modul 307 / Tag 2](/ilv.307/02-modul-307)
 
# Datenhaltung

In diesem Modul behandeln wir ausschliesslich **Datei-basierte Datenhaltung**. *Die Anbindung an eine Datenbank wird in einem späteren Modul behandelt.*

## Formate

### JSON
JSON (*JavaScript Object Notation*) hat sich in der Webenwticklung als Quasi-Standard für Speicherung und Austausch von strukturierten Daten etabliert. Die Syntax entspricht der Programmiersprache *JavaScript* und erlaubt die Abbildung von diversen Datentypen wie String, Number, Boolean, Array Object etc. Mehrere Einträge werden immer in einem Gefäss (Array oder Object) gefasst.

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

[wiki.selfhtml.org/wiki/JSON](https://wiki.selfhtml.org/wiki/JSON)

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
[function.json-decode](https://www.php.net/manual/de/function.json-decode.php)

[function.json-encode](https://www.php.net/manual/de/function.json-encode.php)

> *DEMO*: JSON-String zu PHP
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTExNDM4NDc1NCwzMDg2MDM2ODAsLTExMz
E1ODk4NzgsMTk5NzY5ODI2N119
-->