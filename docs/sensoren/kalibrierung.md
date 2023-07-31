# Kalibrierung

Sensoren vom Typ Dallas DS18B20 haben teilweise Abweichungen von der tatsächlichen Temperatur. In den techn. Spezifikationen der Hersteller wird oft eine Genauigkeit von +-0.5°C im Bereich von -10°C bis 85°C angegeben. Ferner werden die Sensoren als kalibriert bezeichnet.

Mithilfe einer 2-Punkte Kalibrierung können Abweichungen korrigiert werden. Die Kalibrierung vom Brautomat ist eine lineare Korrektur. Zur Kalibrierung der Sensoren wird ein geeichtes Thermometer benötigt. Der Braukessel wird mit einer typischen Menge Wasser befüllt und auf 40°C erhitzt. Der Unterschied zwischen dem Sensorwert und dem geeichten Thermometer wird im Parameter "Offset 1 \[40°C]" eingetragen. Dieser Vorgang wird bei 78°C wiederholt und der Unterschied wird im Parameter "Offset 2 \[78°C]" eingetragen. Alle Sensormesswerten werden künfig anhand dieser Korrektur ausgegeben.

## Vorgehensweise Kalibrierung ohne Referenz-Thermometer

Steht ein Referenz-Thermometer nicht zur Verfügung, kann eine Kalibrierung mit einem Eisbad und einem Kochvorgang durchgeführt werden.\
Es wird für den unteren Messbereich ein Gefäss mit 50% Eiswürfel und 50% kaltem Wasser benötigt. Ein Eisbad hat eine (fast exakte) Temperatur von 0.0°C. Das Eiswasser muss kontinuierlich gerührt werden, vorzugsweise mit einem Magnetrührer. Im Eisbad wird die Kalibrierung auf 0°C gestartet.

Der zweite Punkt für eine Kalibrierung kann über die Höhe über Normalhöhennull und dem damit verbundenen Siedepunkt ermittelt werden. Bei 0m über NHN bzw. bei einem atmosphärischen Druck von 1.013bar beträgt die Siedepunkttemperatur 100.l0°C. Mit steigender Höhe nimmt der atmosphärische Druck ab und somit sinkt die Siedepunkttemperatur. Zunächst muss die örtliche NHN bspw. über google earth ermittelt werden. Der Siedepunkt sinkt je Meter über NHN um 0.003354°C. Auf der Websiete von [rechneronline](https://rechneronline.de/barometer/siedepunkt.php) wird der Siedepunkt über die Höhe über NHN ausgerechnet. Viele Smartphones bieten die Information Höhe in der Kompass- oder Navi-App ebenfalls. Die Höhe über NHN sollte mit einer Genauigkeit von etwa +-20m ermittelt werden. Das entspricht einer Verändeurng der Siedepunkttemperatur von 0.06708°C und damit weit außerhalb der Genauigkeit der Steuerung Brautomat. Die zweite Punkt Kalibrierung wird mit einem MaischeSud Kessel, einem Rührwerk und dem zuvor ermittelten lokalen Siedepunkt durchgeführt. Die Zieltemperatur ist dementsprechen die Siedepunkttemperatur. Es ist darauf zu achten, dass die Siedepunkttemperatur erreicht ist und über mindestens eine Minute gehalten wird, bevor die Kalibrierung für den oberen Wertebereich gestartet wird. Außerdem ist es sehr wichtig, dass das Induktionskochfeld mit konstanter Leistung eingeschaltet bleibt.

Eine Kalibrierung besteht aus 60 Messproben. Der Zeitbedarf beträgt fast genau 60 Sekunden für eine Kalibrierung. Als Ergebnis wird das geometrische Mittel der 60 Messproben genommen. Offset #1 (auch unterer Wertebereich) ist dementsprechend die Differenz von 0.0°C (Eisbad) gegenüber dem Mittelwert aus der Kalibierung Punkt 1. Offset #2 (auch oberer Wertebereich) ist die Differenz zwischen Siedepunkt und dem Mittelwert aus der Kalibrierung 2.

In vielen Fällen reicht eine 1-Punkt-Kalibrierung im Eisbad aus, weil die Abweichung der Sensoren DS18B20 meistens kontant verläuft.

## Vorgehensweise Kalibrierung mit Fieber-Thermometer

Ein Fieber-Thermometer ist ein gut geeignetes Refernz-Thermometer. Der oberere Weiterebereich ist mit einem Fieberthemometer bei ca. 40°C eingeschränkt. Die Durchführung der Kalibrierung entspricht der Vorgehensweise Eisbad und Siedepunkttemperatur. Einziger Unterschied: wenn bspw. 40°C als zweiter Kalibrierungspunkt ausgewählt wurde, dann muss die Induktionskochplatte ausgeschaltet werden, sobald die Zieltemperatur erreicht wurde und über ca. 60 Sekunden konstant blieb (keine Schwanken). Erst dann soll die Kalibrierung, also das erfassen von 60 Messproben gestartet werden.
