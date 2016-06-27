# Up & Going: Arbeitsumgebung | D3


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



###HTML5 Standard minimal Konfiguration mit Einbindung d3.js:###
```html
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="utf-8">
    <title>HKB - Dataviz mit D3.js</title>
    <script src="https://d3js.org/d3.v3.min.js" charset="utf-8"></script>
</head>

<body>


    <script type="text/javascript"> </script>
</body>
</html>
```

<p>&nbsp;</p>

---


###Next: [SVG & HTML/CSS:](../_L1/)

[Übersicht](../README.md#chapter)
