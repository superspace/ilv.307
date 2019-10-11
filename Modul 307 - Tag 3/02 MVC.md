
# MVC Design-Pattern

Eine einfachen PHP-Anwendung mit dem MVC Design-Pattern

*Wir arbeiten bewusst ohne Framework und verzichten auf einen Router.*

MVC steht für Model – View – Controller und hilft uns dabei, eine Anwendung sinnvoll zu strukturieren. Wir verfolgend dabei unter anderem folgende Zielsetzungen:

- Trennung von Daten, Darstellung und Logik
- Wiederverwendung
- Erweiterbarkeit

Der Grundsatz entspricht der Forderung, dass jede Einheit eine klare Aufgabe hat, und diese Aufgabe möglichst ohne Wissen über die anderen Einheiten erfüllen kann.

Ziel des Musters ist ein flexibler Programmentwurf, der eine spätere Änderung oder Erweiterung erleichtert und eine Wiederverwendbarkeit der einzelnen Komponenten möglich macht.

## Trennung von Daten, Darstellung und Logik

### Daten (Model)
Im Model sind unsere Datenfelder sowie die Schnittstelle zur Datenhaltung definiert. 

*In unserem Fall ist dies konkret eine Klasse mit den Attributen Titel, Beschreibung und Rating. Die Schnittstelle zur Datenhaltung entspricht dem Lesen- und Schreiben der Daten in das JSON-File.* 

### Darstellung (View)
Alles was in HTML ausgegeben wird, gehört zur View. 

*Dies umfasst die Listenansicht wie auch unsere Eingabemaske.*

### Steuerung (Controller)
Der Controller nimmt die Benutzer-Inputs auf und steuert die Daten zwischen dem Model und der View.

## Wiederverwendung
Die Trennung des Datenmodells von der Datenhaltung erlaubt uns z.B. später einen Wechsel von der Datenhaltung in JSON zu einer Datenbank vorzunehmen. Zudem kann so die Schnittstelle zur Datenhaltung von verschiedenen Modellen wiederverwendet werden.

## Erweiterbarkeit
Da die Struktur der Anwendung klar definiert ist, lassen sich zusätzliche Funktionen relativ einfach hinzufügen.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ2ODc5NTA5MCwtOTgxMzI5MDY5XX0=
-->