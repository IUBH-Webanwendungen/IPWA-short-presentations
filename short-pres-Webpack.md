# Discovering WebPack

## Web-anwendungen IUBH
## 2022-11-30 Paul Libbrecht

--- 

## Wozu?

* Entwicklung vom Web:
	* vieles in den Client-Ressourcen
	* oder manchmal gar alles
* etwa: eine HTML, dann CSS, JS, Bilder, ...
* Für statische Lieferung zu optimieren: 
	* Kleiner Dateien, spätes Laden, nicht blockierendes Laden
	* Caching unterstützen
	* Aber die Cache-Löschung erlauben
* Werkzeuge für jede Stufe
	* Verkleinerung, Verdichtung, Zusammenbringen, ...
	* Alle zusammenbringen: bundler, wie etwa WebPack
	* Und nur anwenden, wenn nötig
--- 

## Werkzeuge

* NodeJS
* `npm` oder `yarn`
	* starten, zB mit `npm init`
* `package.json`: Projektbeschreibung
	* auch mit Abhängigkeiten
	* und Bauskripte
* WebPack: `npm install --save-dev webpack` 

--- 

## Imports und Loaders

* Eine Referenz von A nach B ist eine Abhängigkeit:
	* von JS to JS: das andere JS soll rein, als Modul
	* von JS to IMG: das Bild soll kopiert werden, und die Referenz soll kommen
	* von HTML to IMG: ähnlich
* Imports verursachen Loaders' Operationen
	* JS Loader: komprimiert (und...)
	* IMG Loader: komprimiert, kopiert oder kombiniert
	* LESS => konvertiert zu CSS
	* Typescript => konvertiert zu JS
	* ... und gibt ein Hash-basiertes Name
* Loaders arbeiten im `development` oder `production` Modus


--- 

## WebPack Anwendung: einfache App
* Zutaten:
	* package.json,
	* einfache Dependencies
	* HTML per Hand, aber mit Verarbeitung
	* bundle some js
* [Demo](https://hoplahup.net/tmp/webpack-demo.tgz)
--- 


## Entwicklung mit WebPack: Dev Server

* Idee: so kurze Feedbackschleifen wie möglich 
* Eine Quelle-Veränderung => Vorschau direkt
* Beeinflusst die Entwicklung: Init => Testsituation
* Demo
--- 

## Nur das nötige

* import macht der Grundsatz
	* aber Output kann vieles mehr beinhalten
	* zB `<img>`  => `<div>` mit JS, was später lädt
		* zB Bild mit unterschiedlichen Größen
* Tree shaking:
	* mit JS-Kenntnis kann mann Dinge noch wegmachen
	* zB ungebrauchte imports oder Funktionen
	* zB logisch unmögliche Teile
* Demos
--- 

## Perspektive

* Sehr weit verbreitet: 
	* Vue.JS Version 2
	* NextJS (bis Version 12)
	* Milliarden mal runtergeladen
* Weiter gehen mit einem [Tutorial und Größenanalyse](https://www.smashingmagazine.com/2021/06/getting-started-webpack/)
* Allgemeine [WebPack Documentation](https://webpack.js.org/)
* Aber viele externe sprechen darüber