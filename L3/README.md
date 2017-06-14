# DATA


#### Einfaches Beispiel, HTML-Struktur (HTML, SVG):####
```html
        <svg width="200" height="200" style="stroke-width: 0;">
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

#### Javascript:####
```javascript
    var datensatz = [ 400, 920, 331, 600, 223, 584, 119, 438 ];
        //datensatz = datensatz.sort(function (a,b) {return d3.descending(a, b); });
        d3.selectAll( "rect" )
            .data( datensatz )
            .attr( "height", function(d,i){
                return d;
            })
            .attr( "y", function(d,i){
                return 200 - d;
            });
            
```

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L3/L3.10.html)


<p>&nbsp;</p>


### Folgende Methoden in D3 geben den Rahmen für diese ersten Beispiele

| Name | von Objekt | Rückgabe | Beschreibung |
| :---------- | :---------- | :---- | :--------------- |
| selectAll(selector) | Selektor | Selektor | Mehrfach-Element-Selektion für jeden Eintrag in der Selektion |
| data() | Auswahl | Array | Hole das Data-Array für die erste Gruppe der Auswahl. |
| enter() | Auswahl | EnterSelection | Rückgabe einer "Sub"-Selektion als Platzhalter-Array für fehlende Elemente, im Zusammenhang mit data() |
| attr(name,value) | Auswahl | Auswahl | Attribute: Eigenschaft und Wert zuweisen. |
| sort(comparator) | Auswahl | Auswahl | Sortiert die Elemente in der Selektion |



<p>&nbsp;</p>


### File: [L3.00.html](L3.00.html)###
#### Das grundlegende Konzept von D3 mit Data####
Datenarray holen, traversieren und pro Datenpunkt ein neues Element erzeugen.
``` javascript
var datenset = [ 5, 10, 15, 20, 25 ];
d3.select("body").selectAll("p")
    .data(datenset)
    .enter()
    .append("p")
    .text("Sprache ist Praxis. Sprache an sich existiert nicht.");
```

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L3/L3.00.html)

<p>&nbsp;</p>
### File: [L3.01.html](L3.01.html)###
#### Daten holen, Elemente erstellen, Daten verarbeiten####
Datenarray holen, Keys und Werte, dann mittels enter() eine Subselektion erstellen aus Vergleich zwischen "vorhandenen" und "benötigten" Elementen. "Benötigte" am Schluss anhängen.
``` javascript
d3.select("body").selectAll("p") // <--- Alle <p> \\\ falls keine vorhanden weiter…
        .data(datenset) // <--- Datenarray holen, Keys und Werte
        .enter() // <--- Subselektion: Vergleich "Vorhandene" mit "Benötigten"
        .append("p") // <--- "Benötigte" am Schluss anhängen
        .text(function(d) { return Math.sin(+d); });  // <--- Textausgabe (Sinus von Datenwert)
```

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L3/L3.01.html)
        
<p>&nbsp;</p>
### File: [L3.02.html](L3.02.html)###
#### Daten holen, Elemente erstellen, Daten verarbeiten####
Datenarray holen, Keys und Werte, dann mittels enter() eine Subselektion erstellen aus Vergleich zwischen "vorhandenen" und "benötigten" Elementen. "Benötigte" am Schluss anhängen.
``` javascript
d3.select("body").selectAll("p") // <--- Alle <p> \\\ falls keine vorhanden weiter…
        .data(datenset) // <--- Datenarray holen, Keys und Werte
        .enter() // <--- Subselektion: Vergleich "Vorhandene" mit "Benötigten"
        .append("p") // <--- "Benötigte" am Schluss anhängen
        .text(function(d) { return Math.sin(+d); });  // <--- Textausgabe (Sinus von Datenwert)
```

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L3/L3.02.html)

<p>&nbsp;</p>
### File: [L3.03.html](L3.03.html)###
#### Das Ganze mit `<div>` als Balkendiagramm####
Gleiches Prinzip: Datenarray holen, mittels enter() ein Vergleich zwischen "vorhandenen" und "benötigten" Elementen erstellen. "Benötigte" anhängen und deren Höhe als Funktion von Data berechnen.
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

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L3/L3.03.html)

<p>&nbsp;</p>
###F ile: [L3.04.html](L3.04.html)###
#### Daten verarbeiten, sortieren####
Datenarray holen, Keys und Werte, dann mittels enter() eine Subselektion erstellen aus Vergleich zwischen "vorhandenen" und "benötigten" Elementen. "Benötigte" am Schluss anhängen.
``` javascript
data = data.sort(function (a,b) {return d3.descending(a, b); });  // Absteigend
data = data.sort(function (a,b) {return d3.ascending(a, b); });  // Aufsteigend
```

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L3/L3.04.html)

<p>&nbsp;</p>
### File: [L3.05.html](L3.05.html)###
#### SVG Elemente####
Koordinatenursprung für SVG ist __Oben__ und __Links__. Positionierung entsprechend anpassen. 
``` javascript
d3.select("rect")
    .attr( "height", 126)
    .attr( "y", 200-126);
```

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L3/L3.05.html)

<p>&nbsp;</p>
### Files: [L3.06.html](L3.06.html) [L3.07.html](L3.07.html) [L3.08.html](L3.08.html) [L3.09.html](L3.09.html) [L3.10.html](L3.10.html) [L3.11.html](L3.11.html)###
#### Datenvisualisierung simpel####
Datenarray zu SVG Balkendiagramm.


        
<p>&nbsp;</p>
### File: [L3.12.html](L3.12.html)###
#### Wie funktioniert das Schlüsselkonzept `selectAll()`, `data()`, `enter()`, `append()` ?####
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
### File: [L3.13.html](L3.13.html)###
#### Die `selectAll()`, `data()`, `enter()`, `append()` Sequenz verstehen####
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


### Next: [Data CSV/TSV](../L4/)

[Übersicht](../README.md#chapter)
