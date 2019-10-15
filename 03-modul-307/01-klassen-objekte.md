 [Modul 307 / Tag 3](/ilv.307/03-modul-307)

# PHP Klassen und Objekte

PHP kann sowohl prozedual wie auch objektorientiert verwendet werden. *Dies ist nicht eine Einführung in die Objekt-orientierte Programmierung.*

## Klasse

Eine Klasse entspricht einer *Schablone*, mit welcher Objekte erstellt werden können. Die Klasse definiert sich über Attribute und Methoden.

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

## Code-Dokumentation

### DocBlock

```php
 /**
 * This is the summary for a DocBlock.
 *
 * This is the description for a DocBlock. This text may contain
 * multiple lines and even some _markdown_.
 *
 * The section after the description contains the tags; which provide
 * structured meta-data concerning the given element.
 *
 * @author  Mike van Riel <me@mikevanriel.com>
 *
 * @since 1.0
 *
 * @param int    $example  This is an example parameter description.
 * @param string $example2 This is a second example.
 * 
 y3*
 */
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwMzAzMzQ0NzcsLTE4ODA0MzA5MCw5Mz
MyNDA5NDFdfQ==
-->