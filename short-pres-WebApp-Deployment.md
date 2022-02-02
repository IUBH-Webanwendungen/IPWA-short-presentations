# Web-App Deployment

## Web-anwendungen IUBH
## 2022-02-02 Paul Libbrecht CC-BY
--- 

### Back to Basics : Eine HTTP-Anfrage

* URL, Namensauflösung, Sockets, 
* HTTP-Headers, Anfrage, Antwort

- - -

### Webapp/Servlet Container

* Funktionen
* Adresse
* War Format
* oft: Proxy

- - -

### "Deployment"
* Die Lieferung eines Softwares
* ... damit es lauffähig wird
* also, auf dem "End-Platz", wo Benutzer starten
* nach dem Deployment: Es ist _released_.

- - -


### Deployment für WebApps
* Datei Upload
* Server-side Caches geleert
* neuer Server-Code ist geladen
* Datenbank, Zustände, Sessions: kommen zurück

- - -


### Servlet-Container Deployment
* Dateien kopieren
* Servlet-Context neumachen
* Servlets neustarten
* Am Einfachsten: Container-Down, Kopieren, Container-up
* Aber es lässt sich auch ohne Neustart machen
* Mit Dateikopieren
* Mit web-API
* Mit gesonderte Kommando


- - -

### Deployment Tool

* Tomcat Manager
* JBoss Wildfly domain
* Glassfish Admin
* ant, maven : plugins (zB: [Tutorial für maven](https://www.cise.ufl.edu/~msr/post/maven-tomcat-deployment/))
* IDEs? Mit einem davon
	* netbeans: ant
	* intelliJ: ein Werkzeug für jeder
* Läuft in HTTP und braucht eine Authentifizierung
	* tomcat-users.xml
	* ähnlichen, zB bei dem ersten Lauf

- - -

### Technisches Erproben auf IDEs

* netbeans 12
* intelliJ Ultimate
* bei beide:
	* Server Konfigurieren (mit Benutzername und PW)
	* Auch Portnummer, damit mann "run" kann

- - -

### Deployment to Production

* Sein Server, von überall zugänglich
	* typisch: Hinter ein NGinx oder Apache Proxy
	* Hat ein Domänename, wo es erreicht wird
* Maintenance Anzeige
	* Dateien hochladen (rsync, FTP, Docker-build...)
	* Server Neustart (CLI)
	* Prüfen
* ... Freischalten
	* Prüfen

- - -

### Advanced Deployment

* A/B Testing: Das Deployment ist nur für manche gemacht
	* ... dann können diese manchen mit Analytics beobachtet werden
* Progressive:
	* Datenzentrum nach Datenzentrum, Clients nach Clients
	* Push to edges
* Kohärenz wichtig:
	* Wenn ich Version F des HTMLs laufe
	* ... dann sollen auch andere der Version F sein
	* der Client-Cache kann beissen: dafür: Pfade ändern
	* keine halb Deployments: dafür: Maintenance-Screen (auch kurz) oder Slots