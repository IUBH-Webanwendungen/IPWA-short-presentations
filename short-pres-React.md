# Der React Framework

## Web-anwendungen IUBH
## 2023-10-04 Paul Libbrecht, CC-BY

--- 

## Grundinformation

* [react.dev](https://react.dev)
* JavaScript Framework, basiert of "Virtual DOM"
* Möchtet:
	* Komponenten
	* Reiche JS-UIs
	* Two way binding
	* Deklaratives UI-Gestaltung
--- 
## Konkret

* [`create-react-app`](https://create-react-app.dev/)
	* gesamt verpackt, "Facebook service"
	* viele best-practice Skripte zusammen gebracht
* components, two way bindings, tests
* oder `eject` dieses und macht dein eigenes Ding

---
## Die Welt in JavaScript: Entwickler

* JSX: JS mit HTML: Leicht zu schreiben!
	* mit Verbindungen
* Komponentensystem: vieles kann wiederverwendet
	* zB [react-switch](https://www.npmjs.com/package/react-switch)
	* viele APIs, auch Kommunikation
* Alles in JavaScript oder in TypeScript
* Sehr reiches Ökosystem

---
## Javascript aber mit HTML
* Die Mischung bringt Gefahren:
	* zB das `class` Attribut muss mit `className` ersetzt werden
* Alles in Komponenten verpackt:
	* `<Menu>` ist ein mögliches HTML Element: nimmt die (importierte) Komponent
	* `<menu>` aber nicht (rohes HTML)
* JSX wird zu JS übersetzt (`createElement` etc)
* HTML kann zugewiesen werden
	* => programmierte Abfolgen

---
## Die Welt in JavaScript: Browser und Robots

* Alles geht dynamisch: JS muss aktiv sein
	* ... HTML ist lächerlich
	* oder muss server-rendering haben
* Adaptierung ab Browser möglich:
	* Komponente X macht Rendering so oder so
* Komponenten: Erkennbare UIs
* VirtualDOM: in Prinzip wenige Updates trotz intensives re-Rendering

---
## React Community

* Lizenz: MIT
	* aber es gibt patentierte Dingen von Meta und anderen
	* lange Debatte über "MIT with additions"
	* ... aufgegeben, da keine Verwendbarkeit
* Meta an der Command
	* ... reiche Beiträge, insb für Performanz
* [community](https://react.dev/community) mit Conferences, Forum
	* mit spezielle Orientierung: Native, App, Remix...

- - -

## Vue, React, Angular, ...

* zB siehe [hier](https://www.browserstack.com/guide/angular-vs-react-vs-vue)
* Vue und React: eher für Anfänger, Angular weniger
* Vue mehr Community orientiert, weniger Komponenten
* React mehr durch Profis geführt