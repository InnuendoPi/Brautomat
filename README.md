# Changelog

Version 1.13

\*Korrektur: Fehler beim Speichern Einstelung Toast Nachrichten behoben (typo) \*Korrektur: Toast Objekte \*Korrektur: Die Ladezeit für die toast.min.js verbessert (dauert trotzdem noch zu lange) \*Geändert: Toasts vom Typ Error bleiben stehen, bis sie angeklickt werden \*Geändert: Abfragen Toasttypen \*Korrektur: Fehler Toasts und Alarme mp3 Einstellung Nur Fehler

Version 1.12

* Neu: Name Maischeplan editierbar (Rezeptname)
* Neu: Info zur Kochdauer und Nachisomerisierungszeit (readonly)
* Korrketur: Zeitberechnung Hopfengabe Typ Ausschlagen
* Korrektur: Nachisomerisierung wenn Hopfengabe Typ Ausschlagen vorhanden ist
* Korrektur: Reihenfolge bei Nachisomerisierung und Ausschlagen korrigiert
* Korrektur: Zeitpunktberechnung Hopfengabe Typ Kochen (3)
* Korrektur: Benachrichtigung Firmware Update WebUpdate (Alert)
* Optimiert: CSS Dateien

Version 1.11 - das kleinerBrauhelfer2 Update

* Neu: Import aus dem Tab Maischeplan: Einmaischen, Aufheizen, Zubrühen und Dekoktion
* Neu: Import aus dem Tab Kochen: Vorderwürze, Ausschlagen und Hopfengabe Kochbeginn, Kochen und Kochende
* Neu: Kochdauer und Nachisomerisierungszeit werden aus kbh2 verwendet
* Neu: der Sudname aus kbh2 wird als Rezeptname im Brautomat verwendet
* Angepasst: Maximale Anzahl Einzelschritte im Maischeplan auf 20 erhöht (Dekoktion)
* Angepasst: Maischeschritt Einmaischen, Zubrühen und Dekoktion werden mit deaktiviertem autonext importiert
* Angepasst: Maischschritt Aufheizen über 76°C wird mit deaktiviertem autonext importiert (Abmaischen)
* Angepasst: Vorderwürzenhopfung wird mit 0min Dauer und 0°C importiert
* Angepasst: ist keine Hopfengabe vom Typ Kochbeginn enthalten, wird vor der ersten Hopfengabe Kochen ein Kochenschritt eingefügt
* Angepasst: die Dauer errechnet sich in dem Fall aus Kochdauer abzüglich der Summe der Hopfengaben
* Angepasst: eine Hopfengabe Ausschlagen mird mit positiver Dauer und 80°C importiert
* Angepasst: die Dauer entspricht beim Ausschlagen der Nachisomerisierungszeit
* Geändert: Der Rezeptimport aus dem kleinenBrauhelfer2 benötigt Version 2.5 oder neuer

Vielen Dank an bourgeoislab für die Unterstützung ;-)

Version 1.1 (rel)

* Update: bootstrap minified CSS (purged)
* Optimiert: Ladegeschwindigkeit verbessert
* Update: Arduino für VSCode 0.5.0
* Update: VSCode 1.75
* Update: Bibliothek PCF8574 0.3.8
* Korrektur: Anzeige Toast zeitgleich auf unterschiedlichen Geräten. Auf iOS weiterhin nur ein workaround möglich
* Geändert: wenn der Maischeprozess gestartet ist, muss der Maischeprozess pausiert werden, um den Maischeplan editieren zu können
* Neu: die Buttons und Icons zum Editieren werden während des Maischeprozesses ausgeblendet auf Smartphones und kleinen Tablets ist die Tabelle Maischeplan durch das Ausblenden vollständig sichtbar
* Neu: die aktuelle Rast wird im Maischeplan farblich markiert.
* Geändert: die Buttons Power (grün), Play und Pause (rot) werden im aktiven Zustand mit voller Farbe dargestellt (vorher outline)
* Geändert: der aktuelle Status Power, Play und Pause wird geräteübergreifend gespeichert
* Korrektur: Toasts timer handling (Toast wurden nicht zugestellt)
* Neu: success.mp und warning.mp3 (Benennung beibehalten)
* Neu: Toasts werden nach 60 Sekunden gelöscht oder durch neuen Toast überschrieben
* Neu: mp3 Alarme für Systemevents
* Geändert: Reboot initiert nun automatisch ein page reload
* Update: ArduinoJSON Bibliothek
* Update: PCF8574 Bibliothek (GPIO Erweiterung)
* Entfernt: Debug Ausgaben
* Korrektur: Log Datei AutoTune
* Geändert: Datei handling
* Geändert: Display Dateien HMI
* Geändert: Anleitung auf gitpages aktualisiert

Version 1.0l

* Korrektur: logischer Fehler in Abfrage Zieltemperatur 0°C behoben
* Update: mp3 Audio für iOS

Version 1.0k

* Neu: MP3 Audio für Toast Nachrichten (info.mp3 und error.mp3) die MP3 Dateien können ausgetauscht werden
* Korrektur: Auswahl Toastnachrichten: Aus, Ein oder nur Fehler
* Korrektur: Anzeige Toast Nachrichten angepasst: Uhrzeit #lfdNr : Nachricht
* Korrektur: ESP8266 cores (#8844)

Version 1.0j

* Neu: Button vorheriger Step. Springt einen Maischeschritt zurück. Wenn Pause aktiviert ist, wird der Rast-Timer der aktuellen Rast zurückgesetzt.
* Korrektur: Bibliothek ESPSoftSerial aktualisiert (github #267)
* Geändert: Anleitung auf gitpages aktualisiert

Version 1.0i

* Update: ESP8266 cores aktualisiert
* Update: Arduino for Visual Code 0.4.13
* Korrektur: Ticker Bibliothek
* Korrektur: Name im AP Modus Brautomat
* Korrektur: Im Modus Kochen wurde ein logischer Fehler in der Auswertung autonext behoben
* Neu: Zubrühen

Version 1.0h

* Korrektur: Speicherzuteilung Rezept nicht ausreichend für 15 Maischeschritte. Neue Größe Rezpet JSON 2048
* Korrektur: Fehler in autonext behoben, wenn setpoint vom nachfolgenden Maischeschritt unter Ist-Temperatur liegt
* Neu: Wenn die Zieltemperatur auf 0°C gesetzt wird und autonext aktiv, wird der Step ohne Temperaturprüfung gestartet
* Korrektur: Typo: Änderung am Objekt IDS während des Brauens ändert die Leistung Objekt HLT.
* Korrektur: Temperatur delta zum Ziel sowohl über als auch unter setpoint (fabs)
* Korrektur: HLT Standardregel INDIVIDUAL\_PID

Version 1.0g

* Geändert: Parameter AutoTune Intervall umbenanntn in PID Intervall (IDS und Nachguss) \[2sek bis 5sek]
* Geändert: Parameter PID Intervall in Tab PID-Manager verschoben
* Geändert: das PID Intervall (SampleTime) legt die Taktung Auslesen Sensor und Leistung an Indution fest
* Anmerkung: Reihenfolge: Sensorwert auslesen - PID Berechnung - berechnete Leistung an IDS senden
* Anmerkung: ein sehr kleines Intervall (alle 2sek) führt zu sehr vielen Berechnungen wordurch der Brautomat träger reagiert.
* Anmerkung: kleinere Intervalle (2sek) kann bei kleinen Maischevolumen (10-15l) vorteilhaft sein
* Korrektur: Fehler HLT PID Anzeige behoben
* Korrektur: HLT AutoTune Zieltemperatur readonly
* Korrektur: Web Interface Parameterbeschreibungen
* Geändert: Das Ein- und Ausblenden der Tabellen Nachguss, Sensoren und Aktoren wird nicht mehr automatisch gespeichert
* Geändert: Das Ändern der Tuning Regel wird nicht mehr automatisch gespeichert
* Neu: Überprüfung Wertebereich für Eingaben der Paramtertypen Leistung, Temperatur, Anzahl und Zeit eingefügt

Version 1.0f

* Update: ESP8266 Arduino 3.1.1
* Geändert: Refresh Sensoren, IDS und HLT auf 2000ms
* Geändert: AutoTune timeout auf 20min
* Geändert: Max Leistung als oberes Limit in die PID Berechnung integriert
* Neu: Eigenschaft Max Leistung HLT eingefügt
* Korrektur: Fehler HLT PID Berechnung behoben
* Korrektur: WebUpdate Tools ist Teil von WebUpdate Firmware. Button WebUpdate Tools entfernt

Version 1.0e und früher

* Neu: Neue Option für Toasts "Info": alle Nachrichten
* Neu: Neue Option für Toasts "Fehler": nur Nachrichten bei Sensor oder WLAN Fehler
* Update: ESP8266 core fix #8796 #8797
* Update: VSCode 1.74.3
* Korrektur: Umwandlung Sensor Adresse in Hex (SetResolution)
* Neu: Parameter Maximale Leistung IDS kann nun während des Brauens verändert werden
* Neu: Parameter Temperatur Kochen IDS kann nun während des Brauens verändert werden
* Neu: Parameter Leistung Kochen IDS kann nun während des Brauens verändert werden
* Neu: Toast Nachrichten bei Sensorfehler
* Neu: Alarm Error bei Sensor Fehler
* Neu: Alarm Error bei WLAN Fehler
* Korrektur: Toast Nachrichten konnten nicht deaktiviert werden
* Korrektur: Auswahl Tuning Regel IDS und Nachguss berechnet keine Werte für P, I, D
* Geändert: Seitenwechsel Display auf 0x66 angepasst (Vorbereitung Update Bibliothek NextionX2)
* Update: ESP8266 3.1.0: Fehler in ESPWebServer behoben (Webseite ganz oder teilweise nicht erreichbar)
* Update: ESP8266 3.1.0: Fehler in ESPSoftSerial behoben (Anbindung Display)
* Update: ESP8266 Arduino 3.1.0
* Update: VSCode 1.74.2
* Update: Nextion HMI Editor 1.65
