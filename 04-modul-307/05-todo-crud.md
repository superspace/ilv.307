 [Modul 307 / Tag 4](/ilv.307/04-modul-307)

# ToDo: Aktualisieren und Löschen

Dem CRUD-Prinzip (`Create-Read-Update-Delete`) folgend sollen die Daten auch bearbeitet und gelöscht werden können. 

### Datenhaltung

#### Identifikation einzelner Einträge

Um den Zugriff auf einzelne Einträge zu ermöglichen, sollte jeder Eintrag eine eindeutige ID aufweisen. In JSON können wir diese ID als Objekt-Schlüssel für den direkten Zugriff verwenden. Dies vereinfacht die Bearbeitung oder Löschung einzelner Einträge. 

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
$value = $values['2'];
```

Eine inkrementelle ID kann mit PHP relativ einfach generiert werden. Wir übergeben der Funktion `max($ids)` alle bestehenen IDs und addieren 1. dazu. Die bestehenden IDs können mit `array_keys($data)` ausgelesen werden.

```php
$ids = array_keys($data);
$id = (!empty($ids)) ? max($ids) + 1 : 1;
```

### Daten bearbeiten

```bash
view/
	update.php          # Daten aktualisieren
```

*index.php*
```php
	case  'update' :
		include  'view/update.php';
		break;
```

*controller.php*

```php
if (isset($_POST['update'])) {

	// Get id
	$id = isset($data['id']) ? $data['id'] : 0;
	
	// Initialize task with id
	$task = new Task($id);
	
	// Update task
	$task->update(...)
}
```

*model/task.class.php*

```php
	function __construct (int $id=0) {
		
		...

		if ($id > 0) {

			$item = $this->store->getItem($id);

			if ($item) {
	
				$this->id = $id;
				$this->title = $item['title'];
				...
			}
		}	
	}

	function save (...) {

		...
		$task = [
			'id' => $this->id,
			...
		];

		if ($this->id > 0) {

			$task['created'] = $this->created;
			$this->store->update($task);

		} else {
			...
		}
	}
```
*store/jsonstore.class.php*
```php
public  function  getItem (int  $id) : array {

	$item = [];
	$this->load();

	if (key_exists($id, $this->data)) {
		$item = $this->data[$id];
	}
	return  $item;
}

  

public  function  update ($item) {

	$this->load();

	if (isset($item['id']) && $item['id'] > 0) {

		$id = $item['id'];
		unset($item['id']);

		$this->data[$id] = $item;
	$this->save();

}
}
```
*view/list.php*

```php
	...
	echo "<a href=\"?view=update&id={$task->getId()}\">Update</a>";
	...
```

*view/update.php*

```php
<!-- Set actual value of title -->
<input type="text" name="title" value="<?=  isset($_POST['title']) ? $_POST['title'] : $task->getTitle(); ?>" required>

<!-- Set id in hidden field -->
<input type="hidden" name="id" value="<?=  $task->getId(); ?>">

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
eyJoaXN0b3J5IjpbLTgyOTkxMzA4MSwtNjc4NzY0OTA1XX0=
-->