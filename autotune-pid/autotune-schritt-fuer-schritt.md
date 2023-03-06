# AutoTune Schritt für Schritt

Das praktische Vorgehen AutoTune schaut wie folgt aus:

![AutoTune](../docs/img/IDS\_AutoTune.jpg)

1.  Befülle Deinen Kessel mit einer typischen Menge Wasser

    a. Eine typische Menge entspricht dem Hauptguss + Schüttung

    Beispiel: 20l Hauptguss und 5kg Schüttung ergibt eine typische Menge von 25l

    b. Schalte das Rührwerk ein
2. Setze eine AutoTune Zieltemperatur. Die Zieltemperatur sollte 20°C oder mehr über der aktuellen Ist-Temperatur liegen.
3. Aktiviere „PID AutoTune“
4. Aktiviere „AutoTune debug“
5. Speichere diese Einstellung ab (IDS speichern)
6. Mit einem Klick auf den grünen Power Button wird "AutoTune IDS" gestartet.

![AutoTune2](../docs/img/IDS\_AutoTune\_start.jpg)

Der AutoTune Prozess dauert je nach Umgebung bis zu 90min. Der meiste Zeitbedarf entsteht während den Abkühlphasen. Je besser ein Braukessel wärmegedämmt ist, desto länger dauert der AutoTune Prozess. Der aktuelle Status ist in der Spalte „in progress 0/5“ sichtbar. Die erste Zahl ist der aktuelle Schritt und die zweite Zahl die Anzahl der AutoTune-Schritte. Treten Fehler auf, erscheint an dieser Stelle „in progress 6/5“ und höher. Der AutoTune Prozess prüft die gefundenen Messerte. Ist ein Messwert fehlerhaft, wird die Messung wiederholt. Es werden maximal 20 Wiederholungen durchgeführt.Das AutoTune Ergebnis wird in den Einstellung der GGM IDS (Zahnrad) im Tab PID-Manager dargestellt:

![AutoTune3](../docs/img/IDS\_AutoTune\_erg.jpg)

Das Ergebnis von AutoTune sind die Werte von "Ultimate gain Ku" und "Ultimate period Pu". Aus diesen zwei Parametern werden P, I und D berechnet. Zur Berechnung der PID-Werte stehen diverse Regeln zur Verfügung. Der Brautomat verwendet eine Tuning-Regel, die für das Brauen (eigentlich für das Erhitzen von Flüssigkeiten) optimiert ist und u.a. auch in CraftBeerPi PIDBoil eingestezt wird.

_Tipp: Nach dem AutoTune Prozess sollte die Konfiguration mittels Backup gesichert werden._

Wenn der AutoTune Prozess beendet ist und wurde "AutoTune debug" aktiviert, kann über den Explorer das Protokoll "autotune\_log.txt" eingesehen werden. Diese Datei sollte nach AutoTune kontrolliert werden. Entscheidend sind die letzten Zeilen in der Protokoll Datei:

`0min0sec: convergence criterion ok: 0.05/0.05`

`0min0sec: Peaks: 1: 61.250 2: 59.750 3: 61.500 4: 59.750`

`0min0sec: Time: 1: 3520743 2: 3385743 3: 2805697 4: 2705697`

`0min0sec: Ultimate gain Ku: xxx`

`0min0sec: Ultimate period Pu: xxx`

`0min0sec: k/min rate Mu: xxx`

`14:12:38 PID AutoTune finished`

1. "convergence criterion ok:" (alle Zahlen hinter diesem Text sind rein informativ)
2. Peaks: 1: (61.250) und 3: (61.500) müssen über der Zieltemperatur (60.0) sein
3. Peaks: 2: (59.750) und 4: (59.750) müssen unter der Zieltemperatur (60.0) sein

Wenn diese drei Bedingungen erfüllt sind, war der AutoTune Prozess erfolgreich.In der Datei "idsAutoTune.txt" bzw. "hltAutoTune.txt" wird das AutoTune Ergebnis im JSON Format abgespeichert. Beide Dateien sind rein informativ und werden für den Betrieb nicht benötigt. In diesen Dateien sind PID-Werte über verschiedene Berechnungsmethoden aufgeführt.

* IDS
* HLT
* INTEGRAL\_PID
* SOME\_OVERSHOOT\_PID
* NO\_OVERSHOOT\_PID
* ZIEGLER\_NICHOLS\_PID
* ZIEGLER\_NICHOLS\_PI
* TYREUS\_LUYBEN\_PID
* TYREUS\_LUYBEN\_PI
* CIANCONE\_MARLIN\_PID
* CIANCONE\_MARLIN\_PI

Die Werte sind lediglich eine Hilfe in Ausnahmefällen. Bspw. kann die Methode Integral\_PID für Wasserkocher ggfs. ein besseres Ergebnis liefern, als die als die voreingestellte Nachguss Methode HLT. Die jeweiligen PID Werte sind als INDIVIDUAL\_PID einzutragen.
