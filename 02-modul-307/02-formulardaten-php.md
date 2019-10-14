# Formulardaten in PHP

Die Request-Daten eines Serveraufrufes werden in den PHP Superglobals `$_REQUEST`, `$_GET` und `$_POST` als Schlüssel-Wert-Paare in einem Array abgelegt. 

#### POST
Die globale Variable `$_POST` beinhaltet alle Schlüssel-Wert-Paare, die über ein Formular mit `method="post"` übermittelt worden sind.

#### GET
Die globale Variable `$_GET` beinhaltet alle Schlüssel-Wert-Paare, die entweder über ein Formular mit `method="get"` oder direkt als URL-Parameter übermittelt worden sind.

#### REQUEST
Die globale Variable `$_REQUEST` beinhaltet alle Schlüssel-Wert-Paare die per POST oder per GET übermittelt worden sind.

### Werte auslesen
Die Werte werden über den Schlüssel ausgelesen. Vorerst sollte immer überprüft werden, ob der Schlüssel existiert. 

Mit dem *Ternary Operator* können wir überprüfen, ob der Schlüssel existiert und den enthaltenen oder den Default-Wert direkt einer Variablen zuweisen: 

```php
$realname = isset($_POST['realname']) ? $_POST['realname'] : ''; 
```
Dies entspricht :

```php
$realname = '';
if (isset($_POST['realname']))
	$realname = $_POST['realname'];
```

==DEMO: Ausgabe von $_POST und $_GET==

[Übung Formulardaten](/ilv.307/02-modul-307/02.1-formulardaten-uebung)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzYxNjE0NTg2XX0=
-->