 [Modul 307 / Tag 3](/ilv.307/03-modul-307)

# PHP Klassen und Objekte

PHP kann sowohl prozedual wie auch objektorientiert verwendet werden. *Dies ist nicht eine Einführung in die Objekt-orientierte Programmierung.*


## Klasse

Eine Klasse entspricht einer *Schablone*, mit welcher Objekte erstellt werden können. Die Klasse definiert sich über Attribute und Methoden.

![UML Diagram](/ilv.307/assets/images/uml-class-task.png)

```php
class Task {

	// Attribute
	public $title = '';
	public $description = '';
	private $priority = 0;

	// Konstante
        const MAX_PRIORITY = 5;

	// Konstruktor
	function __construct (string $title='', string $description='', int $priority=0) {
		$this->title = $title;
		$this->description = $description;
		$this->setPriority($priority);
	}

	// Methoden
	public function setPriority (int $priority) : void {
		if ($this->validatepriority($priority)) {
			$this->priority = $priority;
		}
	}

	public function getPriority () : int {
		return $this->priority;
	}

	private function validatePriority (int $priority) : bool {
		return ($priority > 0 && $priority <= self::MAX_PRIORITY);
	}

        
}
```
Damit auf ein Attribut oder eine Methode aufgerufen werden kann, muss erst eine Instanz (Objekt) der Klasse erstellt werden. Eine Ausnahme sind statische Methoden oder Konstanten, diese lassen sich auch direkt aufrufen.

private/public
: Zugriff auf Attribute und Methoden nur innerhalb des Objekts (*private*) oder auch von aussen (*public*) erlauben

const
: Definition einer Konstanten, Aufruf über `self::MAX_PRIORITY`

__construct()
: Die Methode `__construct()` wird bei der Erstellung eines Objektes aufgerufen. Die aufgeführten Argumente müssen beim Erstellen des Objektes berücksichtigt werden.

$this
: Attribute und Methoden werden innerhalb der Klasse über `$this->` aufgerufen.

```php
// Objekt erstellen
$todo = new ToDo('Klassen erstellen', 'Verstehen, wie Klassen und Objekte funktionieren.', 4);

// Getter aufrufen
$priority = $hero->getPriority();

// Setter aufrufen
$hero->setPriority($priority);
``` 
->
: Der Zugriff auf Attribute und Methoden eines Objektes erfolgt über den Pointer `->`

## Code-Dokumentation

### DocBlock

Ein DocBlock ist ein standardisiert aufgebauter Kommentar um  Methoden, Parameter und Attribute  zu dokumentieren.

Durch die Standardisierung ist der DocBlock sehr einfach zu lesen und zu verstehen und es ist möglich, die technische Dokumentation des Codes zu automatisieren.

[docs.phpdoc.org](https://docs.phpdoc.org/references/phpdoc/basic-syntax.html#what-is-a-docblock)

```php
 /**
 * Einzelige Zusammenfassung
 *
 * Auführlichere Beschreibung, gerne auch über mehrere 
 * Zeilen.
 *
 * @author  Urs Beyeler <dev@superspace.ch>
 *
 * @since 1.0
 *
 * @param int    $wert  Das ist die Parameter-Beschreibung.
 * @param string $wert2 Dies ist ein weiterer Wert.
 * 
 * @return string  Das ist der Rückgabewert der Funktion.
 */
```

Der DocBlock besteht im Wesentlichen aus 3 Teilen:

-  Zusammenfassung
- Beschreibung
- Meta-Daten
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc0MDQ5NTkzLDQyMTE5ODk1NSwtNDY0Nj
g2NzE1LDE3NjQ2MTA4OCwtNzI3MDg5OTg1LDY0MjY3NDg0Miwx
OTMwMjIzNTk3LC0xNjMwNDcwMTE3LDk1ODY0NzgzNSwtMTg4MD
QzMDkwLDkzMzI0MDk0MV19
-->