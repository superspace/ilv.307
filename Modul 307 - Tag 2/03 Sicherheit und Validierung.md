#  Sicherheit (Filter/Sanitize)

Damit keine falschen oder schädlichen Daten auf dem Server verarbeitet werden, müssen diese erst einer Prüfung unterzogen werden. 

- Mit der Funktion `trim()` werden unnötige Leerschläge entfernt. Dies erleichtert die Validierung von  Pflichtfeldern.

- Mit der Funktion `htmlspecialchars()` werden Sonderzeichen  in die entsprechenden HTML-Codes umgewandelt und verhindert damit *Cross-Site-Scripting*.

https://www.php.net/manual/de/function.htmlspecialchars.php

*SQL-Injections wird in einem späteren Modul behandelt.*

==DEMO: Cross-Site-Scripting==

#  Validierung in PHP

Die clientseitige Validierung durch HTML5 oder JavaScript kann in vielen Fällen umgangen werden. Deshalb ist eine zusätzliche serverseitige Validierung in PHP Pflicht.

Zwingende Felder werden mit `empty()` darauf überprüft, ob ein Wert vorhanden ist.

https://www.php.net/manual/de/function.empty.php

Spezielle Formate wie z.B. eine E-Mail-Adresse können über PHP Filter validiert werden:

```php
filter_var($email, FILTER_VALIDATE_EMAIL);
```
https://www.php.net/manual/de/function.filter-var.php

<!--stackedit_data:
eyJoaXN0b3J5IjpbNDg2ODgwNTU2XX0=
-->