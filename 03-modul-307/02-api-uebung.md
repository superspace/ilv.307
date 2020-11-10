 [Modul 307 / Tag 3](/ilv.307/03-modul-307)

# API Übung: Fahrplan Abfrage
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
- Eine Verbindung besteht aus mindestens zwei, oder bei Umsteigen mehreren Stationen.
- Für jede Station werden folgende Daten (falls vorhanden) angegeben: 
	- Stationsname
	- Ankunftszeit
	- Abfahrtszeit mit Gleis und Zugnummer

Die Ausgabe könnte zum Beispiel so aussehen:

![enter image description here](https://lh3.googleusercontent.com/v4FRhh_GoNH2yiWb39iPk1c6emOFmdNcTZaTx76z4vzyzIsjxKaIDdotb7DIctCV9aQhWaWLMtuT "Fahrplan Ausgabe")

###  Vorgaben
Folgende Vorgaben müssen erfüllt sein:
- Es müssen sinnvolle HTML5 Feldtypen gewählt werden.
- Den Formularfeldern müssen entsprechende `label`-Tags zugewiesen werden.

### Zusatzaufgaben
- Bauen Sie folgende zusätzlichen Funktionen ein:
	- Zeigen Sie in der Ausgabe allfällig zu erwartende Verspätungen an.
	- Der Benutzer kann eine Einschränkung von Verkehrsmitteln (z.B. nur mit Zug, Tram, Bus, etc.) vorgeben.
	- Der Benutzer kann definieren, ob er zur angegebenen Zeit losfahren oder ankommen möchte.
	- Der Benutzer kann die maximale Anzahl  Verbindungen selbst definieren.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxMDA5OTI0MzAsMTU2Mzk1NjA1MCw3Mj
kxOTc2NTAsMTkxNzIzMDMzMSwxNTM2MTY4NjgwLDEyMTQ1NTM5
MzksLTIxNjA3MTI1Miw4NTUyOTA5MTNdfQ==
-->