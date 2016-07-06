# DATA

### Folgende Methoden in D3 geben den Rahmen für diese ersten Beispiele

| Name | von Objekt | Rückgabe | Beschreibung |
| :---------- | :---------- | :---- | :--------------- |
| selectAll(selector) | Selektor | Selektor | Mehrfach-Element-Selektion für jeden Eintrag in der Selektion |
| data() | Auswahl | Array | Hole das Data-Array für die erste Gruppe der Auswahl. |
| enter() | Auswahl | EnterSelection | Rückgabe einer "sub"-Selektion (Array) als Platzhalter für fehlende Elemente, im Zusammenhang mit data() |
| attr(name,value) | Auswahl | Auswahl | Attribute: Eigenschaft und Wert zuweisen. |
| sort(comparator) | Auswahl | Auswahl | Sortiert die Elemente in der Selektion |


<p>&nbsp;</p>

####Einfaches Beispiel, HTML-Struktur (HTML, SVG):####
```html
        <svg width="200" height="200" style="stroke-width: 0; background-color: white;">

            <rect  fill="#7600ff"></rect>
            <rect  fill="#6516c1"></rect>
            <rect  fill="#51119b"></rect>
            <rect  fill="#3d1869"></rect>
            <rect  fill="#7600ff"></rect>
            <rect  fill="#6516c1"></rect>
            <rect  fill="#51119b"></rect>
            <rect  fill="#3d1869"></rect>

        </svg>

```

####Javascript:####
```javascript
    var datensatz = [ 400, 920, 331, 600, 223, 584, 119, 438 ];
        datensatz = datensatz.sort(function (a,b) {return d3.ascending(a, b); });

        d3.selectAll( "rect" )
            .data( datensatz )

            .attr( "height", function(d,i){
                return d/10 * 2;
            })

            .attr( "y", function(d,i){
                return 200 - d/10*2;
            })

            .attr( "x", function(d,i){
                return i * 25;
            })

            .attr( "width", 24);
            
```


[Vollständiges Beispiel | Quelltext](index.html)





<p>&nbsp;</p>


###File: [L3.00.html](L3.00.html)###
####Das grundlegende Konzept von D3 mit Data####
Datenarray holen, traversieren und pro Datenpunkt ein neues Elemnt erzeugen.<br>
``` javascript
var datenset = [ 5, 10, 15, 20, 25 ];
d3.select("body").selectAll("p")
    .data(datenset)
    .enter()
    .append("p")
    .text("Sprache ist Praxis. Sprache an sich existiert nicht.");
```

<p>&nbsp;</p>
###File: [L3.01.html](L1.03.html)###
####Variante: Strukturierung mit HTML####
Die Bildung von Struktur unterliegt einzig und allein der Regel, dass valider (= allgemein gültiger) HTML Code entsteht. Das bedeutet, dass zur Auszeichnung des Dokuments (HTML = Hypertext Markup Language = Hypertext Auszeichnungssprache ) alles erlaubt ist, was gültig ist, man also relativ frei ist, diese selber zu bestimmen.
Hier eine Variante, die minimal anders aufgebaut ist, sich jedoch semantisch unterscheidet.
Ein standardkonformer Browser veranlasst das, Unterschiede in Textgrösse für h1 zu rendern (siehe Textgrösse im `<h1>` zu [L1.02.html](L1.02.html) im direkten Vergleich)

        



<p>&nbsp;</p>




---


###Next: [Data CSV/TSV](../_L4/)

[Übersicht](../README.md#chapter)
