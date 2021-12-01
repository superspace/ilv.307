 [Modul 307 / Tag 4](/ilv.307/04-modul-307)

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

	public static  function  getMaxPriority () : int {
		return  self::MAX_PRIORITY;
	}
}
```
Damit auf ein Attribut oder eine Methode aufgerufen werden kann, muss erst eine Instanz (Objekt) der Klasse erstellt werden. Eine Ausnahme sind statische Methoden oder Konstanten, diese lassen sich auch direkt aufrufen.

private/public/protected
: Zugriff auf Attribute und Methoden nur innerhalb des Objekts (*private*) oder auch von aussen (*public*) erlauben

const
: Definition einer Konstanten, Aufruf über `self::MAX_PRIORITY`

__construct()
: Die Methode `__construct()` wird bei der Erstellung eines Objektes aufgerufen. Die aufgeführten Argumente müssen beim Erstellen des Objektes berücksichtigt werden.

$this
: Attribute und Methoden werden innerhalb der Klasse über `$this->` aufgerufen.

static
: Statische Methoden werden direkt über die Klasse aufgerufen. Es wird keine Instanz erstellt: `Task::getMaxPriority()`. In einer statische Methode ist es *nicht* möglich, auf `$this` zuzugreifen. 

```php
// Objekt erstellen
$todo = new Task('Klassen erstellen', 'Verstehen, wie Klassen und Objekte funktionieren.', 4);

// Getter aufrufen
$priority = $todo->getPriority();

// Setter aufrufen
$todo->setPriority($priority);

// Statische Method aufrufen
$max = Task::getMaxPriority();
``` 

Der Zugriff auf Attribute und Methoden eines Objektes erfolgt über den Pointer `->`



<!--stackedit_data:
eyJoaXN0b3J5IjpbOTU0MzE0NTIxLC02Njk1MzY2NDgsLTQ3MT
M5NTY5Nyw1ODc5MDUxNDYsNDIwODk4OTIwLC01MTc4MDY1NzAs
LTc0MDQ5NTkzLDQyMTE5ODk1NSwtNDY0Njg2NzE1LDE3NjQ2MT
A4OCwtNzI3MDg5OTg1LDY0MjY3NDg0MiwxOTMwMjIzNTk3LC0x
NjMwNDcwMTE3LDk1ODY0NzgzNSwtMTg4MDQzMDkwLDkzMzI0MD
k0MV19
-->