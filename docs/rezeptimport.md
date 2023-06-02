# Rezeptimport

Der Brautomat kann Braurezepte aus folgenden Quellen importieren:

* kleinerBrauhelfer2 (ab Version 2.5 Exporttyp Brautomat)
* MaischeMalzundMehr
* BrewFather

Empfohlen wird die Rezeptverwaltung mit dem kbh2. Empfohlen wird der Import von MMuM Rezepten zunächst in kbh2 und dann ein Export im Format brautomat.

_Hinweis: der ESP8266 hat nur einen kleinen RAM Speicher. Rezepte mit sehr lange Texte, Bilder oder anderen Anhängen können ggfs. nicht eingelesen werden._

## Optionen für den Import

Der Brautomat benötigt einen Step Einmaischen (optional) und einen Step Abmaischen. Insbesondere der Schritt Abmaischen dient mit deaktivertem "autonext" als Trennschritt zwischen Maischen und Kochen. Beim Import kann der Brautomat fehlende Einmaisch- und Abmaischschritte einfügen.

## Kochdauer und Nachisomerisierung

Diese beiden Daten werden beim Rezeptimport ausgelesen. Die Datenfelder können nicht editiert werden.

## Rezeptexport

Rezepte können im JSON Format exportiert werden und jederzeit wiederverwendet werden. Das erleichtert insbeosndere bei aufwändigen Rezepten die Einstellungen und Wiederverwendung (Earl Kochmaische, Dekoktion, etc.).

_Empfehlung: Rezepte sollte in einem dafür passendem Tool wie dem kbh2 beabreitet und archiviert werden._
