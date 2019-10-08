### Tag 3

## PHP Klassen und Objekte

PHP ermöglicht sowohl prozeduales wie auch objektorientierte Design-Muster.

### Klasse
Eine Klasse entspricht einer *Schablone*, mit welcher Objekte erstellt werden können. Die Klasse definiert sich über Attribute und Methoden. Eine Klasse kann eine andere Klasse erweitern und erbt dabei die Attribute und Methoden der ersten Klasse.

```php
class Task {

	// Attribute
	const PRIORITY_MAX = 5;

	public $title = '';
	po $description = '';
	private $priority = 0;
	
	// Konstruktor
	function __construct ($title, $description, $priority) {
		$this->title = $title;
		$this->description = $description;
		$this->priority = $priority
	}

	// Methoden
	function setPriority ($priority) {
		if ($priority <= self::PRIORITY_MAX) {
			$this->priority = $priority;
		}
	}
	function getPriority () {
		return $this->priority;
	}
}

$task = new Task('PHP lernen', 'Grundlagen und Anwendung von PHP verstehen', 5);

$task->getPrority();
``` 

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

*In unserem Fall ist dies konkret eine Klasse mit den Attributen E-Mail, Rating und Datum. Die Schnittstelle zur Datenhaltung entspricht dem Lesen- und Schreiben der Daten in das JSON-File.* 

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

Das Arbeitsbeispiel «Ratings» soll nun in ein MVC Design-Pattern überführt werden.

Als Grundlage dient uns folgende Dateistruktur:

```
data/
	items.json          // Datenhaltung in JSON-File
model/
	item.class.php      // Klassenmodell mit Attributen
	storage.class.php   // Schnittstelle zur Datenhaltung 
public/
	index.php           // Ansicht im Web-Root 
view/
	create.php          // HTML-Formular für neuen Eintrag
	list.php            // Auflistung der Einträge
controller.php              // Steuerung
```

`data/items.json`

Das JSON-File zur Speicherung der Daten.

`model/item.class.php`

Das File `item.class.php` enthält die Klasse `Item` mit den benötigten Attributen und der Eingabe-Verabeitung und Validierung. Die Klasse `Item` erweitern die Klasse `Storage`.

`model/storage.class.php`

Die Klasse `Storage` enthält alle Methoden und Attribute die für das Lesen, Schreiben und Aktualsieren der Daten im JSON-File benötigt werden. Diese Klasse bleibt abstrakt und soll wiederverwendet werden können.

`public/index.php`

index.php befindet sich im Web-Root und ist die einzige Seite, die im Browser aufgerufen wird. Anhand eines Parameters `mode` lässt sich die Ansicht steuern.

`view/create.php`

HTML-Formular zur Erfassung neuer Einträge mit Ausgabe möglicher Fehler aus der Validierung.

`view/list.php`

Die Auflistung der erfassten Einträge in HTML.

`controller.php`

Die Steuerung empfängt die Daten aus der Benutzereingabe (`$_POST`), ruft die entsprechende Methode der Klasse auf und gibt gegebenenfalls Fehlermeldungen an die Darstellung zurück.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgwMzQ5MjMyLC0xODIxMDg1OTkxLC0xNz
I0MTk1OTQzXX0=
-->