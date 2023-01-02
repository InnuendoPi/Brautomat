# Brautomat

Der Brautomat ist eine Brausteuerung für die Induktionskochfelder GGM IDS1 und IDS2 mit einem ESP8266 Wemos D1 mini. Der Brautomat wird im Sudhaus von Hobbybrauern eingesetzt und bietet eine intuitiv einfach zu bedienende Steuerung. Beim Maischen werden Rast-Temperaturen automatisiert angefahren und die Rastzeiten eingehalten. Ebenso unterstützt der Brautomat den Hobbybrauer beim Kochen der Würze und bei den Hopfengaben.

Die Hauptfunktionen vom Brautomat sind:

* Steuerung der Induktionskochfelder GGM IDS1 und IDS2 über einen PID-Controller
* PID AutoTune zur Ermittlung der benötigten Einstellungen
* bis zu 5 Temperatursensoren werden unterstützt
* ein Maischeplan mit bis zu 15 Teilschritten
* eine Temperatur-Steuerung für einem Nachguss Kessel (HLT)
* Steuerung von Aktoren, wie bspw. Rührwerk, Pumpen, etc.
* Temperaturverlauf im Sudhaus als Grafik (line chart)
* Maischeplan Import aus Maische Malz und mehr
* Maischeplan Import aus dem kleinen Brauhelfer2
* Maischeplan Export zur Archivierung

## Installation

Die Installation der Firmware wird über das mitgeliferte Script durchgeführt. Hierzu wird das Archiv Firmware.ZIP in einem beliebigen ordner entpackt. Ein Doppelklick auf das Script Flashen.cmd startet die Installation.

Das Script ist voreingestellt auf den seriellen Anschluss COM3. Sollte der Wemos D1 Mini nicht mit COM3 verbunden sein, muss im Script Flashen.cmd an zwei Stellen "COM3" durch den korrekten COM Port ersetzt werden.

## Updates

Updates können im Brautomat bequem über das Menü "Update" eingespielt werden. Eine neue Firmware kann über "WebUpdate" oder "Datei Update" eingespielt werden.
Die Firmware bietet ein Web Update. Über das Web Interface kann eine neue Version eingespielt werden. Ein Kabel oder das Script aus der Installation ist nicht erforderlich.
Eine zweite Möglichkeit Updates einzuspielen bietet die Möglichkeit "Datei Update". Über diese Möglichkeit muss für ein Update die Firmware Datei (.bin) ausgewählt werden.

## Einrichtung

Der Brautomat benötigt als Mindestausstattung einen Temperatursensor vom Typ Dallas DS18B20 und ein Induktionskochfeld GGM IDS. Mit dieser Mindestausstattung wird nun eine Grundkonfiguration erstellt. Mit dieser sehr detaillierten Schritt-für-Schritt Anleitung gelingt auch dem Anfänger der Start in die Brausteuerung mit dem Brautomat. Es werden in der Grundeinrichtung nur die benötigten Einstellungen gezeigt. Alle optionalen Einstellungen werden später erläutert.

1. Einen Temperatursensor einrichten
Im Abschnitt Sensoren wird mit einem Klick auf das Plus Zeichen ein neuer Sensor angelegt

![Sensoren](img/Sensor_einrichten.jpg)

Sensoren vom Typ Dallas DS18B20 haben eine eindeutige Adresse. Über diese Adresse unterscheidet die Firmware intern bis zu 5 Sensoren. Die Adresse kann aus der Auswahlliste ausgewählt, aber nicht verändert werden. Als zweite Eigenschaft besitzt ein Sensor einen Namen. Über den Namen kann der Benutzer die Sensoren unterscheiden. Es empfiehlt sich, einen sprrechenden Namen zu verwenden. In dieser Grundkonfiguration hat der Sensor den Namen "Sensor IDS2.

![Sensoren](img/Sensor_einstellungen.jpg)

Die Eigenschaften Offset 1 und Offset 2 werden später erläutert. Für die Grundkonfiguration belassen wir beide Werte auf 0.00. Mit einem Klick auf "Sensor speichern" wird der Sensor angelegt und im Dashboard im Abschnitt Sensoren angezeigt:

![Sensoren](img/Sensor_dashboard.jpg)

2. Das Induktionskochfeld GGM IDS einrichten
Im ersten Abschnitt "Maischeplan" wird das Induktionskochfeld über das Zahnrad angelegt

![IDS](img/IDS_einrichten.jpg)

Zunächst muss das Induktionskochfeld konfiguriert werden. Die erste Eigenschaft ist der IDS Typ. Es stehen IDS1 und IDS2 zur Auswahl. Es folgen drei Parameter zur Steuerung:

* PIN weiß [Relais] - Standardeinstellung: D5
* PIN gelb [Command] - Standardeinstellung: D6
* PIN blau [Interrupt] - Standardeinstellung: D7

Als nächste Eigenschaft muss der Sensor angegeben werden, welcher mit dem Kessel auf der GGM IDS verbunden ist. In dieser Grundeinrichtung ist nur ein Sensor vorhanden und wird ausgewählt. Die drei folgenden Werte Temperatur delta und Threshold werden später erläutert und werden für die erste Grundeinrichtung nicht benötigt.

![IDS](img/IDS_konfigurieren.jpg)

Nach der Grundkonfigruation muss der PID-Controller im Tab PID Manager eingerichtet werden. Der PID-Controller ist ein sehr wichtiges Element. Je besser der PID-Controller eingestellt ist, desto genauer wird die Rasttemperatur über die Rastzeit gehalten. Mit dem Thema PID beschäftigt sioch diese Anleitung später genauer. Für eine erste Grundeinrichtung werden folgende Werte eingetragen:

![IDS](img/IDS_pid-einrichten.jpg)

Wenn die Werte für "Ultimate gain Ku" und "Ultimate period Pu" eingetragen sind, ermittelt die Auswahl "PID tuning Regel" die drei werte PID Kp Ki und Kd selbstständig. Die Parameter im tab "PID Manager" klingen kompliziert und verwirren auf den ersten Blick. Bitte einfach so hinnehmen und alle Werte eintippen. Eine Erläuterung für Interessierte folgt.
Jetzt wird die Konfugraiton der Induktionskochplatte gespeichert.

An dieser Stelle ist die Grundkonfiguration bereits abgeschlossen. Mit einem Sensor und einer GGM IDS kann nun gebraut werden. Zum Brauen ist ein Maischeplan erforderlich.

## Der Maischeplan

![Maischeplan](img/Maischeplan.jpg)

Der Brautomat hat einen Standard Maischeplan. Die folgende Beschreibung hat nicht das zugrunde liegende Rezept als Inhalt, sondern das Vorgehen beim Maischen mit dem Brautomat. Der Maischeplan hat eine Tabellenform. Diese Tabelle wird baim Maischen von oben nach unten abgearbeitet. Die Zeile "Einmaischen 50°" ist der erste Maischeschritt und "Kochen Hopfengabe 2" der letzte Maischeschritt. Jede Zeile hat diese Spalten:

* Rast ist ein Name für diesen Maischeschritt
* Temeperatur ist die Rasttemperatur
* Dauer ist die Zeit, wie lange der Brautomat die Rasttemperatur hält
* autonext besagt, ob automatisch zum nächsten Schritt gwechselt wird, wenn die Rastdauer erreicht ist

Nach diesen vier Angaben zur Rast folgen Icons mit den folgenden Funktionen

* verschiebe diese Zeile eine Position nach oben
* verschiebe diese Zeile eine Position nach unten
* editiere diese Zeile
* lösche diese Zeile
* speichere die Zeile in die Tabelle

Die Funktion von "autonext" soll an einem Beispiel erläutert werden: der zweite Schritt im Maischeplan mit dem Namen "Maltoserast 63°C  hat als Rasttemperatur 63°C und eine Rastdauer von 25 Minuten. Der Brautmoat steuert in diesem Schritt das Induktionskochfeld zunächst auf 63°C mit maximaler Leistung. Kurz vor den 63°C wird die Leistung zurückgenommen. Es sollen nicht 64°C oder mehr erreicht werden, sondern 63°C. Sobald diese 63°C erreicht sind, startet der Brautomat den Timer. Ein Timer ist eine Stoppuhr. Wenn diese Stoppuhr die Rastdauer von 25 Minuten erreicht hat, überprüft der Brautomat die Eigenschaft "autonext". Wenn das Häkchen gesetzt ist, springt der Brautomat zum nächsten Schritt im Masicheplan. In diesem Bespiel zum Schritt "Zwischenrast". Die Zwischenrast hat eine Rasttemperatur von 67°C. Automatisch erhöht der Brautomat die Leistung vom Induktionskochfeld, um die Rasttemperatur zu erreichen.

Und was passiert, wenn bei "autonext" kein Häkchen gesetzt ist? Die Eigenschaft "autonext im fünften Schritt "Abmaischen 78°C" ist nicht aktiviert. Wenn der Brautomat auf ein deaktivertes autonext trifft, beendet er die aktuelle Rast und setzt die Leistung vom Induktionskochefeld auf 0%. In diesem Status wird der "Play Button" rot angezeigt. Zum Fortsetzen des Brauvorgangs muss auf den Play Button geklickt werden:

![Maischeplan](img/Maischeplan_pause.jpg)

Als aktive Rast wird auf diesem Bild "Kochen" angezeigt. Die aktuelle Leistung wird mit 0% angezeigt und der Play Button ist rot. Dieser Status ist genau dann erreicht, wenn der Schritt "Abmaischen 78°C" erledigt ist und der Brautomat auf das Fortsetzen durch eine Aktivität durch den Brauer wartet.
