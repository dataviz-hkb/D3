# DATA CSV/TSV


#### Beispiele aus 3 | Data sind alle generell zu verbessern. Hier der Versuch:



### File: [L4.00.html](L4.00.html)
#### Versuch 1, Verbesserung über SVG Objekt
Verwendung von SVG, Erstellung der Elemente <g> und <rect> mit den Methoden data(), enter(), append()
<br>Nichts grundsätzlich Neues.





### File: [L4.01.html](L4.01.html)
#### SV-Daten verarbeiten
Daten einlesen und als Vereinfachung und Anlehnung an Beispiel aus 3 | Data auch hier alles an ein  Array übergeben. Daten direkt zu Zahlen konvertieren über den `+`-Operator, dann zu ganzzahlig konvertieren.
``` javascript
var datensatz = [];
d3.csv("data/datensatz.csv", function(error, data) {

        data.forEach(function(d) {
            datensatz.push(parseInt(+d.Rate));
        });
        
}
```

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L4/L4.01.html)
        



### File: [L4.02.html](L4.02.html)
#### Rückgabe von Werten an Objekte
Die Rückgabe von Daten, die mit der gegebenen Selektion in Zusammenhang stehen, geht elegant über eine selbstaufrufende Funktion:
``` javascript
function(d,i) { return +d };
```

wobei __d__ die Daten repräsentiert, die mit der gegebenen Selektion in Zusammenhang stehen
<br>und __i__ die Position der Daten im Array wiedergibt.

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L4/L4.02.html)



### File: [L4.03.html](L4.03.html)
#### Weitere Verbesserung: verlorene Daten zurückholen
Die im CSV Dokument unterschlagenen Daten (Wertepaare) zurückholen. Das Einlesen der Daten:
``` javascript
rows.forEach(function(d) {
    datensatz.push({
        name: d.ID,
        value: +d.Rate
    })
});
```

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L4/L4.03.html)



### File: [L4.04.html](L4.04.html)
#### Skalen, Achsenbeschriftungen dazu
Tooltips ermöglichen, Rückgabe Kantonsname und Wert

[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L4/L4.04.html)



### File: [L4.05.html](L4.05.html)
#### Das fertige Beispiel Waldranking
[Beispiel ansehen](https://dataviz-hkb.github.io/D3/L4/L4.05.html)






---


### Next: [Skalen](../L5/)

[Übersicht](../README.md#chapter)
