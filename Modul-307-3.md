---


---

<h3 id="tag-2">Tag 2</h3>
<h1 id="mvc-design-pattern">MVC Design-Pattern</h1>
<p>Eine einfachen PHP-Anwendung mit dem MVC Design-Pattern</p>
<p><em>Wir arbeiten bewusst ohne Framework und verzichten auf einen Router.</em></p>
<p>MVC steht für Model – View – Controller und hilft uns dabei, eine Anwendung sinnvoll zu strukturieren. Wir verfolgend dabei unter anderem folgende Zielsetzungen:</p>
<ul>
<li>Trennung von Daten, Darstellung und Logik</li>
<li>Wiederverwendung</li>
<li>Erweiterbarkeit</li>
</ul>
<p>Der Grundsatz entspricht der Forderung, dass jede Einheit eine klare Aufgabe hat, und diese Aufgabe möglichst ohne Wissen über die anderen Einheiten erfüllen kann.</p>
<p>Ziel des Musters ist ein flexibler Programmentwurf, der eine spätere Änderung oder Erweiterung erleichtert und eine Wiederverwendbarkeit der einzelnen Komponenten möglich macht.</p>
<h3 id="trennung-von-daten-darstellung-und-logik">Trennung von Daten, Darstellung und Logik</h3>
<h4 id="daten-model">Daten (Model)</h4>
<p>Im Model sind unsere Datenfelder sowie die Schnittstelle zur Datenhaltung definiert.</p>
<p><em>In unserem Fall ist dies konkret eine Klasse mit den Attributen E-Mail, Rating und Datum. Die Schnittstelle zur Datenhaltung entspricht dem Lesen- und Schreiben der Daten in das JSON-File.</em></p>
<h4 id="darstellung-view">Darstellung (View)</h4>
<p>Alles was in HTML ausgegeben wird, gehört zur View.</p>
<p><em>Dies umfasst die Listenansicht wie auch unsere Eingabemaske.</em></p>
<h4 id="steuerung-controller">Steuerung (Controller)</h4>
<p>Der Controller nimmt die Benutzer-Inputs auf und steuert die Daten zwischen dem Model und der View.</p>
<h3 id="wiederverwendung">Wiederverwendung</h3>
<p>Die Trennung des Datenmodells von der Datenhaltung erlaubt uns z.B. später einen Wechsel von der Datenhaltung in JSON zu einer Datenbank vorzunehmen. Zudem kann so die Schnittstelle zur Datenhaltung von verschiedenen Modellen wiederverwendet werden.</p>
<h3 id="erweiterbarkeit">Erweiterbarkeit</h3>
<p>Da die Struktur der Anwendung klar definiert ist, lassen sich zusätzliche Funktionen relativ einfach hinzufügen.</p>
<h2 id="umsetzung">Umsetzung</h2>
<p>Das Arbeitsbeispiel «Ratings» soll nun in ein MVC Design-Pattern überführt werden.</p>
<p>Als Grundlage dient uns folgende Dateistruktur:</p>
<pre><code>data/
	items.json          // Datenhaltung in JSON-File
model/
	item.class.php      // Klassenmodell mit Attributen
	storage.class.php   // Schnittstelle zur Datenhaltung 
public/
	index.php           // Ansicht im Web-Root 
view/
	create.php          // HTML-Formular für neuen Eintrag
	list.php            // Auflistung der Einträge
controller.php              // Steuerung
</code></pre>
<p><em>data/items.json</em></p>
<p>Das JSON-File zur Speicherung der Daten.</p>
<p><em>model/item.class.php</em></p>
<p>Das File <code>item.class.php</code> enthält die Klasse <code>Item</code> mit den benötigten Attributen und der Eingabe-Verabeitung und Validierung. Die Klasse <code>Item</code> erweitern die Klasse <code>Storage</code>.</p>
<p><em>model/storage.class.php</em></p>
<p>Die Klasse <code>Storage</code> enthält alle Methoden und Attribute die für das Lesen, Schreiben und Aktualsieren der Daten im JSON-File benötigt werden. Diese Klasse bleibt abstrakt und soll wiederverwendet werden können.</p>
<p><em>public/index.php</em></p>
<p>index.php befindet sich im Web-Root und ist die einzige Seite, die im Browser aufgerufen wird. Anhand eines Parameters <code>mode</code> lässt sich die Ansicht steuern.</p>
<p><em>view/create.php</em></p>
<p>HTML-Formular zur Erfassung neuer Einträge mit Ausgabe möglicher Fehler aus der Validierung.</p>
<p><em>view/list.php</em></p>
<p>Die Auflistung der erfassten Einträge in HTML.</p>
<p><em>controller.php</em></p>
<p>Die Steuerung empfängt die Daten aus der Benutzereingabe (<code>$_POST</code>), ruft die entsprechende Methode der Klasse auf und gibt gegebenenfalls Fehlermeldungen an die Darstellung zurück.</p>

