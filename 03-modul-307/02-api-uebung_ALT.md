 [Modul 307 / Tag 3](/ilv.307/03-modul-307)

# API Übung: Chuck Norris
### Datenquelle
Unter folgender URL wird eine REST API angeboten, welche den Bezug von "Chuck Norris"-Jokes ermöglicht:
[http://www.icndb.com/api/](http://www.icndb.com/api/)


### Aufgabe
Studieren Sie die API-Dokumentation und erstellen Sie eine Web-Applikation zur Echtzeit-Abfrage der oben genannten API:
- Über ein HTML Formular lassen sich folgende Parameter eingeben:
	- Anzahl Jokes (Pflichtfeld, Ganzzahl, begrenzt auf 1 - 10)
	- Alternativer Vorname (optionales Feld)
	- Alternativer Nachname (optionales Feld)
	- Gewünschte Kategorien (Checkboxen, Mehrfachauswahl möglich)
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
eyJoaXN0b3J5IjpbODU1MjkwOTEzXX0=
-->