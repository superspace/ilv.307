# Client-Server-Kommunikation mit PHP

Die Request-Daten eines Serveraufrufes werden in den PHP Superglobals `$_REQUEST`, `$_GET` und `$_POST` als Schlüssel-Wert-Paarte in einem Array abgelegt. Die 

##### POST
Die globale Variable `$_POST` beinhaltet alle Schlüssel-Wert-Paare, die über ein Formular mit `method="post"` übermittelt worden sind.

##### GET
Die globale Variable `$_GET` beinhaltet alle Schlüssel-Wert-Paare, die entweder über ein Formular mit `method="get"` oder direkt über die URL übermittelt worden sind.

##### REQUEST
Die globale Variable `$_REQUEST` beinhaltet alle Schlüssel-Wert-Paare die per POST oder per GET übermittelt worden sind.

*POST und GET können auch kombiniert werden.* 

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNDM5MTQzNjBdfQ==
-->