<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  0.0.1
date:     2024
language: de
narrator: Deutsch Female
logo:     img/2/datastorage.png
icon:     img/TU_Logo_kurz.png
comment:  Nutzen Sie Python, um mit Werten zu rechnen und die Ergebnisse
          der Berechnungen in Variablen zu speichern.
import:   ./macros.md
import:   ./pyodide.md
link:     styles/main.css

-->

# 2. Werte und Variablen

## Grundrechenarten in Python

Wie der Name Computer – oder auf Deutsch Rechner – zeigt, ist das Beantworten arithmetischer Fragestellungen eine Grundfunktion aller Computer. So kann auch Python Rechenaufgaben für uns lösen. 

Hier stellen wir Python die Rechenaufgabe $2+12\cdot2$:

```python
2+12*2
```
@Pyodide.eval

<div class="alert alert-blue">

Interaktives Python
-------------------

Den Python Code in diesem Kurs können Sie direkt in ihrem Browser ausführen, in dem Sie auf den mit `</>` beschrifteten Knopf drücken. Die "Antwort" von Python erscheint dann direkt darunter.\
Sie können den Code auch verändern, korrigieren oder damit herumexperimentieren.
Rechts unten haben Sie die Möglichkeit, mit den Pfeilen zu den vorherigen Versionen des Codes zurückzukehren.

Probieren Sie:
- Was passiert wenn Sie Unsinn eingeben?
</div>

So erhalten wir das Ergebnis für $2+12\cdot 2$.

Man bezeichnet nun `2+12*2` als einen *Ausdruck* der Programmiersprache *Python*. Das bedeutet, dass Python es interpretieren und auswerten kann. 

Wie man sieht, verwendet Python *Operatoren*, spezielle Symbole für die Grundrechenarten. In diesem Beispiel steht der Operator `+` für die Addition und der Operator`*` für die Multiplikation. 


In Python gilt wie in der Mathematik, dass Multiplikation und Division Vorrang vor Addition und Substraktion haben. Deshalb erhalten wir hier $26$ und nicht $28$ als Ergebnis.
Wollen wir die Auswertungsreihenfolge ändern, können wir die Addition in Klammern setzen:

```python
(2+12)*2
#28
```

Dieser Ausdruck entspricht nun $(2+12)\cdot 2 = 28$ 

```python
5-4/2
#3.0
```

Hier steht `-` für die Substraktion und `/` für die Division. Warum aber gibt *Python* hier `3.0` anstatt einfach `3` an?
Um das zu verstehen müssen Sie zunächst lernen, was ein Datentyp ist.

## Datentypen in Python
Verschiedene Typen von Daten werden in einem Computer unterschiedlich gespeichert. Während man in sogenannten *statischen Programmiersprachen* den jeweiligen Datentyp als Programmierer selbst festlegt, wählt *Python* als *dynamische Programmiersprache* einen passenden Typ selbst aus.

Welchen *Datentyp* ein *Ausdruck* hat, lässt sich durch die *Funktion* `type()` herausfinden. Wir erhalten als Antwort den Datentyp des Ausdrucks, der sich zwischen den Klammern befindet.

`type()` ist eine in Python eingebaute *Funktion*. Wir übergeben ihr einen Ausdruck und erhalten dann einen Rückgabewert. In Lerneinheit 5 werden Sie Funktionen genauer kennenlernen. 


```python
type(20)
# <class 'int'>

type(2+12*2)
# <class 'int'>
```

Diese Werte haben die *Klasse* `int`, das steht für Englisch *integer*, also ganze Zahlen.

Das Ergebnis einer Division ist nicht unbedingt eine ganze Zahl, weshalb auch das Resultat einer Division in Python von einem anderen Typ ist:

```python
5-4/2
#3.0

type(5-4/2)
# <class 'float'>
```

Das erklärt, weshalb das Ergebnis der Division uns mit Nachkommastelle als $3.0$ angegeben wurde: Es ist von der *Klasse* `float`; kurz für *Fließkommazahl*. 
Was es genau damit auf sich hat, lernen Sie später in dieser Lerneinheit wenn wir die *digitale* *Kodierung* von Zahlen erklären.
Selbst wenn das Ergebnis als `int` dargestellt werden könnte, erhalten wir hier eine solche Fließkommazahl zurück.


## Weitere Operatoren in Python

Neben den Operatoren für die Grundrechenarten bietet Python noch weitere Operatoren an. Potenzieren können wir mit `**`.
So ist $2^8$:

```python
2**8
#256
```

Das Potenzieren hat Vorrang vor den Grundrechenarten, so erhalten wir:

```python
2**3*2
#16
```

Also korrekt $2^3 \cdot 2 = 16$

Für viele *Algorithmen*, so auch bei der zuvor vorgestellten Umwandlung von Dezimalzahlen zu Zahlen zur Basis $b$, ist die Ganzzahldivision mit Rest wichtig.

Dividieren wir ganze Zahlen durcheinander, können wir das Ergebnis immer als einen ganzzahligen Quotient und einen ganzzahligen Rest schreiben.

Zum Beispiel ist bei $10 : 3$ der ganzzahlige Quotient $3$ und der Rest $1$.

In Python erhalten wir den ganzzahligen Quotienten mit dem *Operator* `//`:
```python
10 // 3
# 3

type(10 // 3)
# <class 'int'>
```
Wir überprüfen mit der Funktion `type()`, dass es sich tatsächlich um ein ganzzahliges Ergebnis (vom Typ `int`) handelt.

Den Rest bei der ganzzahligen Division erhält man mit dem *Modulo*-*Operator* `%`: 

```python
10 % 3
# 1
```

## Zahlensysteme in Python

Python erlaubt uns nicht nur einfache Berechnungen im Dezimalsystem, es hilft uns auch, gebräuchliche Zahlensysteme zu verwenden.

Beginnt man eine Zahl mit den Zeichen `0b`, wird sie von *Python* als Binärzahl verstanden. So ist `0b10` eine andere Schreibweise für $2$. 

```python
0b10101
# 21
0b101+0b1
# 6
```

Das Ergebnis erhalten wir immer als Dezimalzahl. Die Funktion `bin()` gibt  eine Zahl als Binärzahl zurück. 
So kann man auch das Ergebnis dieser Rechnung als Binärzahl ausgeben:

```python
bin(0b101+0b1)
#'0b110'
```

Auf gleiche Weise kann man in Python auch mit Oktalzahlen und Hexadezimalzahlen rechnen.
Eine Oktalzahl beginnt mit den Zeichen `0o` und die Funktion `oct()` stellt einen Ausdruck als Oktalzahl dar. 
Hexadezimalzahlen beginnen mit den Zeichen `0x` und die dazugehörige Funktion ist `hex()`

So können Sie nun die Aufgaben dieser Lerneinheit mit Python lösen.
Wollen wir zum Beispiel eine Oktal- oder Hexadezimazahl in eine Binärzahl umwandeln, schreiben wir:

```python
bin(0o16)
# '0b1110'
bin(0xfa)
# '0b11111010'
```
