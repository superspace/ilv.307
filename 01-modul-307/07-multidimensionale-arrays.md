# Multidimenionale Arrays
- Von `multidimensionale Arrays` spricht man, wenn Arrays als Elemente in eines Arrays gespeichert sind.  Die Arrays sind somit ineinander verschachtelt.
- Damit lassen sich einfach hierarchische Strukturen abbilden.
 
 ### Beispiel
 Ein Flugzeug besteht aus verschiedenen Attributen:
 ```php
 $flugzeug = Array('registrierung' => 'HB-ABC','hersteller' => 'Airbus','Typ' => 'A380');
 ```
 Wir können in einem Array mehrere Flugzeuge speichern, in dem wir die einzelnen Flugzeug-Arrays in einen übergeordneten Array verpacken:
   ```php
 $flugzeuge = Array(
		 Array('registrierung' => 'HB-ABC','hersteller' => 'Airbus','typ' => 'A380'),
		 Array('registrierung' => 'HB-CDE','hersteller' => 'Boeing','typ' => 'B777'),
		 Array('registrierung' => 'HB-ZCD','hersteller' => 'Piper','typ' => 'Archer')
		 );
 ```

Der Zugriff auf ein bestimmtes Element in der mehrdimensionalen Struktur erfolgt durch aneinanderreihen von Indices/Keys:
 ```php
print('Hersteller:' . $flugzeuge[0]['hersteller']);  
//1.Dimension: Flugzeug mit Index 0  -  2.Dimension: Key "hersteller"
```
> Hersteller: Airbus

Für die komplette Ausgabe wird der übergerodnete Array `$flugzeuge` mittels `foreach()` geloopt. Innerhalb des Loops stehen nun die einzelnen Flugzeug-Arrays zur Verfügung, aus welchen die Attribute ausgelesen werden können:
```php
foreach ($flugzeuge  as  $flugzeug)
{
	print("Registrierung: {$flugzeug['registrierung']}<br>\n");
	print("Hersteller: {$flugzeug['hersteller']}<br>\n");
	print("Typ: {$flugzeug['typ']}\n");
	print("----------<br>\n");
}
```

 > Registrierung: HB-ABC  
    Hersteller: Airbus  
    Typ: A380
    ----------
    Registrierung: HB-CDE  
    Hersteller: Boeing  
    Typ: B777
    ----------
    Registrierung: HB-ZCD  
    Hersteller: Piper  
    Typ: Archer
    ----------


Alternativ können durch einen weiteren Loop alle Attribute dynamisch ausgelesen werden:
```php
foreach ($flugzeuge as $flugzeug)
{
        foreach($flugzeug AS $attribut => $wert)
        {
            print("$attribut: $wert<br>\n");
        }
        print("----------<br>\n");
}
```
 > registrierung: HB-ABC  
    hersteller: Airbus  
    typ: A380
    ----------
    registrierung: HB-CDE  
    hersteller: Boeing  
    typ: B777
    ----------
    registrierung: HB-ZCD  
    hersteller: Piper  
    typ: Archer
    ----------
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyOTU4NDg0MDhdfQ==
-->