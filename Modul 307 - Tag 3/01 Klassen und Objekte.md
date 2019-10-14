# PHP Klassen und Objekte

PHP kann sowohl prozedual wie auch objektorientiert verwendet werden. *Dies ist nicht eine Einführung in die Objekt-orientierte Programmierung.*

## Klasse

Eine Klasse entspricht einer *Schablone*, mit welcher Objekte erstellt werden können. Die Klasse definiert sich über Attribute und Methoden.

```mermaid
classDiagram
Hero
```

```mermaid
sequenceDiagram
Alice ->> Bob: Hello Bob, how are you?
Bob-->>John: How about you John?
Bob--x Alice: I am good thanks!
Bob-x John: I am good thanks!
Note right of John: Bob thinks a long<br/>long time, so long<br/>that the text does<br/>not fit on a row.

Bob-->Alice: Checking with John...
Alice->John: Yes... John, how are you?
```

And this will produce a flow chart:

```mermaid
graph LR
A[Square Rect] -- Link text --> B((Circle))
A --> C(Round Rect)
B --> D{Rhombus}
C --> D
```

```php
class Hero {

	// Attribute
	public $name = '';
	public $realname = '';
	private $popularity = 0;

	// Konstante
	const POPULARITY_MAX = 5;	

	// Konstruktor
	function __construct ($name, $realname, $popularity) {
		$this->name = $name;
		$this->realname = $realname;
		$this->setPopularity($popularity);
	}

	// Methoden
	public function setPopularity ($popularity) {
		if (self::validatePopularity($popularity)) {
			$this->popularity = $popularity;
		}
	}

	public function getPopularity () {
		return $this->popularity;
	}

        static function validatePopularity ($popularity) {
		return ($popularity > 0 && $popularity <= self::POPULARITY_MAX);
	}
}
```
Damit auf ein Attribut oder eine Methode aufgerufen werden kann, muss erst eine Instanz (Objekt) der Klasse erstellt werden. Eine Ausnahme sind statische Methoden oder Konstanten, diese lassen sich auch direkt aufrufen.

private/public
: Zugriff auf Attribute und Methoden nur innerhalb des Objekts (*private*) oder auch von aussen (*public*) erlauben

static
: Definition einer statischen Methode. In statischen Methoden ist es nicht möglich, auf `$this` zuzugreifen.

const
: Definition einer Konstanten, Aufruf über `self::PRIORITY_MAX`

__construct()
: Die Methode `__construct()` wird bei der Erstellung eines Objektes aufgerufen. Die aufgeführten Argumente müssen beim Erstellen des Objektes berücksichtigt werden.

$this
: Attribute und Methoden werden innerhalb der Klasse über `$this->` aufgerufen.

```php
// Objekt erstellen
$task = new Hero('Spiderman', 'Peter Parker', 5);

// Methode aufrufen
$popularity = $task->getPopularity();

// Statisch Methode aufrufen
$isValid = Hero::validatePopularity($popularity);
``` 

->
: Der Zugriff auf Attribute und Methoden eines Objektes erfolgt über den Operator `->`

::
: Der Zugriff auf statische Methoden erfolgt über `::`



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyODk0NjQ4MCw5MzMyNDA5NDEsMjAwMz
QzODI2NywtODg4NjY5Mjg1LC0xMzEyNjQ2NDAsLTcxNDg1Mzg3
OSwtMTQxNDQxNzA3Ml19
-->