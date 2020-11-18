 [Modul 307 / Tag 4](/ilv.307/04-modul-307)
 
# MVC Design-Pattern

## Controller

```bash
data/ 
	tasks.json          # Datenhaltung in JSON-File

model/ 
	task.class.php      # Klassenmodell mit Attributen und Methoden,
			    # beinhaltet Logik und Prozesse
store/
	jsonstore.class.php # Schnittstelle zur Datenhaltung
view/
	taskview.class.php  # Task-Liste laden und sortieren
	create.php          # HTML-Formular für neuen Eintrag
	list.php            # Auflistung der Einträge
	
controller.php              # Steuerung der Anfragen und Aufruf 
des Models
index.php                   # Ausgabe
```


`data/tasks.json`

Das JSON-File zur Speicherung der Daten.

`model/task.class.php`

Das File `task.class.php` enthält die Klasse `Task` mit den benötigten Attributen und Methoden zur Eingabe-Verarbeitung Validierung und Speicherung. 

![MVC](/ilv.307/assets/images/uml-class-task.png)

`public/index.php`

index.php befindet sich im Web-Root und ist die einzige Seite, die im Browser aufgerufen wird. Anhand eines Parameters `view` lässt sich die Ansicht steuern.

`view/create.php`

HTML-Formular zur Erfassung neuer Einträge mit Ausgabe möglicher Fehler aus der Validierung.

`view/list.php`

Die Auflistung der erfassten Einträge in HTML.

`controller.php`

Die Steuerung empfängt die Daten aus der Benutzereingabe (`$_POST`), ruft die entsprechende Methode der Klasse auf und gibt gegebenenfalls Fehlermeldungen an die Darstellung zurück.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNjA1OTIwNDNdfQ==
-->