# NGinx

## Web-anwendungen IUBH
## 2021-09-08 Paul Libbrecht

--- 

## HTTP

* Ein Protokoll durch Sockets, Client-basiert, Request-Response basiert
* 

--- 
## HTTP Ressourcen
* Was kostet Ressourcen im HTTP?
	* Ein offenes Socket (Route, Server, Client)
	* Laufende Anfrageprozessen im Server (CPU, RAM)
	* Coding/Decoding (Verschlüsselung, Bilder-rescale, Parsing...) (Browser, Server)
	* Cache-Festplatten-Raum
* Brainstorm: Sparen?

---

## NGinx
* Ein Server auf C++-basis, für alle gängige Betriebsysteme
* Eine Firma dahinter, um Support zu verkaufen
* Eine Vision der Skalierbarkeit
* Ein Kernproduct Open-Source, eine Erweiterung bezahlt

---
## NGinx vs Apache

* Alter: NGinx ist deutlich jünger
* NGinx ist nur zentral konfigurierbar (kein `.htaccess`)
* Skalierung nicht linear mit der Anfragemenge
* Support für alle moderne Standards (auch HTTP/3)
* Bei beiden: Rewrite-Rules
* Bei beiden: Modulen, VHost

---
## Beispielanwendung: Front-Proxy für Tomcat

* Connection-management
* SSL
* ....

---

## Beispielanwendung: Static File Serving

* ...
* Caching