# DATA


####Einfaches Beispiel, HTML-Struktur (HTML, SVG):####
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

####Javascript:####
```javascript
    var datensatz = [ 400, 920, 331, 600, 223, 584, 119, 438 ];
        datensatz = datensatz.sort(function (a,b) {return d3.descending(a, b); });
        d3.selectAll( "rect" )
            .data( datensatz )
            .attr( "height", function(d,i){
                return d;
            })
            .attr( "y", function(d,i){
                return 200 - d;
            });
            
```

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L3/L3.13.html)


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


###File: [L3.00.html](L3.00.html)###
####Das grundlegende Konzept von D3 mit Data####
Datenarray holen, traversieren und pro Datenpunkt ein neues Element erzeugen.
``` javascript
var datenset = [ 5, 10, 15, 20, 25 ];
d3.select("body").selectAll("p")
    .data(datenset)
    .enter()
    .append("p")
    .text("Sprache ist Praxis. Sprache an sich existiert nicht.");
```

<p>&nbsp;</p>
###File: [L3.01.html](L3.01.html)###
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
###File: [L3.01.html](L3.01.html)###
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
###File: [L3.01.html](L3.01.html)###
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
###File: [L3.01.html](L3.01.html)###
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
###File: [L3.01.html](L3.01.html)###
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
###File: [L3.01.html](L3.01.html)###
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
###File: [L3.01.html](L3.01.html)###
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
###File: [L3.01.html](L3.01.html)###
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
###File: [L3.01.html](L3.01.html)###
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




---


###Next: [Data CSV/TSV](../_L4/)

[Übersicht](../README.md#chapter)
