# Repetition HTML

## Grundgerüst
```html
<!DOCTYPE html>
<html>
    <head>
        <title>Hello World</title>
        <meta  charset="utf-8">
    </head>
    <body>
        <h1>Hello World</h1>
    </body>
</html>
```
## Formulare
```html
<form action="index.php" method="post">
    <label for="field1">Feld 1</label>
    <input type="text" id="field1" name="field1" value="" />
    <button type="submit">Senden</button>
</form>
```
action
: Ziel-URL der Datenübertragung

method
: POST | GET

*POST:* Datenübermittlung an Server

*GET:* Datenanfrage an Server. 

Die Daten können auch als URL-Parameter übergeben werden: 

 `https://www.google.com/search?q=Suchbegriff`

 ist dasselbe wie:
```html
<form action="https://www.google.com/search" method="get">
    <input type="text" name="q" value="Suchbegriff" />
    <button type="submit">Senden</button>
</form>
```


### Input-Felder
```html
<label for="field1">Feld 1</label>
<input type="text" id="field1" name="field1" value="" />
```

type
: Feld-Typ, z.B. text, email, number, datetime

id
: Eindeutiger Indentifikator

name 
: Feld-Name, eindeutiger Wert für die Übermittlung des Wertes

value 
: Der Eingabe-Wert, kann auch vorausgefüllt werden

```html
<!-- Text -->
<input type="text" name="field1" value="" />

<!-- Zahl -->
<input type="number" name="field1" value="" min="" max="" />

<!-- E-Mail -->
<input type="email" name="field1" value="" />

<!-- Datum -->
<input type="datetime" name="field1" value="" />

<!-- Unsichtbar -->
<input type="hidden" name="field1" value="" />

<!-- Mehrzeiliger Text -->
<textarea name="field1"></textarea>

<!-- Checkbox -->
<input type="checkbox" name="field1" value="1" />

<!-- Radio-Button -->
<input type="radio" name="field1" value="1" />

<!-- Dropdown -->
<select name="field1">
    <option value="value1">Wert 1</option>
</select>
```
### Validierung mit HTML5
HTML5 erlaubt die Feld-Validierung im Browser. Die Implementierung der verschiedenen Hersteller variiert jedoch stark, weshalb man sich nicht voll und ganz darauf verlassen darf.
```html
<input type="email" name="field1" value="" required />
```
type
: Bestimmt das zu akzeptierende Format 

required
: Zwingende Eingabe
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxNDcxNjIxNjNdfQ==
-->