# Intro to web-proxies

## Web-anwendungen IUBH
## 2023-02-05 Paul Libbrecht, CC-BY

--- 

## Grundlagen

* HyperText Transfer Protocol, ein Urgestein
	* siehe [alle proposed Standards auf Wikipedia](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol)
* HTTP Demo: Inspector
* HTTP Demo: Telnet
--- 

## Proxy Konzept

* Kann HTTP-in und -out
* Client stellt eine HTTP-Anfrage
* Proxy _wiederholt_ die Anfrage
	* eventuell verändert
		* Typisch: Headers
	* oft: gebuffered


--- 

## Beispiel Proxyeinsatz

* Um Ressourcen zu schonen (Meist _Forward Proxy_):
	* Lagert in Cache und serviert nochmals ohne zu fragen
	* oder servier komprimiert, zB für eine Schulklasse
* Um Inhalt zu filtrieren
	* zB Hotel WLAN Login
* Als _Front-Server_: Bündelung und Connection-Management 
* zB als Load-Balancer
	* Reverse Proxies

--- 

## Proxydemo: ProxyServlet
* Als normales Reverse Proxy
* ZB [von Srinivas Dasari](http://blog.sodhanalibrary.com/2014/05/proxy-servlet-to-forward-requests-to.html)
* Nimmt Anfrage an, öffnet eine HttpURLConnection
	* Leitet die Anfrage um
	* Leitet die Antwort um
* Super um ein Paar Kopfzeilen zu anpassen


- - - 

## Proxy demo
* Apache [mod_proxy](https://httpd.apache.org/docs/trunk/mod/mod_proxy.html)
* `ProxyPass / http://127.0.0.1:38888/`
* Egal was reinkommt, wird zum Port 38888
	* Apache _reinkommt_ : Wird im Konfig niedergeschrieben
	* zB VirtualHost (`Host` Kopfzeile), `RewriteRule`, `Location`...
* Setzt `X-Forwarded-*` Kopfzeilen
* Sehr verbreitet als Front-Server: zB um ein Teil static zu liefern
* Muss mit Redirects aufpassen (_richtiges Hostname_)
	* `ProxyPassReverse`
* ... auch NGinx, HAproxy, ...

- - -

## Reverse Proxies in der Welt
* Kommerzielles Angebot (Schutz, Performanz, Caching, ...):
	* CloudFlare
	* Amazon CloudFront, Akamai
	* Azure, Google, AWS...
	* Konsequenz: Protokollen können gewechselt werden, etwa... https nur am Front
* Normale Docker Landschaft:
	* privates Subnet, verschiedene Servers auf verschiedene Adressen
	* bestimmte Porteröffnungen
	* typischerweise dann ein Apache oder NGinx davor
- Load-balancing: Session stickyness (zb JSESSIONID): spricht den selben App Server an als früher
- Viele Implementationen: NGinx, Apache, Traefik...
* Sicherheitsproxies:
	* _Web Application Firewalls_
	* Simple Password... (Fest im Front Server, auch Signaturprüfend oder Decoding)
- - -

## Demo: NGinx, DNS und eigenen Domänen

...

- - -
## Breite Anwendung von Proxies

* Route zum richtigen
- Informationsfiltern
