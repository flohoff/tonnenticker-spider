tonnenticker spider
===================

Der Tonnenticker ist eine Android und iOS App der Abfallwirtschaftsgesellschaft
des Kreises Warendorf mbH (AWG) und Gesellschaft zur Entsorgung von Abfällen
Kreis Gütersloh mbH (GEG) 

https://play.google.com/store/apps/details?id=de.regioit.abfallapp.tonnentickerpro&hl=de

Leider ist diese App seit Jahren eher unzureichend wie man auch an den äusserst
mangelhaften Bewertungen sieht. So gibt es Haufenweise Beschwerden das
Benachrichtigungen nicht funktionieren. Zum anderen kann man nur einen Standort
anlegen. 

Leider stellen sowohl GEG wie auch AWG die Rohdaten der Abfuhrtermine nicht zur
Verfügung. Meine Anfrage diesbezüglich wurde mehrfach im Kreis geschickt und
blieb bisher Erfolglos. 

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

Der Spider legt ein Verzeichnis mit dem Aktuellen Datenstand aus dem im
appdata json zurückgeliefertem lastImport timestamp.


