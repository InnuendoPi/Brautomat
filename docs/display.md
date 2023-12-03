# Display

Der Brautomat kann optional mit einem Touchdisplay betrieben werden. Unterstützt werden 3.5 Zoll Touchdisplay von Nextion

| Nextion Display | Firmware  |
| --------------- | --------- |
| NX4832T035 (basic Serie) | [NX4832T035](https://raw.githubusercontent.com/InnuendoPi/Brautomat/main/display/brautomat-NX4832T035.tft) |
| NX4832K035 (Enhanced Serie) | [NX4832K035](https://raw.githubusercontent.com/InnuendoPi/Brautomat/main/display/brautomat-NX4832K035.tft) |
| NX4832F035 (Discovery Serie) | [NX4832F035](https://raw.githubusercontent.com/InnuendoPi/Brautomat/main/display/brautomat-NX4832F035.tft)  |

Das Display benötigt für den Betrieb mit dem Brautomat eine Firmware. In der Tabelle ist für je Displaytyp die passende Firmware verlinkt.

## Kabelanschluss

| Kabel         | Nextion Display | Anschlussklemme Platine  |
| ------------- | --------------- | ------------------------ |
|     rot       | Strom + | Vcc |
|   schwarz     | Strom - | GND |
|    blau       | TX      | D1 (SDL)  |
|    gelb       | RX      | D2 (SDA)  |

_Hinweis: der Anschlus D4 verbleibt ungenutzt._

![Anschluss](/docs/img/disp1.jpg)

## Displaydatei flashen

Vor dem ersten Betrieb muss das Display vorbereitet werden. Hierzu wird die passende Display Firmware aus der Tabelle ooben heruntergeladen und auf eine microSD Karte gespeichert. Die microSD Karte wird in den SD Kartenslot vom Display eingesteckt und der Strom eingeschaltet. Der Flashvorgang startet automatisch und wird auf dem Display angezeigt. Nach Abschluss wird der Brautomat ausgeschaltet und die microSD Karte wird entfernt.
