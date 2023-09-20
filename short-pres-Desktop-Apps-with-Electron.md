# Desktop Apps mit Electron

## Web-anwendungen IUBH
## 2023-09-20 Paul Libbrecht, CC-BY

--- 

## Motivation

* Jeder kann Web-entwickeln
* Es gibt Apps, dessen Zweck meist eine "Anzeige aus Daten" ist
	* Wetter, StockQuote, Nachrichten, CPU-Load
* Plattformunterschiede sind nicht mehr interessant
	* ... lass uns die Technologien vereinheitlichen
* und spezielle APIs sind sowieso auch auf Web-Apps erwartet
--- 

## SPA, PWA, Widgets ...

* SPA: Single Page Applications: Einen Web-Anruf, und hier läuft alles
	* mit weiteren Anrufen, mit vieles JavaScript, mit festen Teilen
* PWA: Progress Web Applications: ein MicroSoft Term:
	* Blend zwischen Web-App und Desktop-App
	* Normalerweise installierbar
* Widgets: 
	* Kleine Darstellung, die "in einer Ecke" sitzen
	* Cover-Screen, Dashboards...
* Installierbarkeit, Erkennbarkeit, Zugang

--- 

## iPhone: Mobil kann Web!

* Grosser Beitrag des iPhones: Das Web kann nützlich auf mobilen Geräten sein
	* Webkit gebaut und auf mobilen Performanz adaptiert
	* mobile Web hat gestartet
* Wieder neue Apps schreiben? Nein, WebApps adaptieren
	* Adobe PhoneGap... ist Apache Cordova geworden
	* Apps auf den App Store
	* Sicherheitsprüfungen wachsen, wachsen...

--- 

## Focus auf Desktop: APIs
* eine Web-App in einem Desktop App packen
	* einfach ein Browser?
* Desktop Apps sollten das können:
	* Dateien zugreifen
	* (manche) Netzwerkverbindungen machen
	* Copy-Paste zugreifen, Bluetooth, Drucken, ...
	* erkennbar, aktivierbar, installierbar sein
* Und inviduelle Versionen sollen unabhängig sein
* ElectronJS kann dieses

- - - 

## Electron: ein Desktop Ecosystem
* [ElectronJS](https://www.electronjs.org/)
* Gebaut von vielen großen Players
* JavaScript basierte Projekte (NodeJS)
* liefert immer ein Browser mit (Chromium)
* Build-system: electron Command-Line
* Plugins: ... im package.json

- - -

## Electron Praktisch
* von [electron-quick-start](https://github.com/electron/electron-quick-start) runterladen
* `npm install`
* `npm start`
* ... im Code Dinge ändern
- - -

## Electron: Sicherheit!
* Electron hat zwei Prozesse:
	* Web
	* Node (privilegiert)
* Kommunikation geht mit `postMessage`
* Dann sind nur die Nodeaufrufe, wie DU es entscheidest

- - -
## Wer benutzt Electron?

* Spotify
- VS Code
- Discord
- Teams
- ... [mehr](https://www.electronjs.org/#section_lM5q)
