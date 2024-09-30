<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  0.0.1
date:     2024
language: de
narrator: Deutsch Female
logo:     img/5/repetition.png
icon:     img/TU_Logo_kurz.svg
comment:  Wir lernen Listen und Sequenzen und wie wir mit der for-Schleife über sie iterieren können.
import:   https://raw.githubusercontent.com/LiaTemplates/Pyodide/master/README.md
import:   https://raw.githubusercontent.com/liaScript/mermaid_template/master/README.md
import:   macros/macros.md
import:   macros/midi.md
link:     styles/main.css

-->

# 5. Listen und Schleifen

<div class="alert summary">

<h4>Lernziele</h4>


In diesem Kapitel lernen Sie, wie Sie mit Auflistungen von Daten umgehen und wie Sie Schleifen verwenden können, um über diese zu iterieren. 

Am Ende können Sie:

1. Listen erstellen und darauf zugreifen
2. Listen als Sequenztypen verstehen
3. Mit der `for`-Schleife über Listen iterieren


</div>

## Wozu Listen?

Im letzten Kapitel [„Wiederholung“](https://liascript.github.io/course/?https://raw.githubusercontent.com/tilman-schieber/OKInf/refs/heads/main/4_Wiederholung.md#2) haben Sie auch die sogenannte Mengenschleife kennengelernt. Dabei wird der Schleifenrumpf für jedes Element einer Auflistung einmal durchgeführt. Typischerweise wird dabei dieses Element gelesen, geschrieben oder beides.

Eine solche Vorgehensweise ist für viele Anwendungen sehr nützlich. Beispielsweise können Sie so 

- Den Durchschnitt einer Liste von Zahlen berechnen
- Die Anzahl der Wörter in einem Text zählen
- Eine Liste von Nachnamen alphabetisch sortieren

Wir verwenden hier den Begriff „Auflistung“, da es sich in den wenigsten Fällen tatsächlich um eine Menge im mathematischen Sinn handelt[^1]


<div class="alert example">	
Nehmen Sie an, bei einem Patienten in einem Krankenhaus wird jeden Morgen die Körpertemperatur gemessen. 
Die Krankenschwester führt eine Liste:

![Eine Liste](img/5/liste.png "Die Liste der Krankenschwester") 

Sollen diese Daten nun in einen Computer eingegeben werden, braucht man einen Datentyp, der mehrere Datenelemente enthalten kann[^2].

</div>

<div class="alert definition">	

Skalare und nicht-skalare Datentypen
-------------------------------------

Bei Daten vom Typ `int`, `float` und `boolean` handelt es sich um sogenannte skalare Datentypen. Das bedeutet sie können jeweils einen Wert speichern. Wir benötigen jedoch auch nicht-skalare Datentypen um Konzepte wie eine Liste oder Tabelle im Computer abzubilden. 

Tatsächlich haben wir bereits einige Male nicht-skalare Datentypen verwendet.
Eine Zeichenkette (`str`) ist nichts anderes als eine Auflistung einzelner Buchstaben.

</div>

Eine Liste ist die einfachste Form einer Auflistung in den meisten Programmiersprachen. Sie ermöglicht es, mehrere Werte desselben oder unterschiedlicher Datentypen in einer geordneten Reihenfolge zu speichern. 

Eine Darstellung der Temperaturwerte aus den Notizen der Krankenschwester kann als abstrakte Liste so dargestellt werden:

![Eine Liste](img/5/liste2.png "Die Temperaturliste im Computer") 

Eine Liste ist indexiert, das bedeutet, dass Sie auf einzelne Elemente in der Liste zugreifen können, indem Sie ihren Index verwenden. Zum Beispiel kann hier auf das erste Element mit dem Index 0, auf das letzte mit dem Index 3 zugegriffen werden.


<div class="alert exercise">

Frage
-----

Welche der folgenden mathematischen Konzepte sind skalaren Werte?

- [[X]] Der Winkel $\alpha$ in einem Dreieck
- [[ ]] Der Vektor $\vec{v} \in \mathbb{R}^3$
- [[ ]] Die Menge der natürlichen Zahlen $\mathbb{N}$
- [[X]] Der Koeffizient $a$ der Parabel $y=ax^2$
- [[ ]] Die Matrix $\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}$

</div>



[^1]: Wie Sie wissen, enthält eine Menge in der Mathematik keine doppelten Elemente. Auflistungen in der Informatik enthalten jedoch häufig ein Element mehrfach.
[^2]: Wir könnten zwar für jeden Tag eine neue Variable anlegen, aber damit wären einfache Operationen wie den Durschnitt oder das Maximum zu berechnen sehr aufwändig.

## Listen in Python

Um eine Liste in Python zu erstellen, definiert man einfach eine Variable, die mehrere Werte enthält. Diese Werte werden in eckige Klammern gesetzt und mit Kommas getrennt.  
In diesem Beispiel speichern wir die täglichen Fiebermessungen eines Patienten in der Variable `fieber`:

```python 
fieber = [37.4, 37.7, 38.4, 38.8]
```
@Pyodide.eval

Auf einzelne Elemente der Liste können wir zugreifen, in dem wir den Index des Elements in eckigen Klammern angeben. Beachten Sie, dass das erste Element den Index „Null“ hat.

`fieber[1]` gibt also das zweite Element zurück. Mit `fieber[0]` erhalten wir das erste Element:

```python 
fieber[1]
fieber[0]
```
@Pyodide.eval

Die Funktion `len`, kurz für „length“ gibt die Anzahl der Elemente in der Liste aus. In diesem Fall vier:
```python 
>>> len(fieber)
4
```

Auch Listen sind in Python Objekte: sie unterstützen die Methode „append“, die den Parameter der Liste hinzufügt.  
Mit `fieber.append` fügen wir einen neuen Wert hinzu:

```python 
>>> fieber.append(37.7)
>>> fieber
[37.4, 37.7, 38.4, 38.8, 37.7]
```

Die Liste enthält nun den neuen Wert, und hat eine Länge von Fünf. 
Natürlich kann auch ein bereits existierender Wert in einer Liste geändert werden. So weisen wir hier dem letzten Wert der Liste – `fieber[4]` – den neuen Wert 37.5 zu:

```python 
>>> fieber[4] = 37.5
>>> fieber
[37.4, 37.7, 38.4, 38.8, 37.5]
```
Sie sehen, dass an Index 4 nun der neue Wert steht.

Wir können dem letzten Wert der Liste aber auch die Zeichenkette „keine Messung“ zuweisen. Das macht zum Beispiel Sinn, wenn an diesem Tag kein Fieber gemessen wurde. 

```python 
>>> fieber[4] = "keine Messung"
>>> fieber
[37.4, 37.7, 38.4, 38.8, 'keine Messung']
```

Eine Liste kann nicht nur Zahlen, sondern eine Mischung beliebiger Typen speichern.

Versuchen wir auf einen Index in der Liste zugreifen, der nicht existiert meldet Python einen Fehler:
```python 
>>> fieber[5] = 38.0
Traceback (most recent call last):
  File "<pyshell#12>", line 1, in <module>
    fieber[5] = 38.0
IndexError: list assignment index out of range
```

Hier versuchen wir den Wert mit dem Index 5 neu zuzuweisen, die Liste enthält aber nur Werte von Index Null bis Vier. Das resultiert in dem Fehler „IndexError“.

Listen sind ein sogenannter Sequenztyp und Python bietet zahlreiche eingebaute Funktionen, die auf solchen Sequenztypen operieren.
So lässt sich das Minimum `min`, und auch das Maximum `max` einer liste einfach ermitteln. In diesem Fall also die niedrigste und höchste Temperatur unserer Liste:

```python 
>>> min(fieber)
37.4
>>> max(fieber)
37.8
```

Auch die Summe aller Werte einer Liste ist so schnell berechnet: 
```python 
>>> sum(fieber)
189.8
```
Im Fall unseres Fieber-Beispiels macht das wenig Sinn. Teilen wir aber die Summe durch die Anzahl an Werten, die wir mit `len` ermitteln erhalten wir den Durchschnittswert:

```python 
>>> sum(fieber)/len(fieber)
37.96
```

Lassen Sie uns nun ein Programm schreiben, das die Daten der Liste auf dem Bildschirm ausgibt. Zunächst setzen wir den Index `i` auf 0.
Dann beginnen wir eine `while`-Schleife, die so lange ausgeführt werden soll, wie der index `i` kleiner als die Länge der Liste ist. Der Schleifeninhalt gibt mit einer `print`-Funktion die Information aus, welche Temperatur an welchem Tag gemessen wurde.
In der nächsten Zeile wird der Index `i` um eins erhöht:

```python 
fieber = [37.4, 37.7, 38.4, 38.8, 37.5]
i = 0
while i < len(fieber):
  print("Am Tag", i,"wurden", fieber[i], "Grad Fieber gemessen")
  i += 1
```

Führen wir das Programm aus werden die Inhalte der Liste wie erwartet ausgegeben
```
Am Tag 0 wurden 37.4 Grad Fieber gemessen
Am Tag 1 wurden 37.7 Grad Fieber gemessen
Am Tag 2 wurden 38.4 Grad Fieber gemessen
Am Tag 3 wurden 38.8 Grad Fieber gemessen
Am Tag 4 wurden 37.5 Grad Fieber gemessen
```

Wir verbessern die Ausgabe, in dem wir die Ausgabe der Tage um eins erhöhen:

```
fieber = [37.4, 37.7, 38.4, 38.8, 37.5]
while i < len(fieber):
  print("Am Tag", i+1,"wurden", fieber[i], "Grad Fieber gemessen")
  i += 1
```

So wird nun ab Tag 1 gezählt:
```
Am Tag 1 wurden 37.4 Grad Fieber gemessen
Am Tag 2 wurden 37.7 Grad Fieber gemessen
Am Tag 3 wurden 38.4 Grad Fieber gemessen
Am Tag 4 wurden 38.8 Grad Fieber gemessen
Am Tag 5 wurden 37.5 Grad Fieber gemessen
```

Wir können die Ausgabe weiter verbessern, in dem wir den Tagen Namen geben.
Dafür legen wir eine neue Liste an, die die Namen der Wochentage enthält.

```python 
fieber = [37.4, 37.7, 38.4, 38.8, 37.5]
wochentage = ["Montag", "Dienstag", "Mittwoch", "Donnerstag", "Freitag", "Samstag", "Sonntag"]
i = 0
while i < len(fieber):
  print("Am", wochentage[i],"wurden", fieber[i], "Grad Fieber gemessen")
  i += 1
```
Führen wir das Programm nun aus, erhalten wir den Namen des Tages anstatt einer Zahl:
```
Am Montag wurden 37.4 Grad Fieber gemessen
Am Dienstag wurden 37.7 Grad Fieber gemessen
Am Mittwoch wurden 38.4 Grad Fieber gemessen
Am Donnerstag wurden 38.8 Grad Fieber gemessen
Am Freitag wurden 37.5 Grad Fieber gemessen
```

:::


### Recamán-Folge

![recaman](img/5/recaman.png "Eine Visualisierung der Recamán-Folge[^1]")

Die Recamán-Folge ist eine mathematische Folge, die 1964 von dem kolumbianischen Mathematiker Bernardo Recamán Santos entdeckt wurde. Die Folge wird wie folgt definiert:

- $a_0 = 0$
- $a_{n+1} = a_n - n$, falls $a_n - n > 0$ und $a_{n+1}$ noch nicht in der Folge vorkommt
- $a_{n+1} = a_n + n$, sonst

Intuitiv erklärt:

> Man beginnt auf dem Zahlenstrahl bei 0. Nun springt man nacheinander um $1,2,3,4\ldots$ auf dem Zahlenstrahl hin- und her. Man versucht zunächst zurückzuspringen, wenn das Ziel aber schon in der Folge vorkommt (oder $\leq 0$ ist), springt man stattdessen um diese Distanz nach vorne.[^2]

So sind die ersten Elemente der Folge:

$$ 0\\ 0+1=1\\ 1+2=3\\ 3+3=6\\ 6-4=2\\ 2+5=7\\ \ldots$$

Die Folge hat einige interessante Eigenschaften und lässt sich schön visualisieren (siehe oben). Man kann sie auch auf dem Klavier spielen, das klingt dann ungefähr so:

@midi(img/5/recaman.mid)



<div class="alert exercise">

Aufgabe
-------

Programmieren Sie ein Python-Programm, das die ersten 100 Elemente der Recamán-Folge berechnet und ausgibt.

```python	

recaman = [0]
index = 1

while len(recaman)<100:
    jump_back = recaman[-1]-index
    if jump_back>0 and jump_back not in recaman:
        recaman.append(recaman[-1]-index)
    else:
        recaman.append(recaman[-1]+index)

recaman
```
@Pyodide.eval

</div>



[^1]: Die Folge kann man auch auf dem Klavier spielen, hier können sie hören wie der Anfang der Folge klingt:


[^2]: Eine ausführliche Erklärung finden Sie auch in diesem Video (englisch): [The Slightly Spooky Recamán Sequence](https://www.youtube.com/watch?v=FGC5TdIiT9U "The Slightly Spooky Recamán Sequence (Numberphile)")