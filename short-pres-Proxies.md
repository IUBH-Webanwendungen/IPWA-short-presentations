# Intro to web-proxies

## Web-anwendungen IUBH
## 2020-05-20 Paul Libbrecht

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
	* eventuell mit spezielle Proxy-Verpackung

--- 

## Beispiel Proxyeinsatz

* Um Ressourcen zu schonen (Meist _Forward Proxy_):
	* Lagert in Cache und serviert nochmals ohne zu fragen
	* oder servier komprimiert
	* zB für eine Schulklasse
* Um Inhalt zu filtrieren
	* zB Hotel WLAN Login
* Als _Front-Server_: Bündelung und Connection-Management
* zB als Load-Balancer

--- 

## Proxydemo: ProxyServlet
* Als normales Reverse Proxy
* ZB [von Srinivas Dasari](http://blog.sodhanalibrary.com/2014/05/proxy-servlet-to-forward-requests-to.html)
* Nimmt Anfrage an, öffnet eine HttpURLConnection
	* Leitet die Anfrage um
	* Leitet die Antwort um
* Super um ein Paar Kopfzeilen zu anpassen


- - - 

## Proxy demo: Apache
* `ProxyPass / http://127.0.0.1:38888/`
* Egal was reinkommt, wird zum Port 38888
	* Apache _reinkommt_ : Wird im Konfig niedergeschrieben
	* zB VirtualHost (`Host` Kopfzeile), `RewriteRule`, `Location`...
* Setzt `X-Forwarded-*` Kopfzeilen
* Sehr verbreitet als Front-Server: zB um ein Teil static zu liefern
* Muss mit Redirects aufpassen (_richtiges Hostname_)

## Proxy Demo: Apache: Weiter
* Spice it up mit einem SSH Tunnel
	* Port 38888 => Mein Port 38888
* Erlaubt Laptopentwicklung
	* aber (stabiles) Server mit HTTPS
* Auch noch mehr: Achtung zum Server-name beim Redirect