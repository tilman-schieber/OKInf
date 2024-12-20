<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  1.1.0
date:     2024
language: de
narrator: Deutsch Female
logo:     img/B/logo.png
icon:     img/TU_Logo_kurz.svg
comment:  Musterlösungen für die Aufgaben aus dem Kurs.
import:   https://raw.githubusercontent.com/LiaTemplates/Pyodide/master/README.md
import:   macros/macros.md
link:     styles/main.css

-->

# Musterlösungen



<div class="alert summary">

<h4>Musterlösungen</h4>


Hier finden Sie die Lösungen zu den Vertiefungsaufgaben (mit dem Symbol ✍).

</div>

<!-- class="context"-->
Für den Überblick über den gesamten Kurs kommen Sie @[lialink(hier zurück zur Kursübersicht)](0_Inhalt.md).


## 1: Einführung in Python

### Spielkarten sortieren

<div class="alert exercise">

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

<div class="alert exercise">

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

<div class="alert exercise">

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


## 3: Entscheidungen

### Aufgabe: Ammoniak

<div class="alert exercise my-4">

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


<div class="alert exercise my-4">

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


## 4: Wiederholung

### Summe ungerader Zahlen 

<div class="alert exercise my-3">


Teil 1
------

Lesen Sie eine Ganzzahl $n$ vom Benutzer ein und geben Sie die Summe der ersten n ungeraden Zahlen aus.

für $n=5$ wäre das $1+3+5+7+9=25$

---

Teil 2
------

- Die Summe der ersten $2$ ungeraden Zahlen ist $1+3=4$, 
- die Summe der ersten $3$ ungeraden Zahlen ist $1+3+5=9$, 
- die Summe der ersten $4$ ungeraden Zahlen ist $1+3+5+7=16$. 

Es fällt auf, dass die Summe der ersten $n$ ungeraden Zahlen immer $n^2$ zu ergeben scheint.

Schreiben Sie ein Programm, das überprüft, ob diese Vermutung stimmt. Es reicht wenn Sie es für alle $n \leq 10000$ zeigen.

</div>

Musterlösung:
-------------

Teil 1:

```python
n = int(input())
summe = 0
while n > 0:
    summe += 2*n-1
    n -= 1
print(summe)
```
@Pyodide.eval

Teil 2:

```python
n = 1
while n <= 10000:
    summe = 0
    k = n
    while k > 0:
        summe += 2 * k - 1
        k -= 1
    if summe != n ** 2:
        print("Vermutung falsch für n =",n)
    n += 1

print("Vermutung stimmt für alle n ≤ 10000")
```
@Pyodide.eval


### Alternierende Reihe

Die alternierende Reihe ist eine mathematische Reihe, die sich durch das Vorzeichen der Summanden auszeichnet. Die Summe der alternierenden Reihe ist definiert als:

$$
1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \frac{1}{5} - \frac{1}{6} + \ldots
$$

Die Summe der alternierenden Reihe konvergiert gegen den natürlichen Logarithmus von 2.

<div class="alert exercise my-3">

Aufgabe
-------

Schreiben Sie ein Programm, das die Summe der alternierenden Reihe und damit $\ln(2)$ berechnet. Sie können abbrechen, wenn die Terme kleiner als $10^{-6}$ sind.

</div>

Musterlösung
------------

```python
summe = 0
i = 1
while 1/i > 1e-6:
    if i % 2 == 0:
        summe -= 1/i
    else:
        summe += 1/i
    i += 1

print(summe)
```
@Pyodide.eval




### Fizzbuzz

[Fizzbuzz](https://de.wikipedia.org/wiki/Fizz_buzz) ist ein Kinderspiel, bei dem Kinder abwechseln von 1 auf 100 zählen. Dabei ersetzen sie jedes Vielfache von 3 durch "Fizz", jedes Vielfache von 5 durch "Buzz" und jedes Vielfache von 15 durch "FizzBuzz".

Man zählt also:

<!-- class="ml-3"-->
***"1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, FizzBuzz"*** 

und so weiter.

<div class="alert exercise my-4">

Aufgabe
--------

Schreiben Sie ein Programm, das von 1 bis 100 zählt und dabei die Zahlen durch "Fizz", "Buzz" oder "FizzBuzz" ersetzt, wenn sie die entsprechenden Bedingungen erfüllen.

</div>

Musterlösung
------------

```python
for i in range(1,101):
    if i % 15 == 0:
        print("FizzBuzz")
    elif i % 3 == 0:
        print("Fizz")
    elif i % 5 == 0:
        print("Buzz")
    else:
        print(i)
```
@Pyodide.eval


## 5: Listen&Schleifen

### Fieberliste 2.0

<div class="alert exercise">

Fieberliste 2.0
---------------

Die Fieberliste soll jeweils für eine Woche geführt werden. Der erste Messwert steht also für Montag, der zweite für Dienstag und so weiter.
Verwenden Sie eine zusätzliche Liste mit den Namen der Wochentage.

Passen Sie das Programm so an, dass die Tage mit Namen ausgegeben werden.\
Also z.B.: `Am Montag wurden 37.4 Grad gemessen`



Hier unser Ausgangsprogramm:

```python 
fieber = [37.4, 37.7, 38.4, 38.8, 37.5]
i = 0
while i < len(fieber):
  print("Am Tag", i + 1 ,"wurden", fieber[i], "Grad gemessen")
  i += 1
```
@Pyodide.eval

---

⭐️ ***Bonus:*** Man spricht von "erhöhter Temperatur" wenn die Temperatur über 37.5 Grad liegt und von Fieber bei über 38 Grad. Geben Sie zusätzlich aus, ob der Patient an einem Tag erhöhte Temperatur oder Fieber hatte.	

</div>

Musterlösung:
-------------


```python
fieber = [37.4, 37.7, 38.4, 38.8, 37.5]
wochentage = ["Montag", "Dienstag", "Mittwoch", "Donnerstag", "Freitag"]
i = 0
while i < len(fieber):
    ausgabe = "Am " + wochentage[i] + " wurden " + str(fieber[i]) + " Grad gemessen. "
    if fieber[i] > 38:
        ausgabe += "Fieber!"
    elif fieber[i] > 37.5:
        ausgabe += "Erhöhte Temperatur."
    print(ausgabe)
    i += 1
```
@Pyodide.eval

 *Anmerkung:*\
 Hier wird die Liste der Wochentage hinzugefügt und die Ausgabe entsprechend angepasst. Zur Lösung der Bonusaufgabe fügen wir einer temporären Variable `ausgabe` eine Meldung hinzu, wenn es sich um erhöhte Temperatur oder Fieber handelt. Wenn sie die Zeilen 6-9 löschen, erhalten Sie die Lösung zur Aufgabe ohne Bonus.

### Fibonacci-Zahlen

<div class="alert exercise">

Aufgabe
-------

Programmieren Sie ein Programm, das mit der Liste `fib = [1, 1]` beginnt und die ersten 100 Fibonacci-Zahlen berechnet und an die Liste anhängt.

Was ist die 100. Fibonacci-Zahl?

[[ 354224848179261915075 ]]
[[?]] Achtung: Die erste Fibonacci-Zahl ist `fib[0]`, die 100. Fibonacci-Zahl ist `fib[99]`.


</div>

Musterlösung:
-------------

```python
fib = [1, 1]
for i in range(98):
    fib.append(fib[-1] + fib[-2])
fib[99]
```
@Pyodide.eval

### Recamán-Folge

Aufgabe
-------

Die Recamán-Folge ist eine mathematische Folge, die 1964 von dem kolumbianischen Mathematiker Bernardo Recamán Santos erfunden wurde. Die Folge wird wie folgt definiert:

- $a_0 = 0$
- $a_{n+1} = a_n - n$, falls $a_n - n > 0$ und $a_{n+1}$ noch nicht in der Folge vorkommt
- $a_{n+1} = a_n + n$, sonst

Programmieren Sie ein Python-Programm, das die ersten 100 Elemente der Recamán-Folge berechnet und ausgibt.

</div>

Musterlösung:
-------------

```python	

recaman = [0]
index = 1

while len(recaman)<100:
    jump_back = recaman[-1]-index
    if jump_back>0 and jump_back not in recaman:
        recaman.append(recaman[-1]-index)
    else:
        recaman.append(recaman[-1]+index)
    index += 1

recaman
```
@Pyodide.eval


### Sieb des Eratosthenes

1. Erstelle eine Liste aller Zahlen von 2 bis $n$.
2. Beginne mit der ersten noch nicht gestrichenen Zahl in der Liste und streiche alle Vielfachen dieser Zahl aus der Liste.
3. Gehe zur nächsten ungestrichenen Zahl in der Liste. Ist sie kleiner als $\sqrt{n}$ wiederhole den Schritt 2.
4. Alle nicht gestrichenen Zahlen auf der Liste sind Primzahlen.




<div class="alert exercise">

Aufgabe
-------

Setzen Sie den Algorithmus in Python um. Berechnen Sie alle Primzahlen unter einer Million ($10^6$).

Überlegen Sie sich zunächst wie Sie das "aus der Liste streichen" implementieren wollen.
Hier zwei Ideen:

1. Erstellen Sie eine Liste aller Zahlen bis 1000000. Um eine Zahl zu streichen, entfernen Sie sie aus der Liste.

2. Erstellen Sie eine Liste mit einer Million `True`-Werten. Um eine Zahl `n` zu streichen, setzen Sie `Liste[n]` auf `False`. 

Was ist die größte Primzahl kleiner als eine Million?

</div>

Musterlösung:
-------------

```python
n = 1000000
primzahlen = [True] * n
primzahlen[0] = primzahlen[1] = False

for i in range(2, int(n**0.5)+1):
    if primzahlen[i]:
        for j in range(i*i, n, i):
            primzahlen[j] = False

for i in range(n-1, 0, -1):
    if primzahlen[i]:
        print(i)
        break


```
@Pyodide.eval



