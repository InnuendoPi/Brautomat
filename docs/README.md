# Der Brautomat

Der Brautomat ist eine Brausteuerung für die Induktionskochfelder GGM IDS1 und IDS2 mit einem ESP8266 Wemos D1 mini. Der Brautomat wird im Sudhaus von Hobbybrauern eingesetzt und bietet eine intuitiv einfach zu bedienende Steuerung. Beim Maischen werden Rast-Temperaturen automatisiert angefahren und die Rast-Zeiten eingehalten. Ebenso unterstützt der Brautomat den Hobbybrauer beim Kochen der Würze und bei den Hopfengaben. Im Verfahren aufsteigende Infusion kann der Brautomat den Maischeprozess vollständig automatisieren.
_Hinweis: Induktionskochfelder anderer Hersteller können nicht im Maischeprozess eingesetzt werden._

_**Schnelleinstieg in den Brautomaten: diese zwei Abschnitte lesen und dann Brauen**_

```text
- Grundeinrichtung
- Der Maischeplan

```

Die Hauptfunktionen vom Brautomat sind:

* Steuerung der Induktionskochfelder GGM IDS1 und IDS2 über einen PID-Controller
* PID AutoTune zur Ermittlung der benötigten Einstellungen
* ein Maischeplan mit bis zu 15 Teilschritten
* Steuerung für einen Nachguss Kessel (HLT) über einen PID-Controller
* Steuerung von Aktoren, wie bspw. Rührwerk, Pumpen, etc.
* einfaches PWM für Aktoren
* Temperaturverlauf im Sudhaus als Grafik (line chart)
* Rezept Import aus dem kleinen Brauhelfer2
* Rezept Import aus Maische Malz und Mehr
* Rezept Import aus BrewFather
* Rezept Export zur Rezept Archivierung
* Optionale Unterstützung für 3,5" HMI Touchdisplay Nextion
* Optionale Unterstützung für eine GPIO Erweiterung PCF8574

## 📚 Dokumentation

Beschreibung & Anleitung: [https://innuendopi.gitbook.io/brautomat\_de/](https://innuendopi.gitbook.io/brautomat\_de/)

Diskussion: [https://hobbybrauer.de/forum/viewtopic.php?p=486504#p486504](https://hobbybrauer.de/forum/viewtopic.php?p=486504#p486504)

Changelog: [https://github.com/InnuendoPi/Brautomat/blob/main/CHANGELOG.md](CHANGELOG.md)

## 📰 WebInterface

Der Brautomat wird über einen WebBrowser gesteuert. Es wird ein Browser mit Unterstützung für CSS3, HTML5; Javascript und Server Sent Events (SSE) benötigt.

Übersicht kompatibler [Browser](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events#browser_compatibility)

![Startseite](/docs/img/brautomat.jpg)

![Startseite](/docs/img/IDS-AutoTune-Ziel.jpg)

![Startseite](/docs/img/brautomat-2.jpg)

## 💻 Nextion HMI Touchdisplay

Hinweis: das Display ist eine optionale Erweiterung für den Brautomat. Es werden nur Nextion ITEAD HMI 3.5 Zoll Displays unterstützt.

* Braustatus Info (Infoscreen, keine Steuerung)
* MaischeSud Info (Infoscreen, keine Steuerung)
* Manuelle Steuerung Kochen (manuelle Steuerung GGM IDS2)

![Startseite](/docs/img/kettlepage-sm.jpg) ![Startseite](/docs/img/brewpage-sm.jpg) ![Startseite](/docs/img/induction-mode-sm.jpg)

_"Boxing Bell" (info), "Short School Bell" (error), "Ding sound effect" (warning) und "Success sound effect" (success) mp3 von Free Sounds Library_ [_http://www.freesoundslibrary.com_](http://www.freesoundslibrary.com) _Licence: Attribution 4.0 International (CC BY 4.0). You are allowed to use sound effects free of charge and royalty free in your multimedia projects for commercial or non-commercial purposes._
