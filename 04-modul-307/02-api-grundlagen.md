 [Modul 307 / Tag 4](/ilv.307/04-modul-307)

# API Grundlagen
### Was ist eine API?
- API = application programming interface
- Ein Teil einer Applikation, welcher anderen Applikationen einen Zugang zur Applikation und/oder deren Daten ermöglicht.

### REST (REpresentational State Transfer)
Neben anderen populären Technologien webbasierter API's (wie z.B. SOAP oder WSDL) hat sich REST zu einer der populärsten Technologien für den webbasierten Datenaustausch entwickelt.
 
REST ist kein eigenes Protokoll. Es werden zahlreiche bestehende Protokolle verwendet. So zum Beispiel `HTTP` für die Übertragung sowie `JSON` oder `XML` als Datenformat. Dabei wird auf die Einhaltung von 6 Prinzipien geachtet, auf die wir an dieser Stelle nicht weiter eingehen. Weitere Details:
[https://de.wikipedia.org/wiki/Representational_State_Transfer#Prinzipien](https://de.wikipedia.org/wiki/Representational_State_Transfer#Prinzipien)

 Wir beschränken uns in diesem Kurs auf HTTP und JSON basierte REST API's.

 

### REST per HTTP
Die folgenden 4 HTTP Methoden stehen in REST per HTTP grundsätzlich zur Verfügung:
-   **GET**  - fordert Daten vom Server an
-   **POST**  - übermittelt Daten an den Server
-   **PUT/PATCH**  - ändern bestehende Daten auf dem Server
-   **DELETE**  - löscht bestehende Daten auf dem Server

Dabei ist jedoch zu beachten, dass üblicherweise nur  GET und POST verwendet wird. F 
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTA0MTIyODkxLC0xODk2NjA0NzI2LC0zMD
UxNTc1MDldfQ==
-->