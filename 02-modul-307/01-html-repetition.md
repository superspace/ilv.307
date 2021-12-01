 [Modul 307 / Tag 2](/ilv.307/02-modul-307)

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
: POST / GET

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
```
<label>Text
    <input type="text" name="field1" value="" />
</label>

```html
<!-- Zahl -->
<input type="number" name="field1" value="" min="" max="" />
```
<label>Zahl
    <input type="number" name="field1" value="" min="" max="" />
</label>
```html
<!-- E-Mail -->
<input type="email" name="field1" value="" />
```
<label>E-Mail
    <input type="email" name="field1" value="" />
</label>
```html
<!-- Datum -->
<input type="datetime" name="field1" value="" />
```
<label>Datum
    <input type="datetime" name="field1" value="" />
</label>

```html
<!-- Unsichtbar -->
<input type="hidden" name="field1" value="" />
```
<input type="hidden" name="field1" value="" />

```html
<!-- Mehrzeiliger Text -->
<textarea name="field1"></textarea>
```
<label>Textfeld
<textarea name="field1"></textarea>
</label>

```html
<!-- Checkbox -->
<input type="checkbox" name="field1" value="A" />
```
<label>
<input type="checkbox" name="field1" value="A" /> Titel A
</label>

```html
<!-- Radio-Button -->
<input type="radio" name="field1" value="value-A" />
<input type="radio" name="field1" value="value-B" />
<input type="radio" name="field1" value="value-C" />
```
<label>
    <input type="radio" name="field1" value="value-A" />Wert A
</label>
<label>
    <input type="radio" name="field1" value="value-B" />Wert B
</label>
<label>
    <input type="radio" name="field1" value="value-C" />Wert C
</label>

```html
<!-- Select -->
<select name="field1">
    <option value="value-A">Titel A</option>
    <option value="value-B">Titel B</option>
    <option value="value-C">Titel C</option>
</select>
```
<label for="field1">Auswahl</label>

<select name="field1" id="field1">
    <option value="value-A">Titel A</option>
    <option value="value-B">Titel B</option>
    <option value="value-C">Titel C</option>
</select>

---

### Felder mit mehreren Werten

```html
<!-- Checkbox -->
<input type="checkbox" name="field1[]" value="A" />
<input type="checkbox" name="field1[]" value="B" />
<input type="checkbox" name="field1[]" value="C" />
<input type="checkbox" name="field1[]" value="D" />
```
<label>
    <input type="checkbox" name="field1[]" value="A" /> Titel A
</label>
<label>
    <input type="checkbox" name="field1[]" value="B" /> Titel B
</label>
<label>
    <input type="checkbox" name="field1[]" value="C" /> Titel C
</label>
<label>
    <input type="checkbox" name="field1[]" value="D" /> Titel D
</label>

---

### Multiple Select

```html
<!-- Multiple Select -->
<select name="field1[]" multiple>
    <option value="value-A">Titel A</option>
    <option value="value-B">Titel B</option>
    <option value="value-C">Titel C</option>
</select>
```

<select name="field1[]" multiple>
    <option value="value-A">Titel A</option>
    <option value="value-B">Titel B</option>
    <option value="value-C">Titel C</option>
</select>

Die ausgewählten Werte werden für die Übermittlung in einem Array zusammengefasst.

---

### Validierung mit HTML5

HTML5 erlaubt die Feld-Validierung im Browser. Die Implementierung der verschiedenen Hersteller variiert jedoch stark, weshalb man sich nicht voll und ganz darauf verlassen darf.
```html
<input type="email" name="field1" value="" required />
```
type
: Bestimmt das zu akzeptierende Format 

required
: Zwingende Eingabe

## Datenübermittlung im Browser

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
*POST und GET können auch kombiniert werden.* 

> *DEMO:* REQUEST-Daten in den Browser-Developer-Tools anzeigen
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY4MjYyNzYzOCwtMTIzMzE3NTYwMV19
-->