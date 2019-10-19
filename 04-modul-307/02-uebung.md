# Virtuelle Abfahrtstafel (API Übung)
-	Eingebunden wird die API "Fahrplan" von search.ch: [https://fahrplan.search.ch/api/help](https://fahrplan.search.ch/api/help)
Diese stellt Fahrplan-Daten zu den öffentlichen Verkehrsmitteln in der Schweiz in verschiedenen Formen zur Verfügung.

## Teil 1: Datenbezug und Aufbereitung der Abfahrtstafel
-	Über einen URL Parameter kann ein Bahnhof (Ortschaft) definiert werden. 
-	Nach dem Aufruf wird eine virtuelle Abfahrtstafel für den eingegebenen Bahnhof und die aktuelle Zeit angezeigt.
	-	Wird keine entsprechende Haltestelle gefunden, wird eine entsprechende Fehlermeldung angezeigt.
-	Die Tafel soll schematisch der "echten" Abfahrtstafel entsprechen:
![SBB-Tafel](/ilv.307/assets/images/sbb-tafel.png)

-	Alle auf der Vorlage enthaltenen Daten müssen zwingend abgebildet sein.
-	Grafisch muss die Darstellung nicht exakt identisch sein. 

## Teil 2: Konfigurations-Interface
- Auf einer separaten Seite soll ein Interface zur Konfiguration der Abfahrtstafel angeboten werden.
- Die Konfigurationsdaten sollen dafür in eine JSON-Datei geschrieben und beim Laden der Abfahrtstafel von dort geladen werden.
- Folgende Konfigurationen sollen mindestens möglich sein:
	- Eingabe des Bahnhofes (anstelle des URL-Parameters)
	-  Umstellen zwischen Abfahrts- und Ankunftstafel
	- Maximale Anzahl Verbindungen
	- Transportmittel, welche Angezeigt werden sollen (Zug, Tram, Bus. Schiff, Seilbahn)
	- Verspätungen anzeigen (ja/nein)
	- Gl 


## Zusatzaufgaben: 
- Für die Eingabe des Bahnhofes kann vorab eine Suche durchgeführt werden.
- Die Anzeige aktualisiert sich alle 60 Sekunden selbst, ohne die komplette Seite neu zu laden. (z.B. über AJAX)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk1MjE5MTc2MiwxODIzOTg4NzkyLC0xMD
U5NjE5MTA0LC0xNDIwNjEyOTY4XX0=
-->