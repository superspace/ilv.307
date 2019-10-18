 [Modul 307 / Tag 3](/ilv.307/03-modul-307)

# PHP Klassen und Objekte

PHP kann sowohl prozedual wie auch objektorientiert verwendet werden. *Dies ist nicht eine Einführung in die Objekt-orientierte Programmierung.*


## Klasse

Eine Klasse entspricht einer *Schablone*, mit welcher Objekte erstellt werden können. Die Klasse definiert sich über Attribute und Methoden.

![UML Diagram](/ilv.307/assets/images/uml-class-hero.png)

```php
class Hero {

	// Attribute
	public $name = '';
	public $realname = '';
	private $popularity = 0;

	// Konstante
	const POPULARITY_MAX = 5;	

	// Konstruktor
	function __construct (string $name, string $realname, int $popularity) {
		$this->name = $name;
		$this->realname = $realname;
		$this->setPopularity($popularity);
	}

	// Methoden
	public function setPopularity (int $popularity) : void {
		if ($this->validatePopularity($popularity)) {
			$this->popularity = $popularity;
		}
	}

	public function getPopularity () : int {
		return $this->popularity;
	}

        private function validatePopularity (int $popularity) : bool {
		return ($popularity > 0 && $popularity <= self::POPULARITY_MAX);
	}
}
```
Damit auf ein Attribut oder eine Methode aufgerufen werden kann, muss erst eine Instanz (Objekt) der Klasse erstellt werden. Eine Ausnahme sind statische Methoden oder Konstanten, diese lassen sich auch direkt aufrufen.

private/public
: Zugriff auf Attribute und Methoden nur innerhalb des Objekts (*private*) oder auch von aussen (*public*) erlauben

const
: Definition einer Konstanten, Aufruf über `self::PRIORITY_MAX`

__construct()
: Die Methode `__construct()` wird bei der Erstellung eines Objektes aufgerufen. Die aufgeführten Argumente müssen beim Erstellen des Objektes berücksichtigt werden.

$this
: Attribute und Methoden werden innerhalb der Klasse über `$this->` aufgerufen.

```php
// Objekt erstellen
$hero = new Hero('Spiderman', 'Peter Parker', 5);

// Getter aufrufen
$popularity = $hero->getPopularity();

// Setter aufrufen
$hero->setPopularity($popularity);
``` 

->
: Der Zugriff auf Attribute und Methoden eines Objektes erfolgt über den Operator `->`

::
: Der Zugriff auf statische Methoden erfolgt über `::`

## Code-Dokumentation

### DocBlock

Ein DocBlock ist ein standardisiert aufgebauter Kommentar um Funktionen, Methoden und Attribute  zu dokumentieren.

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
eyJoaXN0b3J5IjpbLTQ5NTQ1NzYzNywtNzI3MDg5OTg1LDY0Mj
Y3NDg0MiwxOTMwMjIzNTk3LC0xNjMwNDcwMTE3LDk1ODY0Nzgz
NSwtMTg4MDQzMDkwLDkzMzI0MDk0MV19
-->