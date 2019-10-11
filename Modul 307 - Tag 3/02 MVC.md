
# MVC Design-Pattern

Eine einfachen PHP-Anwendung mit dem MVC Design-Pattern

*Wir arbeiten bewusst ohne Framework und verzichten auf einen Router.*

MVC steht für Model – View – Controller und hilft uns dabei, eine Anwendung sinnvoll zu strukturieren. Wir verfolgend dabei unter anderem folgende Zielsetzungen:

- Trennung von Daten, Darstellung und Logik
- Wiederverwendung
- Erweiterbarkeit

Der Grundsatz entspricht der Forderung, dass jede Einheit eine klare Aufgabe hat, und diese Aufgabe möglichst ohne Wissen über die anderen Einheiten erfüllen kann.

Ziel des Musters ist ein flexibler Programmentwurf, der eine spätere Änderung oder Erweiterung erleichtert und eine Wiederverwendbarkeit der einzelnen Komponenten möglich macht.

### Trennung von Daten, Darstellung und Logik

#### Daten (Model)
Im Model sind unsere Datenfelder sowie die Schnittstelle zur Datenhaltung definiert. 

*In unserem Fall ist dies konkret eine Klasse mit den Attributen Titel, Beschreibung und Rating. Die Schnittstelle zur Datenhaltung entspricht dem Lesen- und Schreiben der Daten in das JSON-File.* 

#### Darstellung (View)
Alles was in HTML ausgegeben wird, gehört zur View. 

*Dies umfasst die Listenansicht wie auch unsere Eingabemaske.*

#### Steuerung (Controller)
Der Controller nimmt die Benutzer-Inputs auf und steuert die Daten zwischen dem Model und der View.

### Wiederverwendung
Die Trennung des Datenmodells von der Datenhaltung erlaubt uns z.B. später einen Wechsel von der Datenhaltung in JSON zu einer Datenbank vorzunehmen. Zudem kann so die Schnittstelle zur Datenhaltung von verschiedenen Modellen wiederverwendet werden.

### Erweiterbarkeit
Da die Struktur der Anwendung klar definiert ist, lassen sich zusätzliche Funktionen relativ einfach hinzufügen.

## Umsetzung

Das Arbeitsbeispiel «Tasks» soll nun in ein MVC Design-Pattern überführt werden.

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

`public/index.php`

index.php befindet sich im Web-Root und ist die einzige Seite, die im Browser aufgerufen wird. Anhand eines Parameters `view` lässt sich die Ansicht steuern.

`view/create.php`

HTML-Formular zur Erfassung neuer Einträge mit Ausgabe möglicher Fehler aus der Validierung.

`view/list.php`

Die Auflistung der erfassten Einträge in HTML.

`controller.php`

Die Steuerung empfängt die Daten aus der Benutzereingabe (`$_POST`), ruft die entsprechende Methode der Klasse auf und gibt gegebenenfalls Fehlermeldungen an die Darstellung zurück.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk4MTMyOTA2OV19
-->