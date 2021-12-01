 [Modul 307 / Tag 4](/ilv.307/04-modul-307)
 
# Controller

```bash
view/
	create.php          # HTML-Formular für neuen Eintrag
	list.php            # Auflistung der Einträge

controller/ 	
	controller.php      # Steuerung der Anfragen und Aufruf des Models
```

`view/create.php`

HTML-Formular zur Erfassung neuer Einträge mit Ausgabe möglicher Fehler aus der Validierung.

`view/list.php`

Die Auflistung der erfassten Einträge in HTML.

`controller/controller.php`

Die Steuerung empfängt die Daten aus der Benutzereingabe (`$_POST`), ruft die entsprechende Methode der Klasse auf und gibt gegebenenfalls Fehlermeldungen an die Darstellung zurück.
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjM0OTM5Nzk2LC01MTI2Nzc0OTFdfQ==
-->