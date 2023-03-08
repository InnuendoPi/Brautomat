---
description: Anleitung und Beschreibung
layout: editorial
---

# Sonstiges

## Die Platine

![Platine](docs/img/Platine.jpg)

Die Platine zum Projekt Brautomat macht den Aufbau und die Verwendung sehr einfach. Dabei ist die Platine völlig unabhängig vom Projekt Brautomat. Mit einem ESP8266 Wemos D1 mini kann die Platine universell eingesetzt werden. An die Schraubklemmblöcke werden beim Brautomat die GGM IDS, die Sensoren, die Aktoren und das Display angeschlossen.

### Jumperpositionen

Die Platine hat 4 Jumper. Die Jumper J1, J2 und J3 müssen mindestens auf _2-3_ gesetzt werden.

```
Jumpereinstellung Kurzform
- Wird ein Display eingesetzt, müssen J1 und J2 auf 1-2 gesteckt sein. 
- Wir kein Display eingesetzt, müssen J1 und J2 auf 2-3 gesteckt sein. 
- J3 wird immer auf 2-3 gesteckt.

1. Jumper J1: Pin D1 
    - In der Position 1-2 wird Pin D1 (GPIO 5) auf den Displayanschluss umgeleitet (SDL)
    - in der Position 2-3 wird kein Display verwendet (default)
2. Jumper J2: Pin D2
    - In der Position 1-2 wird Pin D2 (GPIO 4) auf den Displayanschluss umgeleitet (SDA)
    - in der Position 2-3 wird kein Display verwendet  (default)
3. Jumper J3: Pin D4
    - In der Position 1-2 wird Pin D4 (GPIO 2) auf den Displayanschluss umgeleitet.
    - in der Position 2-3 wird Pin D4 nicht umgeleitet (default)

4. Jumper J4: Stromzufuhr über GGM IDS
    - wenn der Jumper J4 gesetzt ist, wird die Stromzufuhr von der GGM IDS für den Brautomat genutzt.
    - wenn der Jumper J4 nicht gesetzt ist, wird die Stromzufuhr an den Anschluss *5V* und *GND* angeklemmt.
```

### Teileliste

| Anzahl                                                | Artikelname                    | Link zum Artikel                  |
| ----------------------------------------------------- | ------------------------------ | --------------------------------- |
| 1                                                     | Schraubklemmblock 2pol 2,54    | (eg voelkner )                    |
| 3                                                     | Schraubklemmblock 3pol 2,54    | (eg voelkner )                    |
| 2                                                     | Schraubklemmblock 5pol 2,54    | (eg voelkner )                    |
| 2                                                     | Schraubklemmblock 8pol 2,54    | (eg voelkner )                    |
| 1                                                     | JST-HX Buchse 90° 2,54         | (eg voelkner )                    |
| 1                                                     | Stiftleiste 2,54               | [amazon](https://amzn.to/40Q8Nbv) |
| 4                                                     | Jumper 2,54                    | (eg voelkner )                    |
| 1                                                     | Widerstand 4,7kOhm             | [amazon](https://amzn.to/40OLPBA) |
| 1                                                     | D1 mini NodeMcu ESP8266        | [amazon](https://amzn.to/3RWwyL5) |
| 1                                                     | LevelShifter 8 Channel 5V 3.3V | [amazon](https://amzn.to/3xjkN7S) |
| _Links nach amazon Partner und Voelkner TradeTracker_ |                                |                                   |

Die Position JST-HX Buchse ist für das original Anschlusskabel vorgesehen. Wird ein Ersatzkabel (ohne JST-HX Stecker) verwendet, kann an gleicher Stelle auf der Platine ein Schraubklemmblock 5pol im Rastermaß 2,54mm eingesetzt werden. Der Schaubklemmblock 2pol kann wahlweise unten rechts oder mittig links neben dem Wemos D1 mini eingesetzt werden.

_Tipp:_ _der ESP8266 sollte gesockelt werden. Mit Sockel (im Link oben enthalten) ist ausreichend Platz für den Widerstand unter dem ESP8266. Falls eine Fehlersuche erforderlich ist, kann ein gesockelter ESP8266 von der Platine abgesteckt werden._

Die Anschlüsse vom LevelShifter 8 Kanal müssen zur Anordnung auf der Platine identisch sein. Der Levelshifter aus dem Link hat diese Anordnung der Anschlüsse.

![Levelshifter](docs/img/Levelshifter.jpg)

## Beispiele für Aktoren

### Pumpen

![Aktoren](docs/img/Pumpe1.jpg)

Eine Pumpe ist beim Läutern oder beim Transport in den Gärbehälter eine große Hilfe. Die verwendete Pumpe muss lebensmittelecht sein und für Temperaturen bis 100°C geeignet sein. Die Minipumpen von Rotekt eignen sich sehr gut für den Einsatz in der Brauküche:

![Aktoren](docs/img/Pumpe2.jpg)

| Artikelname                                            | Link zum Artikel                  |
| ------------------------------------------------------ | --------------------------------- |
| Mini-Pumpe 12V DC                                      | [amazon](https://amzn.to/3E4iRUF) |
| Mini-Pumpe 12V DC                                      | [amazon](https://amzn.to/3E4iRUF) |
| Pneumatische Steckverbinder 8mm x 1/2 Zoll 90° drehbar | [amazon](https://amzn.to/3XmH2nP) |

Ebenfalls sehr gut und schnell sind Verbdinungen mit [Camlocks von Braubebo](https://www.braubebo.de/camlock/) wie auf dem ersten Bild dargestellt.

### SSR Solid State Relais

Mit dem Brautomat können sehr einfach SSRs geschaltet werden. SSR oder Solid State Relais schalten mit 3-5V Gleichstrom vom Brautomat den 220V Wechselstromkreis ein- bzw. aus. Die Fotek SSRs sind ideal zur Temperaturregelung und Steuerung über den Brautomat.

![fotek](docs/img/fotek.jpg)

| Artikelname    | Link zum Artikel                  |
| -------------- | --------------------------------- |
| Fotek SSR 40DA | [amazon](https://amzn.to/3RSzKav) |

Anwenungsbeispiele für SSR: Wenn 220V an einem SSR Fotek über den Brautomat geschaltet wird, kann am "anderen Ende" der 220V Leitung eine Steckdose für einen beliebiges Gerät mit Stecker angebracht werden. Zum Beispiel für das Netzteil vom Rührwerk. Oder für einen Nachgusskocher. Oder für ein Ringheizlement. Auch das Netzteil der Rotek Pumpe kann über ein SSR ein- und ausgeschaltet werden.

### Relaismodul

Nicht alle Verbraucher benötigen ein leistungsstarkes SSR. Bspw. können Aktoren wie Rührwerk oder Pumpen mit günstigen Relaisboards geschaltet werden. Ein sehr gutes Relaisboard ist das Keenso 4 Kanal Optokoppler Reaisboard.

![keenso](docs/img/keenso.jpg)

| Artikelname        | Link zum Artikel                  |
| ------------------ | --------------------------------- |
| Relaisboard Keenso | [amazon](https://amzn.to/3K3gg11) |

Das Relaisboard kann per Jumpereinstellung auf High Trigger (es fließt Strom) und Low Trigger (es fließt kein Strom) eingestellt werden. Diese Möglichkeit macht das Relaisboard ideal für den Einsatz mit einem ESP8266 oder einer Port Erweiterung PCF8574.

### Port Erweiterung PCF8574

Wenn mehr Aktoren betrieben werden sollen, als der ESP8266 (nutzbare) GPIOs anbietet, ist die PCF8674 Porterweiterung eine gute Lösung

![pcf8574](docs/img/pcf8574.jpg)

| Artikelname              | Link zum Artikel                  |
| ------------------------ | --------------------------------- |
| Port Erweiterung PCF8574 | [amazon](https://amzn.to/3YrVi02) |

Die Porterweiterung muss an D6 und D7 vom ESP8266 angeschlossen werden. Mit dem Modul PCF8475 werden 6 zusätzliche Anschlüsse bereitgestellt. Der Brautomat unterstützt nur eine Porterweiterung!

### Ringheizelemente

Ein Ringheizlement ist beim Kochen der Würze nützlich, wenn die Leistung der GGM IDS nicht mehr oder nur so eben ausreicht, um die Würze wallend zu kochen. Eine gute Auswahl an Ringheizelementen gibt es beim [Douglas von Crafthareware](https://www.crafthardware.de/products/ringheizelement-3-5-kw-fuer-45-cm-kessel).

***

## Brautomat vs MQTTDevice

Der Brautomat ist eine eigenständige Steuerung und kann nicht mit einem zweiten Brautomat oder CraftBeerPi4 kommunizieren. Ein RaspberryPi, ein Docker Container oder eine andere Python3 Umgebung ist nicht erforderlich. Das ist ein Vorteil und Nachteil zugleich, weil der Brautomat somit auch keine Schnittstelle für individuelle Erweiterungen oder Plugins bietet. Der Brautomat hat den Fokus auf einfach, intuitiv und günstig.

Das [MQTTDevice](https://github.com/InnuendoPi/MQTTDevice4) wird mit CraftBeerPi4 eingesetzt. Das MQTTDevice ein "Befehlsempfänger" und CraftBeerPi4 ist die Steuereinheit. CraftBeerPi4 versendet Steuerbefehle per WLAN im Format MQTT über einen Broker an das MQTTDevice. CraftBeerPi4 kann mit mehr als einem MQTTDevice arbeiten. Eine CBPi4 Umgebung bietet viele Möglichkeiten für individuelle Anpassungen und Erweiterungen. Das ist ein Vorteil und Nachteil zugleich, weil die Abhängigkeiten komplexer werden und Störungen sowie Inkompatibilitäten hervorrufen können. Das MQTTDevice hat den Fokus eine WLAN Anbindung von nahezu beliebigen Geräten an CraftBeerPi4 über das Protokoll MQTT.

Identisch ist in beiden Projekten die Hardware (ESP8266, Temperatursensoren, Display, GGM IDS2) sowie die Platine. Ein Wechsel zwischen die Firmwares Brautomat und MQTTDevice4 ist jederzeit ohne Veränderung möglich.

***

## kleinerBrauhelfer2 & Brautomat

Ab Version 2.5.0 hat das Programm [kleinerBrauhelfer2](https://github.com/kleiner-brauhelfer/kleiner-brauhelfer-2) einen Export Filter für den Brautomat. Die Rezeptentwicklung und Gestaltung ist mit den kbh2 in allen erdenklichen Details möglich. Mit dem Spickzettel bietet der kbh2 einen sehr guten und hilfreichen Ablaufplan für die praktische Umsetzung in der Brauküche. Mit dem Export Filter für den Brautomat können fast alle Schritte im Sudhaus vereinfacht werden. In den folgenden Abschnitten werden einzelne Vorgehensweisen beschrieben, um die Logik und das Vorgehen "vom kleinenBrauhelfer2 zum Brautomat" einfach zu machen.

### Der kbh2 Tab Maischplan

Im Tab Maischplan bietet der kbh2 vier verschiedene Arten Malze zur Maische hinzuzufügen: Einmaischen, Aufheizen, Zubrühen und Dekoktion. Alle vier Arten werden im Brautomat unterstützt. Der Typ Einmaischen wird automatisch mit deaktiviertem autonext eingefügt. Aufheizen und Zubrühen mit aktiviertem autonext. Die Dekoktion ist aber nur mit halber automatik möglich (autonext).

![Kochen](docs/img/kbh2\_maischplan.jpg)

Einen Typ Abmaischen kennt der kbh2 nicht, weil er diesen Typ auch nicht benötigt. Der Brautomat benötigt diesen Maischeschritt, um das Ende vom Maischen und den Übergang zum Läutern zu erkennen. Es sollte in jedem Maischplan ans Ende ein Schritt Abmaischen vom Typ "Aufheizen" mit 76°C oder höher und einer Dauer von 1 Minute angefügt werden. In dieser Kombination wird Abmaischen vom Brautomat erkannt und mit deaktiviertem autonext eingefügt.

![Kochen](docs/img/kbh2\_maischplan2.jpg)

### Der kbh2 Tab Kochen

Der kbh2 denkt anders, als der Brautomat. Im folgenden wird erläutert, wie der kbh2 Export im Brautomat eingelesen wird. Das passiert völlig automatisch. Anders gesagt: man kann die Logik einfach als gegeben hinnehmen. Es ist nicht erforderlich das Thema genauer zu betrachten und zu verstehen.

Spaß macht s trotzdem. Also ... Eine Zeitangabe im kbh2 im Tab Kochen bedeutet "wie lange wird die Hopfengabe gekocht". Aus der Kochdauer ergeben sich Bittere und Aroma. Siehe Formelsammlung im kbh2.

![Kochen](docs/img/hopfen.jpg)

Im Bild kbh2 ist die Hopfengabe dargestellt. Die erste Hopfengabe ist "Hallertauer Perle 7% 2020" mit einer Kochdauer von 65 Minuten. Ein zweiter Parameter ist in diesem Zusammenhang wichtig: auf der linken Seite ist die gesamte Kochdauer mit 80 Minuten grün markiert. Die Würze wird also 15 Minuten lang ohne Hopfen gekocht. Die zweite Hopfengabe ist der "Hallertauer Tradition 5.7% 2020" Hopfen mit einer Kochdauer von 15 Minuten. In den letzten 15 Minuten Kochen der Würze hat die Hallertauer Perle von ursprünglich 65 Minuten noch 15 Minuten Kochzeit übrig und die zweite Hopfengabe Hallertauer Tradition kocht 15 Minuten lang von den verbliebenen 15 Minuten Restkochzeit mit. Die letze Hopfengabe wird zum Ausschlagen gegeben, also nach dem Kochende.

Die Aufgabe vom Brautomat ist den Zeitpunkt der Hopfengabe beim Brauen genau anzugeben und am besten mit einem aktustischem Signal an die Hopfenhgabe erinnern. Um den Zeitpunkt der Hopfengabe während des Kochens zu bestimmen, ist es einfacher "von hinten" anzufangen. Die letzte Hopfengabe "Hallertauer Tradition 5.7% 2020" wird zum Ausschlagen gegeben. Beim Ausschlagen ist das Kochen beendet. Also zählt die Hopfengabe Ausschlagen nicht zur gesamten Kochdauer. Eine Hopfengabe weiter zurück ist der "Hallertauer Tradition 5.7% 2020" Hopfen mit einer Kochdauer von 15 Minuten. Eine Hopfengabe weiter zurück kommt die Hallertauer Perle mit einer Kochdauer von 65 Minuten. Von den 65 Minuten sind 15 Minuten lang Hallertauer Tradition und Perle zusammen im in der Würze. 65 Minuten abzüglich 15 Minuten ergibt den zeitlichen Abstand der Hopfengaben von 50 Minuten. Es muss der Hopfen Perle 50 Minuten vor der Hopfengabe Tradition gegeben werden.

Wir haben eine gesamte Kochedauer von 80 Minuten und eine erste Hopfengabe mit einer Kochdauer von 65 Minuten. Dann ergibt sich eine Differenz von 15 Minuten Kochedauer ohne Hopfengabe.

![Kochen](docs/img/hopfengaben.jpg)

IN gleicher Weise verhält sich die Hopfengabe Ausschlagen. Es ist eine Nachisomerisierungszeit von 10 Minuten gegeben. Die Hopfengabe "Hallertauer Tradition 5.7% 2020" zum Ausschlagen mit einer Kochdauer von -5 Minuten ist Teil der Nachisomerisierung.
