 [Modul 307 / Tag 4](/ilv.307/04-modul-307)

# ToDo: Validierung und Fehlermeldung

Die Validierung erfolgt im Model, in unserem Fall in der Klasse `Task`:

```php

private  function  validate () : array {

	$errors = [];

	if (empty($this->title)) {
		$errors[] = 'Geben Sie bitte einen Titel ein.';
	}

	if ($this->priority < 0 && $this->priority > self::MAX_PRIORITY) {
	$errors[] = 'Geben Sie bitt eine Priorität von 1 bis 5 ein.';
	}
	
	return  $errors;
}
```
Vor der Speicherung wird die Methode `validate()` aufgerufen. Falls Fehler vorhanden sind, werden diese in einem Array zurückgegeben. Sonst wird mit der Speicherung fortgefahren.

```php
public function save () : array {

	$errors = $this->validate();

	if ($errors) {
		return $errors;
	} else {
		// Store data
	}
}
```

In `index.php` werden die Fehler ausgegeben:

```php
$error_message = '';

if (isset($_POST['create'])) {
	
	...
	$errors = $task->save();	

	if ($errors) {
		foreach ($errors as $error) {
			$error_message  .=  '<div class="alert alert-danger">'  .  $error  .  '</div>';
		}

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
eyJoaXN0b3J5IjpbNzg0NzcwNzUxLC0xMDYxMzQ5MDM4XX0=
-->