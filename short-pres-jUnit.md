# j Unit

### Web-anwendungen IUBH
### 2020-12-02 Paul Libbrecht [CC-BY](https://creativecommons.org/licenses/by/4.0/) 


---


## Grundidee
* Java Code schreiben ist leicht und manchmal übersichtlich
* Kann Qualitätscode überprüft werden?
	* statischen Analyse ja
	* Code-Review ja
	* ... aber das beweist keine Lauffähigkeit
* Unit-Tests: Einzelne Teile des Codes auf Funktion **testen**
	* Dafür eine Umgebung _künstlich_ bauen
	* Und die Elementare Funktionen auf elementare (interne) Ergebnisse testen

---

## Beispielanwendung

* Eine Klasse kann Streams "zusammen-bringen" (etwa: Fusionieren)
* Ein Unit-Test gestaltet zwei Streams und prüft, dass das Ergebniststream die Fusion entspricht
	* Prüfung ist typischerweise als _assertion_ gemacht.
* Ein extra Test kann Grenzen von Kodierungen testen (etwa: Unterstützung von ∅ oder grosse Grössen)
* Typisch: Einzelne Methoden werden in Unit-tests geprüft

---

## Formen der automatisierte Tests

* Unit-Tests prüfen kleine Teile
	* mit künstlichen Umgebung
	* sie kosten wenig Ressourcen (daher werden oft gelaufen)
	* sie brauchen keine Aktion und sollen plattformunabhängig sein
* Integration tests prüfen eine realistische Umgebung
	* Richtiges Server, Kommunikation, ...
	* Aber auch automatisiert
	* Sie dürfen lange brauchen (zB Docker aufsetzen ist ok)
* Schlimmste: Flickering Tests: manchmal ok, manchmal nicht
---

## How To jUnit

* einfach mit maven ein Projekt starten
        mvn archetype:generate \
           -DgroupId=de.iubh.webanwendungen.junit \
           -DartifactId=myApp -Dversion=1.0-SNAPSHOT \
           -DarchetypeArtifactId=maven-archetype-quickstart \
           -Dpackage=de.iubhwebanwendungen.junit
* `AppTest` testet die Klasse `App`
	* App wird durch das laufen von jeden `test*` Methoden durchgeführt
	* neue Instanz von `AppTest` für jeden Methodenaufruf


---

## jUnit Leitideen

* Ganzes Code soll leichgewicht getestet werden
* Im Fall, kann die Umgebung _Mock-Objekte_ brauchen (zB eine Fake Modell)
* Unit-testing soll Teil von jeder Kompilierung stattfinden
* Unit-Testing soll auch Teil von Continuous Integration
---

## Test Driven Development

* Wenig schmackhaft: 70% der Zeit ist in Debugging
* Daher: lieber Tests zuerst schreiben dann erst reparieren
* Ähnlich für neue Features: zuerst Tests mit Ziel schreiben, dann implementieren
* Auf Vollständig der Tests immer blicken
* Leicht: Auftraggeber schreibt Tests, auftragnehmer macht die Tests fröhlich