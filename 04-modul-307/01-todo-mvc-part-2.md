
# CRUD

> Create-Read-Update-Delete

### Datenhaltung

#### Identifikation einzelner Einträge

Um den Zugriff auf einzelne Einträge sicherzustellen, sollte jeder Eintrag eine eindeutige ID aufweisen. In JSON können wir diese ID als Schlüssel für den direkten Zugriff verwenden. Dies vereinfacht es uns, einzelne Einträge zu bearbeiten oder zu löschen. 

```json
{
	"ee716009417de64432d6f7195425ed18": {
		"name": "Urs Beyeler",
		"email" : "dev@superspace.ch"
	},
	"02621484d917cd47eaa125b12249d4b3": {
		"name": "Hans Dampf",
		"email": "hans@dampf.ch"
	}
}
```
Zugriff auf einen spezifischen Eintrag:

```php
$values = json_decode($meinJSONString, true);
$value = $values['ee716009417de64432d6f7195425ed18'];
```

Die ID kann per Hash-Funktion mit einem zufälligen Wert und beispielswiese dem aktuellen Zeitpunkt erstellt werden:

```php
$id = hash('md5', time() .  rand(1000,9999));
```

### Datei-Struktur


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIxODA4ODExNl19
-->