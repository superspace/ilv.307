## Validierung

Die Validierung erfolgt im Model, in unserem Fall in der Klasse `Task`

```php
private $errors = [];

private function validate (...) : array {
	
	$errors = [];

	if (empty($title)) {
		$errors[] = "Geben Sie bitte einen Titel ein.";
	}

	...

	return $errors;
}

public function update (...) : void {

	$this->errors = $this->validate(...);

	if (empty($this->errors)) {
		
		// Update values
		...
		
	}
}

public function getErrors () : array {
	return $this->errors;
}
```



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
$idkeys = array_keys($data);
$id = max($ids) + 1;
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
if (isset($_POST['update'])) {

	// Get id
	$id = isset($data['id']) ? $data['id'] : 0;
	
	// InitializCreate Task with id
	$task = new Task($id);
	
	// e task
	$task->update(...)
}

if (isset($_POST['delete'])) {
	
	// Get id
	$id = isset($data['id']) ? $data['id'] : 0;
	
	// Initialize Task with id
	$task = new Task($id);
	
	// Delete task
	$task->delete();

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
	
	function delete () : void {
		
		// Load data
		...
		
			// Delete data
		unset($data[$this->id]);Update data

			// Save data
		...
	}
}
```
*update.php*

```php
<!-- Set actual value of title -->
<input type="text" name="title" value="<?=  isset($_POST['title']) ? $_POST['title'] : $task->title; ?>" required>

<!-- Set id in hidden field -->
<input type="hidden" name="id" value="<?=  $task->id; ?>">

<!-- send action update -->
<button  type="submit"  name="update">Update</button>

<!-- send action delete -->
<button  type="submit"  name="delete">Löschen</button>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5NzM5MTM3NTMsMTk1MTYxODAzOSwtMj
A0NTYwMjQxNywtODM5ODk2NDMzLC0xNDMzODk3NDg4LDEzNjQ1
MzQ1NjEsMTY1MDg5MzU1MiwtMjI4NzY3NjI0LDgwODgyOTU4Nl
19
-->