# Der Brautomat für ESP8266

[![Brautomat](https://img.shields.io/badge/Latest-Brautomat32-blue.svg)](https://github.com/InnuendoPi/Brautomat32) [![Brautomat](https://img.shields.io/badge/EOL-Brautomat-green.svg)](https://github.com/InnuendoPi/Brautomat32)

_End of life: Die Entwicklung für den Brautomat ESP8266 wird ab März 2025 eingestellt. Bitte auf den [ESP32](https://github.com/InnuendoPi/Brautomat32) wechseln._

## Changelog

Version 1.48.8

* Update:       VSCode 1.97
* Update:       Dallas Temperature Bibliothek 4.0.4
* Fix:          Temperatur Übergang Kochen wurde nicht korrekt an PID Controller übertragen, wenn der brauprozess aus dem Flashspeicher fortgesetzt wurde
* Fix:          Typo Debugausgaben ThresTemp und ThresOutput
* Geändert:     InnuAPID Überprüfung Temperatur Übergang Kochen angepasst
* Geändert:     Die Nachricht "WebUpdate abgeschlossen" mit auto reload wurde "manchmal" nicht angezeigt
* Fix:          Fehler im Modul Aktoren UpdatePower behoben
* Geändert:     ajax synchronous get requests
* Fix:          Button "Nachguss löschen" wurde aus WebIf ohne Kessel ID übermittelt
* Fix:          wurde vor dem Power Button Maischeplan Sud oder HLT eingeschaltet, wurde ein Sonderbefehl als erster Maischeschritt nicht ausgeführt
* Fix:          sehr langsame Reaktion im Relais Modus behoben
* Fix:          noiseband und Temperatur delta zum Ziel wurden nicht korrekt im Profil gespeichert
* Geändert:     in der Chart Legende werden die Kesselnamen angezeigt. Die Zieltemperaturen mit dem postfix "target"
* Update:       Chart.js 4.4.1
* Geändert:     Ist und Soll Temperatur Kessel Sud in die Chart eingefügt
* Geändert:     Der Sonderbefehl IDSPROFIL prüft vor dem Profilwechsel den Gerätetyp
* Fix:          SensorID wurde im Sonderbefehl IDSPROFIL nicht korrekt übertragen
* Update:       Dallas Temperature Bibliothek 4.0.3
* Fix:          Bei Profilwechsel und Sonderbefehl IDSPROFIL wurde der Status GPIO invertieren im Relais Modus nicht korrekt übernommen
* Geändert:     default Status GPIO invertieren in der Kessel Konfiguration auf false gesetzt
* Neu:          Im Relais Modus kann der GPIO nun invertiert werden
* Fix:          Freigabe GPIOs bei Wechsel Kesseltyp (off, IDS, Relais) korrigiert
* Fix:          Fehler in der Profilverwaltung behoben
* Update:       Dallas Temperature Bibliothek 4.0.1 (fix err handling, fix device search)
* Update:       Release 1.48 erstellt
