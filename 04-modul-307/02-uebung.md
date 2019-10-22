
# API Übung: Chuck Norris
### Datenquelle
Unter folgender URL wird eine REST API angeboten, welche den Bezug von "Chuck Norris"-Jokes ermöglicht. 
[http://www.icndb.com/api/](http://www.icndb.com/api/)


### Aufgabe
Studieren Sie die API-Dokumentation und erstellen Sie eine Web-Applikation zur Echtzeit-Abfrage der oben genannten API.
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
- Alle Felder müssen in HTML5 und serverseitig validiert werden.
- Den Formularfeldern müssen entsprechende `lable`-Tags zugewiesen werden.
- Die verfügbaren Kategorien müssen in Echtzeit aus der API abgefragt werden.
-  
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MzY0MDIzMjUsNDk3ODE4ODEwLC04NT
c4MjQ5MzksMTQ5NDQyODAwNSwxODIzOTg4NzkyLC0xMDU5NjE5
MTA0LC0xNDIwNjEyOTY4XX0=
-->