## Validierung


## CRUD

> Create-Read-Update-Delete

### Datenhaltung

#### Identifikation einzelner Einträge

Um den Zugriff auf einzelne Einträge sicherzustellen, sollte jeder Eintrag eine eindeutige ID aufweisen. In JSON können wir diese ID als Schlüssel für den direkten Zugriff verwenden. Dies vereinfacht es uns, einzelne Einträge zu bearbeiten oder zu löschen. 

```json
{
	"1": {
		"name": "Urs Beyeler",
		"email" : "dev@superspace.ch"
	},
	"2": {
		"name": "Hans Dampf",
		"email": "hans@dampf.ch"
	}
}
```
Zugriff auf einen spezifischen Eintrag:

```php
$values = json_decode($meinJSONString, true);
$value = $values['1'];
```

Eine inkrementelle ID kann mit PHP relativ einfach generiert werden. Wir übergeben der Funktion `max($ids)` alle bestehenen IDs und addieren 1. dazu. Die bestehenden IDs können mit `array_keys($data)` ausgelesen werden.

```php
$keys = array_keys($data);
$id = max($keys) + 1;
```

### Ergänzung Datei-Struktur

```
view/
	update.php          // Daten aktualisieren
```

*index.php*
```php
	case  'update' :
		include  '../view/update.php';
		break;
```

*controller.php*

```php
elseif (isset($_POST['update'])) {

	// Get id
	$id = isset($data['id']) ? $data['id'] : 0;
	
	// Create Task with id
	$task = new Task($id);
	
	// Update task
	$task->update(...)
}
```

*task.class.php*

```php

class Task {
	
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

		$this->validate(...);
		
		if (empty($this->errors)) {
		
			$this->title = $title;
			...
			
			// Load data
			...

			if (empty($this->id) {
			
				$this->id = self::getId($data)
				$this->created = time();
			
			}
			
			// Update data
			$data[$this->id] = [
			]

			// Save data
			...
		}
	}
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTYxNzQ2NDEsLTE0MzM4OTc0ODgsMTM2ND
UzNDU2MSwxNjUwODkzNTUyLC0yMjg3Njc2MjQsODA4ODI5NTg2
XX0=
-->