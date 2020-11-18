 [Modul 307 / Tag 4](/ilv.307/04-modul-307)
 
# MVC Design-Pattern

## Controller

```diff
data/ 
	tasks.json          # Datenhaltung in JSON-File

model/ 
	task.class.php      # Klassenmodell mit Attributen und Methoden,
			    # beinhaltet Logik und Prozesse
store/
	jsonstore.class.php # Schnittstelle zur Datenhaltung
view/
	taskview.class.php  # Task-Liste laden und sortieren
+	create.php          # HTML-Formular für neuen Eintrag
+	list.php            # Auflistung der Einträge

+controller/ 	
+	controller.php      # Steuerung der Anfragen und Aufruf des Models

index.php                   # Ausgabe
```

`view/create.php`

HTML-Formular zur Erfassung neuer Einträge mit Ausgabe möglicher Fehler aus der Validierung.

`view/list.php`

Die Auflistung der erfassten Einträge in HTML.

`controller/controller.php`

Die Steuerung empfängt die Daten aus der Benutzereingabe (`$_POST`), ruft die entsprechende Methode der Klasse auf und gibt gegebenenfalls Fehlermeldungen an die Darstellung zurück.
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzE0MjgwOTgyXX0=
-->