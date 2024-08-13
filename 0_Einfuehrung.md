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

Ausführlich beschreiben kann man das wie folgt:


> **Algorithmus zur schriftlichen Addition**
> 
>1. Schreibe die zwei Zahlen untereinander, sodass die Stellenwerte (Einer, Zehner, Hunderter, etc.) übereinander stehen.
>2. Wiederhole für jede Spalte von rechts nach links:
>
>    * Addiere die Ziffern der aktuellen Spalte 
>    * Wenn die Summe 10 oder mehr ist, übertrage 1 zur nächsten linken Spalte.
>    * Schreibe den Einerwert der Summe unter die aktuelle Spalte

??[Addieralgorithmus](html/1/addieralgorithmus.html"Interaktiver Additionsalgorithmus (klicken sie auf den ▶️-Knopf)")<!--style = "border:none; height:390px;"-->


Die schriftliche Addition ist für uns Menschen ein sehr nützlicher Algorithmus, da es schwierig ist, mehrstellige Zahlen im Kopf zu addieren. Für viele weitere mathematische Probleme gibt es teils viele verschiedene Algorithmen um sie zu lösen. Hier sind drei berühmte Beispiele: 

- das Berechnen der Wurzel einer Zahl [^2]
- das Finden von Primzahlen [^3]
- die Berechnung des größten gemeinsamen Teilers (ggT) zweier Zahlen [^4]

[^1]: s. [Wikipedia - Al Chwarizmi](https://de.wikipedia.org/wiki/Al-Chwarizmi)
[^2]: s. [Wikipedia - Sieb des Eratosthenes](https://de.wikipedia.org/wiki/Sieb_des_Eratosthenes)
[^3]: s. [Wikipedia - Heron Verfahren](https://de.wikipedia.org/wiki/Heron-Verfahren)
[^4]: s. [Wikipedia - Euklidischer Algorithmus](https://de.wikipedia.org/wiki/Euklidischer_Algorithmus)


## Die Welt der Algorithmen

Auch wenn die Studie der Algorithmen in der Mathematik ihren Anfang nahm, kommen Algorithmen nun in allen möglichen Bereichen zum Einsatz, so z.B. für 

- das Sortieren von Zeilen in einer Excel-Tabelle
- das Verschlüsseln geheimer Daten beim Online Banking
- das Berechnen des besten Wegs bei der Routenplanung
- die Empfehlung des nächsten Youtube-Videos
- die Generierung von Bildern aus einer Textbeschreibung mittels künstlicher Intelligenz

Während einige dieser Probleme und die dazugehörigen Algorithmen sehr komplex sind ist das erste Beispiel, das Sortieren, eine alltägliche Aufgabe und auch mit einem einfachen Algorithmus zu lösen.

> Stellen Sie sich vor, sie haben einen Stapel unsortierter Spielkarten und sie sollen sie nach Größe sortieren.
> Wie geht das am schnellsten?
> Haben Sie schon einmal so eine Sortieraufgabe erledigen müssen?
> Wissen Sie noch, wie Sie sie gelöst haben?




Bubble Sort
-----------

??[Zahlen sortieren](html/1/bubblesort.html"Interaktiver Bubble Sort Algorithmus (klicken sie auf den ▶️-Knopf)")<!--style = "border:none; height:250px;"-->




Ein Algorithmus muss nicht notwendigerweise durch ein Programm ausgedrückt werden. Im vorherigen Beispiel wurde ein Sortieralgorithmus demonstriert und erklärt. Man kann also über Algorithmen nachdenken und diskutieren, ohne eine Programmiersprache zu kennen.





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




