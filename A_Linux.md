<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  1.0.0
date:     2024
language: de
narrator: Deutsch Female
logo:     img/A/linux.png
icon:     img/TU_Logo_kurz.svg
comment:  Eine kurze Einführung in Linux
import:   macros/macros.md
import:   macros/asciinema.md
link:     styles/main.css
-->

# Eine kurze Einführung in Linux
@[asciinema2(`speed: 2, autoPlay:true, rows: 10`)](cast/demo.cast)


<!-- class="context"-->
Diese kurze Einführung zum Thema Linux kann unabhängig vom Rest des Kurses bearbeitet werden.
Für den Überblick über den gesamten Kurs kommen Sie @[lialink(hier zurück zur Kursübersicht)](0_Inhalt.md).


## Was ist ein Betriebssystem?

!["Operator" bei der NASA](img/A/operator.jpg "Quelle: [NASA](https://www.flickr.com/photos/nasacommons/9467782802)")

***Was ist die Aufgabe der Personen auf diesem Bild?***

*Hardwaretechniker?*\
*Programmierer?*\
*Wissenschaftler?*\


Tatsächlich ist nichts davon richtig. Die Personen auf diesem Bild sind sogenannte *Operator*, die die Computer bedienen. 
Ihre Rolle besteht darin, Programme zu laden, deren Ausführung zu überwachen und sicherzustellen, dass die Computer effizient arbeiten. In den Anfangstagen der Computertechnologie mussten Programme direkt in die Hardware geladen werden, was bedeutete, dass alle Programme direkt eine bestimmte Hardware ansprachen.


<div class="alert tip">

<!-- class="lead" -->
**Programme laden im Jahr 1970**

---

Der *Operator* erhält einen Stapel mit Lochkarten vom Programmierer. Jede Lochkarte enthält eine Zeile des Programmcodes. Der *Operator* legt die Lochkarten in den Kartenleser, der die Lochkarten einliest und in den Arbeitsspeicher des Computers lädt. Anschließend startet der *Operator* das Programm und überwacht dessen Ausführung. Wenn das Programm beendet ist, meldet der *Operator* die Ergebnisse an den Programmierer zurück.

---

**Was kann schief gehen?**

- Der Kartenleser liest eine Lochkarte falsch ein oder beschädigt sie.
- Das Programm enthält einen Fehler und der Computer "stürzt ab".
- Der Stapel Karten fällt herunter und die Reihenfolge der Lochkarten wird durcheinander gebracht.

---

![Kartenleser](https://upload.wikimedia.org/wikipedia/commons/1/10/IBM1442.corestore.jpg "Der IBM 1442 Lochkartenstanzer und -leser[^1]") ![Eine Lochkarte](img/A/lochkarte_tu.jpg "eine gestanzte Lochkarte der TU Berlin[^2]") ![Beschädigte Lochkarte](https://upload.wikimedia.org/wikipedia/commons/f/f6/DamagedPunchedCard.jpg "Eine Lochkarte wurde beim Einlesen des Programms beschädigt.[^1]")  ![Lochkarten](https://upload.wikimedia.org/wikipedia/commons/2/26/Punched_card_program_deck.agr.jpg "Ein Programm auf Lochkarten. Der schräge rote Strich hilft die Karten in der richtigen Reihenfolge zu halten.[^1]")

</div>

[^1]: Quelle: Wikimedia Commons
[^2]: Quelle: [Virtuelles Lochkartenmuseum](https://www.punctum.com/interest/punch/html/c0325.de.html)

## Vom Operator zum Operating System

Moderne Computer führen viele verschiedene Programme gleichzeitig aus, kein *Operator* könnte all diese Programme gleichzeitig überwachen. So verwenden wir heute ein *Operating System*, auf deutsch Betriebssystem, um die Aufgaben des *Operators* zu übernehmen.
Betriebssysteme sind spezielle Programme die den Zugriff auf die Hardware steuern und es ermöglichen, dass Programme ausgeführt werden, ohne dass der Programmierer sich mit den technischen Details der jeweiligen Maschine befassen muss.


<div class="flex-container">
<!-- class="flex-child" style="min-width: 180px" -->
```ascii
+-----------------+
|                 |
|    Hardware     |
|                 |
+-----------------+
         |         
+-----------------+
|                 |
| Betriebssystem  |
|                 |
+-----------------+
         |         
+-----------------+
|                 |
|    Software     |
|                 |
+-----------------+
```

<div class="flex-child" style="min-width: 500px">
Betriebssysteme vermitteln also zwischen der Hardware und der Software. Sie abstrahieren[^1] die Hardware und stellen eine Schnittstelle für die Software bereit. Die wichtigsten Aufgaben eines Betriebssystems sind:

- **Prozess- und Speicherverwaltung**: Das Betriebssystem verwaltet die Ausführung von Programmen und den ihnen zugewiesenen Arbeitsspeicher.
- **Dateiverwaltung**: Das Betriebssystem verwaltet Dateien und Ordner und stellt sie für Programme und Anwender in einer Baumstruktur dar.
- **Geräteverwaltung**: Das Betriebssystem erlaubt Programmen, auf Geräte wie Drucker, Tastatur oder Maus zuzugreifen ohne dass technische Details bekannt sein müssen.
- **Benutzerverwaltung**: Fast alle modernen Benutzersysteme sind Mehrbenutzersysteme: Das Betriebssystem trennt die Prozesse und Dateien verschiedener Benutzer voneinander und stellt sicher, dass Benutzer nur auf ihre eigenen Dateien zugreifen können.

</div>
</div>

[^1]: Abstraktion bedeutet, dass technische Details verborgen werden, um die Benutzung zu vereinfachen. So kann ein Betriebssystem beispielsweise benutzt werden um etwas auf dem Bildschirm auszugeben ohne dass der Programmierer wissen muss, wie genau die Hardware des Bildschirms oder der Grafikkarte funktioniert.

## Kurze Geschichte der Betriebssysteme

<div class="flex-container">
<!-- class="flex-child" style="min-width: 400px" -->
```ascii
                    +-----------------+
                    | Großrechner-    |
                    | Betriebssysteme |
                    +--------+--------+
                             |
          +------------------+--------------+
          |                                 |
    +-----+----+                       +----+----+
    |  UNIX    |                       |  DOS    |
    | (1970er) |                       | (1980er)|
    +-----+----+                       +----+----+
          |                                 |
    +-----+-------+                    +----+----+
    |             |                    | Windows |
+---+---+     +---+----+               | (1985)  |
|  BSD  |     | Linux  |               +----+----+
| (1977)|     | (1991) |                    |
+---+---+     +----+---+             +------+-----+
    |              |                 | Windows NT |
+---+-----+        |                 |  (1993)    |
|  macOS  |        |                 +------+-----+
| (2001)  |        |                        |
+----+----+        |                        |
     |         +---+----+          +--------+------+
+----+---+     | Android|          | Windows 10/11 |
|  iOS   |     | (2008) |          |    (2015)     |
| (2007) |     +--------+          +---------------+
+--------+
```

<div class="flex-child">
Die Geschichte der Betriebssysteme begann in den 1960er Jahren mit den ersten Betriebssystemen für Großrechner. In den 1970er Jahren wurde UNIX entwickelt, dessen Nutzerverwaltung, Dateisystem und Aufbau immer noch die Grundlage für heutige Betriebssysteme sind. Aus UNIX gingen in den späten 1970er Jahren BSD (Berkeley Software Distribution) und später Linux (1991) hervor. Bei beiden handelt es sich um UNIX-Varianten die aber frei und quelloffen (*open source*) waren[^1]. Linux ist bis heute weit verbreitet und bildet die Basis für Android (2008).

Parallel dazu entstand in den 1980er Jahren mit DOS ein einfaches Betriebssystem für Personal Computer, aus dem Windows (ab 1985) hervorging. Windows NT (1993) war ein wichtiger Schritt, da es eine neue, stabile Architektur einführte, die die Basis für alle modernen Windows-Versionen wie Windows 10 und Windows 11 bildet.

MacOS basiert auf der Unix-Variante BSD. Auch iOS (2007), das Betriebssystem für mobile Apple-Geräte, baut auf dieser Architektur auf. So sind sogar die zwei vebreitetsten mobilen Betriesbssysteme die Enkelkinder von Unix.

In diesem Kurs lernen wir die Grundlagen der Bedienung von Linux, da Grundkenntnisse in der Bedienung von Linux für viele andere Betriebssysteme von Android bis MacOS hilfreich sind. Selbst Windows 10 und Windows 11 bieten mittlerweile die Möglichkeit, Linux-Programme direkt auszuführen. Außerdem verwenden Server und Cloud-Dienste meistens Linux als Betriebssystem.

</div>
</div>

[^1]: Freie quelloffene Software ist Software, deren Quellcode öffentlich zugänglich ist und von jedem genutzt, verändert und weiterverbreitet werden darf. Somit ist sie auch für den Anwender kostenlos verfügbar. Linux, Firefox, LibreOffice und viele andere Programme sind Beispiele für freie Software.

## Wie komme ich an Linux?

<!--  style="max-width: 400px" -->
![Tux](https://upload.wikimedia.org/wikipedia/commons/3/35/Tux.svg "Tux, das Maskottchen von Linux")
### Linux als Betriebssystem

<!--  style="margin:2em; display:inline-block; width: 150px" -->
<img src="https://upload.wikimedia.org/wikipedia/commons/7/76/Ubuntu-logo-2022.svg">

<!--  style="margin:2em; display:inline-block; width: 110px" -->
<img src="https://upload.wikimedia.org/wikipedia/commons/4/4a/Debian-OpenLogo.svg">

<!--  style="margin:2em; display:inline-block; width: 220px" -->
<img src="https://upload.wikimedia.org/wikipedia/commons/e/e8/Archlinux-logo-standard-version.png">

<!--  style="margin:2em; display:inline-block; width: 150px" -->
<img src="https://upload.wikimedia.org/wikipedia/commons/0/09/Fedora_logo_and_wordmark.svg">

Linux ist eigentlich der Name des Betriebssystemkerns (englisch *Kernel*), also des grundlegenden Teils des Systems, der die Hardware steuert und die Ausführung von Programmen ermöglicht. Für sich allein genommen ist der Kernel jedoch kein vollständiges Betriebssystem. Das erhält man erst durch die Kombination mit einer Vielzahl von Programmen, Tools und Benutzeroberflächen. Diese Gesamtpakete, die den Kernel und all diese zusätzlichen Komponenten enthalten, werden als Distributionen bezeichnet. Bekannte Beispiele dafür sind [Ubuntu](https://ubuntu.com/), [Debian](https://www.debian.org/), [Archlinux](https://archlinux.org/), oder [Fedora](https://getfedora.org/).

Jede dieser Distributionen können Sie als vollwertiges Betriebssystem benutzen.
Wenn sie weiterhin Windows benötigen können Sie Linux auch parallel zu Windows auf Ihrer Festplatte installieren. Beim Start des Computers wählen Sie dann, welches Betriebssystem Sie verwenden möchten. Dies wird als *Dual Boot* bezeichnet.

<!--  class="alert tip" -->
**Tipp:**
Auch wenn die hier genannten Distributionen seit langer Zeit sehr beliebt und weit verbreitet sind, gibt es noch sehr viel mehr. Auch entstehen immer neuere Varianten von bekannten Distributionen, so Beispielsweise [Linux Mint](https://linuxmint.com/) (als Variante von Ubuntu) oder [Manjaro](https://manjaro.org/) (als Variante von Archlinux).\
Seit vielen Jahren führt [DistroWatch](https://distrowatch.com/) eine umfassende Liste von Linux Distributionen.


### Das Windows Subsystem for Linux

Wenn sie Window benutzen und noch nicht bereit sind, Linux auf ihrem Computer zu installieren, besteht ab Windows 10 eine einfachere Möglichkeit: Das Windows Subsystem for Linux (WSL) kann Linux direkt innerhalb von Windows ausführen.

Installation von WSL
====================

1. **Windows-Version überprüfen**:
   - Stellen Sie sicher, dass Sie mindestens **Windows 10 Version 2004** oder höher oder **Windows 11** verwenden. Dies können Sie in den **Einstellungen** unter **System > Info** nachsehen.

2. **Voraussetzungen für WSL aktivieren**:

   - Öffnen Sie die **Systemsteuerung**.
   - Gehen Sie zu **Programme > Programme und Features**.
   - Klicken Sie auf **Windows-Features aktivieren oder deaktivieren**.
   - Aktivieren Sie die Kästchen für:

     - **Windows-Subsystem für Linux**
     - **Virtuelle Maschinen-Plattform**
     - **Hyper-V**

   - Klicken Sie auf **OK** und starten Sie den Computer neu[^1].

3. **Linux-Distribution aus dem Microsoft Store installieren**:

   - Öffnen Sie den **Microsoft Store**.
   - Suchen Sie nach Ihrer gewünschten Linux-Distribution (z.B. Ubuntu) und klicken Sie auf **Installieren**.
   - Aktuell[^2] kann ich [Ubuntu 24.04 LTS](https://apps.microsoft.com/detail/9nz3klhxdjp5) empfehlen.

Nun können Sie ein Linux-Terminal über das Startmenü starten.

[^1]: Bei manchen Computern muss die für WSL benötigte Virtualisierung im BIOS aktiviert werden. Falls Sie eine entsprechende Fehlermeldung erhalten, finden Sie bei [support.microsoft.com](https://support.microsoft.com/de-de/windows/aktivieren-der-virtualisierung-unter-windows-c5578302-6e43-4b4b-a449-8ced115f58e1) mehr Informationen.
[^2]: Stand September 2024. Diese Version wurde im April 2024 veröffentlicht und ist eine LTS-Version, das bedeutet, dass sie mit langfristigem Support (Long-Term Support) für mindestens 5 Jahre, also bis 2029, versorgt wird. LTS-Versionen sind besonders stabil und werden für den Einsatz in produktiven Umgebungen empfohlen.

### MacOS

![Apple](https://upload.wikimedia.org/wikipedia/commons/1/1b/Apple_logo_grey.svg)<!--  style="margin-right:1em; width: 60px" -->
Haben Sie keinen PC sondern einen Mac nutzen Sie bereits ein Betriebssystem, dessen Grundlage auf Unix basiert. MacOS basiert auf BSD, einer Unix-Variante. Sie können auf jedem Mac einfach ein Terminal starten und die meisten Linux-Kommandos verwenden[^1].Um mehr Befehle und Programme zu installieren können Sie [Homebrew](https://brew.sh/) verwenden, ein Paketmanager für MacOS.

[^1]: Eine Einführung gibt es auf [support.apple.com](https://support.apple.com/de-de/guide/terminal/apdb66b5242-0d18-49fc-9c47-a2498b7c91d5/mac)

## Erste Schritte im Terminal
![Terminal](https://upload.wikimedia.org/wikipedia/commons/9/99/DEC_VT100_terminal.jpg "Ein Unix Terminal, Modell VT100" )

### Wer bin ich und wo bin ich?

Egal ob Sie Linux auf ihrem Rechner installiert haben oder WSL bzw. MacOS nutzen: Wir beginnen damit, ein Terminal zu starten[^1] und werden von einer sogenannten *Eingabeaufforderung* begrüßt, die in etwa so aussieht[^2]:

```bash
tilman@Linux:~$
```
Meistens gibt Ihnen diese Eingabeaufforderung ein paar grundlegende Informationen.
Hier in der Form:

```bash
Benutzername@Hostname:Verzeichnis$
```

* **Benutzername** der Name unter dem sie gerade im System angemeldet sind. 
* **Hostname** ist der Name des Computers auf dem das Terminal läuft. Zwar ist das normalerweise einfach der Name ihres Rechners, doch sie können auch Terminals auf entfernten Servern ausführen.
* **Verzeichnis** Hier wird angezeigt, in welchem Verzeichnis Sie sich befinden. Das Kürzel `~` steht dabei für ihr *home*-Verzeichnis (Sie werden gleich lernen, was das bedeutet).

Das Terminal wartet nun darauf, dass sie Befehle eingeben und diese mit <kbd>Enter</kbd> bestätigen.

Manche Befehle lesen sich wie normales Englisch, andere sind Abkürzungen.

So gibt der Befehl `whoami` den aktuellen Benutzernamen aus

`pwd` steht für *print working directory* und gibt an, wo im Dateisystem wir uns gerade befinden.

Hier sehen Sie ein Beispiel *(drücken Sie den Play-Knopf)*:
@[asciinema2(`rows: 5`)](cast/whoami.cast)

<!--  class="alert warning" -->
**Vorsicht root:**
In jedem Linux gibt es den Benutzer *root*, den sogenannten *superuser*. Dieser hat alle Berechtigungen im System und kann deshalb großen Schaden anrichten. Achten Sie darauf, nicht als *root* sondern mit ihrem Benutzernamen angemeldet zu sein.

Vorhin haben wir erwähnt, dass das Symbol `~` eine Abkürzung für das *home*-Verzeichnis ihres Benutzers ist.\
Diese Abkürzung steht also in diesem Fall für den Pfad `home/tilman`, im Ordner `/home` gibt es also für jeden Benutzer einen gleichlautenden persönlichen Ordner[^3]. 



[^1]: Das Terminal finden Sie in den meisten Linux Distributionen und in MacOS unter dem Namen *Terminal* oder so ähnlich. Oft können Sie es auch mit dem Shortcut <kbd>Strg+Alt+T</kbd> starten
[^2]: lassen Sie sich nicht irritieren, wenn ihre Eingabeaufforderung etwas anders aussieht. Ihre Befehle werden von einer sogenannten *shell* entgegengenommen. Ich gehe hier davon aus dass sie die verbreitete shell *bash* verwenden. Verwenden Sie eine andere *shell* kann es etwas anders aussehen.
[^3]: MacOS verwendet den Namen `/Users` statt `/home`.

### Verzeichnisse wechseln

Wie in den meisten Betriebssystemen benutzt auch das Dateisystem in Linux eine hierarchische Ordnerstruktur.
Auf der obersten Ebene ist *root*, das Wurzelverzeichnis. \
Ein Teil einer solchen Struktur sieht wie folgt aus:

<div class="flex-container">

<!-- class="flex-child" style="width: 200px" -->
```ascii
/
|
+--home
|    |
|    +--tilman
|    |
|    +--sreekanth
|
+--bin
|
+--etc
|
+--var
|   |
|   +--log
|
+--dev

```

<div class="flex-child">
Die hier gezeigten Verzeichnisse finden Sie auf jedem Linux oder Unix-System[^1].

- `home` kennen Sie bereits, hier enthält es die persönlichen Ordner zweier Nutzer.
- `bin` enthält installierte Programme
- `etc` enthält Konfigurationsdateien
- `var` enthält zum Beispiel Protokolle (Logs) unter `var/log`.
- `dev` enthält keine Dateien im eigentlichen Sinn, sondern erlaubt direkten Zugriff auf Geräte (*devices*) wie Festplatten oder auf Funktionalitäten wie einen Zufallszahlengenerator.

Um sich in dieser Verzeichnishierarchie zu bewegen, können Sie den Befehl `cd` für *change directory* verwenden.

So bewegen Sie sich mit `cd var` in den Ordner *var*. Beachten Sie, dass ein solcher Pfad relativ zum aktuellen Verzeichnis interpretiert wird. Gibt es unter dem aktuellen Verzeichnis keinen Ordner namens *var* schlägt der Befehl fehl.\
Mit `cd \var` hingegen welchseln Sie direkt von überall her in das Verzeichnis `/var` direkt unter dem Wurzelverzeichnis. Das nennt man einen absoluten Pfad.

</div>
</div>

Auch die schon bekannte Abkürzung `~` können Sie mit dem Befehl `cd` verwenden. Allerdings wechselt auch der Befehl `cd` ohne Angabe eines Verzeichnisses immer in ihren persönlichen Ordner.

```bash
tilman@Linux:/var/log$ cd
tilman@Linux:~$
```

Ebenfalls nützlich ist die Abkürzung `..` für das Verzeichnis eine Ebene über dem aktuellen. Im Verzeichnis `/var/log` wechselt der Befehl `cd ..` also in das Verzeichnis `/var`

```bash
tilman@Linux:/var/log$ cd ..
tilman@Linux:/var$
```

Hier sehen Sie wie man sich mit `cd` durch die Verzeichnisse bewegen kann.
@[asciinema2(`rows: 10`)](cast/cd_pwd.cast)

### Verzeichnisse erstellen, auflisten und löschen

`mkdir` ist eine Abkürzung für *make directory*  mit dem Befehl

```bash
tilman@Linux:~$ mkdir projekte
```

legen wir ein Verzeichnis mit dem Namen *projekte* an. Da wir nun das Dateisystem verändert haben[^1], wollen wir das Ergebnis auch sehen. Dafür ist der Befehl `ls` – kurz für *list* – nützlich. Der Inhalt des aktuellen Verzeichnisses wird angezeigt.

```bash
tilman@Linux:~$ ls
projekte notizen.txt
```
Hier sehen wir nun das soeben erstellte Verzeichnis *projekte* aber auch eine Datei `notizen.txt` die ebenfalls im persönlichen Ordner des Nutzers liegt.

`ls` kann beliebige Verzeichnisse anzeigen, so können Sie sich zum Beispiel auch das Wurzelverzeichnis anzeigen lassen:

```bash
tilman@Linux:~$ ls /
var bin dev opt home ...
```

Wollen wir das soeben erstellte Verzeichnis wieder löschen, geht das mit `rmdir` oder *remove directory*. Allerdings lassen sich damit nur leere Verzeichnisse löschen.

Sowohl mkdir als auch rmdir akzeptieren mehrere, durch Leerzeichen getrennte Verzeichnisnamen um gleichzeitig mehrere Verzeichnisse zu erstellen oder zu löschen.

Hier sehen Sie ein Beispiel:
@[asciinema2(`rows: 8`)](cast/mkdir_rmdir.cast)



[^1]: Um das Dateisystem zu verändern brauchen Sie Schreibrechte. Als normaler Nutzer haben sie meistens nur Schreibrechte in ihrem persönlichen Ordner und können beispielsweise kein Verzeichnis unter `/bin` erstellen.

### Dateien erstellen, editieren und anzeigen

Natürlich gibt es viele Arten von Dateien die mit einer Vielzahl von Anwendungsprogrammen erstellt werden können.
Eine einfache Textdatei lässt sich jedoch auch ohne weiteres im Terminal erstellen.

So wie `mkdir` ein leeres Verzeichnis erstellt, kann mit dem Befehl `touch` eine leere Datei erstellt werden.

Hier erstellen wir in einem bisher leeren Verzeichnis eine Datei `rezepte.txt`:

```bash
tilman@Linux:~/neu$ ls
tilman@Linux:~/neu$ touch rezepte.txt
tilman@Linux:~/neu$ ls
rezepte.txt
```

Da eine leere Datei wenig nützt können wir sie nun mit einem Texteditor bearbeiten.

Die meisten Linux-Distributionen enthalten `nano`, einen minimalistischen Editor, in dem Sie interaktiv eine Datei bearbeiten können. Mit <kbd>Strg+O</kbd>[^1] speichern Sie die Datei, mit <kbd>Strg+X</kbd> verlassen Sie den Editor.

Mit `cat` von *concatenate* können Sie sich dann den Inhalt der Datei anzeigen lassen.

Hier sehen sie, wie man mit nano eine Textdatei bearbeiten und den Inhalt dann mit `cat` ausgeben kann:

@[asciinema](cast/nano.cast)


[^1]: Die Taste <kbd>Strg</kbd> heißt auf englischen Tastaturen <kbd>Ctrl</kbd> und auf einem Mac <kbd>Control</kbd>


### Bewegen, Kopieren und Löschen

Mit dem Befehl `mv`, kurz für `move` können Sie Dateien und Verzeichnisse "bewegen". Das kann man auf zweierlei Weise einsetzen: Erstens können Sie etwas von einem Ort zu einem anderen verschieben, und zweitens können Sie etwas umbenennen, indem Sie den alten Namen durch einen neuen ersetzen, ohne den Speicherort zu ändern.

So benennen wir hier den falsch geschriebenen Ordner "porjekte" in "projekte" um:

```bash
tilman@Linux:~$ mkdir porjekte
tilman@Linux:~$ mv porjekte projekte
```

Hier verschieben wir die Datei `hello_world.py` aus *home* in den Ordner projekte

```bash
tilman@Linux:~$ touch hello_world.py
tilman@Linux:~$ mv hello_world.py projekte
tilman@Linux:~$ ls projekte
hello_world.py
```

Ähnlich funktioniert der Befehl cp, kurz für copy. es wird jedoch eine Kopie der Datei oder des Verzeichnisses erstellt, anstatt es zu verschieben. Das Original bleibt am ursprünglichen Ort erhalten.

So kopieren wir zum Beispiel die Datei hello_world.py in das Verzeichnis "backup", während die Originaldatei im Home-Verzeichnis bleibt:

```bash
tilman@Linux:~$ cp hello_world.py backup
tilman@Linux:~$ ls backup
hello_world.py
tilman@Linux:~$ ls
backup hello_world.py
```

Der Befehl `rm`, kurz für *remove*, wird verwendet, um Dateien und Verzeichnisse zu löschen. Wenn Sie eine Datei auf diese Weise löschen, wird sie vollständig entfernt und kann nicht wiederhergestellt werden.

So können wir so die zuvor erstellte Kopie von `hello_world.py` löschen:

```bash
tilman@Linux:~$ rm backup/hello_world.py
tilman@Linux:~$ ls backup
```

### Optionen, Optionen, Optionen

Die Befehle die sie bis jetzt kennengelernt haben, decken bereits einen großen Teil der täglichen Arbeit im Terminal ab. Mit ein paar zusätzlichen Tricks können diese aber noch vielseitiger eingesetzt werden.

So haben wir gesehen, dass `rmdir` nur leere Verzeichnisse löschen kann. Wenn sie aber den Befehl `rm` mit `rm -r` aufrufen, können Sie auch Verzeichnisse mit Inhalt löschen. `-r` steht für *recursive* und bedeutet, und ist eine Option, die besagt, dass der Befehl rekursiv alle Dateien und Unterverzeichnisse löschen soll. 

<div class="alert warning">
**Vorsicht!** \
`rm -r` ist einer der gefährlichsten Befehle im Linux Terminal.
Ohne Nachfrage werden alle Dateien und Unterverzeichnisse unwiderruflich gelöscht. Vor allem wenn Sie als *root* angemeldet sind, können Sie so das gesamte System löschen. Überlegen Sie also immer zweimal bevor sie <kbd>Enter</kbd> drücken.

</div>

Der Parameter `-r` ist ein Beispiel für eine Option. Optionen sind zusätzliche Argumente, die das Verhalten eines Befehls ändern. Sie werden durch einen Bindestrich und einen Buchstaben oder zwei Bindestriche und ein Wort angegeben[^1].\ 

Hier ein paar Beispiele für Optionen der Ihnen bereits bekannten Befehle:

- `ls -l` zeigt zusätzliche Informationen zu den Dateien an (`-l` steht für *long*)
- `rm -i` fragt vor dem Löschen jeder Datei nach, ob Sie sicher sind (`-i` steht für *interactive*)
- `cp -r` kopiert rekursiv alle Dateien und Unterverzeichnisse (Die Bedeutung von `-r` kennen Sie bereits)	
- `mkdir -p` erstellt das angegebene Verzeichnis, auch wenn die übergeordneten Verzeichnisse im Pfad fehlen. (`-p` steht für *parents*)
- `rm --help` zeigt die Hilfe des Befehls `rm` an. Diese Option funktioniert mit allen Befehlen. Probieren Sie es aus![^2]


[^1]: Man kann so statt `rm -r` auch `rm --recursive` schreiben. Meistens verwendet man aber die Kurzform. Es gibt aber auch Optionen ohne Kurzform, wie zum Beispiel `--help`.
[^2]: Neben dieser eingebauten Hilfe gibt es auch umfangreiche Handbücher für die meisten Befehle. Diese können Sie mit dem Befehl `man` für *manual* aufrufen. So zeigt `man rm` die Hilfe für den Befehl `rm` an.

<div class="alert tip">
**Tipps und Tricks** \
Wir haben bisher nur die Grundlagen der Arbeit im Terminal kennengelernt. 
Hier sind ein paar hilfreiche weiterführende Tipps:

- **Tabulator-Taste <kbd>TAB</kbd>**: Drücken Sie die Tabulator-Taste um Dateinamen und Befehle automatisch vervollständigen zu lassen.
- **Pfeiltasten <kbd>↑</kbd> und <kbd>↓</kbd>**: So können Sie sich durch die zuletzt eingegebenen Befehle bewegen.
- **Platzhalter `*`**: Mit `ls *.txt` können Sie sich alle Dateien mit der Endung `.txt` anzeigen lassen. `rm test*` löscht alle Dateien die mit `test` beginnen.
- **<kbd>Strg</kbd>+<kbd>C</kbd>**: Unterbricht die Ausführung eines Befehls.

</div>


### ❓Fragen

<div class="alert exercise">

Sicherungskopie
----------------

Das Verzeichnis `projekte` enthält 4 Unterverzeichnisse mit vielen Dateien. Sie wollen eine Sicherungskopie namens namens `backup` erstellen.\
Welcher der folgenden Befehle ist korrekt?

- [(X)] `cp -r projekte backup`
- [( )] `cp -r backup projekte`
- [( )] `cp projekte backup`
- [( )] `mv projekte backup`

</div>
<div class="alert exercise">

Heimatverzeichnis
------------------

Sie sind angemeldet als Nutzer `erwin`. Welche der folgenden Befehle bringen Sie in Ihr Heimatverzeichnis?

- [[X]] `cd`
- [[ ]] `cd /`
- [[X]] `cd ~`
- [[X]] `cd /home/erwin`
- [[ ]] `cd /home`
- [[ ]] `cd /erwin`

</div>
<div class="alert exercise">

Verzeichnis löschen
--------------------
In ihrem Heimatverzeichnis befindet sich das leere Verzeichnis `bilder` und das leere Verzeichnis `musik`. \
Welche der folgenden Befehle löschen beide Verzeichnisse?

- [[ ]] `rm bilder musik`
- [[X]] `rm -r bilder musik`
- [[X]] `rmdir bilder musik`
- [[ ]] `rmdir /bilder /musik`
- [[ ]] `rmdir -r bilder musik`
- [[ ]] `rm bilder rm musik`

</div>
