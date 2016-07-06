# DATA CSV/TSV

### CSV/TSV Daten verwenden, einlesen ###


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

---


###Next: [Data CSV/TSV](../_L4/)

[Übersicht](../README.md#chapter)
