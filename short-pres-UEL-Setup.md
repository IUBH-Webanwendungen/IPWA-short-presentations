# UEL, Beans... und Setup

## Programmierung von industriellen Webanwendungen
## 2024-01-31 Paul Libbrecht

--- 
## Konzept: Expression Language

* Expression-Languages (EL)
	* ...
* In meist View-Sprachen gefunden:
	* in JSF, JSP, Velocity
	* in PHP, Nunjucks, ...

--- 

## Wesen am Laufen in einer JSF App

* Webapp
* Container
* Proxies
* Browser
---

## Konzept Bean

* Seid lange ein wichtiges Konzept
	* Einfach: Datenbeinhaltendes Objekt
* Vertrag:
	* Default Constructor
	* set- und get-Methoden
	* nichts mehr!
* Beans sind nützlich wenn in CDI
	* automatisches Lifecycle Management

---
## Let's build

* Tomcat, Webapp (built mit Maven)
* JSF Dependency
* CDI Dependencies
* leeres `beans.xml`
* Kein `web.xml`
* Wie auf [shortcast-dev's business-objects-validation](https://github.com/IUBH-Webanwendungen/shortcasts-dev/tree/business-objects-validation)
* Demo
---
## Sanity Check
* Zuerst: finde zuerst die Basisadresse
* Läuft Tomcat? einfach auf "/"
* Läuft die Webapp statisch mit einem `.txt` oder `.png`?
* Sind XHTML Dateien richtig geliefert?
	* in Quelle?
	* mit einfachen Beans?
	* mit den Beans die ich möchte
* immer graduell bauen
	* insb Classloading kann beissen
	
---

## Wrap up
* Wir kennen jetzt Expression-Languages
* Wir können ein einfaches WebApp mit UEL aufsetzen
	* mit JSF
* Konzepte der Beans und EL ganz allgemein
* Dann kommt die Entdeckung