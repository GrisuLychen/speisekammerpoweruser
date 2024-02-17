# speisekammerpoweruser
Die JSON Datei SpeisekammerPowerUser ist ein NodeRed Flow welcher den Zugriff auf die API der Speisekammer App steuert.
Ziel des Projektes war es, die Ein- und Ausgabe von Produkten per Barcode Scanner zu ermöglichen bzw. besonders schnell durchzuführen.
Näheres zur Speisekammer App gibt es unter: https://speisekammer.app/


# Installation
Der Flow nutzt einige Erweiterungspakete in Node Red. Diese müssen vorher über den Paketmanager in Node Red installiert werden.
Folgende nicht standardmäßig in Node Red enthaltene Pakete sind notwendig:
1. node-red-dashboard
2. node-red-node-ui-table

Um den Flow in Node Red zu nutzen muss die Datei nur unter "Import" eingelesen werden. Im Anschluss müssen die nun neu hinzugefügten Nodes "Übernommen (deployed)" werden.
Sollten hierbei nicht alle notwendigen Pakete installiert sein, wird Node Red einen Fehler anzeigen. Im Anschluss kann das Dashboard aufgerufen werden (hierzu kann im Menü unter "Ansicht - Dashboard" auf den Reiter Dashboard gewechselt werden. Das Dashboard lässt sich dann im oberen rechten Bereich öffnen).

# Setup
Um den Zugang zur API nutzen zu können ist ein Token und für den vollen Funktionsumfang auch ein Abo bei speisekammer.app notwendig. Der Token kann nach der Anmeldung unter https://app.speisekammer.app/developer erstellt werden. Je nach Abo Status ist "lesen" und "schreiben" verfügbar. FÜr den vollen Funktionsumfang ist "schreiben" zu wählen.
Ist der Token erstellt, muss dieser im Dashboard eingegeben werden. Hierzu gibt es im Dasboard auf der Seite Speisekammer den Bereich Setup. Nach einem klick auf "Setup Eingeben" werden 2 Abfragen eingeblendet.
Zunächst ist die URL der API also "https://api.speisekammer.app" einzugeben. Dann der erzeugte Token. Es wird eine Datei mit dem entsprechenden Setup angelegt. Das "Setup2" kann genutzt werden falls ein weiterer Zugriff auf ein anderes Konto bzw. auf die "Staging" oder Entwickler-Version des API zugegriffen werden. Bei einem Neustart wird immer Setup1 geladen.

# Bedienung
Die Funktionsbuttons im unteren Bereich des Dashboards sollten für sich sprechen. Nahezu alle Funktionen lassen sich per Einlesen eines Barcodes bedienen. Eine Liste verfügabrer Barcodes ist in der Excel Liste enthalten. Soll zu einem neu zu erfassenden Artikel das Verfallsdatum eingegeben werden, so ist dieses vor der Eingabe des Artikels zu scannen. Wird der gleiche Artikel mehrfache gescannt wird das gleiche Verfallsdatum verwendet.

# Sets
Sets darf man sich wie einen 6er Wasser vorstellen. Diese sog. Sets haben eigene Barcodes. Sind sie einmal erfasst, werden durch einmaliges Scannen des Sets automatisch die entsprechende Anzahl von Einzelartikeln hinzugefügt

# Gruppen
Gruppen können Artikel zusammen fassen. Zum Beispiel Spagetti, Makaroni und Spirelli zu Nudeln. Hierdurch lassen sich besser Mindestmengen definieren. Achtung! Gruppen müssen derzeit noch manuell in der Speisekammer App administriert werden. Sie müssen immer im Lagerort Gruppen abgelegt werden. Die Barcodes hierfür müssen manuell vergeben und in die einzelnen Gruppenartiekel eingetragen werden.
Zur besseren Übersicht beginnen die Barcodes für Gruppen bei mir mit "G".
