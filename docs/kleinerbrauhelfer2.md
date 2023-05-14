# KleinerBrauhelfer2

Ab Version 2.5.0 hat das Programm [kleinerBrauhelfer2](https://github.com/kleiner-brauhelfer/kleiner-brauhelfer-2) einen Export Filter für den Brautomat. Die Rezeptentwicklung und Gestaltung ist mit den kbh2 in allen erdenklichen Details möglich. Mit dem Spickzettel bietet der kbh2 einen sehr guten und hilfreichen Ablaufplan für die praktische Umsetzung in der Brauküche. Mit dem Export Filter für den Brautomat können alle Schritte übernommen werden.

## Der kbh2 Tab Maischplan

Im Tab Maischplan bietet der kbh2 vier verschiedene Arten Malze zur Maische hinzuzufügen: Einmaischen, Aufheizen, Zubrühen und Dekoktion. Alle vier Arten werden im Brautomat unterstützt. Der Typ Einmaischen wird automatisch mit deaktiviertem autonext eingefügt. Aufheizen und Zubrühen mit aktiviertem autonext. Die Dekoktion wird mit deaktivertem autonext übernommen.

![Kochen](/docs/img/kbh2-maischplan.jpg)

 Der Brautomat benötigt Maischeschritt "Abmaischen", um das Ende vom Maischen und den Übergang zum Läutern zu erkennen. Es sollte in kbh2 Maischplan am Ende ein Schritt Abmaischen vom Typ "Aufheizen" mit 76°C oder höher und einer Dauer von 1 Minute angefügt werden. In dieser Kombination wird Abmaischen vom Brautomat erkannt und mit deaktiviertem autonext eingefügt.

![Kochen](/docs/img/kbh2-maischplan2.jpg)

### Beispiel 1: kbh2 Earl Scheidt Kochmaischverfahren

[Earl Scheid](http://hb-tauschboerse.bplaced.net/Neues_Maischverfahren.htm)

### Beispiel 2: kbh2 Dekoktion Zweimaischverfahren

[Zweimaischverfahren](https://hobbybrauer.de/forum/wiki/doku.php/maischen)

### Beispiel 3: kbh2 Dekoktion Dreimaischverfahren

[Dreimaischverfahren](https://hobbybrauer.de/forum/wiki/doku.php/maischen)

## Der kbh2 Tab Kochen

Eine Zeitangabe im kbh2 im Tab Kochen bedeutet "wie lange wird die Hopfengabe gekocht". Aus der Kochdauer ergeben sich u. a. Bittere und Aroma. Siehe hierzu auch die Formelsammlung im kbh2.\
Die kbh2 Zeitangabe "wie lange wird die Hopfengabe gekocht" wird beim Import in den Brautomat in eine Zeitangabe "zu welcher Zeit erfolgt die Hopfengabe" umgewandelt.

![Kochen](/docs/img/hopfen.jpg)

Im Bild kbh2 ist die Hopfengabe dargestellt. Die erste Hopfengabe ist "Hallertauer Perle 7% 2020" mit einer Kochdauer von 65 Minuten. Ein zweiter Parameter ist in diesem Zusammenhang wichtig: auf der linken Seite ist die gesamte Kochdauer mit 80 Minuten grün markiert. Die Würze wird also 15 Minuten lang ohne Hopfen gekocht. Die zweite Hopfengabe ist der "Hallertauer Tradition 5.7% 2020" Hopfen mit einer Kochdauer von 15 Minuten. In den letzten 15 Minuten Kochen der Würze hat die Hallertauer Perle von ursprünglich 65 Minuten noch 15 Minuten Kochzeit übrig und die zweite Hopfengabe Hallertauer Tradition kocht 15 Minuten lang von den verbliebenen 15 Minuten Restkochzeit mit. Die letze Hopfengabe wird zum Ausschlagen gegeben, also nach dem Kochende.

Die Aufgabe vom Brautomat ist den Zeitpunkt der Hopfengabe beim Brauen anzugeben und am besten mit einem aktustischem Signal an die Hopfenhgabe zu erinnern.\

Vorgegeben ist in diesem Beispiel eine gesamte Kochedauer von 80 Minuten und eine erste Hopfengabe "Hallertauer Perle" mit einer Kochdauer von 65 Minuten. Daraus ergibt sich eine Differenz von 15 Minuten Kochdauer ohne Hopfengabe. Der erste Teilschritt Würzekochen hat eine Dauer von 15 Minuten. Jetzt muss die erste Hopfengabe erfolgen. Die zweite Hopfengabe "Hallertauer Tradition 5.7% 2020" hat eine Kochdauer von 15 Minuten. Von den 65 Minuten sind 15 Minuten lang Hallertauer Perle und Hallertauer Tradition zusammen im in der Würze. 65 Minuten abzüglich 15 Minuten ergibt den zeitlichen Abstand der Hopfengaben von 50 Minuten. Die Hopfengabe Hallertauer Perle muss 50 Minuten vor der Hopfengabe Hallertauer Tradition gegeben werden.\

Die letzte Hopfengabe "Hallertauer Tradition 5.7% 2020" wird zum Ausschlagen gegeben. Beim Ausschlagen ist das Kochen beendet. Also zählt die Hopfengabe Ausschlagen nicht zur gesamten Kochdauer.\

![Kochen](/docs/img/hopfengaben.jpg)

In gleicher Weise verhält sich die Hopfengabe Ausschlagen. Es ist eine Nachisomerisierungszeit von 10 Minuten gegeben. Die Hopfengabe "Hallertauer Tradition 5.7% 2020" zum Ausschlagen mit einer Kochdauer von -5 Minuten ist Teil der Nachisomerisierung.
