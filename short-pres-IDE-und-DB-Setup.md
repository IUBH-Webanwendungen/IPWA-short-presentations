# Setup IDE und Datenbank

## Web-anwendungen IU Internationale Hochschule
## 2023-07-05 Paul Libbrecht
[CC-BY](https://creativecommons.org/licenses/by/4.0/)

--- 

## Grundlagen

* J2EE: ein Framework
	* um Web-basierte Dienste für Unternehmen aufzusetzen
	* eine Sammlung von kompatiblen Specs
	* viele mit offene Implementationsmöglichkeiten
	* d.h.: jedes API hat ein separate Implementation
* Unternehmen IT braucht:
	* Daten zu organisieren => Datenbanken
	* parallele Zugriffen erlauben (=> Servers)
	* Auch mit kleinen Geräten (=> auch Web)
	* Hoch-skalieren zu können (=> High-perf Möglichkeiten)

---
## Typische Architektur

* Datenbank Server
* Web-Application(s)
	* in einem J2EE "Container" lauffähig (zB JBoss, TomEE, manchmal Tomcat)
	* evtl mit einem "Front Proxy": Apache oder NGinx oder HAproxy oder traefik (Connection-Management)
* Mind. aus einem Web-browser zugegriffen
	* evtl auch Web-Service-Clients
	* alles durch EIN http/https Service
* Das Rest ist hinter ein Firewall! (intern sind Connections leicht)
---

## IT Operationen
* App Deployen
	* Webapp code installieren
	* evtl Datenbank aktualiseren
* Konfigurieren
	* zB Verbindungsinfo, Passwörtern, Grenzen
	* Dateien, GUI, ...
* Backups
	* Dateien und DB, nach woanders kopieren
* Monitoren
	* Dauer der Verbindungen
	* CPU/Festplatten/RAM-Auslastung
---

## J2EE vs Servlets vs J2SE 

* Entwicklung braucht nur APIs
* Containers müssen die gewünschte Specs ([viele!](https://jakarta.ee/specifications/)) implementieren
* Konfiguration kann oft "im Container" sein
* Trennung zwischen Implementation und Spec

* zB TomEE vs JBoss vs Glassfish:
	* meist unabhängige Implementationen
	* beide sind J2EE Umgebungen (d.h. j2see + API + Implementierung)

* Im Kurs: 
	* Servlets (Tomcat)
	* JPA (Hibernate)
	* ...



---

## Entwicklungumgebung

* Möglichst nah an der Produktionsebene
* Aber mit kurze Zyklen:
	* Entwickeln • Deployen • Previewen •
* Prozesse:
	* Code-Editierung (IDEs)
	* Kompilierung und Verpackung (zB Maven, Ant, manchmal IDEs...)
	* Deployen (web-Service, Command-Line)
		* Kopieren/Hochladen, Neustarten
	* Previewen (Browser): mit richtigen URLs

* es kann überall brechen!
	* Fehlermeldungen verstehen!

---

## Aufsetzen: Erstmals Unabhängig

* Datenbank:
	* etwa MySQL mit mysql-cli, MySQL-explorer oder PHP-MySQL
	* etwa Derby mit [jj](https://db.apache.org/derby/docs/10.16/getstart/index.html)

* Container:
	* etwa Tomcat oder TomEE, starten mit CLI
		* unbedingt log ansehen! `logs/catalina.out`
	* etwa Glassfish, JBoss, ...
	* Pfade verstehen:
		* typisch: http://localhost:8080/webApp/
		* eine Datei `x.png` in `webApp` ist dann als `http://localhost:8080/webApp/x.png` erreichbar
	* immer zuerst statische Dateien testen
		* `.txt`, `.png`...
	* Beides testen!
		* Starten: mann sieht eine Seite
		* Stoppen: Connection Refused

* Kompilierung und Verpackung
	* `mvn` CLI oder IDE-Projekt bauen
	* es produziert ein Ordner oder ein Zip (`.war`) 


- - -

## Aufsetzen: Der IDE kann alles aber...

* IDEs:
	* Eclipse: open-source, super (zuviel) tunable
	* Netbeans: open-source: alter Großvater, kann alles... wenn mann den folgt
	* IntelliJ IDEA: Kommerziell mit vielen "sensible Defaults" eingepackt
	* viele viele andere! Jeder Vor- und Nachteile
* Kernidee einer IDE: ein Projekt wird editiert und getestet
	* mann kann Code ändern
	* mann kann Code (kompilieren, verpacken, deployen dann) laufen
	* "Play" Knopf die Essenz, aber Achtung, wie vieles es macht
* IDEs können Schnittstellen
	* Command-Line
	* Maven
	* Datenbanken
	* ... und alles eventuell verpackt

---

## Beispiel: IntelliJ, Maven, Derby

* Daneben Tomcat (lieber ohne EE)
	* dann `http://localhost:8080/` prüfen
	* mit einer Datei dazu, log prüfen
* Daneben Derby server laufen
	* log prüfen

* Projekt: [Artikelverwaltung_2_5](https://github.com/IUBH-Webanwendungen/IPWA-Beispielprojekte/tree/jakarta-update/ipwa02_projekte_netbeans/Artikelverwaltung_2_5) (Achtung: Branch Jakarta-Update)
* Auschecken (oder runterladen)
* Genauen Projektordner mit IntelliJ öffnen
	* maven Projekt erkannt
	* langsam alle Abhängigkeiten runterladen
	* versuchen zu verpacken: in target prüfen
	* dann maven "package"
* `.war` zum Tomcat kopieren und neustarten

- - - 

## Mehr IDE Beteiligung
* Database browsen
	* Tabellen listen
	* SQL interkativ gestalten und versuchen
	* Dumps und Restores
* Tomcat Deployment
	* zuerst tomcat-users.xml konfigurieren ([hier](https://tomcat.apache.org/tomcat-10.1-doc/manager-howto.html#Configuring_Manager_Application_Access))
	* Dann hoch und runter
	* Noch immer muss du den Browser steuern
---
## The play button

* Jeder IDE gibt den Eindruck es kann alles laufen
	* Grünes "Play" immer da
	* ... läuft "mit Annahmen"
	* zB: `.html` oder `.xhtml`: einfach mit lokalem Server servieren oder?
	* zB: `.png`... einfach ansehen?
* Zwei Challenges bei der Entwicklung eines Servers
	* Was mann gerade sieht => einem URL: wie??
		* zB Controller? Model-Datei?
		* eher ok mit einer JSF Datei
	* Kompilierung, Deployment, Neustart => Manager

- - -
## Production-Ready
* Siehe Architektur
* Servers werden unabhängig laufen
	* auch wenn mann schläft
* ... unbedingt auf Logs setzen
	* und gute Bug-Reports verlangen
* Immer den Wegen gehen
	* Barebones => IDE
	* Barebones => Deployte Webapps
	* ... weil nur Barebones kann auf einem Server geprüft werden