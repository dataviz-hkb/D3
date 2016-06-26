# L0 | D3.js Arbeitsumgebung

D3 bedeutet 100% Webstandards bezogen. Grundkenntnisse **HTML/CSS** sind deshalb von Vorteil, ebenso Vertrautheit mit der Logik von **XML** und 'Scalable Vector Graphics' **SVG**.

D3 ist eine Javascript Library, d.h. Programmierumgebung vollständig JS (ES5).

####Einrichten einer minimalen Arbeitsumgebung####
zum Beispiel mit *Brackets* besteht aus folgenden Schritten:

* Erstellen eines Verzeichnisses *D3* oder ähnlich
* Verzeichnis mit Brackets öffnen: `Datei` `>` `Ordner öffnen…`
* Erstellen einer Datei index.html, HTML5 validert, in selbiges Verzeichnis
* Einbinden der Library das Repository `https://d3js.org/d3.v3.min.js`
* *Brackets* bietet eine Server-Logik über die *Live Vorschau* um Dateien mittels eines **http-Request** zu öffnen. 
* Alternativ kann unter : `Datei` `>` `Projekt-Einstellungen…` auch die eigene Server-Logik (typischerweise unter *localhost* ) verwendet werden.
* Für den Aufruf von Seiten im Browser gilt : **keine** `Datei` `>` `Datei öffnen…` Geschichten. Dateiaufruf mit gleichzeitigen Datenimport generell mittels eines http-requests um Cross origin requests zu verhindern. 


>Using your own backend — Make sure your local server is already running, serving files from the same folder Brackets is editing. >Choose File > Project Settings and enter whatever URL corresponds to the root folder that's open in Brackets (typically a localhost >URL). Then open a file for one of your webpages (e.g. an HTML, PHP, or ASP file) and launch Live Preview. Brackets will launch Chrome >with the correct URL to load that page from your local server.




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

* `2` is a *literal value expression*
* `b` is a *variable expression*, which means to retrieve its current value
* `b * 2` is an *arithmetic expression*, which means to do the multiplication
* `a = b * 2` is an *assignment expression*, which means to assign the result of the `b * 2` expression to the variable `a` (more on assignments later)

A general expression that stands alone is also called an *expression statement*, such as the following:

These act like building blocks. To build a tall tower, you start first by putting block on top of block on top of block. The same goes with programming. Here are some of the essential programming building blocks:

* You need *operators* to perform actions on values.
* You need values and *types* to perform different kinds of actions like math on `number`s or output with `string`s.
* You need *variables* to store data (aka *state*) during your program's execution.
* You need *conditionals* like `if` statements to make decisions.
* You need *loops* to repeat tasks until a condition stops being true.
* You need *functions* to organize your code into logical and reusable chunks.

Code comments are one effective way to write more readable code, which makes your program easier to understand, maintain, and fix later if there are problems.

Finally, don't neglect the power of practice. The best way to learn how to write code is to write code.

I'm excited you're well on your way to learning how to code, now! Keep it up. Don't forget to check out other beginner programming resources (books, blogs, online training, etc.). This chapter and this book are a great start, but they're just a brief introduction.

The next chapter will review many of the concepts from this chapter, but from a more JavaScript-specific perspective, which will highlight most of the major topics that are addressed in deeper detail throughout the rest of the series.
