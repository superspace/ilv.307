 [Modul 307 / Tag 2](/ilv.307/02-modul-307)

#  Sicherheit (Filter/Sanitize)

Damit keine falschen oder schädlichen Daten auf dem Server verarbeitet werden, müssen diese erst einer Prüfung unterzogen werden. 

> *DEMO:* Cross-Site-Scripting

- Mit der Funktion `trim()` werden unnötige Leerschläge entfernt. Dies erleichtert die Validierung von  Pflichtfeldern.

- Mit der Funktion `htmlspecialchars()` werden Sonderzeichen  in die entsprechenden HTML-Codes umgewandelt und verhindert damit *Cross-Site-Scripting*.

[function.htmlspecialchars.php](https://www.php.net/manual/de/function.htmlspecialchars.php)

*SQL-Injections wird in einem späteren Modul behandelt.*

#  Validierung in PHP

Die clientseitige Validierung durch HTML5 oder JavaScript kann in vielen Fällen umgangen werden. Deshalb ist eine zusätzliche serverseitige Validierung in PHP Pflicht.

> *DEMO:* Umgehung der client-seitigen Validierung

Zwingende Felder werden mit `empty()` darauf überprüft, ob ein Wert vorhanden ist.

[function.empty.php](https://www.php.net/manual/de/function.empty.php)

Spezielle Formate wie z.B. eine E-Mail-Adresse können über PHP Filter validiert werden:

```php
filter_var($email, FILTER_VALIDATE_EMAIL);
```
[function.filter-var.php](https://www.php.net/manual/de/function.filter-var.php)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzMyMjY1OCwtNjgyMDYyNjk2XX0=
-->