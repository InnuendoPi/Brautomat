# Parameter System

## Aktiviere Alarm-Buzzer

Mit diesem parameter kann ein Piezo Buzzer aktiviert werden. Zu beachten gilt, dass der Buzzer an GPIO D8 angeschlossen sein muss. Buzzer Alarme unterstützen den Maischeprozess durch Signaltöne.

## Aktiviere Toasts und mp3 Alarme

Toasts sind kleine Push Nachrichten. Die Nachrichten erscheinen als Kachel unten rechts im Browser. Nach ca. 10sek verschwinden die Toasts wieder. Es gibt Toast Nachrichten zum Maischeprozess, Toast Nachrichten vom System und textlose mp3 Alarme. Dazu passend hat die Eigenschaft Toasts 3 Optionen: Aus, Ein und Fehler. Die Auswahl "Aus" schaltet Toast Nachrichten ab. Die Option "Ein" sendet alle Toasts Nachrichten und mp3-Alarme. Die Option "Fehler" sendet nur Toast Nachrichten bei Systemfehler, aber keine Nachrichten zum Maischeprozess.

Toasts unterstützen eine Audio Ausgabe. So werden Toasts im Maischeprozess nicht nur zu einer visuelle, sondern auch einer akkustischen Erinnerung. Die Firmware beinhaltet die Audio Dateien info.mp3, success.mp3, warning.mp3 und error.mp3. Die Audio Dateien (mp3) können ausgetauscht werden. Lediglich die Benennung muss gleich bleiben. Im Browser sollte Autoplay Audio für die IP-Adresse des Brautomaten erlaubt sein.

_Tipp: iOS Geräte -_ _mp3 Audio benötigt auf iOS Geräten eine "user gesture", bspw. ein Klick oder Touch event. Einfach ein Element auf der Webseite anklicken und mp3 Audio wird ausgegeben. Ohne die user gesture wird die Audio Ausgabe vom iOS System blockiert_

_Tipp: automatische Medienwiedergabe -_ _Alle gängigen Browser wie MS Edge, Chrome oder Firefox haben in den Einstellungen unter Webseitenberechtigung Optionen für die automatische Medienwiedergabe. Es wird empfohlen, die Webseite vom Brautomat in die Liste "Zulassen" hinzuzufügen. Im folgenden Bild ist die Webseite vom Brautomat mit dem mDNS Namen im Microsoft Edge Browser hinzugefügt worden. Alternativ kann auch die IP-Adresse eingetragen werden_

![media](../docs/img/autoplay\_media.jpg)

Mit dieser Einstellung können mp3 Alarme einen Piezo Buzzer ersetzen. Treten beim Systemstart Fehler auf, werden mp3 Audio Signale auf iOS Geräte blockiert. Erst nach einem Klick oder Touch werden mp3 Audio Dateien wiedergegeben. Als workaround für iOS Geräte kann nach dem ersten Start direkt ein Neustart initiert werden. Der Neustart muss als Klick bzw. Touch über System -> Neustart durchgeführt werden. Durch diese "user gesture" werden mp3 Medien automatisch wiedergegeben.

Toast Nachrichten und mp3 Alarme können systembedingt wenige Sekunden zeitverzögert zugestellt werden. Jeder Browser erhält seine eigenen Nachrichten. Zwei Geräte mit geöffnetem Browser auf den Brautomat erhalten (systembedingt) die gleiche Toast Nachricht bis zu 2 Sekunden zeitversetzt. Voreingestellt werden Toasts spätestens nach 60 Sekunden gelöscht. Innerhalb dieser 60 Sekunden überscheiben neue Toasts ältere Nachrichten (keine Stapelverarbeitung).

_Toasts in der Praxis_ _In der Brauküche wird meist ein Gerät und ein Browser mit dem Brautomat verwendet. Toasts mit mp3 Audio bieten eine einfache und laute akkustische Aufforderung zum Handeln. Deshalb ist es vorteilhaft, wenn die Enegerieoptionen beim Brauen deaktiviert werden und der Browser während des Brauens durchgehend aktiv ist. Wenn die Brauküche verlassen wird, sind Toasts auf einem Smartphone oder Tablet eine optischer und akkustischer Begleiter. Auch mobile Geräten müssen durchgehend aktiv sein. Toasts melden sich auf allen verbundenen Browsern. Anders gesagt: jeder Browser merkt sich, welche Toast ID bereits angezeigt wurde. Es ist richtig und gewollt, wenn ein PC Browser und ein Smartphone die gleiche Toast Nachricht minimal zeitversetzt anzeigen_

## Aktviere Porterweiterung PCF8574

Mit diesem Parameter kann eine 8-Port GPIO Erweiterung am ESP8266 betrieben werden. Zu beachten gilt, dass die Port Erweiterung an D5, D6 angeschlossen werden muss. Der Interrupt Modus wird nciht unterstützt.

## Aktiviere Touchdisplay

Mit diesem Parameter kann ein Nextion HMI 3.5 Zoll Display betrieben werden. Der Brautomat bietet drei Ansichten

<<<<<<< HEAD
```- die Kessel Seite:     auf dieser Ansicht werden IDS und Nachguss mit Ist- und Zieltemperaturen dargestellt.
=======
```text
- die Kessel Seite:     auf dieser Ansicht werden IDS und Nachguss mit Ist- und Zieltemperaturen dargestellt.
>>>>>>> main
                        Die aktuelle und die nächste Rast werden mit Dauer angezeigt.
                        Die Länge vom rote Balken unter der Ansicht IDS und Nachguss zeigt die erledigte Rastdauer an.  
```

![Display](../docs/img/kettlepage.jpg)

<<<<<<< HEAD
```- die Brauen Seite:     auf dieser Ansicht wird das Induktionskochfeld dargestellt.
=======
```text
- die Brauen Seite:     auf dieser Ansicht wird das Induktionskochfeld dargestellt.
>>>>>>> main
                        Es wird nur die aktuelle Rast mit Dauer im Kopf angezeigt.
                        Die Länge roter Balken unter den Temperaturen den Fortschrit der aktuellen Rast an.
```

![Display](../docs/img/brewpage.jpg)

<<<<<<< HEAD
```- die Kochen Seite:     auf dieser Ansicht ist für die manuelle Steuerung vom Induktionskochfeld
=======
```text
- die Kochen Seite:     auf dieser Ansicht ist für die manuelle Steuerung vom Induktionskochfeld
>>>>>>> main
                        Im manuellen Betrieb stehen 6 Powerstufen zur Verfügung: 0, 20, 40, 60, 80 und 100% Leistung
                        Der manuelle Betrieb ist nur für die GGM IDS2 geeignet. (IDS1 nicht getestet!) 
```

![Display](../docs/img/induction\_mode.jpg)

Ein Display ist optional. Der Brautomat unterstützt ausschließlich Nextion HMI 3.5 Zoll Touchdisplays (Basic und Discovery Series).

Das Display wird mit einer SD Karte konfiguriert. Die zum Display passende TFT Datei aus dem Ordner Info wird auf eine SD Karte kopiert und in das Display eingesteckt. Sobald das Display eingeschaltet wird, startet die Konfiguration. Der Vorgang dauert etwa eine Minute. Im Display steht der Fortschritt. Sobald die Konfiguration aufgespielt ist, wird das Display abgeschaltet und die SD Karte entfernt. Das Display ist nun einsatzbereit.

Zu beachten gilt, dass SDA, SCL an den PINs D1, D2 betrieben werden müssen.
