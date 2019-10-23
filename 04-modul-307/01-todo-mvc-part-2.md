 [Modul 307 / Tag 4](/ilv.307/04-modul-307)

# ToDo-Verwaltung: Teil 2

## Validierung und Fehlermeldung

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


## Aktualisieren und Löschen

Dem CRUD-Prinzip (`Create-Read-Update-Delete`) folgende sollen die Daten auch bearbeitet und gelöscht werden können. 

### Datenhaltung

#### Identifikation einzelner Einträge

Um den Zugriff auf einzelne Einträge sicherzustellen, sollte jeder Eintrag eine eindeutige ID aufweisen. In JSON können wir diese ID als Schlüssel für den direkten Zugriff verwenden. Dies vereinfacht es uns, einzelne Einträge zu bearbeiten oder zu löschen. 

```json
{
	"1": {
		"title": "ID hinzufügen",
		"description": "Für jeden Eintrag eine Id generieren.",
		"priority" : "5",
		"created" : 1571838767
	},
	"2": {
		"title": "Daten bearbeiten",
		"description": "Bestehende Daten bearbeiten können.",
		"priority" : "3",
		"created" : 1571838790
	},
}
```
Zugriff auf einen spezifischen Eintrag:

```php
$values = json_decode($meinJSONString, true);
$value = $values['1'];
```

Eine inkrementelle ID kann mit PHP relativ einfach generiert werden. Wir übergeben der Funktion `max($ids)` alle bestehenen IDs und addieren 1. dazu. Die bestehenden IDs können mit `array_keys($data)` ausgelesen werden.

```php
$ids = array_keys($data);
$id = max($ids) + 1;
```

### Daten bearbeiten

```
view/
	update.php          // Daten aktualisieren
```

*public/index.php*
```php
	case  'update' :
		include  '../view/update.php';
		break;
```

*controller.php*

```php
if (isset($_POST['update'])) {

	// Get id
	$id = isset($data['id']) ? $data['id'] : 0;
	
	// InitializCreate Task with id
	$task = new Task($id);
	
	// e task
	$task->update(...)
}
```

*model/task.class.php*

```php
	function __construct ($id) {

		if (!empty($id)) {

			$data = self::load();

			if ($data && key_exists($id, $data) {
				$this->id = $id;
				$this->title = $item['title'];
				...
			}
		}	
	}

	function update (...) {

		$this->errors = $this->validate(...);
		
		if (empty($this->errors)) {
		
			$this->title = $title;
			...
			
			// Load data
			...

			if (empty($this->id) {
			
				$this->id = self::getId($data)
				$this->created = time();
			
			}
			
		// 		$data[$this->id] = array(
				'title' => $this->title,
				...
			)

			// Save data
			...
		}
	}
```
*view/update.php*

```php
<!-- Set actual value of title -->
<input type="text" name="title" value="<?=  isset($_POST['title']) ? $_POST['title'] : $task->title; ?>" required>

<!-- Set id in hidden field -->
<input type="hidden" name="id" value="<?=  $task->id; ?>">

<!-- send action update -->
<button  type="submit"  name="update">Update</button>
```

### Daten löschen

*controller.php*

```php
if (isset($_POST['delete'])) {
	
	// Get id
	$id = isset($data['id']) ? $data['id'] : 0;
	
	// Initialize Task with id
	$task = new Task($id);
	
	// Delete task
	$task->delete();
}
```

*model/task.class.php*

```php
	function delete () : void {
		
		// Load data
		...
		
		// Delete data
		unset($data[$this->id]);
		
		// Save data
		...
	}
```

*view/update.php*

```php
<!-- send action delete -->
<button  type="submit"  name="delete">Löschen</button>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU0MDI5MTYyMCwyMDQwNDcyNzg2LC0xOT
czOTEzNzUzLC0yMDQ1NjAyNDE3LC04Mzk4OTY0MzMsLTE0MzM4
OTc0ODgsMTM2NDUzNDU2MSwxNjUwODkzNTUyLC0yMjg3Njc2Mj
QsODA4ODI5NTg2XX0=
-->