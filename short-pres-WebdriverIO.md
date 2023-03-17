# Webdriver IO

## Web-anwendungen IUBH
## 2023-03-15 Paul Libbrecht CC-BY

--- 

## Grundidee von Browser-Testing

* Wir entwickeln Web-Anwendungen
	* also die Bentuzung von Webseiten
* Browser Testing: Ein Browser verwenden, der ein Benutzer ähnelt
	* ganz standard für den Entwickler:
		* eine reproduzierbare Situation
		* immer wieder durchgelaufen, bis es befriedigend klappt
	* aber der Browser konnte _skriptet_ werden!
* Lass uns ein Browser nehmen und wir pilotieren es
	* alle Browsers mögen das
	* Standard definiert: [WebDriver (Selenium API)](https://www.w3.org/TR/webdriver/)
	* Kommunikation: HTTP


--- 

## Webdriver IO

* NodeJS Bibliothek, steuert ein Webdriver API
* Integriert sich in einem Testframework
* OpenSource, durch die OpenJS Foundation gefördert
* Viele Integrationen
* Jedes Skript:
	* gehe dort
	* warte für diese Situation
	* "It should", "assert" (zB finde Text)
--- 



## Setup

* Beispielprojekt
	* zB mit [create-wdio](https://www.npmjs.com/package/create-wdio)
	* zB mit Mocha, wait-for, page-objects, firefoxdriver, allure...
* Jedes Driver braucht auch ein Engine
* demo

- - -

## Zutaten

* Umgebungspec: `wdio.conf.js`
* Skripte
* page-Objekte

---
## Perspektive

* Für e2e Tests
* Für Kompatibilitätstests
	* => Bis Browserstacks
* Für last-Tests?
* Konkurrenz: CypressJS, SilkPerfomer