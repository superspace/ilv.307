
# Lösungen: Kontrollstrukturen  
## Aufgabe 1
#### Schritt 1
Generieren Sie in einer Variable `$runs` eine Zufallszahl zwischen 1 und 10 und zeigen Sie diese an.
*Tipp: Verwenden Sie hierzu `rand()`*
```php
$runs = rand(1, 10);
print("Anzahl Durchl&auml;ufe: $runs<br><br>\n");
```

#### Schritt 2
Durchlaufen Sie eine Schleife `$runs` Mal und geben Sie bei jedem Durchlauf eine Zufallszahl zwischen 1 und 100 aus.
```php
$run_counter = 0;
while($run_counter < $runs)
{
    $number = rand(1,100);
    print("$number<br>\n");
    $run_counter++;
}
```

#### Schritt 3
Färben Sie die Zahlen gemäss folgender Anweisungen ein:
- Zahlen die `30 oder kleiner` sind: grün
- Zahlen die `70 oder grösser` sind: rot
- Die Zahl `50`: blau
```php
 if($number <= 30) $color = '#00FF00';
 else if($number >= 70) $color = '#FF0000';
 else if($number == 50) $color = '#0000FF';
 else $color = '#000000';
 /////
 print("<div style=\"color:$color;\">$number</div>\n");
```

#### Schritt 4
Unterstreichen Sie alle `geraden Zahlen` die grösser `kleiner als 20` oder `grösser als 80` sind.

```php
$runs = rand(1, 10);
print("Anzahl Durchl&auml;ufe: $runs<br><br>\n");

$run_counter = 0;
while($run_counter < $runs)
{
    $number = rand(1,100);

    if($number <= 30) $color = '#00FF00';
    else if($number >= 70) $color = '#FF0000';
    else if($number == 50) $color = '#0000FF';
    else $color = '#000000';

    if(($number < 20 || $number > 80) && $number%2 == 0)
    {
        $underline= "underline";
    }
    else
    {
        $underline= "normal";
    }

    print("<div style=\"color:$color; text-decoration:$underline\">$number</div>\n");
    
    $run_counter++;
}
```

#### Schritt 5
Kopieren Sie Ihren Code und bauen Sie Ihre `while`-Schlife zu einer `for`-Schleife um, resp. umgekehrt.

```php
$runs = rand(1, 10);
print("Anzahl Durchl&auml;ufe: $runs<br><br>\n");

for($run_counter = 0; $run_counter < $runs; $run_counter++)
{
    $number = rand(1,100);

    if($number <= 30) $color = '#00FF00';
    else if($number >= 70) $color = '#FF0000';
    else if($number == 50) $color = '#0000FF';
    else $color = '#000000';

    if(($number < 20 || $number > 80) && $number%2 == 0)
    {
        $underline = "underline";
    }
    else
    {
        $underline = "normal";
    }

    print("<div style=\"color:$color; text-decoration:$underline\">$number</div>\n");
}
```


## Aufgabe 2
#### Schritt 1
Generieren Sie eine Schulnote (1-6) per Zufall.

#### Schritt 2
Geben Sie die Note als Zahl und als Wort (6 = "sehr gut", 5= "gut" usw.) aus:
> Note: 4 (genügend)

Verwenden Sie für diese Ausgabe ein `switch-case` Struktur.

```php
$maximal = rand(10,100);
$erreicht = rand(0,$maximal);
$note = round(($erreicht / $maximal * 5) + 1);

print("Es wurden $erreicht von $maximal Punkten erreicht.<br>\n");
print("Dies ergibt die Note: $note (");

switch($note) {
    case 1:
        print("schlecht");
        break;
    case 2:
        print("schwach");
        break;
    case 3:
        print("ungen&uuml;gend");
        break;
    case 4:
        print("gen&uuml;gend");
        break;
    case 5:
        print("gut");
        break;
    case 6:
        print("sehr gut"); 
        break;    
    default:
	    print("N/A"); 
}
print(")");
```


## Aufabe 3
Bauen Sie das Script aus Aufgabe 1 wie folgt um:
- Erstellen Sie eine Funktionso um da , welche die Aufgabe der Formatierung nach Bedingungen (Farbe /und unterstrichen) übernimmt.
	- Eingebeparameter: Zahl
	- Ausgabe: Formatiertes HTML-Code Segment
- Rufen Sie die Funktion innerhalb der Schleife entsprechend auf. 
```php
function formatNumber($number)
{
    if($number <= 30) $color = '#00FF00';
    else if($number >= 70) $color = '#FF0000';
    else if($number == 50) $color = '#0000FF';
    else $color = '#000000';

    if(($number < 20 || $number > 80) && $number%2 == 0)
    {
        $underline = "underline";
    }
    else
    {
        $underline = "normal";
    }
    return "<div style=\"color:$color; text-decoration:$underline\">$number</div>\n";
}

$runs = rand(1, 10);
print("Anzahl Durchl&auml;ufe: $runs<br><br>\n");

for($run_counter = 0; $run_counter < $runs; $run_counter++)
{
    $number = rand(1,100);
    print(formatNumber($number));    
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTQyMDM4MDE0XX0=
-->