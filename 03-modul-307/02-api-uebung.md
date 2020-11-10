 [Modul 307 / Tag 3](/ilv.307/03-modul-307)

# API Übung: Fahrplan Anfrage
### Datenquelle
Die Firma Swisscom Directories AG bietet eine frei verfügbare API auf JSON-Basis zum Bezug von Fahrplandaten in der Schweiz:
[https://fahrplan.search.ch/api/help](https://fahrplan.search.ch/api/help)


### Aufgabe
Studieren Sie die API-Dokumentation für die Methode `Routensuchen` und erstellen Sie eine Web-Applikation zur Echtzeit-Abfrage der oben genannten API:
- Über ein HTML Formular lassen sich folgende Parameter eingeben:
	- Abfahrtsort
	- Zielort
	- Datum
	- Uhrzeit
- Nach dem Absenden des Formulars werden maximal 5 Verbindungen angezeigt. 
- Eine Verbindung besteht aus mindestens zwei oder bei Umsteigen mehr Stationen.
- Für jede Station werden folgende Daten (falls vorhanden) angegeben: 
	- Stationsname
	- Ankunftszeit
	- Abfahrtszeit mit Gleis und Zugnummer

Die Ausgabe könnte zum Beispiel so aussehen:
![enter image description here](https://picasaweb.google.com/115082439297599357168/6893416633931035553#6893416638512693538 "Fahrplan Ausgabe")

###  Vorgaben
Folgende Vorgaben müssen erfüllt sein:
- Es müssen sinnvolle HTML5 Feldtypen gewählt werden.
- Alle Felder müssen in HTML5 und serverseitig validiert werden.
- Den Formularfeldern müssen entsprechende `label`-Tags zugewiesen werden.

### Zusatzaufgabe
- Einzelne Jokes können mit "gefällt mir" markiert werden:
	- Diese werden in der Folge in einer JSON-Datei gespeichert.
	- In einer separaten Ansicht können die mit "gefällt mir" markierten Jokes angesehen werden.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA3MzI5NzUzOSwxOTE3MjMwMzMxLDE1Mz
YxNjg2ODAsMTIxNDU1MzkzOSwtMjE2MDcxMjUyLDg1NTI5MDkx
M119
-->