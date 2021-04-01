# Sessions & Servlet-Containers

## Web-anwendungen IUBH
## 2021-03-31 Paul Libbrecht [CC-BY](https://creativecommons.org/licenses/by/4.0/) 

--- 

## Session?

* Speicherort für Server-Programmen
	* damit das Dialog mit einem Benutzern "Spuren" lässt (Wünsche, Bestellungen, editierte Information)
* Servlet: [HttpSession](https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpSession.html)
* Meist eine Lagerung für "Key-Value" Pairs
	* Key: Strings
	* Values: Was du willst
--- 

## Speicherung von Session

* Im RAM:
	* schnell schreib- und les-bar
* Runterfahren: Serialisierung von allem
	* Die Value-Objekte (und allen referenzierten Dabei)
* Hochfahren: De-Serialisierung
* tomcat: `work/Catalina/<host>/<webapp>/SESSIONS.ser`

--- 
## Session Hijacking

* Wie wird ein Browser zu einem Session abgebildet?
	* Meist mit JSESSIONID Cookie
	* Oder mit JSESSIONID Parameter
* let's try

---

## Session durch Clusters

* Eine typische Architektur:
	* ein Front-Server (zB Apache, Nginx)
	* viele Tomcats (mit Proxy)
	* eine (fette) Datenbank
* Speziale Feature: selbe JSESSIONID => selbes Tomcat
	* .... oder Sessions sind synchronisiert
	* zB JGroup, Redis...

---

