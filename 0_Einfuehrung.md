<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  0.0.1
date:     2024
language: de
narrator: Deutsch Female
logo:     img/oberkurs_logo.png
icon:     img/TU_Logo_kurz.png
comment:  Oberkurs Informatik am Studienkolleg der
          Technischen Universität Berlin. <br> Teil 1 (Hallo Python)
import:   https://raw.githubusercontent.com/LiaTemplates/Pyodide/master/README.md
import:  https://raw.githubusercontent.com/liaScript/mermaid_template/master/README.md
link:     styles/main.css
-->

# Was ist Programmieren?


                  {{|> US English Male}}
> “Everybody should learn to program a computer because it teaches you how to think.”
>
> -- Steve Jobs
 
Programmieren ist der Prozess, Anweisungen so zu formulieren, dass ein Computer sie verstehen und ausführen kann. Zunächst muss das Problem in einer Weise strukturiert und beschrieben werden, dass es von einem Computer Schritt für Schritt gelöst werden kann. Diese strukturierten Anweisungen werden als Algorithmus bezeichnet. Anschließend wird der Algorithmus in eine Programmiersprache übersetzt, die der Computer versteht. Das Ergebnis ist ein Programm, das vom Computer ausgeführt werden kann.

![Vom Algorithmus zum Programm](img\1\inf-le01-11c-grafik-algorithmus.png "Abbildung 1: vom Algorithmus zum Programm")


## Von der Idee zum Algorithmus
![al-Khwarizmi](img\1\alkhwarizmi.png "Abbildung 2: ein Portrait von al-Khwarizmi")<!--style = "width: 200px;"-->

Das Wort Algorithmus leitet sich vom Namen eines persischen Mathematikers, *al-Chwarizmi*[^1] (خوارزمی), ab, der Lösungswege für zahlreiche mathematische Probleme entwickelte und mit seinem Buch über Algebra einen großen Einfluss auf die Entwicklung der Mathematik hatte.

Ein Algorithmus ist eine systematische Vorgehensweise zur Lösung eines Problems bzw. einer Aufgabe. In der Informatik wird ein Problem durch eine Eingabe (was ist gegeben) und eine Ausgabe (was möchte man erhalten) beschrieben. Eine einfache Additionsaufgabe kann wie folgt definiert werden. 

_Man bekommt zwei Zahlen als Eingabe und möchte als Ausgabe die Summe dieser beiden Zahlen._

Ein Algorithmus für dieses Problem ist aus der Schule bekannt: 

_Schreibe eine Zahl unter die andere und addiere Stelle für Stelle._

[^1]: s. [Wikipedia - Al Chwarizmi](https://de.wikipedia.org/wiki/Al-Chwarizmi)

### Ein einfacher Algorithmus

Die schriftliche Addition, wie wir Sie aus der Schule kennen, ist ein einfacher Algorithmus.
Ausführlich beschreiben kann ihn wie folgt:


> **Algorithmus zur schriftlichen Addition**
> 
>1. Schreibe die zwei Zahlen untereinander, sodass die Stellenwerte (Einer, Zehner, Hunderter, etc.) übereinander stehen.
>2. Wiederhole für jede Spalte von rechts nach links:
>
>    * Addiere die Ziffern der aktuellen Spalte 
>    * Wenn die Summe 10 oder mehr ist, übertrage 1 zur nächsten linken Spalte.
>    * Schreibe den Einerwert der Summe unter die aktuelle Spalte

??[Addieralgorithmus](html/1/addieralgorithmus.html"Interaktiver Additionsalgorithmus (klicken sie auf den ▶️-Knopf)")<!--style = "border:none; height:390px;"-->


### Algorithmen in der Mathematik
Die schriftliche Addition ist für uns Menschen ein sehr nützlicher Algorithmus, da es schwierig ist, mehrstellige Zahlen im Kopf zu addieren. Für viele weitere mathematische Probleme gibt es teils viele verschiedene Algorithmen um sie zu lösen. Hier sind drei berühmte Beispiele: 

- das Berechnen der Wurzel einer Zahl [^1]
- das Finden von Primzahlen [^2]
- die Berechnung des größten gemeinsamen Teilers (ggT) zweier Zahlen [^3]



[^1]: s. [Wikipedia - Sieb des Eratosthenes](https://de.wikipedia.org/wiki/Sieb_des_Eratosthenes)
[^2]: s. [Wikipedia - Heron Verfahren](https://de.wikipedia.org/wiki/Heron-Verfahren)
[^3]: s. [Wikipedia - Euklidischer Algorithmus](https://de.wikipedia.org/wiki/Euklidischer_Algorithmus)


### Die Welt der Algorithmen

Auch wenn die Studie der Algorithmen in der Mathematik ihren Anfang nahm, kommen Algorithmen nun in allen möglichen Bereichen zum Einsatz, so z.B. für 

- das Sortieren von Zeilen in einer Excel-Tabelle
- das Verschlüsseln geheimer Daten beim Online Banking
- das Berechnen des besten Wegs bei der Routenplanung
- die Empfehlung des nächsten Youtube-Videos
- die Generierung von Bildern aus einer Textbeschreibung mittels künstlicher Intelligenz

Während einige dieser Probleme und die dazugehörigen Algorithmen sehr komplex sind ist das erste Beispiel, das Sortieren, eine alltägliche Aufgabe und kann mit einem einfachen Algorithmus gelöst werden.

> Stellen Sie sich vor, sie haben einen Stapel unsortierter Spielkarten und sie sollen diese aufsteigend nach ihrem Wert sortieren.
> Wie würden Sie das machen?
> 
>    [[___ ___ ___ ___]]



### Bubble Sort
Die am einfachsten zu beschreibende Sortiermethode ist das sogenannte *Bubble Sort*

Dabei wird der Reihe nach jede Karte mit ihrem Nachbar verglichen, sind sie nicht richtig sortiert werden sie getauscht.
Ist man am Ende der Reihe angekommen beginnt man von vorne bis kein Tausch mehr nötig ist.


Ausführlich kann man den Algorithmus für eine Liste aus vergleichbaren Elementen so formulieren:

> **Algorithmus Bubble Sort**
> 
> *Eingabe:* eine unsortierte Liste<br>
> *Ausgabe:* die sortierte Liste
> 
>1. Beginne beim ersten Element 
>2. Vergleiche das aktuelle Element mit dem nächsten
>3. Vertausche die Elemente wenn nötig
>4. Gehe zum nächsten Element
>5. Wiederhole 2.-4. bis das letzte Element erreicht ist
>6. Wenn in diesem Durchlauf kein Element vertauscht wurde, ist die Liste sortiert.
>7. Ansonsten gehe zu 1.


Hier sehen Sie wir Bubble Sort mit einer zufälligen Liste funktioniert:

??[Zahlen sortieren](html/1/bubblesort.html"Interaktiver Bubble Sort Algorithmus (klicken sie auf den ▶️-Knopf)")<!--style = "border:none; height:250px;"-->


#### Flussdiagramm: Bubble Sort

> EIn Flussdiagramm (englisch *Flowchart*) ist eine übersichtliche Weise einen Algorithmus zu skizzieren.
> Flussdiagramme haben noch viele weitere Anwendungsmöglichkeiten und es gibt sie in vielen Varianten.
> Wir verwenden eine sehr einfache Version:
>
> - Wir beginnen oben und folgen den Pfeilen
> - Anweisungen stehen in einem Rechteck
> - Entscheidungen stehen in einer Raute, nach einer Entscheidung folgen wir dem jeweils richtigen Pfeil.
> - Sind wir ganz unten angekommen, so sind wir fertig.

<!--style="max-width: 450px;margin:3em"-->
```mermaid @mermaid
flowchart TD
    
    A[Beginne beim ersten Element] --> B[Vergleiche das aktuelle Element mit dem nächsten]
    B --> C{Vertauschen<br>nötig?}
    C -->|Ja| D[Vertausche die Elemente]
    C -->|Nein| E[Gehe zum nächsten Element]
    D --> E
    E --> F{Ende<br>erreicht?}
    F -->|Nein| B
    F -->|Ja| G{wurde<br>vertauscht?}
    G -->|Nein| H[Liste ist sortiert]
    G -->|Ja| A

```

### ❓Fragen

Welche der folgenden Aussagen sind wahr?
------------------------------------------

- [[X]] Algorithmen sind nach einem persischen Mathematiker benannt
- [[ ]] Der Sieb des Eratosthenes ist ein Algorithmus zur Berechnung der Quadratwurzel
- [[X]] Beim Programmieren übersetzt man Algorithmen in die Sprache des Computers
- [[ ]] Jedes mathematische Problem hat immer genau eine mathematische Lösung
- [[ ]] Algorithmus ist das lateinische Wort für Computerprogramm
*********************************************
* Der Sieb des Eratosthenes ist ein Algorithmus zur Bestimmung von Primzahlen.
* Das Wort Algorithmus leitet sich vom Namen des persischen Mathematikers Al-Chwarizmi ab.
*********************************************

---

Woher kommt der Name Bubble Sort?
----------------------------------------

- [( )] Der Erfinder war ein Programmierer mit dem Spitznamen "Bubbles"
- [( )] Frühe Röhrencomputern nutzten sogenannten "Bubble Memory" um Daten zu speichern.
- [( )] Der Algorithmus wurde von einem Programmierer in einem Sprudelbad erfunden.
- [(X)] unsortierte Elemente bewegen sich wie aufsteigende Luftblase ans Ende der Liste.

---

Sortieren Sie diese Liste mit Bubble Sort. Wie viele Vertauschungen sind nötig?
-------------------------------------------------------------------------------

<!--style="max-width: 400px;"-->
```ascii
.----..----..----..----..----..----.
| 10 || 14 ||  1 || 15 || 34 || 20 |
.----..----..----..----..----..----.
```         

- [( )] 6
- [(X)] 3
- [( )] 2
- [( )] 9
*********************************************

im ersten Durchgang *zwei* Vertauschungen:

<!--style="max-width: 400px;"-->
```ascii
                          
          <-->              <-->     
.----..----..----..----..----..----.
| 10 ||  1 || 14 || 15 || 20 || 34 |
.----..----..----..----..----..----.
```

im zweiten Durchgang *eine* Vertauschung: 

<!--style="max-width: 400px;"-->
```ascii
    <-->                          
.----..----..----..----..----..----.
| 10 ||  1 || 14 || 15 || 20 || 34 |
.----..----..----..----..----..----.
```

Insgesamt also drei!
  
*********************************************
---





## Vom Algorithmus zum Programm

Direkt verstehen kann ein Computer nur die sogenannte Maschinensprache, die z.B. so aussehen kann:

```
B8 01 00 BB 02 00 01 D8   
```

Übersetzt man diesen Code in eine menschenlesbare Form sieht es so aus:

```asm
MOV AX, 0001h
MOV BX, 0002h
ADD AX, BX 
```
Dieses Programm lädt 1 und 2 in Register[^1], addiert deren Inhalt und speichert das Ergebnis in AX.

Außerdem muss man das Problem in einer Weise strukturieren und beschreiben, dass es überhaupt von einem Computer ausgeführt werden kann.<br><br>
In der Informatik beschreiben sogenannte Algorithmen, wie ein bestimmtes Problem systematisch gelöst werden kann.






```python
import sys

for i in range(3):
	print("Hello", 'Python #', i)

```
@Pyodide.eval

[^1]: dabei handelt es sich um einen Speicherplatz direkt im Prozessor. AX,BX und CX sind Namen wichtiger Register.

## Überschrift 2


part




