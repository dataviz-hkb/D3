# DATA


####Beispiele aus 3 | Data sind generell zu verbessern:####



###File: [L4.00.html](L4.00.html)###
####Versuch 1, Verbesserung über SVG Objekt####
Verwendung von SVG, Erstellung der Elemente <g> und <rect> mit den Methoden data(), enter(), append()
<br>Nichts grundsätzlich Neues.

<p>&nbsp;</p>

###File: [L4.01.html](L4.01.html)###
####CSV-Daten verarbeiten####
Daten einlesen und als Vereinfachung und Anlehnung an Beispiel aus 3 | Data auch hier alles an ein  Array übergeben. Daten direkt zu Zahlen konvertieren über den `+`-Operator, dann zu ganzzahlig konvertieren.
``` javascript
var datensatz = [];
d3.csv("data/datensatz.csv", function(error, data) {

        data.forEach(function(d) {
            datensatz.push(parseInt(+d.Rate));
        });
        
}
```

        
<p>&nbsp;</p>
###File: [L3.02.html](L3.02.html)###
####Daten holen, Elemente erstellen, Daten verarbeiten####
Datenarray holen, Keys und Werte, dann mittels enter() eine Subselektion erstellen aus Vergleich zwischen "vorhandenen" und "benötigten" Elementen. "Benötigte" am Schluss anhängen.
``` javascript
d3.select("body").selectAll("p") // <--- Alle <p> \\\ falls keine vorhanden weiter…
        .data(datenset) // <--- Datenarray holen, Keys und Werte
        .enter() // <--- Subselektion: Vergleich "Vorhandene" mit "Benötigten"
        .append("p") // <--- "Benötigte" am Schluss anhängen
        .text(function(d) { return Math.sin(+d); });  // <--- Textausgabe (Sinus von Datenwert)
```

<p>&nbsp;</p>
###File: [L3.03.html](L3.03.html)###
####Das Ganze mit `<div>` als Balkendiagramm####
Gleiches Prinzip: Datenarray holen, mittels enter() ein Vergleich zwischen "vorhandenen" und "benötigten" Elementen erstellen. "Benötigte" anhängen und deren Höhe als Funktion von Data berechnen.
[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L3/L3.03.html)
``` javascript
d3.select("#datawrapper").selectAll("div")
        .data(datenset)
        .enter()
        .append("div")
        .attr("class", "bar")
        .style("height", function(d) {
                return Math.abs(100*(Math.sin(d) + Math.cos(d))) + "px";
        })
        .style("background-color", "deeppink");
```


<p>&nbsp;</p>
###File: [L3.04.html](L3.04.html)###
####Daten verarbeiten, sortieren####
Datenarray holen, Keys und Werte, dann mittels enter() eine Subselektion erstellen aus Vergleich zwischen "vorhandenen" und "benötigten" Elementen. "Benötigte" am Schluss anhängen.
``` javascript
data = data.sort(function (a,b) {return d3.descending(a, b); });  // Absteigend
data = data.sort(function (a,b) {return d3.ascending(a, b); });  // Aufsteigend
```


<p>&nbsp;</p>
###File: [L3.05.html](L3.05.html)###
####SVG Elemente####
Koordinatenursprung für SVG ist __Oben__ und __Links__. Positionierung entsprechend anpassen. 
``` javascript
d3.select("rect")
    .attr( "height", 126)
    .attr( "y", 200-126);
```

<p>&nbsp;</p>
###Files: [L3.06.html](L3.06.html) [L3.07.html](L3.07.html) [L3.08.html](L3.08.html) [L3.09.html](L3.09.html) [L3.10.html](L3.10.html) [L3.11.html](L3.11.html)###
####Datenvisualisierung simpel####
Datenarray zu SVG Balkendiagramm.


        
<p>&nbsp;</p>
###File: [L3.12.html](L3.12.html)###
####Wie funktioniert das Schlüsselkonzept `selectAll()`, `data()`, `enter()`, `append()` ?####
Gegeben: Datenarray mit 16 Feldinhalten (Zahlenwerte). SVG Objekt mit 8 `<rect>`Elementen.
Was passiert? 

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L3/L3.12.html)

``` javascript
var datensatz = [ 20.4, 124, 43.4, 122, 6, 63, 24, 220, 122, 6, 63, 24, 2, 5, 143, 24 ];
```
``` html
<svg width="400" height="200" style="stroke-width: 0;">
        <rect x="0" y="176" width="24" height="24" fill="#7600ff"></rect>
        <rect x="25" y="176" width="24" height="24" fill="#6516c1"></rect>
        <rect x="50" y="176" width="24" height="24" fill="#51119b"></rect>
        <rect x="75" y="176" width="24" height="24" fill="#3d1869"></rect>
        <rect x="100" y="176" width="24" height="24" fill="#7600ff"></rect>
        <rect x="125" y="176" width="24" height="24" fill="#6516c1"></rect>
        <rect x="150" y="176" width="24" height="24" fill="#51119b"></rect>
        <rect x="175" y="176" width="24" height="24" fill="#3d1869"></rect>
</svg>
```
``` javascript
var svg = d3.select("svg");
svg.selectAll("rect")
        .data(datensatz)
        .enter().append("rect")
            .attr("class", "bar")
            .attr("width", 24)
            .style("fill", "deeppink")
            .attr("height", function(d,i) { return d })
            .attr("y", function(d,i) {  return 200 - d })
            .attr("x", function(d,i) { return i*25 });
```

<p>&nbsp;</p>
###File: [L3.13.html](L3.13.html)###
####Die `selectAll()`, `data()`, `enter()`, `append()` Sequenz verstehen####
Die  Sequenz muss aufgeteilt werden, um das Konzept auch in diesem Fall erfolgreich zu halten, d.h. um jene benötigten Elemente hinzuzufügen und um diese der gesamten Selektion zugänglich zu machen. Aufteilung in: 

1. Auswahl aller Elemente, Datenarray holen
2. enter() = Vergleich zwischen "vorhandenen" und "benötigten" Elementen. "Benötigte" am Schluss anhängen
3. Attribute zuschreiben

Das Aufteilen der Sequenz in zwei Teile erlaubt es der enter().append() Selektion die bereits bestehende Selektion 
selectAll("rect") um die 8 fehlenden Elemente zu erweitern. Diese Selektion beinhaltet nun alle 16 benötigten Elemente, die in einem dritten Schritt ihre Attribute erhalten.
            
[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L3/L3.13.html)
            
``` javascript
var     svg = d3.select("svg");
var     update = svg.selectAll("rect").data(datensatz);

        update.attr("class", "foo");
        
        update.enter().append("rect")
            .attr("class", "bar")
            .attr("width", 24)
            .attr("height", 24)
            .style("fill", "deeppink");
            
        update.attr("height", function(d,i) { return d })
            .attr("y", function(d,i) {  return 200 - d })
            .attr("x", function(d,i) { return i*25 });
```


          

<p>&nbsp;</p>




---


###Next: [Skalen](../L5/)

[Übersicht](../README.md#chapter)
