 [Modul 307 / Tag 4](/ilv.307/04-modul-307)

# ToDo: Validierung und Fehlermeldung

Die Validierung erfolgt im Model, in unserem Fall in der Klasse `Task`:

```php

private  function  validate () {

	$errors = [];

	if (empty($this->title)) {
		$errors[] = 'Geben Sie bitte einen Titel ein.';
	}

	if ($this->priority < 0 && $this->priority > self::MAX_PRIORITY) {
	$errors[] = 'Geben Sie bitt eine Priorität von 1 bis 5 ein.';
	}
	
	return  $errors;
}

public function save () {


}
```

In `index.php` werden die Fehler ausgelesen und die entsprechende View gesetzt:

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
if (isset($errors)) {
	foreach($errors as $error) {
		echo  "<p>$error</p>";
	}
}
``` 
*view/update.php*

```php
...
<?php include 'errors.inc.php'; ?>
...
```




<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2Njg0OTQwNzgsLTEwNjEzNDkwMzhdfQ
==
-->