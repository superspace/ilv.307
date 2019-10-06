### Tag 1

# PHP Einführung

## Setup PHP

### php.ini
Über die php.ini-Datei lässt sich die PHP-Instanz global konfigurieren. Der Speicherort der Datei hängt von der Installation ab.  
```ini
memory_limit   = 128MB
display_errors = off
error_logs     = /Applications/MAMP/logs/php_error.log
```
Die aktuellen Einstellungen können über die Funktion `phpinfo()` ausgegeben werden.

Die Einstellungen können aber auch direkt im PHP-Script angepasst werden:

```php
ini_set('error_level', 'E_ALL ~E_NOTICE');
ini_set('display_errors', true);
```

==Demo Fehlermeldung==

## Editor/IDE

### Visual Studio Code

#### Extensions
- PHP Intellisense
- PHP Debug

#### Debugging
##### XDebug aktivieren
*MAMP*
https://joshbuchea.com/enable-xdebug-in-mamp-for-mac/

*XAMP*
http://www.sintesisdigital.com.mx/dashboard/docs/activate-use-xdebug.html

==Demo Debugging==

## PHP Grundlagen

### Klassen und Objekte

PHP ermöglicht sowohl prozeduales wie auch objektorientierte Design-Muster.

#### Klasse
Eine Klasse entspricht einer *Schablone*, mit welcher Objekte erstellt werden können. Die Klasse definiert sich über Attribute und Methoden. Eine Klasse kann eine andere Klasse erweitern und erbt dabei die Attribute und Methoden der ersten Klasse.

```php
class Person {
	// Attribute
	private $name = '';
	private $email = '';
	
	// Konstruktor
	function __construct ($name, $email, $age) {
		$this->name = $name;
		$this->email = $email;
	}

	// Methoden
	function setEmail ($email) {
		$this->email = $email
	}
	function getEmail () {
		return $this->email;
	}
}

$me = new Person('Urs Beyeler', 'dev@superspace.ch', 42);
$me->setEmail('info@superspace.ch');
``` 

```php
class Apprentice extends Person {

	private var company = '';
	private var startyear = 0;


}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NTY1ODkxNzgsNTYzNTg1NzUyLDExMz
A4ODEyMTcsMTA2NDE5NTIwNywtMjQ3MzE3NTU0XX0=
-->