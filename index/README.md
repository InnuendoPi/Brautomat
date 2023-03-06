---
description: Anleitung und Beschreibung
---

# Brautomat

Der Brautomat ist eine Brausteuerung für die Induktionskochfelder GGM IDS1 und IDS2 mit einem ESP8266 Wemos D1 mini. Der Brautomat wird im Sudhaus von Hobbybrauern eingesetzt und bietet eine intuitiv einfach zu bedienende Steuerung. Beim Maischen werden Rast-Temperaturen automatisiert angefahren und die Rast-Zeiten eingehalten. Ebenso unterstützt der Brautomat den Hobbybrauer beim Kochen der Würze und bei den Hopfengaben. Im Verfahren aufsteigende Infusion kann der Brautomat den Maischeprozess vollständig automatisieren. _Hinweis: Induktionskochfelder anderer Hersteller können nicht im Maischeprozess eingesetzt werden._

_**Schnelleinstieg in den Brautomaten: diese zwei Abschnitte lesen und dann Brauen**_

```
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
* Maischeplan Import aus dem kleinen Brauhelfer2
* Maischeplan Import aus Maische Malz und mehr
* Maischeplan Export zur Rezept Archivierung
* Optionale Unterstützung für 3,5" HMI Touchdisplay Nextion
* Optionale Unterstützung für eine GPIO Erweiterung PCF8574
