# Virtuelle Abfahrtstafel (API Übung)
-	Eingebunden wird die API "Fahrplan" von search.ch: [https://fahrplan.search.ch/api/help](https://fahrplan.search.ch/api/help)
Diese stellt Fahrplan-Daten zu den öffentlichen Verkehrsmitteln in der Schweiz in verschiedenen Formen zur Verfügung.

## Teil 1: Datenbezug und Aufbereitung der Abfahrtstafel
-	Über einen URL Parameter kann ein Bahnhof (Ortschaft) definiert werden. 
-	Nach dem Aufruf wird eine virtuelle Abfahrtstafel für den eingegebenen Bahnhof und die aktuelle Zeit angezeigt.
	-	Wird keine entsprechende Haltestelle gefunden, wird eine entsprechende Fehlermeldung angezeigt.
-	Die Tafel soll schematisch der (echten) Abfahrtstafel entsprechen:
![SBB-Tafel](/ilv.307/assets/images/sbb-tafel.png)

-	Alle auf der Vorlage enthaltenen Daten müssen zwingend abgebildet sein.
-	Die Darstellung soll nach demselben Schema erfolgen.
-	Grafisch muss die Darstellung nicht exakt identisch sein.
-	Die Zugsbezeichnungen (z.B. S1, S3, IC, ICE usw.) sollen als dynamisch generierte Grafiken eingebunden werden und möglichst der Vorlage entsprechen.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwMTk3Mjc0MjcsLTE0MjA2MTI5NjhdfQ
==
-->