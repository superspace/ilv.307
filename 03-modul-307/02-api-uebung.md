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
- Nach dem Absenden des Formulars werden die entsprechenden Datensätze angezeigt, bestehend aus:
	- Joke
	- Kategorie(n)
	- Joke-ID

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
eyJoaXN0b3J5IjpbOTkxNjI4MTYsMTIxNDU1MzkzOSwtMjE2MD
cxMjUyLDg1NTI5MDkxM119
-->