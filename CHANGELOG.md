# Changelog

ESP8266 Arduino 3.1.2\
VSCode 1.83 Arduino-CLI 0.34.2\
VSCode plugin ESP8266Littlefs based on VSCode plugin ESP8266fs\
InnuAPID AutoTune PID lib based on [Brett Beauregard](https://github.com/br3ttb/Arduino-PID-Library)\
InnuTicker task scheduler lib\
InnuFramework CSS/JS bootstrap 4.6.2\
Server Sent Events (8 SSE channels)

Version 1.35

* Geändert:     Steuerbefehle für IDS, HLT und Aktoren

Version 1.34a

* Fix:          Übersetzung
* Fix:          Links zu gitbook Parameter
* Geändert:     Quellcode ESP8266 und ESP32 zusammengefügt.
* Geändert:     Neues Format Maische Malz und mehr Rezeptimport

Version 1.33j

* Geändert:     GPIO Auswahl für Buzzer
* Geändert:     Zurücksetzen in Werkseinstellung angepasst (WLAN und Konfig löschen aktiviert)
* Fix:          Standard PID Regel MaischeSud korrigiert
* Geändert:     Standard SampleTime MaischeSud angepasst
* Fix:          Fehler maximale Anzahl an Sensoren
* Fix:          Fehler beim reload WebIf nach Neustart
* Fix:          Nach Wiederherstellung der Konfiguration wurde das Fenster nicht geschlossen
* Fix:          Datei lang.js in WebUpdate hinzugefügt (keine Sprachauswahl nach Update auf 1.33f)
* Geändert:     Auswahlliste Sensor-Typ (DS18B20, PT100x) und Sensor-Pin (2-, 3-, 4-Leiter) in Sprachfiles verschoben
* Geändert:     Auswahlliste PID Regeln in Sprachfiles verschoben
* Geändert:     Auswahlliste Typ IDS in Sprachfiles verschoben
* Neu:          Toast Nachrichten an Sprachfiles angepasst
* Fix:          Sprachfiles Auswahl Toasts und MP3 falsche Reihenfolge (on/off vertauscht)
* Neu:          Auswahl Sprache (de, en)
* Neu:          Verzeichnis /language
* Neu:          offenes Format (JSON) für Sprachdateien und ToolTipps erstellt

Version 1.32c

* Fix:          Fehler maximale Anzahl an Sensoren
* Fix:          Fehler beim reload WebIf nach Neustart
* Fix:          Nach Wiederherstellung der Konfiguration wurde das Fenster nicht geschlossen
* Fix:          Fehler WebIf behoben (Webseite wurde teilweise geladen)
* Fix:          Fehler WebIf behoben howler.js entfernt
* Geändert:     Auf html5audio umgestellt
* Neu:          GGM IDS Pin Interrupt kann deaktiviert werden: Errorcodes der IDS werden nicht ausgelesen
* Neu:          GPIO Pin "Aus" eingefügt. Die Auswahl deaktiviert einen Aktor und gibt den GPIO frei
* Fix:          Variablentyp mismatch korrigiert

Version 1.31

* Neu:          NTP Server konfigurierbar
* Fix:          Initialisierung Piezo
* Update:       jQuery 3.7.1
* Update:       Howler 2.2.4 (play audio files)
* Optimiert:    InnuFramework CSS (purge)
* Geändert:     Display MaischeSud angepasst

Version 1.30b

* Fix:          Bootreihenfolge Treiber Display
* Fix:          Bootreihenfolge Treiber DS18B20
* Fix:          Absturz bei Displayaktivierung behoben
* Fix:          KBH2 Datei wurde nach Rezeptimport nicht gelöscht (debug)
* Fix:          WebUpdate OOM/MFLN github
* Geändert:     Anzeigedauer Toast-Nachrichten reduziert: info, success 10s, warning 20s
* Fix:          Anzeigefehler Leistung IDS im Status statePlay (Play Button rot) nach Maischeschritt mit deaktiviertem autonext
* Fix:          Anzeigefehler Timer nach Button Prev/Next auf Maischeschritt Aktor schalten behoben
* Fix:          Zeitgesteuerter Braustart: Aktor einschalten als erster Schritt wurde nicht erkannt
* Geändert:     Sensorkalibrierung auf 15 Messwerte reduziert

Version 1.29

* Fix:          Fehler bei der Erkennung Aktor ein/ausschalten im Maischeplan behoben
* Neu:          Schalten von Aktoren und Nachguss im Maischeplan

Version 1.28

* Fix:          Maischeprozess beendet: nur eine Toastnachricht/Signal "Prozess beendet"
* Geändert:     WebIf Sensorkalibrierung
* Geändert:     Anzahl Sensorwerte Kalibrierung von 60 auf 30 reduziert
* Fix:          Startpage Display
* Fix:          PCF8574 Initialisierung (Fehler 0x82)
* Cleanup:      Debug Ausgaben entfernt
* Cleanup:      Quellcode strukturiert u. optimiert Teil 4
* Fix:          WebUpdate (connection lost)
* Geändert:     Update Intervall Sensoren, IDS2, HLT und SYS sind abhängig (Minimum)
* Geändert:     Standard Updateintervall Sensoren, IDS und HLT auf 2000ms geändert
* Fix:          Fehler bei Änderung SampleTime behoben
* Geändert:     Standardauflösung Sensoren auf 12bit gesetzt (+- 0.0625°C)
* Fix:          Ticker Anpassungen IDS2, HLT und Sensoren
* Geändert:     WLAN reconnect auf WiFi Events umgestellt (builtin)
* Geändert:     WLAN Ticker entfernt
* Cleanup:      Quellcode strukturiert u. optimiert Teil 3
* Geändert:     Server requests SSE & keepAlive handling
* Cleanup:      WebServer response, var
* Fix:          Debug output File browser entfernt
* Neu:          Tab Sysinfo
* Geändert:     Umstellung auf Arduino-CLI
* Fix:          kbh2 Import Hopfengabe Type Vorderwuerze 0 (Kochen alt) wurde nicht korrekt eingelesen
* Fix:          kbh2 Import Hopfengabe Type Vorderwuerze 0 (Kochen alt) wurde bei der Restzeit Kochen nicht eingerechnet
* Fix:          Größe JSON für MaischeSud Kessel angepasst
* Geändert:     PWM Aktoren duty cycle
* Geändert:     DS18B20 Sensorabfrage (requestTemperatures) und Ausgabe der berechneten Temperaturen unterteilt
* Geändert:     minimale Zeitdifferenz zwischen Sensorabfrage und Ausgabe Temperatur auf Resolution Timeout gesetzt (bspw. bei 11bit 375ms)
* Cleanup:      Typ und Scope diverser Variablen
* Cleanup:      Identifizieren Pin und Typ Aktoren
* Cleanup:      alle WebServer Antworten auf minimal response reduziert
* Cleanup:      sämltiche String concat Manipulationen in den Flash Speicher verschoben
* Cleanup:      sämtliche Klassenvariablen (Sensoren, Aktoren und Induktion) überarbeitet
* Cleanup:      Variablentyp String in allen ArduinoJSON (serialize, deserialize) durch char arrays ersetzt
* Cleanup:      Quellcode strukturiert u. optimiert Teil2

Version 1.27

* Cleanup:      Quellcode strukturiert u. optimiert
* Geändert:     DateiUpdate
* Geändert:     Zeichenanzahl für Namen Sensoren und Aktoren auf maximal 15 Zeichen beschränkt
* Korrektur:    Bei maximaler Anzahl Aktoren wurde zu wenig RAM für das SSE JSON reserviert
* Korrektur:    Web Interface Speichern Profil wurde mit zweifach server.send ok beendet
* Geändert:     Uhrzeit NTP Ticker ersetzt (erforderlich für SSL Verbindung)
* Geändert:     WebUpdate Standardverbindung SSL
* Geändert:     Speicherverbrauch WebUpdate optimiert
* Neu:          Log Datei WebUpdate (webUpdateLog.txt)
* Fix:          github MFLN Verprobung WebUpdate
* Fix:          WebUpdate
* Erneuert:     Zertifikate SSL
* Fix:          reload Maischetabelle ohne server send ok beendet
* Fix:          memory usage Import Filter, wenn sehr große Rezepte (Dateigröße) importiert werden
* Fix:          Anzeige Display bei langen (zusammengesetzten) Namen im Maischeplan
* Fix:          Anzeige Mengenangaben linksbündig (Schüttung, Wasser, Hopfen, Zugaben)
* Fix:          Import KBH2 Rundungsfehler behoben
* Fix:          Importfilter kbh2 wurde nach Abschluss Import nicht gelöscht
* Fix:          Importfilter BrewFather Berechnung Dauer Kochen Hopfen
* Geändert:     Importfilter MMum VWH
* Geändert:     Import kleinerBrauhlfer2 Version 2.6 Dekoktion
* Geändert:     Status Icon SSE readonly in die Systemzeile verschoben

Version 1.26:   Update kleinerBrauhelfer2 Version 2.6

* Geändert:     Import kleinerBrauhlfer2 Version 2.6 Einmaischen, Aufheizen, Zubrühen und Zuschütten
* Neu:          Verwaltung von Hardware profilen (MaischeSud Kessel: erstellen, löschen, wechseln)
* Neu:          Sensorkalibrierung über das WebIf
* Neu:          Sensor Offset Berechnung erstellt ein Logfile
* Neu:          Sensor Offset Berechnung über Mittelwert aus 60 Messproben
* Fix:          eine Veränderung der Zieltemperatur in einem pausierten Maischeprozess wurde nicht im Display angezeigt (WebIf ok)
* Fix:          doppelter server.send OK entfernt
* Fix:          in der Ansicht Tabelle Maischeplan beim Brauen (kleine Lücke auf der re Seite)
* Fix:          Fehler in Dateisystem behoben
* Fix:          Löschen letzter Sensor, letzter Aktor oder HLT hat den Eintrag im Dashboard nicht entfernt (erst nach reload)
* Fix:          Wenn der Maischeprozess gestartet und ein reload auf das WebIf durchgeführt wurde, waren alle Icons zuum Editieren der Tabelle eingeblendet
* Fix:          eine Veränderung der Zieltemperatur in einem pausierten Maischeprozess wurde nicht korrekt übernommen (Anzeige ok, aber Zieltemperatur falsch)
* Geändert:     Icon Kalender (geplanter Braustart) entfernt -> im Menü Maischeplan editieren enthalten
* Geändert:     Korrekturen WebIf

Version 1.25 dev

* Neu:          Maischeplan Verwaltung (Maischeplan wechsel)
* Info:         Der Maischeplan Name ist auf 26 Zeichen beschränkt (maximale Dateinamenlänge Arduino LittleFS 31 (Sudname plus Endung .json)
* Info:         der Maischeplan Name wird als Dateiname verwendet (Leerzeichen und Umlaute werden ersetzt)
* Info:         Speicherort der Maischepläne im Flash unter /Rezepte/
* Info:         der vorhandene (alte) Maischeplan (mashplan.json) wird automatisch konvertiert und nach /Rezepte verschoben
* Info:         ein vorhandener (neuer) Maischeplan wird bei einem Import mit identischem Maischeplan Namen überschrieben
* Neu:          Maischeplan Wechseln
* Neu:          Maischeplan löschen
* Neu:          SSE auto reconnect
* Neu:          SSE checkAlive für Mobile Browser (nur auf iOS getestet)
* Geändert:     Funktion Pause Button während der Aufheizphase. Siehe [Anleitung - Die Steuerung](https://innuendopi.gitbook.io/brautomat_de/der-maischeplan/die-steuerung)
* Geändert:     Systemmenü Rezepte entfernt. Maischeplan Import/Export nach Maischeplan editieren verschoben
* Geändert:     SSE reconnect und CheckAlive timing
* Geändert:     Anleitung überarbeitet
* Geändert:     Datei Explorer erweitert (Dateiordner)
* Geändert:     InnuFramework (CSS, Icons, Tooltips)
* Fix:          Auswahl Sensor Einrichtung MaischeSud Kessel
* Fix:          Arduino ESP8266 core: No poison after block with current git version (Issue #8952)

Version 1.23a

* Geändert:     Manuelles Kochen in den Voreinstellungen auf deaktiviert geändert
* Geändert:     Grafik Chart in den Voreinstellungen auf deaktiviert geändert
* Korrektur:    "Grundkonfiguration ausführen" als Schrittname wurden nicht angezeigt, wenn keine Konfiguration vorhanden ist
* Neu:          Chart ein/ausklappbar (Button collapse) - Grafik wird eingeklappt im Hintergrund aktualisiert
* Geändert:     Anleitung überarbeitet
* Geändert:     InnuFramework

Version 1.23

* Geändert:     Anleitung überarbeitet
* Geändert:     Abschlusstest AutoTune IDS, AutoTune HLT
* Geändert:     Abschlusstest Brauen

Version 1.22e - 1.22j

* Neu:          Maischeplan ein/ausklappbar (Button collapse)
* Neu:          Ändern der Leistung zur Laufzeit in der Aktoren-Tabelle über zwei Buttons (Schritte +/- 10%)
* Neu:          Aktoren PWM Schalter (zum Ausblenden der Buttons Änderung der Leistung in der Tabelle Aktoren)
* Geändert:     Maischeplan SSE optimiert
* Korrektur:    Maischeplan Änderung über SSE (Aktualisierung aller verbundenen Clients)
* Korrektur:    Arduino ESP8266 core: Fix for occasional timeout issues #8944 (net error timeout - WebIf Fehler)
* Geändert:     PID Nachguss Vorgaben angepasst
* Korrektur:    WebIf laden der select box Parameter (empty rsponse)
* Geändert:     Ticker Intervalle IDS und HLT
* Geändert:     Ticker Intervalle PID Berechnung
* Geändert:     Ticker Intervalle und durycylcles Aktoren (PWM)
* Korrektur:    Arduino ESP8266 core: Fix for dangerous relocation: j: cannot encode #8925
* Geändert:     Arduino ESP8266 core: Add support WiFiClientSecure TCP KeepAlive #8940
* Geändert:     Intervalle (SampleTime) können im laufendem Betrieb geändert werden
* Geändert:     Intervalle (SampleTime) Bereich vergrößert 3000 - 7000
* Geändert:     Nachguss PID Temperatur und GPIO Taktung erweitert
* Geändert:     Sensorzuweisung Nachguss
* Korrektur:    PID Debug Ausgaben
* Korrektur:    SetPoint und Target Nachguss
* Geändert:     InnuFramework
* Korrektur:    Anzahl Verbindungen (request) WebIf verringert
* Korrektur:    Verzögerung beim Start SSE mit Firefox behoben
* Neu:          Überprüfung SSE checkAlive für Tablets/Smartphones

Version 1.22d

* Geändert:     PID Algorithmus IDS: Individuell oder IDS
* Geändert:     PID Algorithmus HLT: Individuell oder Nachguss
* Geändert:     PID Algorithmus: Button löschen entfernt
* Geändert:     Datenmenge und requests PID Manger IDS/HLT minimiert
* Geändert:     Web Interface Reihenfolge
* Korrektur:    Sudname nach Deaktivierung geplanter Braustart nicht korrekt angezeigt

Version 1.22c

* Geändert:     Datentranfer Optimierung (push)
* Geändert:     Flash Speicher Optimierung
* Korrektur:    Arduino ESP8266 core: WiFi Client core fix #8941
* Korrektur:    Start HLT AutoTune
* Geändert:     Web cache control

Version 1.22b

* Korrektur     Fehler beim Einlesen der Konfiguration (Temperaturvorgaben IDS, zugewiesener Sensor)

Version 1.22a

* Korrektur:    Rezeptimport KBH2 Zusätze: falscher Parameter ausgewertet (menge statt erg_menge)
* Korrektur:    Step Aktualisierung wurde u.U. doppelt in einem loop aufgerufen
* Fix:          Fehler beim Laden WebIf bzw. unvollständiges Laden (streamfile header response #8873)
* Fix:          JSON parse Sensoren Daten: unexpected non-whitespace character (array)
* Geändert:     InnuFramework mimeTypes und mimeTables
* Geändert:     Start Server Sent Event optimiert
* Geändert:     Laden vom WebIf beschleunigt
* Geändert:     Der Button Status Server Sent Events führt nur bei disconnect einen reload aus (rot)\
                Wenn SSE verbunden ist, hat der Button außer tooltip keine Funktion (grün)

Version 1.22

* Geändert:     Rezept Import kbh2: Hopfengabe wird zusammengesetzt aus Name, Alpha [%] und Menge [gr]
* Korrektur:    Rezepttyp Erkennung korrigiert (type mismatch, Zahlendreher nach Optimierung).
* Neu:          Rezeptimport KBH2 Hopfengaben und Zutaten um Mengenangaben erweitert
* Neu:          Rezeptimport KBH2 Zubrühen um Mengen- und Temperaturangaben erweitert
* Neu:          Rezeptimport KBH2 Dekoktion um Mengenangaben erweitert
* Neu:          Rezeptimport KBH2 um Zutaten aus den Tabs Maischen und Kochen erweitert
* Neu:          Eigenschaften Temperatur Einmaischen und Abmaischen für Rezeptimport eingefügt
* Neu:          Eigenschaften Temperatur Vorderwürzenhopfung und Whirpoolhopfung für Rezeptimport eingefügt
* Geändert:     Rezept Import BrewFather: Daten (Zeit, Temp) werden vor verarbeiten überprüft
* Korrektur:    Rezept Import BrewFather: Rastennamen und Hopfengaben auf 50 Zeichen begrenzt
* Korrektur:    Rezept Import BrewFather: Berechnung Kochdauer Hopfengabe
* Korrektur:    Rezept Import BrewFather: Rastdauer 0 Minuten, wenn Rezept mit Fließkommazahlen erstellt wurde
* Korrektur:    Start Chart Ticker (Graph Temperaturen) bei Braustart über Timer
* Korrektur:    Bei Braustart über Timer wurden die Buttons zum Editieren nicht ausgeblendet
* Korrektur:    Aktualisieren der Buttons bei Braustart über Timer (Power Button war nicht aktiv grün gesetzt)
* Korrektur:    Speichern der Konfiguration HLT
* Korrektur:    Refresh Maischeplan nach editieren nicht korrekt geladen
* Korrektur:    Import MMuM Filtergröße
* Korrektur:    Import type mismatch JSON as int to var unsigend long
* Korrektur:    Import sehr großer Rezepte
* Korrektur:    Import Filter Speicherverbrauch optimiert
* Neu:          IDS Parameter Temperatur kochen: Temperatur bei der die Würze wallend kocht
* Korrektur:    Parameter Temperatur kochen umbenannt in Übergang zum Kochen
* Korrektur:    Rezept Import kbh2: autonext wurde falsch gesetzt
* ZF:           Alle Importfilter sollten nun komplett sein. Empfehlung: kleinerBrauhelfer2!
* Korrektur:    Rezept Import MMuM: Hopfengaben zum gleichen Zeitpunkt
* Korrektur:    Rezept Import MMuM: Typ Hopfen_VWH_1_Sorte eingefügt
* Neu:          Optionen für den Import: Einmaischen 50°C für 1min mit deaktiviertem autonext, falls nicht vorhanden (oder gefunden)
* Neu:          Optionen für den Import: Abmaischen 78°C für 1min mit deaktiviertem autonext, falls nicht vorhanden (oder gefunden)
* Neu:          Import MaischeMalzundMehr Rezepte: Dekoktion
* Korrektur:    Rezept Import KBH2: Hopfengaben zum gleichen Zeitpunkt
* Korrektur:    Rezept Import KBH2: Vorderwürzenhopfung vor Step Kochen
* Korrektur:    Step Dauer 0 Minuten
* Deaktiviert:  Hinweis (Toasts) neue Version
* Neu:          Import Brewfather Rezepte
* Korrektur:    Import Brewfather: Hopfengabe Zeitpunkt
* Geändert:     Import MaischeMalzundMehr Rezepte: JSON Import Filter eingefügt (Anmerkungen werden nicht mehr eingelesen)
* Geändert:     Import MaischeMalzundMehr Rezepte: Überprüfung auf Maischeform Infusion eingefügt
* Korrektur:    Import MaischeMalzundMehr Rezepte: Import Rezept Name u. Kochdauer
* Neu:          Import MaischeMalzundMehr Rezepte: Import Hopfengaben hinzugefügt

Version 1.21

* Optimiert:    Quellcode überarbeitet
* Neu:          Hinweis (Toasts) neue Version
* Geändert:     Anleitung
* Update:       JQuery 3.7.0

Version 1.20

* Optimiert:    Web Interface Geschwindigkeit  
* Neu           Synchronisierung ESP8266 und Web Browser (SSE)
* Neu           Server Sent Events (SSE) ersetzen Ajax/JQuery requests (http polling)
* Neu           8 SSE Kanäle (channels) stehen zur Verfügung
* Neu           Favicon
* Geändert:     Anleitung
* Korrektur:    Reload nach Firmware Update (Toast)
* Korrektur:    Reload nach SSE connection closed (Toast)

Version 1.19

* Neu:          SSE
* Korrektur:    CSS/JS load files unknown length
* Korrektur:    Konvertierungsfehler Datum Uhrzeit nach epochtime (Berechnung Startzeit Brauen)
* Neu:          Schaltjahr Epochtime
* Korrektur:    Rezept Import

Version 1.18

* Neu:         Zeitsteuerung Brauen eingefügt
* Neu:         DateTimePicker im Menü Sud (Zeitsteuerung)
* Neu:         Manueller Modus im Web Interface eingefügt
* Geändert:    Sichtbarkeit der Dashboard Elemente (Systemeinstellungen - Dashboard)
* Optimiert:   Icons (icomoon free)
* Geändert:    Option Manueller Modus im Dashboard aktiviert
* Korrektur:   Tippfehler
* Optimiert:   Geschwindigkeit Web Interface

Version 1.17

* Update:      SoftSerial 8.0.2 (Kommunikation Nextion Display)
* Optimiert:   Geschwindigkeit Nextion Display
* Korrektur:   Während AutoTune wird die erste Zeile Maischeplan nicht mehr markiert
* Geändert:    Beim Start vom Brautomat wird die GGM IDS auf null Prozenzt Leistung gesetzt
* Geändert:    Erkennen von Min/Max AutoTune
* Geändert:    Überprüfung ob AutoTune Peaks stabil sind
* Optimiert:   Während AutoTune GGM IDS wird die Auflösung Temperstursensor auf 12bit gesetzt (max. Auflösung, 0.0625°C)
* Geändert:    Prüfung auf isConnected der Temperatursensoren entfernt (fehlerhafter Rückgabe bei manchen DS18B20 Sensoren)
* Geändert:    Sensor Fehler Code Auswertung entfernt (-254, -253, -252, -127). Sensorwerte ab -127.0 werden als Sensorfehler behandelt
* Optimiert:   MP3 Dateien komprimiert
* Optimiert:   Reihenfolge web requests optimiert
* Geändert:    AutoTune debug Log komprimiert
* Erweitert:   Dashboard Status (not yet ready)
* Korrektur:   JS Toasts (Typo)
* Korrektur:   WebUpdate Toasty entfernt (alte JS)
* Neu:         Tab Dashboard: Konfiguration der Elemente auf dem Dashboard
* Geändert:    Ansicht Dashboard
* Geändert:    Refresh Dashboard

Version 1.15   maintenance/Framework update

* Optimiert:   Framework Innuticker Display Update read SoftSerial (updateBack)
* Optimiert:   Web Interface Ladevorgang verbessert (toasts lib)
* Optimiert:   TouchDisplay Reaktionszeit beschleunigt
* Geändert:    Framework Aktualisierung der Ticker Objekte (updateBack)
* Ersetzt:     Toast Lib

Version 1.14  maintenance update

* Update:     ESP8266 Arduino 3.1.2
* Update:     VSCode 1.76 Arduino 0.6
* Update:     ArduinoJSON 6.21
* Update:     SoftwareSerial 8.0.1
* Optimiert:  Framework

Version 1.13

* Korrektur:   Fehler beim Speichern Einstelung Toast Nachrichten behoben (typo)
* Korrektur:   Toast Objekte
* Korrektur:   Die Ladezeit für die toast.min.js verbessert (dauert trotzdem noch zu lange)
* Geändert:    Toasts vom Typ Error bleiben stehen, bis sie angeklickt werden
* Geändert:    Abfragen Toasttypen
* Korrektur:   Fehler Toasts und Alarme mp3 Einstellung Nur Fehler

Version 1.12

* Neu:        Name Maischeplan editierbar (Rezeptname)
* Neu:        Info zur Kochdauer und Nachisomerisierungszeit (readonly)
* Korrketur:  Zeitberechnung Hopfengabe Typ Ausschlagen
* Korrektur:  Nachisomerisierung wenn Hopfengabe Typ Ausschlagen vorhanden ist
* Korrektur:  Reihenfolge bei Nachisomerisierung und Ausschlagen korrigiert
* Korrektur:  Zeitpunktberechnung Hopfengabe Typ Kochen (3)
* Korrektur:  Benachrichtigung Firmware Update WebUpdate (Alert)
* Optimiert:  CSS Dateien

Version 1.11 - das kleinerBrauhelfer2 Update

* Neu:        Import aus dem Tab Maischeplan: Einmaischen, Aufheizen, Zubrühen und Dekoktion
* Neu:        Import aus dem Tab Kochen: Vorderwürze, Ausschlagen und Hopfengabe Kochbeginn, Kochen und Kochende
* Neu:        Kochdauer und Nachisomerisierungszeit werden aus kbh2 verwendet
* Neu:        der Sudname aus kbh2 wird als Rezeptname im Brautomat verwendet
* Angepasst:  Maximale Anzahl Einzelschritte im Maischeplan auf 20 erhöht (Dekoktion)
* Angepasst:  Maischeschritt Einmaischen, Zubrühen und Dekoktion werden mit deaktiviertem autonext importiert
* Angepasst:  Maischschritt Aufheizen über 76°C wird mit deaktiviertem autonext importiert (Abmaischen)
* Angepasst:  Vorderwürzenhopfung wird mit 0min Dauer und 0°C importiert
* Angepasst:  ist keine Hopfengabe vom Typ Kochbeginn enthalten, wird vor der ersten Hopfengabe Kochen ein Kochenschritt eingefügt
* Angepasst:  die Dauer errechnet sich in dem Fall aus Kochdauer abzüglich der Summe der Hopfengaben
* Angepasst:  eine Hopfengabe Ausschlagen mird mit positiver Dauer und 80°C importiert
* Angepasst:  die Dauer entspricht beim Ausschlagen der Nachisomerisierungszeit
* Geändert:   Der Rezeptimport aus dem kleinenBrauhelfer2 benötigt Version 2.5 oder neuer

Vielen Dank an bourgeoislab für die Unterstützung ;-)

Version 1.1 (rel)

* Update:     bootstrap minified CSS (purged)
* Optimiert:  Ladegeschwindigkeit verbessert
* Update:     Arduino für VSCode 0.5.0
* Update:     VSCode 1.75
* Update:     Bibliothek PCF8574 0.3.8
* Korrektur:  Anzeige Toast zeitgleich auf unterschiedlichen Geräten. Auf iOS weiterhin nur ein workaround möglich
* Geändert:   wenn der Maischeprozess gestartet ist, muss der Maischeprozess pausiert werden, um den Maischeplan editieren zu können
* Neu:        die Buttons und Icons zum Editieren werden während des Maischeprozesses ausgeblendet
              auf Smartphones und kleinen Tablets ist die Tabelle Maischeplan durch das Ausblenden vollständig sichtbar
* Neu:        die aktuelle Rast wird im Maischeplan farblich markiert.
* Geändert:   die Buttons Power (grün), Play und Pause (rot) werden im aktiven Zustand mit voller Farbe dargestellt (vorher outline)
* Geändert:   der aktuelle Status Power, Play und Pause wird geräteübergreifend gespeichert
* Korrektur:  Toasts timer handling (Toast wurden nicht zugestellt)
* Neu:        success.mp und warning.mp3 (Benennung beibehalten)
* Neu:        Toasts werden nach 60 Sekunden gelöscht oder durch neuen Toast überschrieben
* Neu:        mp3 Alarme für Systemevents
* Geändert:   Reboot initiert nun automatisch ein page reload
* Update:     ArduinoJSON Bibliothek
* Update:     PCF8574 Bibliothek (GPIO Erweiterung)
* Entfernt:   Debug Ausgaben
* Korrektur:  Log Datei AutoTune
* Geändert:   Datei handling
* Geändert:   Display Dateien HMI
* Geändert:   Anleitung auf gitpages aktualisiert

Version 1.0l

* Korrektur:  logischer Fehler in Abfrage Zieltemperatur 0°C behoben
* Update:     mp3 Audio für iOS

Version 1.0k

* Neu:        MP3 Audio für Toast Nachrichten (info.mp3 und error.mp3)
              die MP3 Dateien können ausgetauscht werden
* Korrektur:  Auswahl Toastnachrichten: Aus, Ein oder nur Fehler
* Korrektur:  Anzeige Toast Nachrichten angepasst: Uhrzeit #lfdNr : Nachricht
* Korrektur:  ESP8266 cores (#8844)

Version 1.0j

* Neu:        Button vorheriger Step. Springt einen Maischeschritt zurück.
              Wenn Pause aktiviert ist, wird der Rast-Timer der aktuellen Rast zurückgesetzt.
* Korrektur:  Bibliothek ESPSoftSerial aktualisiert (github #267)
* Geändert:   Anleitung auf gitpages aktualisiert

Version 1.0i

* Update:     ESP8266 cores aktualisiert
* Update:     Arduino for Visual Code 0.4.13
* Korrektur:  Ticker Bibliothek
* Korrektur:  Name im AP Modus Brautomat
* Korrektur:  Im Modus Kochen wurde ein logischer Fehler in der Auswertung autonext behoben
* Neu:        Zubrühen

Version 1.0h

* Korrektur:  Speicherzuteilung Rezept nicht ausreichend für 15 Maischeschritte. Neue Größe Rezpet JSON 2048
* Korrektur:  Fehler in autonext behoben, wenn setpoint vom nachfolgenden Maischeschritt unter Ist-Temperatur liegt
* Neu:        Wenn die Zieltemperatur auf 0°C gesetzt wird und autonext aktiv, wird der Step ohne Temperaturprüfung gestartet
* Korrektur:  Typo: Änderung am Objekt IDS während des Brauens ändert die Leistung Objekt HLT.
* Korrektur:  Temperatur delta zum Ziel sowohl über als auch unter setpoint (fabs)
* Korrektur:  HLT Standardregel INDIVIDUAL_PID

Version 1.0g

* Geändert:   Parameter AutoTune Intervall umbenanntn in PID Intervall (IDS und Nachguss) [2sek bis 5sek]
* Geändert:   Parameter PID Intervall in Tab PID-Manager verschoben
* Geändert:   das PID Intervall (SampleTime) legt die Taktung Auslesen Sensor und Leistung an Indution fest
* Anmerkung:  Reihenfolge: Sensorwert auslesen - PID Berechnung - berechnete Leistung an IDS senden
* Anmerkung:  ein sehr kleines Intervall (alle 2sek) führt zu sehr vielen Berechnungen wordurch der Brautomat träger reagiert.
* Anmerkung:  kleinere Intervalle (2sek) kann bei kleinen Maischevolumen (10-15l) vorteilhaft sein
* Korrektur:  Fehler HLT PID Anzeige behoben
* Korrektur:  HLT AutoTune Zieltemperatur readonly
* Korrektur:  Web Interface Parameterbeschreibungen
* Geändert:   Das Ein- und Ausblenden der Tabellen Nachguss, Sensoren und Aktoren wird nicht mehr automatisch gespeichert
* Geändert:   Das Ändern der Tuning Regel wird nicht mehr automatisch gespeichert
* Neu:        Überprüfung Wertebereich für Eingaben der Paramtertypen Leistung, Temperatur, Anzahl und Zeit eingefügt

Version 1.0f

* Update:     ESP8266 Arduino 3.1.1
* Geändert:   Refresh Sensoren, IDS und HLT auf 2000ms
* Geändert:   AutoTune timeout auf 20min
* Geändert:   Max Leistung als oberes Limit in die PID Berechnung integriert
* Neu:        Eigenschaft Max Leistung HLT eingefügt
* Korrektur:  Fehler HLT PID Berechnung behoben
* Korrektur:  WebUpdate Tools ist Teil von WebUpdate Firmware. Button WebUpdate Tools entfernt

Version 1.0e und früher

* Neu:        Neue Option für Toasts "Info": alle Nachrichten
* Neu:        Neue Option für Toasts "Fehler": nur Nachrichten bei Sensor oder WLAN Fehler
* Update:     ESP8266 core fix #8796 #8797
* Update:     VSCode 1.74.3
* Korrektur:  Umwandlung Sensor Adresse in Hex (SetResolution)
* Neu:        Parameter Maximale Leistung IDS kann nun während des Brauens verändert werden
* Neu:        Parameter Temperatur Kochen IDS kann nun während des Brauens verändert werden
* Neu:        Parameter Leistung Kochen IDS kann nun während des Brauens verändert werden
* Neu:        Toast Nachrichten bei Sensorfehler
* Neu:        Alarm Error bei Sensor Fehler
* Neu:        Alarm Error bei WLAN Fehler
* Korrektur:  Toast Nachrichten konnten nicht deaktiviert werden
* Korrektur:  Auswahl Tuning Regel IDS und Nachguss berechnet keine Werte für P, I, D
* Geändert:   Seitenwechsel Display auf 0x66 angepasst (Vorbereitung Update Bibliothek NextionX2)
* Update:     ESP8266 3.1.0: Fehler in ESPWebServer behoben (Webseite ganz oder teilweise nicht erreichbar)
* Update:     ESP8266 3.1.0: Fehler in ESPSoftSerial behoben (Anbindung Display)
* Update:     ESP8266 Arduino 3.1.0
* Update:     VSCode 1.74.2
* Update:     Nextion HMI Editor 1.65
