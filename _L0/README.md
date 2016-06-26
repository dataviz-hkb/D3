# D3.js Arbeitsumgebung

D3 bedeutet 100% Webstandards bezogen. Grundkenntnisse **HTML/CSS** sind deshalb von Vorteil, ebenso Vertrautheit mit der Logik von **XML** und 'Scalable Vector Graphics' **SVG**.<br>
D3 ist eine Javascript Library, d.h. Programmierumgebung vollständig JS (ES5).


#####Einrichten einer minimalen Arbeitsumgebung zum Beispiel mit *Brackets* besteht aus folgenden Schritten:#####

* Erstellen eines Verzeichnisses *D3* oder ähnlich
* Verzeichnis mit Brackets öffnen: `Datei` `>` `Ordner öffnen…`
* Erstellen einer Datei index.html, HTML5 validert, in selbiges Verzeichnis
* Einbinden der Library das Repository `https://d3js.org/d3.v3.min.js`
* *Brackets* bietet eine Server-Logik über die *Live Vorschau* um Dateien mittels eines **http-Request** zu öffnen. 
* Alternativ kann unter : `Datei` `>` `Projekt-Einstellungen…` auch die eigene Server-Logik (typischerweise *localhost* ) verwendet werden.
* Für den Aufruf von Seiten im Browser gilt **HTPP**, d.h. **keine** `Datei` `>` `Datei öffnen…`
* Dateiaufruf mit gleichzeitigen Datenimport **generell mittels eines http-requests** um Cross origin requests zu verhindern. 


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
