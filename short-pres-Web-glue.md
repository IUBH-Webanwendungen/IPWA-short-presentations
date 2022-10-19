# Web-Glue

## Web-anwendungen IUBH
## 2022-10-19 Paul Libbrecht [CC-BY](https://creativecommons.org/licenses/by/4.0/) 

--- 
## Grundidee

* Jede Technologie hat seine Stärken und Schwächen
* Auch auf dem Web...
* Manche Plattformen sind gut für Kooperation, Einkaufen, Layout, ...
* Web-Glue (auch Mash-up genannt):
	* Komplementarität auf der Webseite-Ebene üben
	* HTML und JS mit spezialisierten Quellen
	* fortgeschrittene Funktionen als _micro-services_
	* Statischen Inhalt als statischen Dateien
---
## Elementares Beispiel 1: CDNs für Videos

* Problem: Videos liefern braucht fette Röhren
* grosse Infrastrukturen verwenden
	* und diese im Video Element als `SRC` eingeben
	* die `Range`Header honorieren
* oder `iframe`s von Youtube, Vimeo oder ähnlichen aus
* Vorteile: das Video spielt bei vielen Geräten und Netzwerkbedingungen
* Nachteile: Datenschutz leicht verletzt; eigentlich wäre ein ADV nötig
---
## Elementares Beispiel 2: Pay-me Knopf

* Paypal Button Beispiel
* Auch bei Banken
* Kompletteres: Shopify
* Auch hier ist Datenschutz leicht verletzt
---
## Origin und Cross-Origin Anfrange

* https://javascript.info/fetch-crossorigin

---
## Web-Glue mit einem Front-Server

* `/forum` geht zum Forum
* `/img` geht zum Verzeichnis
* `/pages` liefert statische Webseiten...
* Best-Practice: Front HTTPS2 Server
	* NGinx, Apache, ...
	* Kann auch eventuell zu mehreren Diensten verteilen
	* Achtung: Stickyness konnte nötig sein (bei Sessions)
---
## Web-Glue mit CDNs: Bad practice?

* oft wird es angeboten, ein CDN für eine JS Bibliothek zu verwenden
	* zB [MathJax](https://www.mathjax.org/#gettingstarted)
* Falsches Glauben: das bringt Cache-Effekten
	* Browsers machen "Cache-Partitionning"
* Gefahren: gut [hier](https://httptoolkit.tech/blog/public-cdn-risks/) dokumentiert
* Ein noch offenes Thema, zB [hier](https://hillbrad.github.io/sri-addressable-caching/sri-addressable-caching.html)


