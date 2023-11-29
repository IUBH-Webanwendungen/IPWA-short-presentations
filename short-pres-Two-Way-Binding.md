# Two-Way Binding durch die Technologien

## Web-anwendungen IUBH
## 2023-11-22 Paul Libbrecht

--- 

## Konzept Two Way Binding

* Information ist das Kern der Informatik
	* Aber isolierte Information ist nichts Wert
	* Information muss kopiert werden
		* um auf den richtigen Platz zu landen
* Binding: [Binding Properties](https://en.wikipedia.org/wiki/Binding_properties_pattern)
* Two way binding: Zwei Plätze der Speicher synchronisieren sich

--- 

## Anwendungen von Two Way Binding

* Um die GUI zu einem Modell zu verbinden
	* zB Textbox <-> Variable <-> Record
* Um die Daten zu replizieren (DBs...)
* Mitten in Message-Busses
* Nicht unbedingt sofort...
--- 

## Two Way Binding in VueJS

* Nehmen wir ein sehr einfach Vue App (zB [hier](https://vuejs.org/guide/quick-start.html))
	* component properties
	* console Änderungen
* `ref`/`reactive`: wie [hier](https://vuejs.org/guide/essentials/reactivity-fundamentals.html)
* [v-model](https://vuejs.org/guide/components/v-model.html)
* oder VueX / [Pinia](https://pinia.vuejs.org/)
* Achte: Feld (vue 2) => Reactive Prop (3)

---
## Two Way Binding in JSF
* `<inputText id=".." value="controller.object.property"/>`
* value-expressions
* Synchronisierung geht bei der Anfragen
	* auch in AJAX Calls
* Wichtig: nicht nur lesen auch schreiben
* Two-way Binding heisst: ich sehe die sync-Abläufe nicht!
	* vergleiche mit `request.getParameter()`...
--- 

## Two Way Binding in Angular

* Einfaches [property Binding](https://angular.io/tutorial/first-app/first-app-lesson-06)
* dann Interpolation (wieder einweg)
* dann [change-detection](https://angular.io/guide/change-detection)

--- 

## Shared Memory als Two Way Binding

* zB zwischen JS und WASM auf Emscripten
	* siehe [Memory Views](https://emscripten.org/docs/porting/connecting_cpp_and_javascript/embind.html?highlight=memory#memory-views)
	* Bytes können geteilt werden
	* Aber Kodierung muss auf beiden Seiten gemacht werden
	* ... und mit Signals versehen werden

--- 

## Take Away
* Einfaches Entwurfmuster des Pattern-Bindings
* Besonders einfach bei Two-Way-Binding
* Braucht aber Synchronisierungsroutinen
	* Sie können teuer (CPU-wise) sein
* Ist in vielen Umgebungen verfügbar