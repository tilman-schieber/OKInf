<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  0.0.1
date:     2024
language: de
narrator: Deutsch Female
logo:     img/3/decisions.png
icon:     img/TU_Logo_kurz.svg
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

### Spielkarten sortieren

<div class="alert alert-yellow">

Stellen Sie sich vor, sie haben einen Stapel unsortierter Spielkarten und sie sollen diese aufsteigend nach ihrem Wert sortieren.

Wie würden Sie das machen?\
Skizzieren Sie ihre Vorgehensweise!

</div>

Musterlösung:
-------------

Es gibt viele Möglichkeiten, Karten zu sortieren. Beim Kartenspielen steckt man die Karten in der Hand in der Regel beim Aufnehmen an den richtigen Platz. Dieses Sortierverfahren nennt man auch [*Insertion Sort*](https://de.wikipedia.org/wiki/Insertionsort) oder *Sortieren durch Einfügen*.

Man kann auch die niedrigste Karte aussuchen, sie ganz nach links legen und dann die nächstkleinste Karte aussuchen und so weiter. Dieses Verfahren nennt man [*Selection Sort*](https://de.wikipedia.org/wiki/Selectionsort) oder *Sortieren durch Auswählen*.




## 2: Werte und Variablen

### Titrationsrechner

<div class="alert alert-yellow">

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




### Quadratische Gleichungen

<div class="alert alert-yellow">

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


## 2: Werte und Variablen

### Aufgabe: Ammoniak

<div class="alert alert-yellow my-4">

Schreiben Sie ein Programm, das

1. die aktuelle Temperatur des Ammoniaks einliest
2. Mit einem oder mehreren if-statements den Aggregatzustand ermittelt
3. den aktuellen Aggregatzustand des Ammoniaks ausgibt, entweder "fest", "flüssig" oder "gasförmig"

</div>

Musterlösung:
-------------

Der Schmelzpunkt von Ammoniak liegt bei −77,7 °C, der - Siedepunkt bei −33 °C

```python
t = float(input())

aggregatzustand = "unbekannt"

if t < -77.7:
    aggregatzustand="fest"
elif t < -33:
    aggregatzustand="flüssig"
else:
    aggregatzustand="gasförmig"

print(aggregatzustand)
```
@Pyodide.eval


### Schaltjahre

* Ein [Schaltjahr](https://de.wikipedia.org/wiki/Schaltjahr)  ist ein Jahr, das durch vier teilbar ist
* *Aber:* Durch 100 teilbare Jahre sind keine Schaltjahre
* *Aber:* Durch 400 teilbare Jahre sind Schaltjahre


<div class="alert alert-yellow my-4">

Schreiben Sie ein Programm, das prüft, ob ein gegebenes Jahr ein Schaltjahr ist:

1. Lesen Sie ein Jahr vom Benutzer ein.
2. Wandeln Sie es in eine Ganzzahl um.
3. Überprüfen Sie, ob das Jahr ein Schaltjahr ist.
4. Geben Sie die Anzahl der Tage aus, die das Jahr hat (365 für normale Jahre, 366 für Schaltjahre).

</div>

Musterlösung:
-------------

Um den Entscheidungsprozess direkt in Code zu übersetzen können wir folgenden Code schreiben:

```python
jahr = int(input())
if jahr % 4 == 0:
    if jahr % 100 == 0:
        if jahr % 400 == 0:
            tage = 366
        else:
            tage = 365
    else:
        tage = 366
else:
    tage = 365

print(tage)
```
@Pyodide.eval

Es ist auch möglich das mit einem einzigen if-else-Statement zu lösen. Können sie herausfinden wie? 

<details>
<summary>*klicken Sie für die Lösung*</summary>

```python
if jahr % 4 == 0 and (jahr % 100 != 0 or jahr % 400 == 0):
    tage = 366
else:
    tage = 365
``` 
</details>
