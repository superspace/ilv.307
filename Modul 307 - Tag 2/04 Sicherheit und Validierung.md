#  Sicherheit (Filter/Sanitize)

Damit keine falschen oder schädlichen Daten auf dem Server verarbeitet werden, müssen diese erst einer Prüfung unterzogen werden. 

- Unnötige Leerschläge, Tabs etc. entfernen

Mit der Funktion `trim()` werden unnötige Leerschläge entfernt.

- Cross-Site-Scripting (XSS) verhindern

Mit der Funktion `htmlspecialchars()` werden Sonderzeichen  in die entsprechenden HTML-Codes umgewandelt.

https://www.php.net/manual/de/function.htmlspecialchars.php

*SQL-Injections wird in einem späteren Modul behandelt.*

==DEMO: Cross-Site-Scripting==

#  Validierung in PHP

Die clientseitige Validierung durch HTML5 oder JavaScript kann in vielen Fällen umgangen werden. Deshalb ist eine zusätzliche serverseitige Validierung in PHP Pflicht.

Bevor die Daten auf dem Server weiterverarbeitet werden, müssen diese einer inhaltlichen Validierung unterzogen werden.

Zwingende Felder werden mit `empty()` darauf überprüft, ob ein Wert vorhanden ist.

https://www.php.net/manual/de/function.empty.php

Spezielle Formate wie z.B. eine E-Mail-Adresse können über PHP Filter validiert werden:

```php
filter_var($email, FILTER_VALIDATE_EMAIL);
```
https://www.php.net/manual/de/function.filter-var.php

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAzNDk4MjQ2MF19
-->