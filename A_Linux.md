<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  0.0.1
date:     2024
language: de
narrator: Deutsch Female
logo:     img/A/linux.png
icon:     img/TU_Logo_kurz.png
comment:  Eine kurze Einführung in Linux
import:   ./macros.md
link:     styles/main.css
-->

# Eine kurze Einführung in Linux
@[asciinema](cast/test.cast)

## Was ist ein Betriebssystem?

<!--style="max-width: 200px;margin:3em"-->
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

## Wie komme ich an Linux?
### Linux als Betriebssystem
Linux ist eigentlich der Name des Betriebssystemkerns (englisch *Kernel*), also des grundlegenden Teils des Systems, der die Hardware steuert und die Ausführung von Programmen ermöglicht. Für sich allein genommen ist der Kernel jedoch kein vollständiges Betriebssystem. Erst durch Kombination mit einer Vielzahl von Programmen, Tools und Benutzeroberflächen entsteht ein vollständiges Betriebssystem. Diese Gesamtpakete, die den Kernel und all diese zusätzlichen Komponenten enthalten, werden als Distributionen bezeichnet. Bekannte Beispiele dafür sind [Ubuntu](https://ubuntu.com/), [Debian](https://www.debian.org/), [Archlinux](https://archlinux.org/), oder [Fedora](https://getfedora.org/).

Jede dieser Distributionen können Sie als vollwertiges Betriebssystem benutzen.
Wenn sie weiterhin Windows benötigen können Sie Linux auch parallel zu Windows auf Ihrer Festplatte installieren. Beim Start des Computers wählen Sie dann, welches Betriebssystem Sie verwenden möchten. Dies wird als *Dual Boot* bezeichnet.

Ab Windows 10 besteht eine einfachere Möglichkeit: Das Windows Subsystem for Linux (WSL) kann Linux direkt innerhalb von Windows ausführen.


### Das Windows Subsystem for Linux

1. **Windows-Version überprüfen**:
   - Stellen Sie sicher, dass Sie mindestens **Windows 10 Version 2004** oder höher oder **Windows 11** verwenden. Dies können Sie in den **Einstellungen** unter **System > Info** nachsehen.

2. **Voraussetzungen für WSL aktivieren**:
   - Öffnen Sie die **Systemsteuerung**.
   - Gehen Sie zu **Programme > Programme und Features**.
   - Klicken Sie auf **Windows-Features aktivieren oder deaktivieren**.
   - Aktivieren Sie die Kästchen für:
     - **Windows-Subsystem für Linux**
     - **Virtuelle Maschinen-Plattform** (für WSL 2 erforderlich)
     - **Hyper-V** (optional, für WSL 2)
   - Klicken Sie auf **OK** und starten Sie den Computer neu.

3. **Linux-Distribution aus dem Microsoft Store installieren**:
   - Öffnen Sie den **Microsoft Store**.
   - Suchen Sie nach Ihrer gewünschten Linux-Distribution (z.B. Ubuntu) und klicken Sie auf **Installieren**.
   - Aktuell[^1] kann ich [Ubuntu 24.04 LTS](https://apps.microsoft.com/detail/9nz3klhxdjp5) empfehlen.

Nun können Sie ein Linux-Terminal über das Startmenü starten.

[^1]: Stand September 2024. Diese Version wurde im April 2024 veröffentlicht und ist eine LTS-Version, das bedeutet, dass sie mit langfristigem Support (Long-Term Support) für mindestens 5 Jahre, also bis 2029, versorgt wird. LTS-Versionen sind besonders stabil und werden für den Einsatz in produktiven Umgebungen empfohlen.

### MacOs
Mac Os ist kein Linux basiert aber auf einem Unix. Terminal ist ähnlich


@asciinema('test')

