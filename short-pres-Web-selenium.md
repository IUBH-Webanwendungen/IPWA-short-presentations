# Robot-Browsing

## Web-anwendungen IUBH
## 2020-08-05 Paul Libbrecht CC-BY

--- 

## Grundidee

* Das Web ist für Web-Browsers
	* aber Benutzern dahinter sind manchmal müde
* Zwischen Maschinen gibt es Webservices
* Aber manchmal müssen Maschinen die Arbeit der Menschen übernehmen
	* Eine Webseite laden und deren Text schnappen
	* Ein Klick erledigen und _sehen was kommt_
	* Ein Test durchführen
--- 

## Prinzip: (Web)Scraping

* Ein UI muss als solches akzeptiert werden
	* bewährte Maschine (80x24 Grün)
	* ein Web-Browser mit Cookies
	* ein Ergebnis einer komplexen Abfolgen
* Aber es wird automatisch gesteuert
	* geklickt, gedruckt...
* ... und automatisch gelesen
--- 

## Robot-Anwendung: Spiders

* Automatisch lesen um ein Suchindex zu gestalten
	* Bücher der Bibliothek
	* Notizzen von allen
	* Kompletten Webseiten
	* Web-crawlers
* Beispiel:
	* `wget --recursive`
	* [Apache Nutch](http://nutch.apache.org/)
	* alle Web-Robots (GoogleBot, YandexBot, [Heritrix](https://github.com/internetarchive/heritrix3/), ...)
* Meist fokussiert: Massive Arbeit
* Achtung: wenige führen JavaScript aus

--- 

## Echtes Browser

* Ein Browser laden... Ein Link klicken... Ein Formular füllen...
	* Kann alles programmiert werden
* Dafür: [Selenium](https://www.selenium.dev/)
	* Eine Schnittstelle, um Browsers anzusprechen
	* Bibliotheken für jeden Programmiersprachen
	* Back-ends für jeden Browsers (Firefox, Chromium, Webkit...)
--- 

## Beispiel SeleniumProjekt

* Wir brauchen:
	* Ein _executable_: [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/) oder [GeckoDriver](https://github.com/mozilla/geckodriver/releases)
	* Die nötige Jars:
		* zB durch Maven generiert
		* Zuerst `mvn archetype:generate -Dfilter=quickstart`
		* dann SeleniumHQ Dependencies
		
<dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-java</artifactId>
        <version>3.141.59</version>
    </dependency>

## Anwendungen

* Integration Testing
	* Start Server, Open-Browser, Machetwas, prüfe dass das kommt
	* Klein oder gross
	* draussen oder drin (Silkperformer, Saucelabs, ...)
* Web-Scraping
* Perfomanz-Analyse
* Mit einem Rechner (~20 Browsers) oder ein Cloud
