# Web-services

## Web-anwendungen IUBH
## 2020-07-01 Paul Libbrecht CC-BY

--- 

## Grundidee

* Das Web ist überall...
	* In vielen Orte können nur HTTP(S) Ports erreicht werden
* Aber Anwendungen wachsen
	* GUIs auf mehrere Orte und Servers
	* verteilte Kommunikation zwischen Servers
* Web-Funktion: Von Programmen zu Programmen

--- 

## Beispielanwendung von Webservices

* Storage, Drucker, Konvertierung
* Knowledge-base-Anfrage
* Reasoning, Prediction...
* Publication, Authorization
--- 

## Standards für Webservices

* First things first: HTTP und HTTPS
* XML
	* XML-RPC: einfaches Remote procedure call
	* SOAP: Reiches WS-calls mit vielen Sub-standards
		* immer mit POST
	* WSDL: Beschreibung eines Webservices
* UDDI: Discovery
* x-www-url-formencoded
* Transportsprachen: XML, RDF, JSON
* SPARQL, GraphQL...
* REST (nicht so richtig ein Standard)
* RSS, OAI-PMH , ....
* OAuth: Erlaubnis zum Zugang einer Ressource mit Benutzerabfrage

--- 

## Web-services in der Welt

* Fast jede Webseite heutzutage benutzt was eines Webservices
	* auch Analytics kann darunter als solches gesehen
* AWS Batterie
* Google Webservices
* MS, Yahoo, DeepL...
* jedes bietet sein Tutorial, oft Clientbibliothek
* mit API-key, Mengebegrenzung und Pricing

--- 
## Example web-service: coindesk

https://vuejs.org/v2/cookbook/using-axios-to-consume-apis.html

----

## Web-service documentation

* WSDL hat vieles getan
* mehr ist nötig, um REST orientiert anzutreten
* [OpenAPI](https://de.wikipedia.org/wiki/OpenAPI)/[Swagger](https://swagger.io/tools/open-source/) Methoden
	* Webservice gerade drin im Quellcode
	* etwa wie Javadoc... aber für rest-services
