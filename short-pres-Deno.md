# Deno Engine

## Web-anwendungen IU Internationale Hochschule
## 2023-11-07 Paul Libbrecht
[CC-BY](https://creativecommons.org/licenses/by/4.0/)

--- 

## Wieso Deno?

* eine JavaScript Engine
* vom selben Gründer als NodeJS
	* ... mit der selben V8 Grundengine
* aber:
	* in Rust geschrieben
	* mit flexiblere Packages
	* mit einem Permission-Model
* auch open-source, mit TypeScript "nativ"
* auch mit einer Firma dahinter: Ziel: Cloud bis zu dem Edge

--- 

## Ein Security-Model?

* ... wie die alte Java Welt, aber für Servers, und zähmbar
* Die Idee: Code kann aus dem Web geholt werden
	* dann muss es geschützt laufen
* zB [Make an http request](https://docs.deno.com/runtime/manual/getting_started/first_steps#making-an-http-request)
* Nur damit kann mann wild Code laufen
	* etwa als "[Serverless Code](https://docs.deno.com/deploy/manual)"
--- 

## First steps

* [Install](https://docs.deno.com/runtime/manual/getting_started/installation)
* ... ein Paar first-steps
* bis Import-Maps
--- 

## Transition von NPM?

* Kann, in Prinzip auch `package.json` anwenden
	* scripts und dependencies
* [Transition cheathseet](https://docs.deno.com/runtime/manual/references/cheatsheet)
* Einfach ein Stück JS nehmen? 
	* => imports konvertieren
	* zB try [Algebrite](https://www.npmjs.com/package/algebrite)
* Deno speicher Dependencies einzeln
--- 

## Zukunftorientierung

* Deno hat viele Features die JS etabliert haben:
	* Persistence à la localStorage (aber big-data): [KV](https://docs.deno.com/kv/manual)
	* Viele standards [Web-Platform-APIs](https://docs.deno.com/runtime/manual/runtime/web_platform_apis)
		* Workers, Crypto, WebSocket, ...
	* Grundlegende WebServer: Nativ
		* ExpressJS "zu standard"
