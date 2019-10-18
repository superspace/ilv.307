 [Modul 307 / Tag 1](/ilv.307/01-modul-307)
 
# Übung: Kontrollstrukturen anwenden

## Aufgabe 1

#### Schritt 1
Generieren Sie in einer Variable `$runs` eine Zufallszahl von 1 bis 10 und zeigen Sie diese an.
*Tipp: Verwenden Sie hierzu* `rand()`

#### Schritt 2
Durchlaufen Sie eine Schleife `$runs` Mal und geben Sie bei jedem Durchlauf eine Zufallszahl zwischen 1 und 100 aus.

#### Schritt 3
Färben Sie die Zahlen gemäss folgender Anweisungen ein:
- Zahlen die `30 oder kleiner` sind: grün
- Zahlen die `70 oder grösser` sind: rot
- Die Zahl `50`: blau

#### Schritt 4
Unterstreichen Sie alle `geraden Zahlen` die `kleiner als 20` oder `grösser als 80` sind.

#### Schritt 5
Kopieren Sie Ihren Code und bauen Sie Ihre `while`-Schlife zu einer `for`-Schleife um, resp. umgekehrt.


## Aufgabe 2
#### Schritt 1
Generieren Sie eine Schulnote (1-6) per Zufall nach folgender Formel:
`(Erreichte Punktezahl / Maximale Punktezahl * 5) + 1`
Sowohl die erreichte wie auch die maximale Punktezahl sollen per Zufall generiert werden. Beachten Sie dabei:
- Die erreichte Punktezahl darf nicht grösser als die maximale Punktezahl sein!
- Es muss auf ein "ganze" Noten gerundet werden.

#### Schritt 2
Geben Sie die Note als Zahl und als Wort (6 = "sehr gut", 5= "gut" usw.) aus:
> Note: 4 (genügend)


## Aufgabe 3
Bauen Sie das Script aus Aufgabe 1 wie folgt um:
- Erstellen Sie eine Funktion, welche die Aufgabe der Formatierung nach Bedingungen (Farbe/unterstrichen) übernimmt.
	- Eingebeparameter: Zahl
	- Ausgabe: Formatiertes HTML-Code Segment
- Rufen Sie die Funktion innerhalb der Schleife entsprechend auf. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NjQzMjE4MDksNjI1OTY5MTUwXX0=
-->