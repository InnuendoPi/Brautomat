# Installation

Die Erstinstallation unterteilt sich in Firmware flashen und WLAN Konfiguration.

## Firmware flashen

Die Installation der Firmware wird über das mitgeliferte Script "Flashen.cmd" durchgeführt. Hierzu wird das Archiv Firmware.ZIP in einem beliebigen ordner entpackt. Der Wemos wird mit einem USB Kabel am PC/Notebook angeschlossen. Ein Doppelklick auf das Script Flashen.cmd startet die Installation.

Das Betriebssystem erstellt beim Anschluss vom Wemos D1 mini automatisch einen seriellen COM Port. Abhängig vom System kann das COM3, COM4 oder höher sein. Das Script Flashen.cmd ist voreingestellt auf den seriellen Anschluss COM3. Sollte der Wemos D1 Mini nicht mit COM3 verbunden sein, muss im Script Flashen.cmd in den Zeilen 6 und 8 "COM3" durch den korrekten COM Port ersetzt werden.

```bash
1: @ECHO OFF
2: CLS
3: SET SCRIPT_LOCATION=%~dp0
4: cd %SCRIPT_LOCATION%
5: echo erase flash
6: esptool.exe -cp COM3 -cd nodemcu -ce
7: echo Flash firmware and LittleFS
8: esptool.exe -cp COM3 -cd nodemcu -ca 0x000000 -cf Brautomat.ino.bin -ca 0x200000 -cf Brautomat.mklittlefs.bin
9: echo ESC to quit
10: pause
11: exit
```

## WLAN Konfiguration

Nach dem Flashen startet der Brautomat im AccessPoint Mode. Ein offenes WLAN mit dem Namen Brautomat wird sichtbar. Mit diesem WLAN muss eine Verbindung hergestellt werden. Sobald die Verbindung hergestellt ist, öffnet der Webbrowser das WLAN Portal. Sollte sich das Portal nicht automatisch öffnen, muss als Adresse <http://192.168.4.1> eingegeben werden.

![IDS](/docs/img/wlan1.jpg)

Über den Button "Configure WiFi" wird die Konfiguration WLAN angezeigt

![IDS](/docs/img/wlan2.jpg)

Hier muss das WLAN (SSID) und das Password konfiguriert werden. Mit Speichern startet der Brautomat neu und verbindet sich mit dem WLAN. Das Web Interface vom Brautomat ist über <http://brautomat> erreichbar.

## Updates

Updates können im Brautomat über das Menü "Update" eingespielt werden. Eine neue Firmware kann über "WebUpdate" oder "Datei Update" eingespielt werden. Bei einer Aktualisierung der Firmware per WebUpdate lädt die Firmware die aktuelle Version aus dem Internet aus dem github Repository. Bei der Aktualisierung per Datei Update wird die Firmware per Upload vom lokalen PC geladen. Ein USB-Kabel oder das Script aus der Installation sind nicht erforderlich.
