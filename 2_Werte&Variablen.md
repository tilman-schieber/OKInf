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
import:   macros/macros.md
import:   https://raw.githubusercontent.com/LiaTemplates/Pyodide/master/README.md
link:     styles/main.css

-->

# 2. Werte und Variablen

<!-- class="lead" -->
In diesem Kapitel lernen Sie, mit Python einfache mathematische Fragestellungen zu beantworten.\
Am Ende können Sie:

1. Grundrechenarten, Potenzieren und Ganzzahldivision in Python anwenden.
2. Zahlen in andere Zahlensysteme umrechnen.
3. Die Grundlagen von Datentypen in Python verstehen.
4. Ergebnisse in Variablen speichern.

## Grundrechenarten in Python

Wie der Name Computer – oder auf Deutsch Rechner – zeigt, ist das Beantworten arithmetischer Fragestellungen eine Grundfunktion aller Computer. So kann auch Python Rechenaufgaben für uns lösen. 

Hier stellen wir Python die Rechenaufgabe $2+12\cdot2$:

```python
2+12*2
```
@Pyodide.eval

<div class="alert alert-blue">


Interaktives Python
--------------------

Den Python Code in diesem Kurs können Sie direkt in ihrem Browser ausführen, in dem Sie auf den mit `</>` beschrifteten Knopf drücken. Die "Antwort" von Python erscheint dann direkt darunter.\
Sie können den Code auch verändern, korrigieren oder damit herumexperimentieren.
Rechts unten haben Sie die Möglichkeit, mit den Pfeilen zu den vorherigen Versionen des Codes zurückzukehren.

</div>

Dieser Code gibt uns das Ergebnis für $2+12\cdot 2$, also $26$.

Man bezeichnet nun `2+12*2` als einen *Ausdruck* der Programmiersprache *Python*. Das bedeutet, dass Python es interpretieren und auswerten kann. 

Wie man sieht, verwendet Python *Operatoren*, spezielle Symbole für die Grundrechenarten. In diesem Beispiel steht der Operator `+` für die Addition und der Operator `*` für die Multiplikation. 

In Python gilt wie in der Mathematik, dass Multiplikation und Division Vorrang vor Addition und Substraktion haben. Deshalb erhalten wir hier $26$ und nicht $28$ als Ergebnis.
Wollen wir die Auswertungsreihenfolge ändern, können wir die Addition in Klammern setzen:

```python
(2+12)*2
```
@Pyodide.eval


Dieser Ausdruck entspricht nun $(2+12)\cdot 2 = 28$ 

Natürlich können wir auch subtrahieren und dividieren:

```python
5-4/2
```
@Pyodide.eval

Hier steht `-` für die Substraktion und `/` für die Division.

## Datentypen in Python

Verschiedene Typen von Daten werden in einem Computer unterschiedlich gespeichert. Während man in sogenannten *statischen Programmiersprachen* den jeweiligen Datentyp als Programmierer selbst festlegt, wählt *Python* als *dynamische Programmiersprache*[^1] einen passenden Typ selbst aus.

Welchen *Datentyp* ein *Ausdruck* hat, lässt sich durch die *Funktion* `type()` herausfinden. Wir erhalten als Antwort den Datentyp des Ausdrucks, der sich zwischen den Klammern befindet.

`type()` ist eine in Python eingebaute *Funktion* [^2]. Wir übergeben ihr einen Ausdruck und erhalten dann einen Rückgabewert.  


```python
type(20)
```
@Pyodide.eval

Der Wert `20` hat die *Klasse* `int`, das steht für Englisch *integer*, also ganze Zahlen.

Das Ergebnis einer Division ist nicht unbedingt eine ganze Zahl, weshalb auch das Resultat einer Division in Python von einem anderen Typ ist:

```python
type(5-4/2)
```
@Pyodide.eval

Das Ergebnis der Division ist also von der *Klasse* `float`; kurz für *Fließkommazahl*. 
Selbst wenn das Ergebnis als `int` dargestellt werden könnte, erhalten wir hier eine solche Fließkommazahl zurück.

Sie werden bald noch viele weitere Datentypen kennenlernen. Probieren Sie doch einmal die Funktion `type` mit verschiedenen Ausdrücken aus. Können Sie neue Datentypen finden?[^3]





[^1]: Java, C, C++ und Pascal sind Beispiele für statische Programmiersprachen. Python, Javascript, PHP und Lua sind dynamisch. 

[^2]: Später werden Sie auch lernen, eigene Funktionen zu programmieren.

[^3]: Was ist `type("Hallo")`? Und was `type(int)` oder `type(bin)`? Können Sie sich die Ergebnisse erklären?

## Fließkommazahlen

Schreiben wir in Python eine Zahl mit Dezimalpunkt, versteht Python sie automatisch als Fließkommazahl.

```python
type(2.0 + 3)
```
@Pyodide.eval

Beachten Sie, dass Python einen Punkt als Dezimaltrennzeichen verwendet und nicht wie im Deutschen üblich ein Komma.

Rechnen wir mit Fließkommazahlen, können überraschende Ergebnisse auftreten:


```python
0.1 + 0.2
```
@Pyodide.eval


Auch wenn hier nur eine kleine Abweichung vom richtigen Ergebnis 0.3 auftritt, können solche Fehler zu Problemen führen. Bei der Nutzung von Fließkommazahlen sollten ihre Beschränkungen immer mit bedacht werden.

Python erlaubt es auch, Fließkommazahlen in wissenschaftlicher Notation zur Basis 10 anzugeben. Um zum Beispiel ein Mol oder das Gewicht eines Elektrons zu notieren, schreibt man das in Python wie folgt:

```python
6.02214076e23
9e-31
```

Man schreibt also zunächst die Mantisse[^1], dann ein e gefolgt vom Exponenten zur Basis 10.




## Weitere Operatoren in Python

Neben den Operatoren für die Grundrechenarten bietet Python noch weitere Operatoren an. Potenzieren können wir mit `**`.
So ist $2^8$:

```python
2**8
```
@Pyodide.eval

Das Potenzieren hat Vorrang vor den Grundrechenarten, so erhalten wir:

```python
2**3*2
```
@Pyodide.eval

Also korrekt $2^3 \cdot 2 = 16$

Dividieren wir ganze Zahlen, können wir das Ergebnis immer als einen ganzzahligen Quotient und einen ganzzahligen Rest schreiben.

Zum Beispiel ist bei $10 : 3$ der ganzzahlige Quotient $3$ und der Rest $1$.

In Python erhalten wir den ganzzahligen Quotienten mit dem *Operator* `//`:

```python
10 // 3
```
@Pyodide.eval

Wir überprüfen mit der Funktion `type()`, dass es sich tatsächlich um ein ganzzahliges Ergebnis (vom Typ `int`) handelt:

```python
type(10 // 3)
```
@Pyodide.eval


Den Rest bei der ganzzahligen Division erhält man mit dem *Modulo*-*Operator* `%`: 

```python
10 % 3
```
@Pyodide.eval

### Übung: Assymetrische Verschlüsselung

Assymetrische Verschlüsselung benutzt eine öffentlichen Schlüssel um Nachrichten an eine Person zu verschlüsseln, die diese dann mit einem privaten Schlüssel entschlüsseln kann.

Als einfaches Beispiel kann man $$priv=17$$ als privaten und $$pub=2753$$ als öffentlichen Schlüssel verwenden.\
Verschlüsselt wird dann nach der Formel 

$$m^{priv}\!\!\mod 3233$$ und entschlüsselt nach $$c^{pub}\!\!\mod 3233$$. **mod** steht für den Modulo-Operator, den Sie in Python ja bereits kennengelernt haben.

Verwenden Sie Python um die folgenden Aufgaben zu lösen:

<div class="alert alert-yellow">


Verschlüsseln Sie die Nachricht $m=123$:

  [[855]]


</div>


<div class="alert alert-yellow">

Entschlüsseln Sie die codierte Nachricht $c=2573$:

  [[377]]

@pyconsole [^1]

</div>

[^1]: Dieser Knopf öffnet ein neues Fenster mit einer browserbasierten Python-Konsole. Sie können es im Hintergrund immer offen lassen um Aufgaben zu lösen oder die Lerninhalte nachzuvollziehen.

## Zahlensysteme in Python

Python erlaubt uns nicht nur einfache Berechnungen im Dezimalsystem, es hilft uns auch, gebräuchliche Zahlensysteme zu verwenden.

Beginnt man eine Zahl mit den Zeichen `0b`, wird sie von *Python* als Binärzahl verstanden. So ist `0b10` eine andere Schreibweise für $2$. 

```python
0b10101
```
@Pyodide.eval

Das Ergebnis erhalten wir immer als Dezimalzahl. Die Funktion `bin()` gibt  eine Zahl als Binärzahl zurück. 
So kann man auch das Ergebnis der Rechnung $$ 11011_2 + 101_2$$ als Binärzahl ausgeben:

```python
bin(0b11011+0b101)
```
@Pyodide.eval

Auf gleiche Weise kann man in Python auch mit Oktalzahlen und Hexadezimalzahlen rechnen.
Eine Oktalzahl beginnt mit den Zeichen `0o` und die Funktion `oct()` stellt einen Ausdruck als Oktalzahl dar. 
Hexadezimalzahlen beginnen mit den Zeichen `0x` und die dazugehörige Funktion ist `hex()`

<div class="alert alert-yellow">

Aufgabe
-------

Was ist Summe der Oktalzahl $7141_8$ und der Hexadezimalzahl $\text{C24}_{16}$?

  [[6789]]

@pyconsole

</div>

