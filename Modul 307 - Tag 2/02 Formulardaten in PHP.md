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

Mit dem *Ternary Operator* können wir überprüfen, ob der Schlüssel existiert und den Wert

```php
$realname = isset($_POST['realname']) ? $_POST['realname'] : ''; 
```

*POST und GET können auch kombiniert werden.* 

==DEMO: Ausgabe von $_POST und $_GET==

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ2NTQ1NDY3MSwtMTIyNzQ3NTUwMF19
-->