 [Modul 307 / Tag 4](/ilv.307/04-modul-307)

# Übung KNW
## Wetter-Screen

### API
Für diese Aufgabe verwenden Sie folgende API:
[openweathermap.org](https://openweathermap.org/current)

*HINWEIS: Zur kostenlosen Nutzung der API bedarf es einer Registration. Sie können sich mit Ihrer `@gibmit.ch` Adresse oder eine Adresse Ihrer Wahl registrieren.*

### Auftrag

#### Frontend
Auf Bildschirmen, die an öffentlichen Orten montiert sind, sollen die aktuellen Wetterdaten vier verschiedener Ortschaften angezeigt werden:
![Wetter Screen](https://toive.ch/m307/screen.jpg)

Für jede Ortschaft werden folgende Attribute angezeigt:

- Offizieller Name sowie das Land der Ortschaft
- Wetterlage (als Icon)
- Temperatur (auf eine Kommastelle gerundet)
- Relative Luftfeuchtigkeit in %
- Luftdruck in hPa
- Windrichtung als Pfeil dargestellt
- Windgeschwindigkeit

![Wetter Screen](https://toive.ch/m307/wetterdaten-single.PNG)

*HINWEIS: Die Icons sind unter folgender URL zu finden: [http://openweathermap.org/img/wn/10d@2x.png](http://openweathermap.org/img/wn/10d@2x.png) (`10d = icon-code`)*

 
#### Backend
Auf einer separaten Seite (Backend) soll es möglich sein, die Ausgabe auf dem Screen (Frontend) über ein Formular zu konfigurieren.  Folgende Einstellungen können getätigt werden:
- Die vier angezeigten Ortschaften können frei konfiguriert werden.
- Die Masseinheiten von Windgeschwindigkeit und Temperatur können zwischen metrisch und imperial umgestellt werden. 
- Die Luftfeuchtigkeit kann ein oder ausgeschaltet werden.
- Die Überschrift kann frei definiert werden.
- Die Hintergrundfarben können frei definiert werden.

Die Konfiguration soll in einer JSON-Datei abgelegt werden.
Wenn das Konfigurationsformular geladen wird, soll es mit den aktuellen Werte vorausgefüllt sein.

[Vorlage](/ilv.307/04-modul-307/weather.zip)