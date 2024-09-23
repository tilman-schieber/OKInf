<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  0.0.1
date:     2024
language: de
narrator: Deutsch Female
logo:     img/3/decisions.png
icon:     img/TU_Logo_kurz.png
comment:  Setzen Sie Logik ein, um den Fluss eines Programmes zu steuern
          und so Entscheidungen zu treffen. 
import:   https://raw.githubusercontent.com/LiaTemplates/Pyodide/master/README.md
import:   macros/macros.md
link:     styles/main.css

-->

# Musterlösungen



<div class="alert alert-green">

<h4>Musterlösungen</h4>


Hier finden Sie die Lösungen zu den Vertiefungsaufgaben (mit dem Symbol ✍).

</div>


## 1: Einführung in Python

Übung ✍️
--------

Stellen Sie sich vor, sie haben einen Stapel unsortierter Spielkarten und sie sollen diese aufsteigend nach ihrem Wert sortieren.

Wie würden Sie das machen?\
Skizzieren Sie ihre Vorgehensweise!

</div>

Musterlösung:
-------------

Es gibt viele Möglichkeiten, Karten zu sortieren. Beim Kartenspielen steckt man die Karten in der Hand in der Regel beim Aufnehmen an den richtigen Platz. Dieses Sortierverfahren nennt man auch [*Insertion Sort*](https://de.wikipedia.org/wiki/Insertionsort) oder *Sortieren durch Einfügen*.

Man kann auch die niedrigste Karte aussuchen, sie ganz nach links legen und dann die nächstkleinste Karte aussuchen und so weiter. Dieses Verfahren nennt man [*Selection Sort*](https://de.wikipedia.org/wiki/Selectionsort) oder *Sortieren durch Auswählen*.




## 2: Werte und Variablen


<div class="alert alert-yellow">

Titrationsrechner✍
------------------------
Bei einer Titration wird die Konzentration einer unbekannten Lösung bestimmt, indem man eine Lösung bekannter Konzentration (Titrant) in kleinen Mengen zu der unbekannten Lösung gibt, bis z.B. ein Indikator umschlägt.	

Es gilt die Formel $$c_1 \cdot V_1 = c_2 \cdot V_2$$ wobei $c_1$ die Konzentration des Titranten, $V_1$ das Volumen des Titranten, $c_2$ die Konzentration der unbekannten Lösung und $V_2$ das Volumen der unbekannten Lösung ist.

Schreiben Sie ein Programm, das die Konzentration der unbekannten Lösung berechnet.

Volumen der unbekannten Lösung, sowie Konzentration und Volumen des Titranten sollen vom Benutzer eingegeben werden. 

</div>

Musterlösung:
-------------

```python
V1 = float(input("Volumen Titrant in ml: "))
c1 = float(input("Konzentration Titrant in mol/l: "))
V2 = float(input("Volumen unbekannte Lösung in ml: "))
c2 = c1 * V1 / V2
print("Konzentration der unbekannten Lösung:", round(c2,2), "mol/l")
```


<div class="alert alert-yellow">

Quadratische Gleichungen✍
--------------------------

Eine Gleichung der Form $ax^2 + bx + c = 0$ lässt sich mit der *quadratischen Formel* lösen:

$$x_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

Schreiben Sie ein Programm, das die Lösungen einer quadratischen Gleichung berechnet. Die Koeffizienten $a$, $b$ und $c$ sollen vom Benutzer eingegeben werden. Und dann die Nullstellen $x_1$ und $x_2$ ausgegeben werden.

</div>


Musterlösung:
-------------

```python
a = float(input("a: "))
b = float(input("b: "))
c = float(input("c: "))
d = b**2 - 4*a*c
x1 = (-b + d**0.5) / (2*a)
x2 = (-b - d**0.5) / (2*a)
print("x1 =", x1)
print("x2 =", x2)
```


