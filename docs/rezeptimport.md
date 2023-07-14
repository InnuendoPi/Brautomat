# Rezeptimport

Der Brautomat kann Braurezepte aus folgenden Quellen importieren:

* kleinerBrauhelfer2 (ab Version 2.5 Exporttyp Brautomat)
* MaischeMalzundMehr
* BrewFather

Empfohlen wird die Rezeptverwaltung und -entwicklung mit dem kbh2. Der Exportfilter "Brautomat" beinhaltet alle Daten, die zum Brauen benötigt werden. Nur mit dem kbh2 sind Mengenangaben wie bspw. bei Hopfengaben in Gramm oder beim Zubrühen in Liter mit Temperatur möglich.

Rezepte aus MaischeMalzundMehr sollten ebenfalls zunächst im kleinenBrauhelfer2 importiert und auf die individuellen Anlagenwerte, Rohstoffe etc. angepasst werden.

Rezepte aus BrewFather müssen die Eigenschaft boilTime (Kochdauer) mit einem ganzzahligen Wert belegt haben. Empfohlen wird auch ein Wert für den Parameter Equipment -> whirlpoolTime. Rastnamen können bei BrewFather einen (nahezu beliebig) langen Fließtext enthalten. Der Text wird ab Zeichen 50 abgeschnitten. Brewfather erlaubt Fließkommazahlen und Text als Rastdauer. Die Parameter werden in ganzzahlige Werte gewandelt oder auf 0 gesetzt.

_Hinweis: der ESP8266 hat nur einen kleinen RAM Speicher. Rezepte mit sehr lange Texten, Bildern oder anderen Anhängen können ggfs. nicht eingelesen werden._

## Optionen für den Import

Der Brautomat benötigt einen Step Einmaischen (optional) und einen Step Abmaischen. Insbesondere der Schritt Abmaischen dient mit deaktivertem "autonext" als Trennschritt zwischen Maischen und Kochen. Beim Import kann der Brautomat fehlende Einmaisch- und Abmaischschritte einfügen.

## Kochdauer und Nachisomerisierung

Die Daten Kochdauer und Nachisomerisierung werden beim Rezeptimport ausgelesen. Mit diesen zwei Parametern werden die Zeitpunkte Hopfen- und Zutatengabe beim Import ermittelt. Kochdauer und Nachisomerisierung können daher nach dem Import im Brautomat nicht verändert werden.

## Rezeptexport

Rezepte können im JSON Format exportiert werden und jederzeit wiederverwendet werden. Das erleichtert insbeosndere bei aufwändigen Rezepten die Einstellungen und Wiederverwendung (Earl Kochmaische, Dekoktion, etc.).

_Empfehlung: Rezepte sollte in einem dafür passendem Tool wie dem kbh2 beabreitet und archiviert werden._
