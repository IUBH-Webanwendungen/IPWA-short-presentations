# Backups

## Web-anwendungen IUBH
## 2020-04-14 Paul Libbrecht

--- 

## Wozu?

* Sicherheit, dass Daten _wiedergefunden werden_ 
	* etwa on Crash
	* ... oder schlechte Programmierung
* Indem die Daten woanders kopiert werden
* Backup: Ständiges Prozess
* Restore: Bei Bedarf, einzelnes Prozess
	* ... nachdem mann erkannt hat, dass es nötig ist

--- 
## Unterschiedliche Frequenzen

* Typischerweise täglich gemacht
	* also kann nur die Arbeite eines Tages verloren sein
* Auch stündlich macht Sinn, auch wöchentlich und monatlich
	* 5-10 pro Rythmus halten
* Hintergrundprogrammen
* Regelmäßige Snapshots (also, nicht alles wieder und wieder)
* ... immer beachten: Wie lange dauert ein Restore?
	* Schlechtes Beispiel: Brand bei OVH (Straßburg): 3 Monate Downtime


--- 
## DBs: Hot Backups?

* Datenbanken speichern auf Festplatte
	* also einfach kopieren?
	* kann nur _konsistent_ dann sein, wenn die DB off ist
	* geht aber nicht
* Andere Strategien, in DB integriert
	* Snapshots
	* Logs
	* Können auch für Replikation verwendet werden


--- 
## DBs Werkzeuge

* [`mysqldump`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html)
	* `mysql < backup.sql`
* [Postgres](https://www.postgresql.org/docs/9.1/backup.html)
* Derby von Java aus (siehe [hier](https://db.apache.org/derby/docs/10.9/adminguide/cadminhubbkup01.html#cadminhubbkup01))
* H2, anderen in Memory?


--- 
## Best Practice

* Hot Backups bei Servers
* Mehrere Frequenzen
	* weil mann nicht richtig ein Problem sofort identifiziert
* Mehrere Orten
	* ein Live-Backup ist nichts anderes als zweite Festplatte
		* Virus drin, dann auch dort
	* zB im Fall eines Brandes
* Cloud-backup?
	* Gute Praxis aber bitte stark veschlüsseln

---
