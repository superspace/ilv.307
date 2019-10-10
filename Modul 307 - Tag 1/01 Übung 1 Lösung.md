# Lösungen: Erste Schritte mit PHP
#### Strings und Zeilenumbruch

```php
print("Ich &uuml;be PHP<br>\nPHP gef&auml;llt mir");   
```
- `<br>` ist für die HTML-Ausgabe und `\n` für PHP (Umbruch im Quelltext)
- Mit `PHP` generiert man `HTML-Code`!

#### Ausgaben
```php
print "Hallo ";
echo "Hallo ", $name, ", wie geht es Dir?";
```
- Während `print` nur ein Argument entgegen nimmt, kann `echo` mehrere Argumente entgegennehmen und gibt diese nacheinander aus.
```php
print ("Hallo");
echo ("Hallo");
```
- Sowohl `print` als auch `echo` kann mit oder ohne Klammern geschrieben werden.

#### Variablen
```php
$vorname = "Stefan";
$nachname = "Huber";
$jahr = 1983;
```

#### Datentypen I
```php
print("vorname:".gettype($vorname)."<br>");
print("jahr: ".gettype($jahr)."<br>");
```
- Die Datentypen werden von PHP automatisch vergeben. 

#### Datentypen II

```php
$jahr = (float) 1983;
```
- Ein bestimmter Datentyp kann erzwungen werden. 


#### Ausgeben und Verkettung von Strings

```php
print("Mein Name ist $vorname $nachname und ich bin $jahr geboren.");
print('Mein Name ist '.$vorname.' '.$nachname.' und ich bin '.$jahr.' geboren.<br>');
```
- In über double quotes `"` defineirte Strings können variabeln integriert werden, dies geht bei single quotes `'`nicht.
-  Mehrere Strings können über einen Punkt `.` zusammengehängt werden. 
```php
print("$jahr ist $vorname {$nachname}s Geburtstag.");
```
- Variabeln können bei Bedarf durch Curly Brackets `{}` abgegrenzt werden.
```php
print("$jahr ist $vorname {$nachname}\'s \"Geburtstag\".");
```
- Sonderzeichen wie `'` oder `"` werden durch einen Backslash `\` eingeleitet. Auch ein Backslash selbst wird durch einen Backslash eingeleitet: 
```php
print("Der Pfad lautet Modul307\\Uebung");
```
#### Rechnen I

```php
$alter = 2015 - $jahr;
print("Mein Name ist ".$vorname." ".$nachname." und ich bin ".$alter." Jahre alt.<br>");
//oder direkt in der Ausgabe:
print("Mein Name ist ".$vorname." ".$nachname." und ich bin ".(2015-$jahr)." Jahre alt.<br>");
```
- Die Berechnung kann in einer zusätzlichen Variabel vorab oder direkt in der Ausgabe berrechnet werden.
  
#### Rechnen II
```php
print("3 + 3 = " . (3+3) . "<br>"); //Addition
print("10 - 3 = " . (10-3) . "<br>"); //Subtraktion
print("8 * 4 = " . (8*4) . "<br>"); //Multiplikation
print("10 / 2 = " . (10/2) . "<br>"); //Division
print("14 % 3 = " . (14%3) . "<br>"); //Modulo
```

#### Datum I
```php
$heute = time();
print($heute);
```
- Ausgegeben wird ein `Unix Timestamp` (Anzahl Sekunden seit 01.01.1970):
> 1570630274
```php
$heute = time();
print(date("d.m.Y", $heute));
```
- Die Funktion `date()` formatoiert einen Unix Timestamp um. Dabei im String-Parameter 1   verschiedenste Zeichen als Platzhalter verwendet werden.
- Wenn Parameter 2 (der Timestamp) weggelassen wird, wird der aktuelle Timestamp verwendet.
- Eine Liste der möglichen Zeichen: [https://www.php.net/manual/de/function.date.php](https://www.php.net/manual/de/function.date.php)

#### Datum II
```php
$neues_datum = $heute + (215*24*60*60);
print(date("D, d.m.Y", $neues_datum));
```
- Dem aktuellen Timestamp werden die Anzahl Sekunden innert 215 tagen addiert.
- An Stelle der Berechnung kann natürlich auch direkt der Wert eingegeben werden, was aber weniger leserlich ist:
```php
$neues_datum = $heute + 18576000;
```
 
#### Array I: erstellen
Definition über die Funktion `Array()`. Es werden automatisch fortlaufende Indizes generiert:
```php
$wochentage = Array("Montag", "Dienstag", "Mittwoch", "Donnerstag", "Freitag", "Samstag", "Sonntag");
```
Definition über leere Square brackets `[]`. Es werden automatisch fortlaufende Indizes generiert:
```php
$wochentage[] = "Montag";
$wochentage[] = "Dienstag";
$wochentage[] = "Mittwoch";
$wochentage[] = "Donnerstag";
$wochentage[] = "Freitag";
$wochentage[] = "Samstag";
$wochentage[] = "Sonntag";
```
Definition über manuell definierte Indices in den Square brackets `[]`.:
```php
$wochentage[1] = "Montag";
$wochentage[2] = "Dienstag";
$wochentage[3] = "Mittwoch";
$wochentage[4] = "Donnerstag";
$wochentage[5] = "Freitag";
$wochentage[6] = "Samstag";
$wochentage[7] = "Sonntag";
```
An Stelle von Indices können auch alphanumerische Keys genutzt werden. Man spricht dann von einem `assoziativen Array`:
```php
$wochentage['mo'] = "Montag";
$wochentage['di'] = "Dienstag";
$wochentage['mi'] = "Mittwoch";
$wochentage['do'] = "Donnerstag";
$wochentage['fr'] = "Freitag";
$wochentage['sa'] = "Samstag";
$wochentage['so'] = "Sonntag";
//oder:
$wochentage = Array('mo' => "Montag", 'di' => "Dienstag", 'mi' => "Mittwoch", 'do' => "Donnerstag", 'fr' => "Freitag", 'sa' => "Samstag", 'so' => "Sonntag");
```

#### Array II: loopen
```php
foreach($wochentage AS $tag)
{
	print("$tag<br>");
}
```
- `foreach()`extrahiert die Elemente eines Arrays in einem Loop und stellt deren Werte innerhalb des Loops zur Verfügung.
- Neben den Werten können auch die Keys eines assoziativen Arrays ausgegeben werden:
```php
foreach($wochentage AS $key => $tag)
{
	print("$tag ($key)<br>");
}
```
 
#### Array III: sortieren

```php
asort($wochentage);
foreach($wochentage AS $tag)
{
	print($tag."<br>");
}
```
- Die Funktion `asort()` sortiert die Elemente eines Arrays alphanumerisch nach deren Werten.
- *Tipp: Multidimensionale Arrays können mittels `array_multisort()` sortiert werden: [https://www.php.net/manual/de/function.array-multisort.php](https://www.php.net/manual/de/function.array-multisort.php)*  


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUxMDc2OTQ0XX0=
-->