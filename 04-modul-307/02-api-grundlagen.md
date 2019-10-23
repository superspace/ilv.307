 [Modul 307 / Tag 4](/ilv.307/04-modul-307)

# API Grundlagen
### Was ist eine API?
- API = application programming interface
- Ein Teil einer Applikation, welcher anderen Applikationen einen Zugang zur Applikation und/oder deren Daten ermöglicht.

### REST (REpresentational State Transfer)
Neben anderen populären Technologien webbasierter API's (wie z.B. SOAP oder WSDL) hat sich REST zu einer der populärsten Technologien für den webbasierten Datenaustausch entwickelt.
 
REST ist kein eigenes Protokoll. Es werden zahlreiche bestehende Protokolle verwendet. So zum Beispiel `HTTP` für die Übertragung sowie `JSON` oder `XML` als Datenformat. Dabei wird auf die Einhaltung von 6 Prinzipien geachtet, auf die wir an dieser Stelle nicht weiter eingehen. Weitere Details:
[https://de.wikipedia.org/wiki/Representational_State_Transfer#Prinzipien](https://de.wikipedia.org/wiki/Representational_State_Transfer#Prinzipien)

 *Wir beschränken uns in diesem Kurs auf HTTP und JSON basierte REST API's.*

 

### REST per HTTP
Die folgenden 4 HTTP Methoden stehen in REST per HTTP grundsätzlich zur Verfügung:
-   **GET**  - fordert Daten vom Server an
-   **POST**  - übermittelt Daten an den Server
-   **PUT/PATCH**  - ändern bestehende Daten auf dem Server
-   **DELETE**  - löscht bestehende Daten auf dem Server

Dabei ist jedoch zu beachten, dass oft nur  GET und POST verwendet wird. Das Ändern von Daten erfolgt häufig ebenfalls über die POST Methode, während das Löschen von Datensätzen auch über einen URL-Parameter in einem GET Request gelöst werden kann. Dies entspricht nicht der offiziellen REST Definition, hat sich aber in der Praxis bewährt.

 *Wir beschränken uns in diesem Kurs auf die Implementierung von read-only API's per GET Methode.*

### Beispiel für einen GET Request (HTTP und JSON)
Meist werden die Parameter, welche an die API übermittelt werden sollen, per URL Parameter übergeben:
```
http://api.superheld.xyz/getHero?universe=marvel&popuplarity=5
```  
Als Antwort liefert die API die entsprechenden Datensätze im JSON Format:
```json
[
	{
		"name":"Iron Man",
		"universe":"Marvel",
		"popuplarity":5
	},
	{
		"name":"Thor",
		"universe":"Marvel",
		"popuplarity":5
	}
]
```  

### Implementation in PHP
Alle benötigten Werkzeuge zur Implementation einer HTTP-GET/JOSN API sind bereits bekannt:
- Die PHP-Funktion `file_get_contents` erlaubt auch das Lesen einer fernliegenden "Datei" 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MjIwODk2MDgsLTE4OTY2MDQ3MjYsLT
MwNTE1NzUwOV19
-->