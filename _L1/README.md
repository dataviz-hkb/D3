# SVG  & HTML/CSS

D3.js ist 100% Webstandards bezogen. Grundkenntnisse **HTML/CSS** sind deshalb von Vorteil, ebenso Vertrautheit mit der Logik von **XML** und 'Scalable Vector Graphics' **SVG**.<br>
D3 ist eine Javascript Library, d.h. Programmierumgebung vollständig JS (ES5 - Stand Juni 2016).


#####Einrichten einer Arbeitsumgebung zum Beispiel mit [Brackets](http://brackets.io) besteht aus folgenden Schritten:#####

* Erstellen eines Verzeichnisses *'D3'* oder ähnlich
* Verzeichnis mit Brackets öffnen: `Datei` `>` `Ordner öffnen…`
* Erstellen einer Datei index.html, HTML5 validert, in selbiges Verzeichnis
* Einbinden der Library das Repository `https://d3js.org/d3.v3.min.js`
* [Brackets](http://brackets.io) bietet eine Server-Logik über die *Live Vorschau* um Dateien mittels eines **http-Request** zu öffnen. 
* Alternativ kann unter : `Datei` `>` `Projekt-Einstellungen…` auch die eigene Server-Logik (typischerweise *localhost* ) verwendet werden.
* Für den Aufruf von Seiten im Browser gilt **HTTP**, d.h. **keine** Empfehlung für `Datei` `>` `Datei öffnen…` etc.
* Chrome and Opera verhindern XMLHttpRequest zu lokalen Dateien (Z.B. JSON, CSV, etc.). Dateiaufruf mit gleichzeitigem Datenimport **generell** mittels eines **http-requests**.



###Bildet diese Dokumentenstruktur ab:###
```html
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Dokument Crash Kurs</title>
</head>

<body>
    <h1>A dozen direct censures are easier to bear than one morganatic compliment.</h1>
    <p>Der Begriff <a href='http://de.wikipedia.org/wiki/Morganatische_Ehe'>morganatisch</a> geht auf die morganatische Ehe zurück. Als morganatische Ehe (lat. matrimonium morganaticum, mittellateinische Neubildung zu althochdeutsch morgangeba, «Morgengabe») oder Ehe zur linken Hand bezeichnet man eine im europäischen Adel nicht selten vorkommende Form der Ehe, bei der einer der beiden Ehepartner (meistens die Frau) von niedrigerem Stand war als der andere (Nichtebenbürtigkeit).</p>
    <ul>
        <li>Mark Twain, from Pudd'nhead Wilson's New Calendar in Following the Equator (1897)</li>
        <li>morganatic, from latin "matrimonium morganaticum"</li>
        <li>Zu deutsch, morganatisch: unaufrichtig, linkisch, zweifelhaft, fragwürdig</li>
    </ul>
</body>
</html>
```

<p>&nbsp;</p>

---


### [Next:](../_L1/)

[Übersicht](../README.md#chapter)
