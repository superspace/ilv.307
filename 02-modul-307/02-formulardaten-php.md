 [Modul 307 / Tag 2](/ilv.307/02-modul-307)

# Formulardaten in PHP

Die Request-Daten eines Serveraufrufes werden in den PHP Superglobals `$_REQUEST`, `$_GET` und `$_POST` als Schlüssel-Wert-Paare in einem Array abgelegt. 

#### POST
Die globale Variable `$_POST` beinhaltet alle Schlüssel-Wert-Paare, die über ein Formular mit `method="post"` übermittelt worden sind.

#### GET
Die globale Variable `$_GET` beinhaltet alle Schlüssel-Wert-Paare, die entweder über ein Formular mit `method="get"` oder direkt als URL-Parameter übermittelt worden sind.

#### REQUEST
Die globale Variable `$_REQUEST` beinhaltet alle Schlüssel-Wert-Paare die per POST oder per GET übermittelt worden sind.

### Werte auslesen
Die Werte werden über den Schlüssel ausgelesen. Vorerst sollte immer überprüft werden, ob der Schlüssel existiert. 

Mit dem *Ternary Operator* können wir überprüfen, ob der Schlüssel existiert und den enthaltenen oder den Default-Wert direkt einer Variablen zuweisen: 

```php
$realname = isset($_POST['realname']) ? $_POST['realname'] : ''; 
```
Dies entspricht :

```php
$realname = '';
if (isset($_POST['realname']))
	$realname = $_POST['realname'];
```


## Werte in Formfeldern ausgeben

Formularfelder können auch mit bereits vorhandenen Daten befüllt werden. Dazu werden die Werte mittels PHP in die HTML-Tags hineinschrieben. Wir verwenden dazu den PHP-Echo-Tag: `<?= $output =>`.

### Input-Feld
```php
$title = 'Ein Titel';
```
```html
<input type="text" name="title" value="<?= $title ?>">
```
<p>
    <input type="text" name="title" value="Ein Titel">
</p>

### Textarea-Feld
```php
$text = 'Ein Text, der auch mehrere Zeilen lang sein kann.';
```
```html
<textarea name="text" rows="3"><?= $text ?></textarea>
```
<p>
    <textarea name="text">Ein Text, der auch mehrere Zeilen lang sein kann.</textarea>
</p>

### Select
```php
$category = 'B';
```
```html
<select name="category">
    <option value="A" <?= $category == 'A' ? 'selected' : '' ?> >Kategorie A</option>
    <option value="B" <?= $category == 'B' ? 'selected' : '' ?> >Kategorie B</option>
    <option value="C" <?= $category == 'C' ? 'selected' : '' ?> >Kategorie C</option>
</select>
```
<p>
    <select name="category">
        <option value="A"> Kategorie A</option>
        <option value="B" selected> Kategorie B</option>
        <option value="C"> Kategorie C</option>
    </select>
</p>

### Radio Buttons
```php
$category = 'C';
```
```html
    <input type="radio" name="category" 
        value="A" <?= $category == 'A' ? 'checked' : '' ?> /> Kategorie A
    <input type="radio" name="category" 
        value="B" <?= $category == 'B' ? 'checked' : '' ?> /> Kategorie B
    <input type="radio" name="category" 
        value="C" <?= $category == 'C' ? 'checked' : '' ?> /> Kategorie C
```
<p>
<label>
    <input type="radio" name="category" value="A" /> Kategorie A
</label>
<label>
    <input type="radio" name="category" value="B" checked /> Kategorie B
</label>
<label>
    <input type="radio" name="category" value="C" checked/> Kategorie C
</label>
</p>

### Checkbox

Array mit mehreren aktiven Werten 

```php
$categories = ['B', 'C'];
```
```html
    <input type="checkbox" name="categories[]" 
        value="A" <?= in_array('A', $categories) ? 'checked' : '' ?> /> Kategorie A
    <input type="checkbox" name="categories[]" 
        value="B" <?= in_array('B', $categories) ? 'checked' : '' ?> /> Kategorie B
    <input type="checkbox" name="categories[]" 
        value="C" <?= in_array('C', $categories) ? 'checked' : '' ?> /> Kategorie C
```
<p>
<label>
    <input type="checkbox" name="categories[]" value="A" /> Kategorie A
</label>
<label>
    <input type="checkbox" name="categories[]" value="B" checked /> Kategorie B
</label>
<label>
    <input type="checkbox" name="categories[]" value="C" checked/> Kategorie C
</label>
</p>
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE4Nzk4NzM2MF19
-->