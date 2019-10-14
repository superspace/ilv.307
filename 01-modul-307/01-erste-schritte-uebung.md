 [Modul 307 / Tag 1](/ilv.307/01-modul-307)

# Übung: Erste Schritte mit PHP

#### Strings und Zeilenumbruch

Schreiben Sie ein Script, welches folgende Ausgabe macht:
```
Ich übe PHP
PHP gefällt mir
```
Der Zeilenumbruch soll **sowohl** in der normalen Browser-Ansicht, **als auch** im HTML-Quellcode vorhanden sein. Was ist diesbezüglich zu beachten?

#### Ausgaben
Recherchieren Sie die Unterschiede zwischen  `print` und `echo`. Testen Sie die Unterschiede in einem Script. 

#### Variablen
Erstellen Sie:
-- eine Variable mit dem Namen `vorname` und Ihrem Vorname als Wert.
-- eine Variable mit dem Namen `nachname` und Ihrem Nachname als Wert.
-- eine Variable mit dem Namen `jahr` und Ihrem Geburtsjahr als Wert.

#### Datentypen I
Was müssen Sie tun, damit `vorname` und `nachname` als `STRING` und `jahr` als `INT` erstellt wird?
Beantworten Sie diese Frage direkt im Code als Kommentar.
*Tipp: Zum Debugen von Datentypen eignet sich die Funktionen `gettype()` und `var_dump()`*

#### Datentypen II
Stellen Sie sicher, dass die Variable `jahr` den Datentypen `float` aufweist.
Welche weiteren Datentypen gibt es in PHP? 

#### Ausgeben und Verkettung von Strings
Erweitern Sie vorhergehendes Script so, dass folgender Satz ausgegeben wird:

> Mein Name ist Paul Hubacher und ich bin 1980 geboren.

Vorname, Nachname und Jahr sollen von den Variablen stammen, der Rest des Satzes soll direkt ausgegeben werden.

Verändern Sie die Ausgabe nun so, das folgender Satz angezeigt wird. Achten Sie dabei auf die Ausgabe des `s` nach dem Nachnamen.
> 1980 ist Paul Hubachers Geburtstag

Nun soll die Ausgabe wie folgt erfolgen:
> 1980 ist Paul Hubacher's "Gebrtstag" 

#### Rechnen I
Verändern Sie das vorhergehende Script so, dass die Ausgabe nun wie folgt lautet:

> Mein Name ist Paul Hubacher und ich bin 35 Jahre alt.

Das Alter soll an Hand der Variable `jahr` und dem aktuellen Jahr berechnet werden.
*(Sie dürfen das aktuelle Jahr hartcodiert benutzen.)*


#### Rechnen II
Recherchieren Sie alle in PHP verfügbaren mathematischen Operatoren und machen Sie zu jedem ein praktisches Beispiel.

#### Datum I
Testen Sie, was der Aufruf der Funktion `time()` zurückgibt. Was hat diese Rückgabe zu bedeuten?
Bringen Sie PHP dazu, die Ausgabe in ein menschlich lesbares Format zu zeigen.

#### Datum II
Geben Sie das Datum im Format `dd.mm.jjjj` und den Wochentag aus, welcher heute in 215 Tagen ist.

 
#### Array I: erstellen
Erstellen Sie einen Array mit 7 Elementen, wobei jedes Element als Wert einer der sieben Wochentage enthält. (Montag, Dienstag, Mittwoch usw.)
*Tipp zur Funktionskontrolle: Die Struktur eines Arrays können Sie mittels der Funktion `print_r()` analysieren.* 

#### Array II: loopen
Finden Sie heraus, wie sie am einfachsten einen Loop durch alle Elemente des Arrays machen können. Innerhalb des Loops geben Sie die Werte gefolgt von einem Zeilenumbruch aus:
> Montag 
> 
> Dienstag
> 
> Mittwoch
> Donnerstag
> Freitag
> Samstag
> Sonntag

#### Array III: sortieren
Fügen Sie zwischen der Erstellung des Arrays und der Ausgabe eine Codezeile ein, welche die Werte im Array alphabetisch sortiert. Die Ausgabe soll danach wie folgt aussehen:

> Dienstag
> Donnerstag
> Freitag
> Mittwoch
> Montag
> Samstag
> Sonntag
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTkwMjk0NjE1MywxNjA5MTUyNTkzLC0xOD
M5NzIxNTQwXX0=
-->