
# File-Handling

## Lesen und Schreiben von Dateien
Mit PHP können Dateien auf dem Filesystem erstellt, gelesen und modifiziert werden. *VORSICHT* Diese Funktionen sind irreversibel und können auch grossen Schaden auf dem System anrichten!

### Datei lesen

Mit `readfile()` wird eine Datei gelesen und direkt ausgegeben. Wir haben aber keine Möglichkeit, den Inhalt zu verarbeiten.

Die Funktionen `fopen()` ,  `fread()` und `fclose()` geben uns mehr Kontrolle bei der Verarbeitung der Datei. So können beispielsweise sehr grosse Dateien als Stream gelesen werden und es ist auch möglich, Dateien über ein Netzwerk (z.B. http://) zu öffnen.

https://www.php.net/manual/de/function.fopen.php

Mit  `file_get_contents()` lassen sich Dateien lokal wie auch im Netzwerk öffnen. Die Funktion übergibt den Inhalt der Datei in einen String. Diese Funktion ist ein sogenannte Wrapper, im Hintergrund wird `fopen()` und `fread()` ausgeführt.

https://www.php.net/manual/de/function.file-get-contents.php

## Datei schreiben

Ach hier können `fopen()`, `fwrite()` und `fclose()` verwendet werden.

Die Funktion `file_put_contents()` ist ein Wrapper für die oben genannten Funktionen und erledigt die Aufgabe mit einem Funktionsaufruf. 

https://www.php.net/manual/de/function.file-put-contents.php

##### Datei erstellen

Neue Dateien können mit der Funktion `fopen()` erzeugt werden.

`file_put_contents()` erstellt automatisch fehlende Dateien.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAxNzAwMDc1NiwtOTQzNzcyMDQzLDIwMT
cwMDA3NTZdfQ==
-->