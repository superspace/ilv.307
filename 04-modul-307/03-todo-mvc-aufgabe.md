 [Modul 307 / Tag 3](/ilv.307/03-modul-307)
 
# Aufgabe: ToDo-Verwaltung mit MVC-Pattern

Das prozedurale Script der ToDo-Verwaltung soll nun in ein MVC Design-Pattern überführt werden.

Als Grundlage dient uns folgende Dateistruktur:

```
data/
	tasks.json          // Datenhaltung in JSON-File
model/
	task.class.php      // Klassenmodell mit Attributen und Methoden
public/
	index.php           // Ansicht im Web-Root 
view/
	create.php          // HTML-Formular für neuen Eintrag
	list.php            // Auflistung der Einträge
controller.php              // Steuerung
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
eyJoaXN0b3J5IjpbLTExOTI1OTU1MV19
-->