
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
ssss
```

#### Schritt 3
Färben Sie die Zahlen gemäss folgender Anweisungen ein:
- Zahlen die `30 oder kleiner` sind: grün
- Zahlen die `70 oder grösser` sind: rot
- Die Zahl `50`: blau
```php
ssss
```

#### Schritt 4
Unterstreichen Sie alle `geraden Zahlen` die grösser `kleiner als 20` oder `grösser als 80` sind.

```php
ssss
```

#### Schritt 5
Kopieren Sie Ihren Code und bauen Sie Ihre `while`-Schlife zu einer `for`-Schleife um, resp. umgekehrt.

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
        $fontweight = "underline";
    }
    else
    {
        $fontweight = "normal";
    }

    print("<div style=\"color:$color; text-decoration:$fontweight\">$number</div>\n");
    
    $run_counter++;
}
```


## Aufgabe 2
#### Schritt 1
Generieren Sie eine Schulnote (1-6) per Zufall.

#### Schritt 2
Geben Sie die Note als Zahl und als Wort (6 = "sehr gut", 5= "gut" usw.) aus:
> Note: 4 (genügend)

Verwenden Sie für diese Ausgabe ein `switch-case` Struktur.


## Aufabe 3
Bauen Sie das Script aus Aufgabe 1 wie folgt um:
- Erstellen Sie eine Funktionso um da , welche die Aufgabe der Formatierung nach Bedingungen (Farbe /und unterstrichen) übernimmt.
	- Eingebeparameter: Zahl
	- Ausgabe: Formatiertes HTML-Code Segment
- Rufen Sie die Funktion innerhalb der Schleife entsprechend auf. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNjA2NTQwMDcsLTEyNTc3NzEzMV19
-->