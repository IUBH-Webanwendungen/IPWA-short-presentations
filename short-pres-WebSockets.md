# Intro to websockets

## Web-anwendungen IU Internationale Hochschule
## 2023-02-01 Paul Libbrecht
[CC-BY](https://creativecommons.org/licenses/by/4.0/)

--- 

## Grundlagen

* HyperText Transfer Protocol, ein Urgestein
	* siehe [alle proposed Standards auf Wikipedia](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol)
* ... aber der Server möchtet was zum Browser schicken
	* Elementare Möglichkeit: immer wieder anfragen (_polling_)
	* Elaborierter: Auf Nachrichten in WebSockets zuhören

--- 

## Was sind WebSockets?

* Eine Alternative zu HTTP/HTTPS, auch ein Protokoll
	* [RFC6455](https://datatracker.ietf.org/doc/html/rfc6455)
* Aber Inhalte bilateral zu liefern
	* ohne Request/Response
* Inhalte sind als Frames ausgetauscht
* Gedacht als Komplement zu HTTP/HTTPS

--- 

## Stufen

* siehe [javascript.info](https://javascript.info/websocket)
* Basiert auf den `Upgrade` headers
* Danach: beider Seiten: `on('message', (msg)=> {...})`

--- 

## Anwendungen
* Chat Applikationen
	* zB [WS](xx)
* Datenbank Synchronisieren (zB [PouchDB](https://pouchdb.com/))
	* Wieso nicht... Modelländerungen synchronisieren
* Synchronisierte Explorationen
	* zB BabylonJS Modell-Sync ([Artikel](https://babylonjs.medium.com/share-3d-models-with-websockets-demo-a54f401c7f69)) Demo
* Near real time
---

## Infrastruktur

* Achtung: Web-Sockets sind teuer
	* stetige Pakete
	* normal: Heartbeats
	* Fluten kann ein Problem sein
	* Immer Verbindungen polieren
* [socket.io](https://socket.io/) als Werkzeugkasten, oder anderen
	* nicht selten werden WebSockets mit Polling emuliert
* Proxy-en benötigt etwas spezielles... [hier](https://medium.com/@ibraheemabukaff/how-to-proxy-websockets-with-nginx-e333a5f0c0bb)


- - -
## Take Away
* Effektive Near-real-time Synchronisierung mit WebSockets.