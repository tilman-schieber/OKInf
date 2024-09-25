<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  1.0.1
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

<div class="alert alert-green">

<h4>Lernziele</h4>


In diesem Kapitel lernen Sie, mit Python einfache mathematische Fragestellungen zu beantworten und die Ergebnisse in Variablen zu speichern.
Außerdem lernen wir einige weitere Grundlagen kennen.

Am Ende können Sie:

1. Grundrechenarten, Potenzieren und Ganzzahldivision in Python anwenden.
2. Zahlen in andere Zahlensysteme umrechnen.
3. Die Grundlagen von Datentypen in Python verstehen.
4. Ergebnisse in Variablen speichern.
5. Eingaben vom Benutzer entgegennehmen und Ausgaben auf dem Bildschirm ausgeben.

</div>



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

Den Python Code in diesem Kurs können Sie direkt in Ihrem Browser ausführen, in dem Sie auf den mit `</>` beschrifteten Knopf drücken. Die "Antwort" von Python erscheint dann direkt darunter.\
Sie können den Code auch verändern, korrigieren oder damit herumexperimentieren.
Rechts unten haben Sie die Möglichkeit, mit den Pfeilen zu den vorherigen Versionen des Codes zurückzukehren.

</div>

Dieser Code gibt uns das Ergebnis für $2+12\cdot 2$, also $26$.

Man bezeichnet nun `2+12*2` als einen *Ausdruck* der Programmiersprache *Python*. Das bedeutet, dass Python es interpretieren und auswerten kann. 

Wie man sieht, verwendet Python *Operatoren*, spezielle Symbole für die Grundrechenarten. In diesem Beispiel steht der Operator `+` für die Addition und der Operator `*` für die Multiplikation. 

In Python gilt wie in der Mathematik, dass Multiplikation und Division Vorrang vor Addition und Subtraktion haben. Deshalb erhalten wir hier $26$ und nicht $28$ als Ergebnis.
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

### Übung: Temperaturumrechnung

<div class="alert alert-yellow">	

Sie lesen den Wetterbericht für New York:

![74 Grad Fahrenheit](img/2/fahrenheit.png)<!-- style="width: 250px"-->

In den USA wird die Temperatur in Fahrenheit gemessen. Man rechnet von Celsius nach Fahrenheit mit folgender Formel um: $$C = \frac{5}{9} \cdot (F - 32)$$

Setzen Sie diese Formel in Python um, und berechnen Sie so, wie warm es in New York ist (gerundet auf zwei Nachkommastellen):



  [[23.33]]
*************************************

```python
round((5/9)*(74-32),2)
```
@Pyodide.eval

*************************************


@pyconsole

</div>



### Übung: Pythagoras

<div class="alert alert-yellow">	

<div class="flex-container">

<div class="flex-child">

<!--style="
  max-width: 115px;
  display: inline-block;
  stroke: green;" -->
```ascii

 +
 |\
 | \
 |  \ 
a|   \c
 |    \
 +-----+
    b
```


</div>

<div class="flex-child-4">

Links sehen Sie die Skizze eines rechtwinkligen Dreiecks mit den Seiten $a,b,c$.

Ein rechtwinkliges Dreieck hat die Kathetenlängen $$a=900\qquad b=945 $$
Berechnen Sie mit Python die Länge der Hypotenuse $c$!

  [[1305]]
  [[?]] Der Satz des Pythagoras ist $a^2 + b^2 = c^2$.
  [[?]] Die Wurzel einer Zahl $x$ ist $x^{0.5}$.
*************************************
eine einzeilige Lösung in Python könnte so aussehen:

```python
(900**2 + 945**2)**0.5
```

*************************************


@pyconsole

</div>
</div>
</div>


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

Eine nützliche Funktion in Python ist `round()`, die eine Fließkommazahl auf eine bestimmte Anzahl von Dezimalstellen rundet:

```python
round(0.1 + 0.2, 2)
```
@Pyodide.eval

Wir übergeben hier zuerst die Fließkommazahl, die wir runden wollen und dann die Anzahl der Dezimalstellen, auf die gerundet werden soll.
Diese Funktion nimmt also zwei Argumente, die durch Komma getrennt werden.


<div class="alert alert-yellow">	

Frage
------

Was passiert wenn Sie die Funktion `round` mit nur einem Argument aufrufen?

- [[ ]] Sie rundet auf die nächste ganze Zahl ab.
- [[X]] Sie rundet auf die nächste ganze Zahl auf oder ab.
- [[ ]] Sie rundet auf die nächste ganze Zahl auf.
- [[ ]] Es gibt einen Fehler.
  

</div>


Python erlaubt es auch, Fließkommazahlen in wissenschaftlicher Notation zur Basis 10 anzugeben. Die Avogadro-Konstante[^1] $6.02214076 \cdot 10^{23}$ und das Gewicht eines Elektrons $9\cdot 10^{-31}$ kg schreibt man in Python wie folgt:

```python
6.02214076e23
9e-31
```

Man schreibt also zunächst die sogenannte Mantisse[^2], dann ein e gefolgt vom Exponenten zur Basis 10.

[^1]: Die [Avogadro-Konstante](https://de.wikipedia.org/wiki/Avogadro-Konstante) gibt die Anzahl der Atome oder Moleküle in einem Mol einer Substanz an.
[^2]: Die Mantisse ist der Teil einer Zahl, der die signifikanten Stellen enthält. 

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

### Übung: Asymmetrische Verschlüsselung

Asymmetrische Verschlüsselung benutzt einen öffentlichen Schlüssel um Nachrichten an eine Person zu verschlüsseln, die diese dann mit einem privaten Schlüssel entschlüsseln kann.

Als einfaches Beispiel kann man $$priv=17$$ als privaten und $$pub=2753$$ als öffentlichen Schlüssel verwenden.\
Verschlüsselt wird dann nach der Formel 

$$m^{priv}\!\!\mod 3233$$ und entschlüsselt nach $$c^{pub}\!\!\mod 3233$$
**mod** steht für den Modulo-Operator, den Sie in Python ja bereits kennengelernt haben.

Verwenden Sie Python um die folgenden Aufgaben zu lösen:

<div class="alert alert-yellow">


Verschlüsseln Sie die Nachricht $m=123$:[^1]

  [[855]]
  [[?]] Versuchen Sie die obige Formel in Python umzusetzen.
  [[?]] Der Modulo-Operator in Python ist `%`.
*************************************
nach der obigen Formel setzen wir einfach ein:

```python
123**17 % 3233
```
so erhalten wir $855$.

*************************************

</div>


<div class="alert alert-yellow">

Entschlüsseln Sie die codierte Nachricht $c=2573$:

  [[377]]
*************************************
wir setzen ein:

```python
2573**2753 % 3233
```
so erhalten wir $377$.

*************************************

@pyconsole [^2]

</div>

[^1]: Klicken Sie auf den 💡-Knopf neben der Aufgabe um Hinweise zu erhalten. Der ✔-Knopf zeigt die Lösung".
[^2]: Dieser Knopf öffnet ein neues Fenster mit einer browserbasierten Python-Konsole. Sie können es im Hintergrund immer offen lassen um Aufgaben zu lösen oder die Lerninhalte nachzuvollziehen.

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

Was ist die Summe der Oktalzahl $7141_8$ und der Hexadezimalzahl $\text{C24}_{16}$?

  [[6789]]

@pyconsole

</div>

## Variablen

So wie wir in der Mathematik Variablen nutzen, denen wir Werte zuweisen können, verwendet auch ein Computerprogramm Variablen. Variablen sind in der Informatik nichts anderes als benannte Speicherplätze für Werte. Mit dem Operator = für die sogenannte Zuweisung können wir eine neue Variable einführen:

```python
x = 5
x + 2
```
@Pyodide.eval

Variablennamen können Zahlen, Buchstaben und den Unterstrich _ enthalten. Sie dürfen aber nicht mit einer Zahl beginnen.

Folgende Variablennamen sind gültig:

```python 
vorname
vorname2
mein_Alter
WARNUNGSTEXT
_temp
```

Folgende Variablennamen sind aber ungültig:

```python 
27_feld
WARNUNG!
name-2
$alter
```

<div class="alert alert-yellow" style="">

Aufgabe
-------

Welche der folgenden Variablennamen sind gültig?

[[x]] `__intern__`
[[ ]] `20%discount`
[[x]] `Größe`
[[x]] `_`
[[x]] `m5L2K3`
[[ ]] `first.name`

</div>

Ab Python Version 3.0 ist es möglich, Schriftzeichen nicht-englischer Sprachen zu verwenden. So kann 姓名, радиус oder π als Variable verwendet werden.

Auch wenn kurze Variablennamen praktisch sein können, sollte man als Programmierer darauf achten, dass die Variablennamen informativ sind.

Diese beiden Codebeispiele machen das gleiche, das auf der linken Seite ist aber für einen Menschen leichter zu verstehen:

<div class="flex-container">

<div class="flex-child">

```python	
betrag_euro = 20
wechselkurs = 1.1
betrag_dollar = betrag_euro * wechselkurs
```

</div>

<div class="flex-child">

```python	
e = 20
k = 1.1
d = e * k
```

</div>
</div>


## Ein- und Ausgabe
In allen bisherigen Beispielen haben wir Python direkt die Ausdrücke gegeben, die es auswerten sollte. Im Normalfall schreibt man aber Programme, die mit dem Benutzer interagieren. 

Dafür müssen wir Python dazu bringen, Eingaben vom Benutzer entgegenzunehmen und Ausgaben auf dem Bildschirm auszugeben.

Wir beginnen mit einem einfachen Beispiel, das den Benutzer nach seinem Namen fragt und ihn dann begrüßt:

```python
name = input()
print("Hallo", name)
```
@Pyodide.eval[^1]

Der Befehl `input()` wartet auf eine Eingabe des Benutzers und gibt diese als Zeichenkette zurück. Optional kann als Argument auch ein Text angegeben werden, der als Eingabeaufforderung angezeigt wird.
Der Befehl `print()` gibt die Argumente auf dem Bildschirm aus. Er nimmt beliebig viele Argumente und gibt diese durch Leerzeichen getrennt aus.

<div class="alert alert-blue">

Zeichenketten oder *Strings*
----------------------------

In Python werden Zeichenketten oder *Strings*[^2] in Anführungszeichen geschrieben. Man kann entweder einfache Anführungszeichen `'` oder doppelte Anführungszeichen `"` verwenden. Strings die von drei Anführungszeichen begrenzt werden, können auch Zeilenumbrüche enthalten.
Aber auch in normalen Zeichenketten kann man durch die Sequenz[^3] `\n` einen Zeilenumbruch erzeugen.

Hier ein paar Beispiele für gültige Strings:

```python
"Das ist ein String"
'Das ist auch ein String'
'Man kann die jeweils "anderen" Anführungszeichen in einem String verwenden'
"""Das ist ein String, der
über mehrere
Zeilen
geht"""
"Auch dieser String\nenthält einen Zeilenumbruch"
```

Es gibt noch zahlreiche spezielle Schreibweisen für Strings, die Sie später kennenlernen werden. Für einfache Ein- und Ausgabe reichen diese aus.

</div>

Im letzten Abschnitt haben wir Euro in Dollar umgerechnet, sehr viel mehr Sinn macht ein Programm, das den Benutzer nach dem Betrag in Euro fragt und dann den Betrag in Dollar ausgibt.

```python	
eingabe = input()
betrag_euro = float(eingabe)
wechselkurs = 1.1
betrag_dollar = round(betrag_euro * wechselkurs, 2)
print("Der Betrag in Dollar ist:", betrag_dollar)
```
@Pyodide.eval

Dieses Codebeispiel verwendet die bereits bekannten Befehle `input()` und `print()` für die Ein- und Ausgabe.
`float()` verwenden wir hier um den eingegebenen Wert in eine Fließkommazahl umzuwandeln[^4]. Da `input()` immer eine Zeichenkette zurückgibt, müssen wir den Wert umwandeln, um damit rechnen zu können.\
Auch runden wir das Ergebnis auf zwei Dezimalstellen, wie das bei Währungen üblich ist.


[^1]: Wenn Sie dieses Programm im Browser ausführen, erscheint normalerweise ein Eingabefeld, in das Sie Eingaben machen können. Führen Sie das Programm auf ihrem Rechner aus, wird die Eingabe in der Konsole erwartet.
[^2]: Der Typ von Zeichenketten wird in Python mit `str` abgekürzt. Das können Sie z.B. mit `type("Hallo")` überprüfen.
[^3]: Man spricht von einer *Escape-Sequenz*. Es gibt noch weitere, wie `\t` für einen Tabulator. Da `\` damit eine besondere Bedeutung hat, muss in einem String `\\` geschrieben werden wenn man einen einfachen Backslash haben möchte.
[^4]: auf ähnliche Weise können Sie auch `int()` verwenden, um eine Zeichenkette in eine ganze Zahl umzuwandeln, oder umgekehrt mit `str()` eine Zahl in eine Zeichenkette.

## Kommentare

Jede Zeile in Python, die mit einem `#` beginnt, wird von Python ignoriert. Diese Zeilen werden als *Kommentare* bezeichnet und dienen dazu, den Code zu dokumentieren. 

Das Programm aus dem [letzten Abschnitt](#ein-und-ausgabe) könnte auch so aussehen:

```python	
# lese die Eingabe des Benutzers als String ein
eingabe = input()
# konvertiere den String in eine Fließkommazahl
betrag_euro = float(eingabe)
# setze den Wechselkurs
wechselkurs = 1.1
# berechne den Betrag in Dollar und runde auf zwei Stellen
betrag_dollar = round(betrag_euro * wechselkurs, 2)
# gebe den Betrag in Dollar aus
print("Der Betrag in Dollar ist:", betrag_dollar)
```

Der Code ist für Python völlig gleichwertig zu der Version ohne Kommentare, aber die Kommentare sind nützlich, um den Code zu dokumentieren und ihn damit anderen Programmierern zu erklären.

Dennoch ist Code, der so verständlich ist, dass er sich selbst erklärt, besser als Code, der viele Kommentare benötigt. Bevorzugen Sie im Zweifelsfall also immer sprechende Variablennamen und klare Strukturen. 


## ❓Aufgaben

<div class="alert alert-yellow">

Python-Ausdrücke
----------------

Wie lautet das Ergebnis der folgenden Ausdrücke und von welchem Typ ist das Ergebnis?

- `(13 % 3) * 2` ergibt [[0|1|(2)|4]] und ist vom Typ [[(int)|float]]
- `2 * 0b100` ergibt [[1|2|4|(8)|200]] und ist vom Typ [[(int)|float]]
- `4 * float("2.5")` ergibt [[0|4|(10)|20]] und ist vom Typ [[int|(float)]]
- `1 + 2 * 3/2` ergibt [[2|(4)|4.5|9]] und ist vom Typ [[int|(float)]]


</div>

---

<div class="alert alert-yellow">

Variablenzuweisung
------------------

```python
x = 2
y = x * 2
z = 1
z = z + 1
x = y + z
print (x+y)
```

Welchen Wert gibt das Programm aus? *(versuchen Sie die Aufgabe im Kopf zu lösen!)*

[[6|7|8|9|(10)]]
**************************
Am Ende des Programms ist `x=6`, `y=4` und `z=2`. Das Programm gibt also $6+4=10$ aus.

**************************


</div>

<div class="alert alert-yellow">

Titrationsrechner✍[^1]
------------------------
Bei einer Titration wird die Konzentration einer unbekannten Lösung bestimmt, indem man eine Lösung bekannter Konzentration (Titrant) in kleinen Mengen zu der unbekannten Lösung gibt, bis z.B. ein Indikator umschlägt.	

Es gilt die Formel $$c_1 \cdot V_1 = c_2 \cdot V_2$$ wobei $c_1$ die Konzentration des Titranten, $V_1$ das Volumen des Titranten, $c_2$ die Konzentration der unbekannten Lösung und $V_2$ das Volumen der unbekannten Lösung ist.

Schreiben Sie ein Programm, das die Konzentration der unbekannten Lösung berechnet.

Volumen der unbekannten Lösung, sowie Konzentration und Volumen des Titranten sollen vom Benutzer eingegeben werden. 

</div>


<div class="alert alert-yellow">

Quadratische Gleichungen✍
--------------------------

Eine Gleichung der Form $ax^2 + bx + c = 0$ lässt sich mit der *quadratischen Formel* lösen:

$$x_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

Schreiben Sie ein Programm, das die Lösungen einer quadratischen Gleichung berechnet. Die Koeffizienten $a$, $b$ und $c$ sollen vom Benutzer eingegeben werden. Und dann die Nullstellen $x_1$ und $x_2$ ausgegeben werden.

</div>



[^1]: Aufgaben mit diesem Symbol werden nicht online korrigiert und sind für die Vertiefung des Stoffes gedacht. Sie können die Aufgaben in einer Python-Umgebung Ihrer Wahl lösen.