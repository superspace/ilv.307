---


---

<h3 id="tag-2">Tag 2</h3>
<h1 id="php-konkret">PHP Konkret</h1>
<h2 id="repetition-html">Repetition HTML</h2>
<h3 id="grundgerüst">Grundgerüst</h3>
<pre><code>&lt;html&gt;
    &lt;head&gt;
        &lt;title&gt;Hello World&lt;/title&gt;
        &lt;meta  charset="utf-8"&gt;
    &lt;/head&gt;
    &lt;body&gt;
        &lt;h1&gt;Hello World&lt;/h1&gt;
    &lt;/body&gt;
&lt;/html&gt;
</code></pre>
<h3 id="formulare">Formulare</h3>
<pre><code>&lt;form action="index.php" method="post"&gt;
    &lt;input type="text" name="field1" value="" /&gt;
    &lt;button type="submit"&gt;Senden&lt;/button&gt;
&lt;/form&gt;
</code></pre>
<p><em>action:</em> Ziel-URL der Datenübertragung<br>
<em>method:</em> POST | GET</p>
<p><em><strong>POST</strong></em> Datenübermittlung an Server<br>
<em><strong>GET:</strong></em> Datenanfrage an Server.<br>
Die Daten können auch als URL-Parameter übergeben werden:</p>
<p><code>https://www.google.com/search?q=Suchbegriff</code></p>
<p>ist dasselbe wie:</p>
<pre><code>&lt;form action="https://www.google.com/search" method="get"&gt;
    &lt;input type="text" name="q" value="Suchbegriff" /&gt;
    &lt;button type="submit"&gt;Senden&lt;/button&gt;
&lt;/form&gt;
</code></pre>
<h4 id="input-felder">Input-Felder</h4>
<p><code>&lt;input type="text" name="field1" value="" /&gt;</code></p>
<p><em>type:</em> Feld-Typ, z.B. text, email, number, datetime<br>
<em>name:</em> Feld-Name, eindeutiger Wert für die Übermittlung des Wertes<br>
<em>value:</em> Der Eingabe-Wert, kann auch vorausgefüllt werden</p>
<h5 id="text">Text</h5>
<p><code>&lt;input type="text" name="field1" value="" /&gt;</code></p>
<h5 id="zahl">Zahl</h5>
<p><code>&lt;input type="number" name="field1" value="" min="" max="" /&gt;</code></p>
<h5 id="e-mail">E-Mail</h5>
<p><code>&lt;input type="email" name="field1" value="" /&gt;</code></p>
<h5 id="datum">Datum</h5>
<p><code>&lt;input type="datetime" name="field1" value="" /&gt;</code></p>
<h5 id="unsichtbar">Unsichtbar</h5>
<p><code>&lt;input type="hidden" name="field1" value="" /&gt;</code></p>
<h5 id="mehrzeiliger-text">Mehrzeiliger Text</h5>
<p><code>&lt;textarea name="field1"&gt;&lt;/textarea&gt;</code></p>
<h5 id="checkbox">Checkbox</h5>
<p><code>&lt;input type="checkbox" name="field1" value="1" /&gt;</code></p>
<h5 id="radio-button">Radio-Button</h5>
<p><code>&lt;input type="radio" name="field1" value="1" /&gt;</code></p>
<h5 id="dropdown">Dropdown</h5>
<pre><code>&lt;select name="field1"&gt;
    &lt;option value="value1"&gt;Wert 1&lt;/option&gt;
&lt;/select&gt;
</code></pre>
<h4 id="validierung-mit-html5">Validierung mit HTML5</h4>
<p>HTML5 erlaubt die Feld-Validierung im Browser. Die Implementierung der verschiedenen Hersteller variiert jedoch stark, weshalb man sich nicht voll und ganz darauf verlassen darf.</p>
<pre><code>&lt;input type="email" name="field1" value="" required /&gt;
</code></pre>
<p><em>type:</em> Bestimmt das zu akzeptierende Format<br>
<em>required:</em> Zwingende Eingabe</p>
<h3 id="client-server-kommunikation-mit-php">Client-Server-Kommunikation mit PHP</h3>
<h4 id="postgetrequest">POST/GET/REQUEST</h4>
<h5 id="post">POST</h5>
<p>Die globale Variable <code>$_POST</code> beinhaltet alle Schlüssel-Wert-Paare, die über ein Formular mit <code>method="post"</code> übermittelt worden sind.</p>
<h5 id="get">GET</h5>
<p>Die globale Variable <code>$_GET</code> beinhaltet alle Schlüssel-Wert-Paare, die entweder über ein Formular mit <code>method="get"</code> oder direkt über die URL übermittelt worden sind.</p>
<h5 id="request">REQUEST</h5>
<p>Die globale Variable <code>$_REQUEST</code> beinhaltet alle Schlüssel-Wert-Paare die per POST oder per GET übermittelt worden sind.</p>
<p><em>POST und GET können auch kombiniert werden.</em></p>
<h4 id="sicherheit-filtersanitize">Sicherheit (Filter/Sanitize)</h4>
<p>Damit keine falschen oder schädlichen Daten auf dem Server verarbeitet werden, müssen diese erst einer Prüfung unterzogen werden.</p>
<ul>
<li>Unnötige Leerschläge, Tabs etc. entfernen</li>
</ul>
<p>Mit der Funktion <code>trim()</code> werden unnötige Leerschläge entfernt.</p>
<ul>
<li>Cross-site Scripting (XSS) verhindern</li>
</ul>
<p>Mit der Funktion <code>htmlspecialchars()</code> werden Sonderzeichen  in die entsprechenden HTML-Codes umgewandelt.</p>
<p><a href="https://www.php.net/manual/de/function.htmlspecialchars.php">https://www.php.net/manual/de/function.htmlspecialchars.php</a></p>
<p><em>SQL-Injections wird in einem späteren Modul behandelt.</em></p>
<h4 id="validierung-in-php">Validierung in PHP</h4>
<p>Bevor die Daten auf dem Server weiterverarbeitet werden, müssen diese einer inhaltlichen Validierung unterzogen werden.</p>
<p>Zwingende Felder werden mit <code>empty()</code> darauf überprüft, ob ein Wert vorhanden ist.</p>
<p><a href="https://www.php.net/manual/de/function.empty.php">https://www.php.net/manual/de/function.empty.php</a></p>
<p>Spezielle Formate wie z.B. eine E-Mail-Adresse kann über PHP Filter validiert werden:</p>
<p><code>filter_var($email, FILTER_VALIDATE_EMAIL)</code></p>
<p><a href="https://www.php.net/manual/de/function.filter-var.php">https://www.php.net/manual/de/function.filter-var.php</a></p>
<h4 id="error-handling">Error-Handling</h4>
<p><em>TODO</em></p>
<h3 id="file-handling">File-Handling</h3>
<h4 id="lesen-und-schreiben-von-dateien">Lesen und Schreiben von Dateien</h4>
<p>Mit PHP können Dateien auf dem Filesystem erstellt, gelesen und modifiziert werden. <em>VORSICHT</em> Diese Funktionen sind irreversibel und können auch grossen Schaden auf dem System anrichten!</p>
<h5 id="datei-lesen">Datei lesen</h5>
<p>Mit <code>readfile()</code> wird eine Datei gelesen und direkt ausgegeben. Wir haben aber keine Möglichkeit, den Inhalt zu verarbeiten.</p>
<p>Die Funktionen <code>fopen()</code> ,  <code>fread()</code> und <code>fclose()</code> geben uns mehr Kontrolle bei der Verarbeitung der Datei. So können beispielsweise sehr grosse Dateien als Stream gelesen werden und es ist auch möglich, Dateien über ein Netzwerk (z.B. http://) zu öffnen.</p>
<p><a href="https://www.php.net/manual/de/function.fopen.php">https://www.php.net/manual/de/function.fopen.php</a></p>
<p>Mit  <code>file_get_contents()</code> lassen sich Dateien lokal wie auch im Netzwerk öffnen. Die Funktion übergibt den Inhalt der Datei in einen String. Diese Funktion ist ein sogenannte Wrapper, im Hintergrund wird <code>fopen()</code> und <code>fread()</code> ausgeführt.</p>
<p><a href="https://www.php.net/manual/de/function.file-get-contents.php">https://www.php.net/manual/de/function.file-get-contents.php</a></p>
<h5 id="datei-schreiben">Datei schreiben</h5>
<p>Ach hier können <code>fopen()</code>, <code>fwrite()</code> und <code>fclose()</code> verwendet werden.</p>
<p>Die Funktion <code>file_put_contents()</code> ist ein Wrapper für die oben genannten Funktionen und erledigt die Aufgabe mit einem Funktionsaufruf.</p>
<p><a href="https://www.php.net/manual/de/function.file-put-contents.php">https://www.php.net/manual/de/function.file-put-contents.php</a></p>
<h5 id="datei-erstellen">Datei erstellen</h5>
<p>Neue Dateien können mit der Funktion <code>fopen()</code> erzeugt werden.</p>
<p><code>file_put_contents()</code> erstellt automatisch fehlende Dateien.</p>
<h3 id="datenhaltung">Datenhaltung</h3>
<p>Wir behandeln ausschliesslich datei-basierte Datenhaltung in. Die Anbindung an eine Datenbank wird in einem späteren Modul behandelt.</p>
<h4 id="formate">Formate</h4>
<h5 id="json">JSON</h5>
<p>JSON (JavaScript Object Notation) hat sich als quasi Standard für die Haltung und Übergabe von strukturierten Daten etabliert. Die Syntax entspricht JavaScript und erlaubt die Abbildung von diversen Datentypen wie String, Number, Boolean, Array Object etc. Mehrere Einträge werden immer in einem Gefäss (Array oder Object) gefasst.</p>
<p><em>Ein einzelner Eintrag:</em></p>
<p><code>"Eintrag A"</code></p>
<p><em>Mehrere Einträge:</em></p>
<pre><code>[
	"Eintrag A",
	"Eintrag B",
	"Eintrag C"
]
</code></pre>
<p><em>Mehrere Einträge mit Schlüssel-Wert-Paaren:</em></p>
<pre><code>[
	{
		"name": "User A",
		"email": "user-a@email.com",
		"alter": 32
	},
	{
		"name": "User B",
		"email": "user-b@email.com",
		"alter": 27
	}
]
</code></pre>
<p><a href="https://wiki.selfhtml.org/wiki/JSON">https://wiki.selfhtml.org/wiki/JSON</a></p>
<h5 id="xml">XML</h5>
<p>Historisch immer noch relevant ist das XML-Format (Extensible Markup Langauge), mit welchem ebenfalls strukturierte Daten abgebildet werden können.</p>
<pre><code>&lt;?xml version="1.0" encoding="utf-8"?&gt;
&lt;users&gt;
	&lt;user name="User A" email="user-a@email.com"&gt;
		&lt;age&gt;32&lt;/age&gt;
	&lt;/user&gt;
	&lt;user name="User B" email="user-b@email.com"&gt;
		&lt;age&gt;27&lt;/age&gt;
	&lt;/user&gt;
&lt;/users&gt;
</code></pre>
<h5 id="csv">CSV</h5>
<p>Mit CSV (Comma separated Values) können tabellarische Informationen erfasst werden.</p>
<h5 id="yaml">YAML</h5>
<p>YAML (Yet another Markup Language) eignet sich für die Definition von Schlüssel-Wert-Paaren und wird gerne für Konfigurations-Daten verwendet.</p>
<h4 id="parsen">Parsen</h4>
<h5 id="json-1">JSON</h5>
<p>Mit den Funktionen <code>json_decode()</code> und <code>json_encode()</code> können Daten aus PHP direkt in das JSON-Format und andersrum umgewandelt werden. Dabei werden die Datentypen String, Boolean, Number, Array etc. berücksichtigt.</p>
<p>Daten aus einem JSON-File auslesen und als assoziativer Array zurückgeben:</p>
<p><code>$meinArray = json_decode('relativer/pfad/zum/file.json', true);</code></p>
<p>Einen Array aus PHP im JSON-Format ausgeben:</p>
<p><code>$meinJsonString = json_encode($meinArray);</code></p>
<p><a href="https://www.php.net/manual/de/function.json-decode.php">https://www.php.net/manual/de/function.json-decode.php</a><br>
<a href="https://www.php.net/manual/de/function.json-encode.php">https://www.php.net/manual/de/function.json-encode.php</a></p>

