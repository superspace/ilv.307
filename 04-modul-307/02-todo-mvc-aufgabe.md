 [Modul 307 / Tag 4](/ilv.307/04-modul-307)
 
# Aufgabe: ToDo-Verwaltung mit MVC-Pattern

Das prozedurale Script der ToDo-Verwaltung soll nun in ein MVC Design-Pattern überführt werden.

Als Grundlage dient uns folgende Dateistruktur:

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
	
index.php                   # Steuerung der Anfragen und Aufruf des Models
```

`data/tasks.json`

Das JSON-File zur Speicherung der Daten.

`model/task.class.php`

Das File `task.class.php` enthält die Klasse `Task` mit den benötigten Attributen und Methoden zur Eingabe-Verarbeitung Validierung und Speicherung. 

![MVC](/ilv.307/assets/images/uml-class-task.png)

`store/jsonstore.php`

Die Klasse JSONStore enthält Methoden, die für Speicherung und Abruf der Daten im JSON-File benötigt werden. 

`view/taskview.php`

Die Klasse TaskView enthält Methoden, die wir für die Darstellung der Tasks benötigen.

`index.php`

index.php befindet sich im Web-Root und ist die einzige Seite, die im Browser aufgerufen wird. 


### Vorgehen

1. Markieren Sie im bestehenden Code die Abschitte nach deren Aufgabe im MVC-Modell. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ5NTcyNjUwOCwxNzI1Mzk5NzQ0XX0=
-->