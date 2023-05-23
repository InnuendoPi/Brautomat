# Funktionen

Die folgende Beschreibung hat nicht das zugrunde liegende Rezept als Inhalt, sondern das Vorgehen beim Maischen mit dem Brautomat. Der Maischeplan hat eine Tabellenform. Diese Tabelle wird beim Maischen von oben nach unten abgearbeitet. In diesem Beispiel ist die Zeile "Einmaischen 50°C" der erste Maische-Schritt und "Nachisomerisierung" der letzte Maische-Schritt. Eine sehr wichtige Funktion im Maischeplan hat die Eigenschaft _autonext_.

Zur Orientierung wird zunächst der Aufbau der Tabellenzeilen beschrieben. Jede Zeile der Tabelle hat diese Spalten:

* Die Spalte "Rast" zeigt einen Namen für diesen Maische-Schritt
* Die Spalte "Temperatur" zeigt die Rast-Temperatur (auch Ziel- oder Soll-Temperatur genannt)
* Die Spalte "Dauer" ist die Rast-Dauer (Timer), wie lange der Brautomat die Rast-Temperatur halten soll
* Die Spalte "autonext" besagt, ob automatisch zum nächsten Schritt gwechselt wird, wenn die Rast-Dauer (Timer) erfüllt ist

Nach diesen vier Angaben zum Maische-Schritt hat jede Zeile Buttons zum Editieren mit den folgenden Funktionen: (von links nach rechts)

* verschiebe diese Zeile eine Position nach oben
* verschiebe diese Zeile eine Position nach unten
* editiere diese Zeile
* lösche diese Zeile
* speichere die Zeile in die Tabelle

Zusammen mit den Steuerelementen Power, Play, Pause, Forward und Backward ergibt sich eine einfache intuitiv zu bedienende Brausteuerung.\

Der zweite Schritt im Maischeplan mit dem Namen _Maltoserast 63°C_ hat als Rast-Temperatur 63°C und eine Rast-Dauer von 25 Minuten. Der Brautmoat steuert in diesem Schritt das Induktionskochfeld zunächst auf 63°C. Sobald diese 63°C erreicht sind, startet der Brautomat den Timer. Ein Rast-Timer ist eine Stoppuhr. Wenn diese Stoppuhr die Rast-Dauer von 25 Minuten erreicht hat, überprüft der Brautomat die Eigenschaft _autonext_. Wenn _autonext_ aktiviert ist, springt der Brautomat automatisch zum nächsten Schritt im Maischeplan. In diesem Bespiel zum Schritt _Zwischenrast_. Die Zwischenrast hat eine Rasttemperatur von 67°C. Automatisch erhöht der Brautomat die Leistung vom Induktionskochfeld, um die Rast-Temperatur zu erreichen. Der Masicheprozess verläuft bei aktiviertem autonext automatisch.

Die Eigenschaft _autonext_ im fünften Schritt _Abmaischen 78°C_ ist nicht aktiviert. Wenn der Brautomat auf ein deaktivertes autonext trifft, beendet der Brautomat die aktuelle Rast nach Ablauf der Rast-Dauer und setzt die Leistung vom Induktionskochfeld auf 0% (aus). In diesem Status wird der "Play Button" rot angezeigt. Zum Fortsetzen des Brauvorgangs muss auf den Play Button geklickt werden:

![Maischeplan](/docs/img/Maischeplan-autonext.jpg)

Als aktive Rast wird auf diesem Bild "Kochen" angezeigt. Die aktuelle Leistung wird mit 0% angezeigt und der Play Button ist rot. Dieser Status ist genau dann erreicht, wenn die Rast _Abmaischen 78°C_ beendet ist und der Brautomat auf das Fortsetzen durch eine Aktivität durch den Anwender wartet. Der Maischeprozess verläuft bei deaktiviertem autonext manuell.

Im Bild Maischeplan sind das Einmaischen und das Abmaischen mit deaktiviertem autonext dargestellt. Das Einmaischen hat eigentlich keine Rast-Dauer und ist beendet, wenn das Schrot im Hauptgusswasser ist. Die Rast-Dauer kann für das Einmaischen einfach auf 1 Minute, aber mit deaktiviertem autonext konfiguriert werden. Der Brautomat heizt dann auf Einmaischtemperatur, hält diese Temperatur für eine Minute, schaltet nach der Minute das Induktionskochfeld ab und geht in den Wartestatus "Play Button klicken".\
Das Abmaischen ist meist nach sehr kurzer Zeit (im Bild 1 Minute) beendet. Es folgt die Läuterruhe und das Läutern. Hier entscheidet der Brauer, wann das Aufheizen zum Kochen beginnen soll.

_Tipp: bei deaktiviertem autonext am Rastende wird die GGM IDS abgeschaltet. Mit dem Pause Button wird die Rast-Zeit angehalten (Timer). Die GGM IDS bleibt eingeschaltet und hält die aktuelle Temperatur._

Wenn die Funktion _autonext_ aktiviert ist, überprüft der Brautomat forlaufend die aktuelle Ist-Temperatur mit der Rast-Temperatur. Die Eigenschaft "Temperatur delta zum Ziel" gibt an, wie viel Grad Unterschied vorhanden sein darf, um den nächsten Maische-Schritt zu starten. In dem Beispiel Maltoserast 63°C und bei einem "Temperatur delta zum Ziel" von 0.3°C würde der Maischeschritt ab einer Ist-Temperatur von 62.7°C gestartet (bzw. ab 63.3°C).

_Tipp: mit "Temperatur delta zum Ziel" wird ein Temperaturbereich um die Rast-Temperatur angegeben, innerhalb dem der Timer einer Rast gestartet wird._

Eine Sonderfunktion hat die Rast-Temperatur 0°C bei aktivertem autonext: wenn die Rast-Temperatur auf 0°C gesetzt und autonext aktiviert ist, wird der nachfolgende Maischeschritt ohne Temperaturüberprüfung automatisch gestartet. Diese Sonderfunktion kann bspw. nach dem Kochen der Würze nützlich sein, wenn einer Timer für die Nachisomerisierung gestartet und die GGM IDS ausgeschaltet werden soll.

Durch die Tabellenform ist das Grundprinzip vom Brautomat die aufsteigende Infusion. Das schließt Varianten wie bspw. das Earlsche Kochmaischverfahren ein. Mit Hilfe der Eigenschaft "autonext" können auch andere Brauverfahren umgesetzt werden. Es gilt aber zu beachten, dass der Brautomat bei anderen Brauverfahren nur mit "halber Automatik" unterstützen kann. Ein auslösender Trigger für eine Aktion wie bspw. das Ziehen von Teilmaischen, muss durch den Anwender manuell erfolgen. Eine Rast mit einer Minute Dauer und deaktiviertem autonext kann ein Auslöser sein. Hat ein Schritt im Maischeplan die Eigenschaft "autonext" deaktivert und ist eine Aktion durch den Anwender erfolgt, dann kann mittels dem Play Button der nächste Schritt gestartet werden.

_Tipp: Hopfengaben - Im Bild Maischeplan ist das Würzekochen unterteilt in "Kochen", "Kochen Hopfengabe 1" und "Kochen Hopfengabe 2". Die Unterteilung kann passend zur Anzahl der Hopfengaben vorgenommen werden. Wenn ein Buzzer angeschlossen ist, ertönt mit jedem Schritt ein Signalton._
