# Web-app-containers

## Web-anwendungen IUBH
## 2020-06-24 Paul Libbrecht

--- 

## Wozu?

* Java Programmen für das Web
* Standards anwenden
	* und Vendor Unabhängigkeit schaffen
	* IBM mit RedHat mit Sun mit Oracle mit Caucho mit Nginx? ersetzen

--- 
## Architektur

* HTTP, Front-proxy, ,Servlets

---

## Beispiel: Tomcat

* Was es macht?
	* nur Servlets
	* lange eine Referenzimplementierung
* Open-Source Dimensionen
---

## Beispiel: Jetty

* Was es macht?
	* nur Servlets
	* Leichtgewicht... embedded!
* LGPL anstatt APL

---

## Beispiel JBoss

* Komplett für Entreprise
* "Domain" Konzept
	* meist mit einem CLI-Client


---

## Beispiel Glassfish

* Für Entreprise
* ... aber mit Management
* ... bis hin zu JMX

---

## Hosting einkaufen?

* Es existiert, ist aber nicht so verbreitet
  * zB [profi1 tomcat](https://www.profi1.de/tomcat-hosting.html)
  * auch [hier](https://www.mochahost.com/de/jsp_hosting.php)...
* Virtuelle Maschinen die vorkonfiguriert sind, etwa von Bitnami, oder [auf DigitalOcean](https://www.digitalocean.com/community/tutorials/install-tomcat-9-ubuntu-1804)
* Docker-basiert

---

## Beyond eigenes Hosting: Cloud

* Heutzutage erwartet mann Cloud
* Günstige, funktionsorientierte Einheiten
* (halb-)automatische Skalierung
* Normal wäre ein _App Service_:
  * einfache Umgebung, um individuelle Funktionen zu laufen
  * wenig Umgebungsabhängigkeiten
  * HTTP(S)-Erreichbarkeit, Monitoring, ...
  * Rest ist static


---

## App Services für Java

* [Azure Java](https://docs.microsoft.com/en-us/azure/developer/java/) kann es als Linux Umgebung oder App Service anbieten
  * proprietäre Clients, teilw proprietäre APIs, aber auch Linux
* [AWS Java](https://aws.amazon.com/de/developer/language/java/)
  * nur mit deren Tools, soweit, dass sie ihre eigene JDK verteilen
* [Google AppEngine for Java](https://cloud.google.com/appengine/docs/java/): kleien Funktionen oder kompletten (docker-basierten) Umgebungen
* mit kleine Funktionen ist die Rechnung genauer und bedarfsorientiert
* Providerbindung kommt sehr schnell
