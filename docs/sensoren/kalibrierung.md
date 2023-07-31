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

## Logfile Sensorkalibrierung

Bei jeder Kalibrierung wird ein Logfile geschrieben. Ein Beispiel

```text
13:22:37 Sensor Kalibrierung gestartet
*** Sensor Name: Sensor IDS2
*** Modell: DS18B20
*** Adresse: 2827c59d0d0000b1
*** Resolution: 12bit
*** Timeout: 750ms
-----------------------------------------
ID	Soll		Ist			Diff		Offset
#01	24.6000		24.0000		-0.6000		0.6000
#02	24.6000		24.0000		-0.6000		0.6000
#03	24.6000		24.0000		-0.6000		0.6000
#04	24.6000		24.0000		-0.6000		0.6000
#05	24.6000		24.0000		-0.6000		0.6000
#06	24.6000		24.0000		-0.6000		0.6000
#07	24.6000		23.9375		-0.6625		0.6089
#08	24.6000		24.0000		-0.6000		0.6078
#09	24.6000		23.9375		-0.6625		0.6139
#10	24.6000		24.0000		-0.6000		0.6125
#11	24.6000		24.0000		-0.6000		0.6114
#12	24.6000		23.9375		-0.6625		0.6156
#13	24.6000		23.9375		-0.6625		0.6192
#14	24.6000		23.9375		-0.6625		0.6223
#15	24.6000		24.0000		-0.6000		0.6208
#16	24.6000		23.9375		-0.6625		0.6234
#17	24.6000		23.9375		-0.6625		0.6257
#18	24.6000		23.9375		-0.6625		0.6278
#19	24.6000		23.9375		-0.6625		0.6296
#20	24.6000		24.1250		-0.4750		0.6219
#21	24.6000		24.6875		0.0875		0.5881
#22	24.6000		25.3125		0.7125		0.5290
#23	24.6000		25.7500		1.1500		0.4560
#24	24.6000		26.0625		1.4625		0.3760
#25	24.6000		26.1875		1.5875		0.2975
#26	24.6000		26.3125		1.7125		0.2202
#27	24.6000		26.3750		1.7750		0.1463
#28	24.6000		26.4375		1.8375		0.0754
#29	24.6000		26.4375		1.8375		0.0095
#30	24.6000		26.4375		1.8375		-0.0521
#31	24.6000		26.3750		1.7750		-0.1077
#32	24.6000		26.3125		1.7125		-0.1578
#33	24.6000		26.3125		1.7125		-0.2049
#34	24.6000		26.2500		1.6500		-0.2474
#35	24.6000		26.2500		1.6500		-0.2875
#36	24.6000		26.1875		1.5875		-0.3236
#37	24.6000		26.1250		1.5250		-0.3561
#38	24.6000		26.0625		1.4625		-0.3852
#39	24.6000		26.0625		1.4625		-0.4128
#40	24.6000		26.0000		1.4000		-0.4375
#41	24.6000		25.9375		1.3375		-0.4595
#42	24.6000		25.8750		1.2750		-0.4789
#43	24.6000		25.8750		1.2750		-0.4974
#44	24.6000		25.8125		1.2125		-0.5136
#45	24.6000		25.7500		1.1500		-0.5278
#46	24.6000		25.7500		1.1500		-0.5413
#47	24.6000		25.6875		1.0875		-0.5529
#48	24.6000		25.6250		1.0250		-0.5628
#49	24.6000		25.6250		1.0250		-0.5722
#50	24.6000		25.5625		0.9625		-0.5800
#51	24.6000		25.5000		0.9000		-0.5863
#52	24.6000		25.5000		0.9000		-0.5923
#53	24.6000		25.4375		0.8375		-0.5969
#54	24.6000		25.3750		0.7750		-0.6002
#55	24.6000		25.3750		0.7750		-0.6034
#56	24.6000		25.3125		0.7125		-0.6054
#57	24.6000		25.3125		0.7125		-0.6072
#58	24.6000		25.2500		0.6500		-0.6080
#59	24.6000		25.2500		0.6500		-0.6087
#60	24.6000		25.1875		0.5875		-0.6083
-----------------------------------------
Temperatur von Offset #1:	24.6000
Mittelwert nach 60 Messungen:	25.2083
Offset #1:	-0.6083
=========================================
```

Der Mittelwert von 60 Messproben lautet -0.6083. Dieser Wert wird als Offset verwendet.
