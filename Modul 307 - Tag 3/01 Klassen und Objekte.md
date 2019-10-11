### Tag 3

## PHP Klassen und Objekte

PHP ermöglicht sowohl prozeduales wie auch objektorientierte Design-Muster.

### Klasse
Eine Klasse entspricht einer *Schablone*, mit welcher Objekte erstellt werden können. Die Klasse definiert sich über Attribute und Methoden. Eine Klasse kann eine andere Klasse erweitern und erbt dabei die Attribute und Methoden der ersten Klasse.

```php
class Task {

	// Attribute
	public $title = '';
	public $description = '';
	private $priority = 0;

	// Konstante
	const PRIORITY_MAX = 5;	

	// Konstruktor
	function __construct ($title, $description, $priority) {
		$this->title = $title;
		$this->description = $description;
		$this->setPriority($priority);
	}

	// Methoden
	public function setPriority ($priority) {
		if ($priority > 0 && $priority <= self::PRIORITY_MAX) {
			$this->priority = $priority;
		}
	}
	public function getPriority () {
		return $this->priority;
	}
}

// Objekt erstellen
$task = new Task('PHP lernen', 'Grundlagen und Anwendung von PHP verstehen', 5);

// Methode aufrufen
$priority = $task->getPrority();
``` 

private/public
: Zugriff auf Attribute und Methoden nur innerhalb des Objekts (*private*) oder auch von aussen (*public*) erlauben

const
: Definition einer Konstanten, Aufruf über `self::PRIORITY_MAX`

__construct()
: Die Methode `__construct()` wird bei der Erstellung eines Objektes aufgerufen. Die aufgeführten Argumente müssen beim Erstellen des Objektes berücksichtigt werden.

$this
: Attribute und Methoden werden innerhalb der Klasse über `$this->` aufgerufen.

->
: Der Zugriff auf Attribute und Methoden eines Objektes erfolgt über den Operator `->`



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM1NjM3NDk0M119
-->