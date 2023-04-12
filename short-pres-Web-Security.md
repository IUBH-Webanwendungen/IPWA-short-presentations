# Web-Security

## Web-anwendungen IUBH
## 2023-04-12 Paul Libbrecht

--- 

## Basics Reminder HTTP

* Ein Protokoll durch Sockets, Client-basiert, Request-Response basiert
* Telnet Demo
* Web-Inspector

---
## Was heisst Web-Security?
* Security:  Confidentiality, Integrity, Availability
	* ... einer Web-Applikation

--- 
## Angriffstypen einer WebApp
* XSS
* Datenvergiftung
* ungeschützte Zugänge
* Impersonation
* Privileg-Eskalation
* DOS/Flut

---
## Typische Angriffsablauf
* XSS durch Links oder Form-Submission
* Identitätsraub
* Dateneintritt
* Ausführbare Lücke auf dem Server
* Code-Veränderung
	* ... possessed
---
## Elementare Hygiene
* innerHTML, document.write => innerText
* nur HTML oder JS produzieren, wo Strings vertraut sind
* statische Webseiten bevorzugen
	* (=> Microservices)
* Server software als unprivilegiertes Benutzer laufen
* Entwicklung von Produktion trennen
* Server software code nur von anderen schreibbar
* DB-Anfragen bei Parametern, kein String-concat!
	* query = "select * from user where name like '%?%';"; query.setParam(1,name);
* Externes/Internes Monitoring mit Benachrichtigung
* Aktualisierungen
* Schlankere Systeme
* HTTP-only cookies
* Weiter:
	* Server-Performanz, pro Benutzer Begrenzung (insb Video), immer Platz für Admin-Zugang lassen,
	* Web-Application-Firewall?

---
## Weiter mit Web-Security

- [Wertvolle Best-practice](https://www.martinfowler.com/articles/web-security-basics.html)
	- Trust, Reject unexpected, Encode, bind DB-params, protect transit, hash and salt pwd, auth safely, protect sessions, authorize actions
- CyberSecurity dreht sich sehr über das Web normalerweise (Studiengang, Dienstleister, ...)
- [OWASP](https://owasp.org/)
- Von [CVEs](https://cve.mitre.org/cve/) informiert werden