# SVG  & HTML/CSS

D3.js ist 100% Webstandards bezogen. Grundkenntnisse **HTML/CSS** sind deshalb von Vorteil, ebenso Vertrautheit mit der Logik von **XML** und 'Scalable Vector Graphics' **SVG**.<br>
D3 ist eine Javascript Library, d.h. Programmierumgebung vollständig JS (ES5 - Stand Juni 2016).


####Das hier…####
![Domtree](dom_tree.png)



####…bildet diese Dokumentenstruktur ab:####
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


#Crash Kurs HTML/CSS#


Kommentar zum Material

###File: [L1-01.html](L1-01.html)###
Unstrukturierter Content, Dokument mit minimalem Markup, Text

<p>&nbsp;</p>
###File: [L1-02.html](L1-02.html)###
####Strukturierung mit HTML####
Semantische Struktur dort, wo möglich und sinnvoll.<br>
D.h. Überschrift wird zu Überschrift (`<h1>` bzw. `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`)<br> 
Absatz wird zu Absatz (`<p>`) etc. <br> Übersicht in der HTML-Referenz: https://developer.mozilla.org/de/docs/Web/HTML/Element<br>
`<div>` als generisches Element wird generell dort eingesetzt, wo nicht-semantische Verpackung/Gliederung/Struktur gewünscht ist.

<p>&nbsp;</p>
###File: [L1-03.html](L1-03.html)###
####Variante: Strukturierung mit HTML####
Die Bildung von Struktur unterliegt einzig und allein der Regel, dass valider (= allgemein gültiger) HTML Code entsteht. Das bedeutet, dass zur Auszeichnung des Dokuments (HTML = Hypertext Markup Language = Hypertext Auszeichnungssprache ) alles erlaubt ist, was gültig ist, man also relativ frei ist, diese selber zu bestimmen.
Hier eine Variante, die minimal anders aufgebaut ist, sich jedoch semantisch unterscheidet.
Ein standardkonformer Browser veranlasst das, Unterschiede in Textgrösse für h1 zu rendern (siehe Textgrösse im `<h1>` zu [L1-02.html](L1-02.html) im direkten Vergleich)

        



<p>&nbsp;</p>
###File: [L1-04.html](L1-04.html)###
####Strukturierung mit HTML, gestalterischer Eingriff mit CSS####
Jetzt kann CSS kommen. Drei Möglichkeiten CSS einzubinden und zu verwenden: 

1. direkt im Dokument, über `<style type="text/css"> … </style>` im `<head>`
2. verlinkt auf ein Dokument, über `<link rel="stylesheet" href=" … " type="text/css">` im `<head>`
3. Inline, als Attribut, über beispielsweise `<p style="color: deeppink;"> </p>` direkt dem Element zugewiesen




<p>&nbsp;</p>
###File: [L1-05.html](L1-05.html)###
####DOM-Traversierung und Selektion####
<a href="dom_tree.png"><img src="dom_tree.png" width="180"></a>&nbsp;&nbsp;&nbsp;Präzise und effizient zu selektieren zu können ist eine Grundvoraussetzung für den gestalterischen Eingriff. Das Bild veranschaulicht, was zu tun ist. Gegeben: ein __HTML-strukturiertes Dokument__ mit Inhalt. <br>Damit __CSS__ einem Element bzw. dem Inhalt eines Elements Gestaltungsattribute zuschreiben kann, muss der DOM über alle Verwandtschaftsgrade traversiert werden. Um das zu vereinfachen bieten sich die Attribute `class` und `id` an. <br>Klassen- und ID-Bezeichner in HTML erlauben CSS die direkte Selektion über folgendes Muster:

#####mit:
* dem vorangestellten Punkt: &nbsp;__&middot;__&nbsp; wird der Bezeichner als Klassen-Selektor interpretiert. <br>Beispiel: ``` .testKlasse { … }  selektiert <p class="testKlasse"> … </p>  ```

* dem vorangestellten Hash: &nbsp;__#__&nbsp; wird der Bezeichner als ID-Selektor interpretiert. <br>Beispiel: ```  #testID { … }  selektiert <p id="testKlasse"> … </p>  ``` 

* __ohne__ | Selektiert generische Elemente (auch SVG) <br>Beispiel: `span { … }`selektiert `<span> … </span>` 

#####Nota bene:
* Ein Element kann zu __zwei (drei, vier, …) Klassen__ gehören, jedoch nur eine ID haben. __Eine ID__ kann auch nur __einmal__ pro Dokument vorkommen. 

* Mehrfach-Selektion ist möglich über die Verwendung von Kommata. <br>Beispiel: Gegeben die Elemente
<br><body> … </body>` , `<p id="testID"> … </p>` und `<h1> … </h1>` 
<br>diese werden in CSS über die Syntax `body, #testID, h1 { … }` gemeinsam selektiert

* Die Kombination von generischen Selektoren mit Klassen-Selektoren verschärfen die Selektionsbedingungen. <br>Beispiel, gegeben folgende Struktur:  `<h1 class="kursiv"> … </h1>  <p class="kursiv"> … </p>`  hier selektiert `h1.kursiv { … }` ausschliesslich die Überschrift. Der Absatz bleibt unverändert, obwohl er zur gleichen Klasse gehört.

<p>&nbsp;</p>
###File: [L1-06.html](L1-06.html)###
####Kaskadierung, Vererbung####
Das Beispiel zeigt die Vererbung von Eigenschaft und Wert an Kinds-Elemente.
Einbindung von Schriften über das Repository von Google Fonts (https://fonts.google.com)
```css
/* Änderung in Zeile 9: */
@import url(http://fonts.googleapis.com/css?family=Open+Sans:400,300,700);

/* und Zeile 17 */
font-family: 'Open Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif;
```
Vererbung der Schrift an alle Kinds-Elemente entspricht der Erwartung an den Dokumentenbaum (Kinder > Eltern > Grosseltern, etc.)





<p>&nbsp;</p>
###File: [L1-07.html](L1-07.html)###
####Strukturierung mit HTML####
Dieses Beispiel, um zu illustrieren, welcher Aufwand nötig wäre, um visuell das gleiche Ergebnis zu erhalten, ohne Vergabe von Klassen und ID's mit der HTML-Struktur aus Dokument [L1-02.html](L1-02.html)





<p>&nbsp;</p>

---


###Next: [Javascript Basics](../_L2/)

[Übersicht](../README.md#chapter)
