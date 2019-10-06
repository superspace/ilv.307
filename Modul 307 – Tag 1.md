### Tag 1

# PHP Einführung

## Setup PHP

### php.ini
Über die php.ini-Datei lässt sich die PHP-Instanz global konfigurieren. Der Speicherort der Datei hängt von der Installation ab.  
```ini
error_reporting   = E_ALL & ~E_NOTICE
display_errors = off
error_logs     = /Applications/MAMP/logs/php_error.log
```
Die aktuellen Einstellungen können über die Funktion `phpinfo()` ausgegeben werden.

Die Einstellungen können aber auch direkt im PHP-Script angepasst werden:

```php
ini_set('error_reporting', E_ALL);
ini_set('display_errors', true);
```
https://www.php.net/manual/de/function.error-reporting.php

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

	private $company = '';
	private $startyear = 0;

	function __construct ($name, $email, $company, $startyear) {
		$this->company = $company;
		$this->startyear = $startyear;

		parent::__construct($name, $email);
	}
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMxMDU0ODYzNiwxMDE2OTE5NzU5LDU2Mz
U4NTc1MiwxMTMwODgxMjE3LDEwNjQxOTUyMDcsLTI0NzMxNzU1
NF19
-->