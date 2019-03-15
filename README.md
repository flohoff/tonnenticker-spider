tonnenticker spider
===================

Der Tonnenticker ist eine Android und iOS App der Abfallwirtschaftsgesellschaft
des Kreises Warendorf mbH (AWG) und Gesellschaft zur Entsorgung von Abfällen
Kreis Gütersloh mbH (GEG) 

https://play.google.com/store/apps/details?id=de.regioit.abfallapp.tonnentickerpro&hl=de

Leider war die Vorgänger App schon unzureichend und die neuerstellung
durch die RegioIT hat die Designprobleme des Vorgängers übernommen.

Die Bewertungen im PlayStore sprechen ihre eigene Sprache. Ich selber habe
die Benachrichtigungen nie ans laufen bekommen.

Leider stellen sowohl GEG wie auch AWG die Rohdaten der Abfuhrtermine nicht zur
Verfügung. Meine Anfrage diesbezüglich wurde mehrfach im Kreis geschickt und
blieb bisher erfolglos. 

spider
------

Der Spider nutzt die vom Tonnenticker Pro genutzte Backend API um die aktuellen
Abfuhrtermine aller Orte und Straßen abzuholen und als JSON files abzulegen.

Genutzte URLs:

	https://krwaf-abfallapp.regioit.de/abfall-app-krwaf/rest/appdata
	https://krwaf-abfallapp.regioit.de/abfall-app-krwaf/rest/fraktionen
	https://krwaf-abfallapp.regioit.de/abfall-app-krwaf/rest/orte
	https://krwaf-abfallapp.regioit.de/abfall-app-krwaf/rest/orte/${ortid}/strassen
	https://krwaf-abfallapp.regioit.de/abfall-app-krwaf/rest/strassen/${strassenid}/termine

Der Spider legt ein Verzeichnis mit dem aktuellen Datenstand aus dem im
appdata json zurückgeliefertem lastImport timestamp.


icalwrite
---------

icalwrite erzeugt für einen Ort und eine Straße ein ICAL file (ics) das in Handelsüblichen
Kalenderapplikationen importiert werden kann. Getests mit Mozilla Thunderbird/Sunbird.

Google Calendar import geht gerade noch nicht. 

	./icalwrite -d 11.03.2019_14\:12\:32 -o Herzebrock-Clarholz -s Kleikamp

Anschliessend liegt im aktuellen Verzeichniss ein

	Herzebrock-Clarholz-Kleikamp.ics	

Es fehlt noch Einschränkungen auf die Tonnen.

