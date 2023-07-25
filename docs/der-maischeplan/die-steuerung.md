# Die Steuerung

Direkt unterhalb vom Maischeplan befindet sich die Steuerung. Mithilfe der 5 Buttons Power, Play, Pause Backward und Forward wird der Maischeprozess gesteuert.

![Maischeplan](/docs/img/Buttons.jpg)

## Der Power Button

Über den Power Button wird der Maischeprozess ein- bzw. ausgeschaltet. Sobald AutoTune in den Einstellungen der GGM IDS oder im Nachguss aktiviert ist, wird der AutoTune Prozess über den Power Button gestartet bzw. gestoppt.

_Tipp: Wenn der Maischeprozess gestartet ist, sind die Funktionen zum editieren des Maischeplans deaktiviert. Wird der Maischeprozess pausiert, kann der Maischeplan während des Maischeprozesses verändert werden._

## Der Play Button

Der Play Button hat im Maischeprozess zwei Funktionen:

1. Die erste Funktion lautet "starte den Rast-Timer für die aktuelle Rast". Der Play Button startet unabhängig von der IST-Temperatur den Rast-Timer.\
Beispiel: wenn im Schritt Kochen die Würze bereits wallend kocht, die Ist-Temperatur mit 98,5°C aber unter der Rast-Temperatur mit 100°C liegt und somit der Rast-Timer nicht startet.\
Der Play Button wird rot angezeigt.

2. Die zweite Funktion vom Play Button hängt mit der Eigenschaft _autonext_ zusammen: setze den Maischeprozess mit der nächsten Rast fort. Die Funktionen "mit der nächsten Rast den Maischeprozess fortsetzen" wurde mit der Beschreibung _autonext_ im Maischeplan erläutert.\
Ein Anwendungsfall ist das Einmaischen. Wird der Schritt Einmaischen mit deaktiviertem autonext konfiguriert, verbleibt der Maischeprozess im einem Wartestatus bis der Play Button angeklickt wird. Der Play Button wird rot angezeigt.

## Der Pause Button

Mit dem Pause Button wird der Rast-Timer im Maischeprozess angehalten. Der Pause Button wird dann rot angezeigt. Der Maischeprozess wird mit einem Klick auf den Pause Button fortgesetzt. Wichtig: Während einer Pause wird die aktuelle Ist-Temperatur gehalten, d. h. das Induktionskochfeld bleibt eingeschaltet. Hier unterscheiden sich "Pause" und "autonext": bei deaktiviertem autonext wird die GGM IDS ausgeschaltet.

## Der Backward Button

Mit dem Backward Button wird zum vorherigem Schritt im Maischeplan gesprungen. War der Maischeprozess pausiert, wird der Rast-Timer der aktuellen Rast zurückgesetzt und neu gestartet.

## Der Forward Button

Mit dem Forward Button wird zum nächsten Schritt im Maischeplan gesprungen oder falls es der letzte Schritt im Plan war der Maischeprozess beendet.

## Der Maischeplan anzeigen Button

Der Masicheplan anzeigen Button klappt die Tabelle Maischeplan ein und aus.

![Maischeplan](/docs/img/Maischeplan-anzeigen.jpg)

Der Masicheplan anzeigen Button bleibt nach Braustart sichtbar. Alle anderen Buttom zum Verändern des Maischeplans werden bei Braustart ausgeblendet.
