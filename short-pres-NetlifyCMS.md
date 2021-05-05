# NetlifyCMS

## Web-anwendungen IUBH
## 2021-05-05 Paul Libbrecht CC-BY
--- 
## Grundidee Jamstack

* Server Hosting ist gefährlich, teuer, langsam
* Sehr sehr vieles kann im client gemacht:
	* Rechnungen und Interaktion (zB Validierung, Editierung)
	* Gestaltung von Client Code kommt mit speziale Mitteln
* ... bis auf wenige Services:
	* die könnten als API laufen
	* und duch "web-glue" zusammengebracht werden
		* etwa: Wetter-Anzeige, Kontaktformular, Shopping-basket, Lagerung, Authentifizierung...
--- 

## Continuous Integration für Websites

* Annahme: Eine Webseite ist... ein Projektordner
	* mit etwas Struktur
	* die auf ein Repository verwaltet wird
	* ... die eine static Webseite generieren kann
* Continuous Integration:
	* bei jedem Commit ein "Website-Bauen"
	* ständig dem letzten Zustand sichtbar machen
* Automatisierte Prozess solange mann ins Repository committen kann
--- 

## Verchiedene Workplaces

* Lokale Maschine
	* lokales Server, überwacht Festplatte, baut inkrementll
	* alles bearbeitbar
	* direktes Reload (zB durch Browserify)
* Repository
	* "etwas dokumentierte" Änderungen
	* mehrere Benutzer, evtl mehrere Branches
	* alles anpassbar, alle Änderungen rückgangig-bar
	* Commit => Publish
* NetlifyCMS
	* Editierung von definierte Werten im Generationsprozess
	* zB Seiten-Core, Tags, Meta-info
	* Autorisierung zu Comitten nötig
	* ... Publish durch commit

--- 

## Demo

* https://github.com/polx/explore-cms-11ty displayed on https://explore-cms-11ty.hoplahup.net/ and edited in CMS and locally
* ... an application of https://www.netlifycms.org/
* Separate parts can also be used