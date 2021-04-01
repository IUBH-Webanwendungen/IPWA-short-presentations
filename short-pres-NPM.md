# NPM

## Web-anwendungen IUBH
## 2020-08-26 Paul Libbrecht CC-BY

--- 

## Kurze Erinnerung zu JavaScript

* Originellerweise eine Kommunikationssprache: HTML <-> Java Applets
* Langsam festgestellt:
	* Es gibt mehr zu tun und Java Applets sind klonky
	* JavaScript kann super kurz sein (zB jQuery) und ist einfacher
	* JavaScript Runtime kann schnell werden (zB V8)

---- 

## Lass uns JavaScript Command-Line schreiben

* Extrahiere JavaScript raus vom Browser 
	* ==> Kein DOM!
	* [NodeJS]
* Gib das Filesystem und Server Fähigkeiten
* Anstatt "lange Operationen"... call-backs
`tuDas().`
`     then( (result) => { file.write("hurra") })`
`     .error(console.log("ah-well"))`

--- 

## Dependencies in JavaScript

* Wir brauchen aber Bibliotheken!
	* für alles!
* Jede gibt ein Objekt mit ein Paar Eigenschaften
* eingebettet zB mit `const fs = require('fs')` => Objekt [`fs`](https://nodejs.dev/learn/the-nodejs-fs-module)
* Wo wird es gesucht?
	* typischerweise zuerst in `node_modules`
--- 

## NPM

* eine Firma (Eigentum von GitHub von MicroSoft)
* ein Command-Line Werkzeug
	* überall verfügbar
* ein Repository https://www.npmjs.com/
* Tausende von Bibliotheken unter OpenSource Lizenzen
	* Für meisten sind Dependencies _verpackt_

--- 
## Versuch

* `npm init`
* `npm install --save random`
* dann einfach [ein Beispiel](https://www.npmjs.com/package/random#usage) versuchen
* auch einfach `node` starten

- - - 

## Weiter mit NPM

* Eine "client" Bibliothek installieren
	* für radnom: 