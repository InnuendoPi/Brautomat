# Der Brautomat

Der Brautomat ist eine Brausteuerung für die Induktionskochfelder GGM IDS1 und IDS2 mit einem ESP8266 Wemos D1 mini. Der Brautomat bietet eine intuitiv einfach zu bedienende Steuerung.

Hauptfunktionen:

* Steuerung der Induktionskochfelder GGM IDS1 und IDS2
* PID-Controller integriert
* PID-AutoTune
* Verwaltung von Maischeplänen
* Maischepläne mit bis zu 20 Teilschritten
* Steuerung für einen Nachguss Kessel (HLT)
* Steuerung von Aktoren, wie bspw. Rührwerk, Pumpen, etc.
* PWM für Aktoren
* Temperaturverlauf im Maischeprozess als Grafik (line chart)
* Rezept Import aus dem kleinen Brauhelfer2
* Rezept Import aus Maische Malz und Mehr
* Rezept Import aus BrewFather
* Rezept Export
* Optionale Unterstützung für 3,5" HMI Touchdisplay Nextion
* Optionale Unterstützung für eine GPIO Erweiterung PCF8574

## 📚 Dokumentation

Beschreibung & Anleitung: [https://innuendopi.gitbook.io/brautomat\_de/](https://innuendopi.gitbook.io/brautomat\_de/)

Diskussion: [https://hobbybrauer.de/forum/viewtopic.php?p=486504#p486504](https://hobbybrauer.de/forum/viewtopic.php?p=486504#p486504)

Changelog: [https://github.com/InnuendoPi/Brautomat/blob/main/CHANGELOG.md](CHANGELOG.md)

## 📰 WebInterface

Der Brautomat wird über einen WebBrowser gesteuert.

![Startseite](/docs/img/brautomat.jpg)

![Startseite](/docs/img/IDS-AutoTune-Ziel.jpg)

![Startseite](/docs/img/brautomat-2.jpg)

## 💻 Nextion HMI Touchdisplay

* Kesselübersicht
* MaischeSud
* Manuelle Steuerung Kochen

![Kesselübersicht](/docs/img/kettlepage-sm.jpg) ![MaischeSud](/docs/img/brewpage-sm.jpg) ![Manuelle Steueung](/docs/img/induction-mode-sm.jpg)

_"Boxing Bell" (info), "Short School Bell" (error), "Ding sound effect" (warning) und "Success sound effect" (success) mp3 von Free Sounds Library_ [http://www.freesoundslibrary.com](http://www.freesoundslibrary.com) _Licence: Attribution 4.0 International (CC BY 4.0). You are allowed to use sound effects free of charge and royalty free in your multimedia projects for commercial or non-commercial purposes._
