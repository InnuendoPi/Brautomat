# Funktionen der Buttons

## Beschreibung aller Buttons

Der Maischeplan verfügt über Buttons zum Editieren, erweitern oder Löschen der Tabelle. Diese sind eher selbsterklärend.

### Der grüne Speichern Button

Mit dem günen Button Tabelle speichern in der Kopfzeile der Tabelle Maischeplan wird der Inhalt der Tabelle in eine Datei (JSON) abgespeichert.

### Der blaue Speichern Button

Mit dem blauen Button Zeile speichern wird die Ändeurng der aktuellen Zeile in die Tabelle übernommen.

### Der Aktualisiere Maischeplan Button

Mit dieser Funktion wird die Tabelle neu aus der Datei eingelesen. Zu beachten gilt, dass alle nicht gespeicherten Änderungen ohne Rückfrage verworfen werden.

### Der Löschen Button

Mit dem Löschen Button wird die gesamte Tabelle geleert. Zu beachten gilt, dass erst mit Klick auf Tabelle Speichern die Änderung übernommen wird.

### Der + Button

Mit dem Plus-Button wird eine neue Rast hinzugefügt. Zu beachten gilt, dass die neue Zeile in der Tabelle mit Klick auf das blaue Speichern-Symbol in der Tabellenzeile übernommen werden muss und abschließend mit einem Klick auf das grüne Speichern-Symbol die Tabelle gespeichert wird.

### Der Graph Button

Mit dem Graph Button kann die visuelle Darstellung vom Temperaturverlauf ein- bzw. ausgeblendet werden. Zusätzlich können einzelne Graphen durch Klick auf den Graphnamen ein- und ausgeblendet werden. Die Standardeinstellung auf sichtbar eingestellt.

_Tipp: Wenn der Temperaturverlauf nicht interessant ist, einfach auf den grünen Graph Button klicken. Sobald die Grafik ausgeblendet ist, einmal die Systemkonfiguration öffnen und auf Speichern klicken. So wird die Einstellung Grafik Temperaturverlauf aus- bzw. einblenden gespeichert._

### Der Kalender Button

Das Kalender Icon wird grün dargestellt, wenn ein automatischer Braustart aktivert wurde. Standarddarstellung ist grau und entspricht keinem automatischen Braustart. Ein Klick auf das Icon deaktiviert einen konfigurierten Autostart.

### Der Server Sent Events Button

Ab Brautomat Version 1.20 versendet der Brautomat alle Daten als Server Sent Events (SSE) Broadcasts in Kanälen. Bis Version 1.18 wurden alle Daten vom Browser per http polling abgefragt. Gängige Browser können automatisch Server Sent Events abonnieren. Das SSE Icon in der Kopfzeile wird grün dargestellt, wenn eine Verbindung hergestellt wurde und ein SSE Kanal abonniert wurde (automatisch beim Aufruf der Web Interface). Sollte die Verbindung verloren gehen, wird das SSE Icon rot dargestellt. Ein Klick auf das Icon führt ein reload durch.

### Der Maischeplan anzeigen Button

Der Button Maischeplan anzeigen hat eine collapse Funktion: während des Brauen verbraucht der Maischeplan unnötig viel Bildschirmfläche. Mit collapse lässt sich die Tabelle Maischeplan ein- und ausklappen.
