# Troubleshooting

Tipps & Tricks ... to be continued ...

## WLAN

Die WLAN Reichweite vom Arduino ESP8266 ist begrenzt. Unter System -> Reset wird die aktuelle WLAN Signalstärke angezeigt. Je näher der Wert an null liegt, desto stärker ist das Signal. Werte von -50dBm bis -75dBm sind sehr gut. Ein Wert kleiner als -80dBm ist schlecht und führt zu Problemen. In Brauküchen mit schwacher WLAN Signalstärke kann das PID Intervall bspw. auf 7000ms erhöht werden, um die Datenmenge zu verkleinern. Auch sollte beim schwacher Signalstärke nur ein aktiver Browser genutzt werden (siehe hierzu Server Sent Events weiter unten). Ein passender Standort für den Brautomat im WLAN (oder ein zus. Repeater) ist wichtig. Eine gute Signalstärke hat nicht zwangsläufig, aber in den meisten Fällen eine höhere und stabilere Datenübertragungsrate zur Folge.

Das Web Interface vom Brautomat baut auf dem bootstrap Framework 4.6 mit Javascript auf. Die benötigten Dateien (css, js und fonts) liegen im Flash Speicher vom Brautomat. Das hat einen Vor- und einen Nachteil. Der Vorteil ist, dass keine Internetverbindung für das Laden der erforderlichen Dateien beim Brauen benötigt wird. Der Nachteil ist, dass im lokalen WLAN der Brautomat jedem verbundenen Browser die Framework Dateien einmalig bei Verbindungsaufbau komprimiert bereitstellen und senden muss. Wird eine Datei bspw. wegen schwacher WLAN Signalstärke nicht korrekt und nur sehr langsam übermittelt, funktioniert das Web Interface nicht korrekt. Das WebInterface baut sich dem Fall nicht korrekt (es schaut dann wie eine Textseite aus) oder unvollständig auf (die Tabellen bleiben leer). In den meisten Fällen reicht ein Reload der Webseite aus (Strg-Shift-R). Im aktuellen Arduino ESPWebServer 3.2.1 repository auf github gibt es hierzu Hinweise, aber noch keine Lösung (bspw. http header string allocation #8873, siehe debug Informationen weiter unten).

Nach einem Firmware Update sollte der Brautomat immer ausgeschaltet und der Browser Cache gelöscht werden.

## Browser

Getestet wird der Brautomat auf Win11 mit MS Edge und Firefox in der jeweils aktuellen Version, sowie auf iOS Geräten mit MS Edge und Safari. Bevorzugt verwendet wird während der Entwicklung MS Edge. Unabhängig vom Browser muss die automatische Audiowiedergabe für die Toasts Nachrichten (Audio) für die Adresse des Brautomat aktiviert werden. Die Adresse vom Brautomat sollte ebenfalls in blockierenden Browser Plugins in den Ausnahmen aufgenommen werden.

## Server Sent Events & Energiesparpläne und automatisches Sperren von Clients

Der Brautomat sendet Daten über Server Sent Events an verbundene und aktive Browser. Bis zu 8 Geräte können sich zeitgleich mit dem Brautomat verbinden. Energiesparpläne oder automatisches Sperren können eine Verbindung unterbrechen. Der Brauprozess wird bei einem Verbindungsabbruch nicht angehalten oder abgebrochen! Der Brautomat arbeitet ganz normal weiter. Nicht verbundene Browser erhalten lediglich keine neuen Daten. Unter Daten sind Temperaturen, aktueller Maischeschritt, aktuelle Leistungen, Charts etc. zu verstehen. Eine Server Sent Events Verbindung zum Brautomat ist der "Datenkanal", durch den die Dten zum Browser gesendet werden. Wird die Verbidnung zum Brautomat unterbrochen, wird der Datenkanal beendet und muss (durch ein Reload der Webseite) neu aufgebaut werden. Ein verbundener und aktiver Browser erkennt, wenn sein Datenkanal beendet ist und meldet sich am Brautomat nach kurzer Zeit automatisch neu an.\
Die Toast Nachricht "Verbindung zum Brautomat verloren (SSE)" kann irritieren und zu hektischen Handlungen verführen. Die Meldung "Verbindung zum Brautomat verloren" ist kein Fehler oder ein Ausfall der Steuerung. Im Gegenteil: während einer ausgedehnten Kombirast kann der Browser in der Brauküche geschlossen werden (die Verbindung geht "verloren"), während dessen ein mitgeführtes Tablet den aktuellen Stand korrekt anzeigt. Anmeldungen am Brautomat haben keine Reihenfolge oder Prioritäten. Es hat keine Auswirkung, ob der Webbrowser vom PC oder das Tablet zuerst oder zuletzt verbunden wird. Der Brauprozess kann auf Gerät A gestartet, auf Gerät B pausiert, auf Gerät C beobachtet und auf Gerät D beendet werden. Sind alle vier Geräte aktiv und verbunden, zeigen alle Browser (nahezu) zeitgleich identische Daten an, weil jedes dieser vier Geräte ein einen eigenen Datenkanal hat.

## Rezeptimport

Der Rezeptimport kann aufgrund des begrenzten Speichers keine Rezepte mit PDF und Bildanhängen importieren. Im kleinenBrauhelfer kann das Format Brautomat gewählt werden. Bei MaischeMalzundMehr Rezepten ist der Import in kbh2 eine einfache und gute Lösung.

## AutoTune

Beim AutoTune Prozess sollte der Fokus nicht auf Perfektion i. S. v. 0.1°C liegen. Die Abweichung der Sensoren ist meist größer. Der Parameter AutoTune noiseband ist mit einem Wert von 0.3 ausreichend nah an der Zieltemperatur, um die Zieltemperatur sehr gut zu treffen und über die Rastdauer zu halten.\
Sehr gut isolierte Maische- Sudkessel benötigen einen größere AutoTune Datenreihe. In der Datenreihe werden Messwerte in zeitlicher Abfolge festgehalten. Am Anfang steht der aktuelle Messwert und ganz am Ende der Reihe steht der älteste Messwert. Der Wert AutoTune Datenreihe besagt, "auf wie viele Werte vor der aktuellen Messung schaut der Brautomat (in die Vergangenheit) zurück, um eine Temperaturänderung von mindestens AutoTune noiseband (0.3) zu erkennen". Für einen gut isolierter Kessel sollte die Datenreihe mit 75 Messpunkten befüllt werden. Bei einem nicht isoliertem Kessel reicht eine Datenreihe von 50 Messpunkten aus. Diese zwei Parameter müssen je nach Umgebung angepasst werden. Die Standardvorgaben sollten in den allermeisten Fällen sehr gute Werte ermitteln.\

## Sensoren und Kalibrierung

Sensoren vom Typ Dallas DS18B20 werden auf sehr vielen Plattformen zu sehr unterschiedlichen Preisen angeboten. Die Sensorkalibrierung hilft Abweichungen zu minimieren. In jedem Fall sollte der Sensor der IDS kalibriert werden, weil Abweichungen von mehreren Grad Celsius (je nach Herkunft) möglich sind.\
Wenn ein Sensor regelmäßig im Web Interface mit Sensor Error (Toasts) gemeldet wird, sollte zunächst ein anderer Anschluss für den Sensor ausprobiert werden. Die drei Anschlüsse auf der Platine für die Sensoren sind gleichwertig und haben keine vorgegebene Reihenfolge. Bei Sensorproblemen sind die Lötpunkte der 3er-Schraubklemmblöcke und der Widerstand 4.7kOhm (auf der Platine unter dem ESP8266) zu prüfen.

## Debug Informationen

successful HTTP response:

```bash
file: /brautomat.min.css mimeType: text/css size: 171474 sent: 171474 duration: 1.05s
file: /brautomat.min.js mimeType: application/javascript size: 421227 sent: 421227 duration: 2.62s
```

failed http response:

```bash
file: /brautomat.min.css mimeType: text/css size: 171474 sent: 10890 err: sent less data than expected
file: /brautomat.min.js mimeType: application/javascript size: 421227 sent: 21347 err: sent less data than expected
```
