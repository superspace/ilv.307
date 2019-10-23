 [Modul 307 / Tag 4](/ilv.307/04-modul-307)

# ToDo: Validierung und Fehlermeldung

Die Validierung erfolgt im Model, in unserem Fall in der Klasse `Task`:

```php
	private $errors = [];

	function __construct (...) {

		$this->errors = $this->validate(...);

		if (empty($this->errors)) {
		
			// Update values
			...
		}
	}

	private function validate (...) : array {
	
		$errors = [];

		if (empty($title)) {
			$errors[] = "Geben Sie bitte einen Titel ein.";
		}

		...

		return $errors;
	}

	public function getErrors () : array {

		return $this->errors;
	}
```

Im `controller.php` werden die Fehler ausgelesen und die entsprechende View gesetzt:

```php
if (isset($_POST['create'])) {
	
	...
	
	if ($errors = $task->getErrors()) {
		$view = 'create';
	} else {
		header("Location:{$_SERVER['PHP_SELF']}");
	}
}
```

Um die Anzeige der Fehlermeldung in der View wiederverwenden zu können, erstellen wir eine separate PHP-Datei, und binden diese mit  `include` ein.

*view/errors.inc.php*

```php
if (!empty($errors)) {
	$error_messages = '';
	foreach($errors as $error) {
		$error_messages  .=  "<p>$error</p>";
	}
	echo  $error_messages;
}
``` 
*view/update.php*

```php
...
<?php include 'errors.inc.php'; ?>
...
```




<!--stackedit_data:
eyJoaXN0b3J5IjpbLTUxODU1MzA5NV19
-->