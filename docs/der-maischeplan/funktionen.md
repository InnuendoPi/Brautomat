# Funktionen

Die folgende Beschreibung hat nicht das zugrunde liegende Rezept als Inhalt, sondern das Vorgehen beim Maischen mit dem Brautomat. Der Maischeplan hat eine Tabellenform. Diese Tabelle wird beim Maischen von oben nach unten abgearbeitet. In diesem Beispiel ist die Zeile "Einmaischen 50°C" der erste Maische-Schritt und "Nachisomerisierung" der letzte Maische-Schritt. Eine sehr wichtige Funktion im Maischeplan hat die Eigenschaft _autonext_.

![Maischeplan](/docs/img/Maischeplan.jpg)

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

Die Symbole zum Editieren der Maischeschritte werden ausgeblendet, sobald der Brauprozess gestartet wird.\
Zusammen mit den Steuerelementen Power, Play, Pause, Forward und Backward ergibt sich eine einfache intuitiv zu bedienende Brausteuerung.

![Maischeplan](/docs/img/Maischeplan-autonext.jpg)

Der zweite Schritt im Maischeplan mit dem Namen _Maltoserast 63°C_ hat als Rast-Temperatur 63°C und eine Rast-Dauer von 25 Minuten. Der Brautmoat steuert in diesem Schritt das Induktionskochfeld zunächst auf 63°C. Sobald diese 63°C erreicht sind, startet der Brautomat den Timer. Ein Rast-Timer ist eine Stoppuhr. Wenn diese Stoppuhr die Rast-Dauer von 25 Minuten erreicht hat, überprüft der Brautomat die Eigenschaft _autonext_. Wenn _autonext_ aktiviert ist, springt der Brautomat automatisch zum nächsten Schritt im Maischeplan. In diesem Bespiel zum Schritt _Zwischenrast_. Die Zwischenrast hat eine Rasttemperatur von 67°C. Automatisch erhöht der Brautomat die Leistung vom Induktionskochfeld, um die Rast-Temperatur zu erreichen. Der Masicheprozess verläuft bei aktiviertem autonext automatisch.

![Maischeplan](/docs/img/Maischeplan-autonext2.jpg)

Die Eigenschaft _autonext_ im siebten Schritt _Abmaischen 78°C_ ist nicht aktiviert. Wenn der Brautomat auf ein deaktivertes autonext trifft, beendet der Brautomat die aktuelle Rast nach Ablauf der Rast-Dauer und setzt die Leistung vom Induktionskochfeld auf 0% (aus). In diesem Status wird der "Play Button" rot angezeigt. Zum Fortsetzen des Brauvorgangs muss auf den Play Button geklickt werden.

Als aktive Rast wird auf diesem Bild "Kochen" angezeigt. Die aktuelle Leistung wird mit 0% angezeigt und der Play Button ist rot. Dieser Status ist genau dann erreicht, wenn die Rast _Abmaischen 78°C_ beendet ist und der Brautomat auf das Fortsetzen durch eine Aktivität durch den Anwender wartet. Der Maischeprozess verläuft bei deaktiviertem autonext manuell.

In dem Bild ist ebenfalls die Toast Nachricht "Klicke Play Button" dargestellt. Toasts können optional aktiviert werden und erscheinen mit Ton, sobald ein Schritt beendet oder eine manuelle Aktivität erforderlich ist.

Im ersten Bild Maischeplan sind das Einmaischen und das Abmaischen mit deaktiviertem autonext dargestellt. Das Einmaischen hat eigentlich keine Rast-Dauer und ist beendet, wenn das Schrot im Hauptgusswasser ist. Der Brauprozess wird dann mit Klick auf den roten Play Button fortgesetzt.
Das Abmaischen ist meist nach sehr kurzer Zeit (im Bild 1 Minute) beendet. Es folgt die Läuterruhe und das Läutern. Auch hier wird der Brauprozess erst forgesetzt, wenn der Play Button geklickt wird.

_Tipp: bei deaktiviertem autonext am Rastende wird die GGM IDS abgeschaltet. Mit dem Pause Button wird die Rast-Zeit angehalten (Timer). Die GGM IDS bleibt eingeschaltet und hält die aktuelle Temperatur._

Wenn die Funktion _autonext_ aktiviert ist, überprüft der Brautomat forlaufend die aktuelle Ist-Temperatur mit der Rast-Temperatur. Die Eigenschaft "Temperatur delta zum Ziel" gibt an, wie viel Grad Unterschied vorhanden sein darf, um den nächsten Maische-Schritt zu starten. In dem Beispiel Maltoserast 63°C und bei einem "Temperatur delta zum Ziel" von 0.3°C würde der Maischeschritt ab einer Ist-Temperatur von 62.7°C gestartet (bzw. ab 63.3°C).

_Tipp: mit "Temperatur delta zum Ziel" wird ein Temperaturbereich um die Rast-Temperatur angegeben, innerhalb dem der Timer einer Rast gestartet wird._

Eine Sonderfunktion hat die Rast-Temperatur 0°C bei aktivertem autonext: wenn die Rast-Temperatur auf 0°C gesetzt und autonext aktiviert ist, wird der nachfolgende Maischeschritt ohne Temperaturüberprüfung automatisch gestartet. Diese Sonderfunktion kann bspw. nach dem Kochen der Würze nützlich sein, wenn einer Timer für die Nachisomerisierung gestartet und die GGM IDS ausgeschaltet werden soll.

Durch die Tabellenform ist das Grundprinzip vom Brautomat die aufsteigende Infusion. Das schließt Varianten wie bspw. das Earlsche Kochmaischverfahren ein. Mit Hilfe der Eigenschaft "autonext" können auch andere Brauverfahren umgesetzt werden. Es gilt aber zu beachten, dass der Brautomat bei anderen Brauverfahren nur mit "halber Automatik" unterstützen kann. Ein auslösender Trigger für eine Aktion wie bspw. das Ziehen von Teilmaischen, muss durch den Anwender manuell erfolgen. Eine Rast mit einer Minute Dauer und deaktiviertem autonext kann ein Auslöser sein.

_Tipp: Hopfengaben und Zusätze - Im Bild ist ein Maischeplan dargestellt, der aus dem Programm kleinerBrauhelfer2 importiert wurde. Zusätze- und Hopfennamen, Mengen, Alphasäure und Zeitpunkt der Gaben werden aus dem kbh2 Export übernommen. Auch bei Zusätze und Hopfengaben erscheinen Toasts mit Klang. Wenn ein Piezo Buzzer aktiviert wurde, ertönt mit jedem Schritt ein Signalton._

_Tipp: Zubrühen - Im Bild Maischeplan ist ein Schritt Zubrühen dargestellt. Auch dieser Schritt ist inklusive der Angaben zur Menge und Temperatur aus dem kleinenBrauhelfer2 importiert worden._
