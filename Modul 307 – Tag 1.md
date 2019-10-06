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
	//Attribute
	$name = '';
	$email = '';
	$age = 0;
	
	// Konstruktor
	function __construct ($name, $email, $age) {
		$this->name = $name;
		$this->email = $email;
		$this->age = $age;
	}

	// Methoden
	function setEmail ($email) {
		$this->email = $email
	}
}

$me = new Person('Urs Beyeler', 'dev@superspace.ch', 42);
$me->setEmail('info@superspace.ch');

print_r($me);
``` 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMwMjU1NDU5MiwxMDY0MTk1MjA3LC0yND
czMTc1NTRdfQ==
-->