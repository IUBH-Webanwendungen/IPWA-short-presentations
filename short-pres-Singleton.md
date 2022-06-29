# Singletons

## Web-anwendungen IUBH
## 2022-06-29 Paul Libbrecht [CC-BY](https://creativecommons.org/licenses/by/4.0/) 

--- 
## Objekte Zugreifen

* Erstes Aufruf: Baut ein Objekt
* `Object o = new MeinObject()`
* und ab hier ist es zugreifbar
	* in Aufrufen: Parametern passen
	* allgemeiner: Return-Values
	* ... aber zur View?
		* (machbar aber komplex... )
	* und für alle weitere Aufrufe? Ein richtiger Platz definieren

---

## Entwicklungsmuster (Design Pattern)
* Eine erkennbare und wiederholbare Praxis
* Verbreitetes Buch
* In der Sprache von allen
* Dinge wie publish/subscribe, klasse/subklasse, singleton, ...

--- 
## Das Singleton Muster

 * In einem Kontext, etwa in einer App, Web-App, ...
 * Muss von einer Klasse, ein Objekt:
	 * so früh wie möglich **initialisiert** werden
	 * immer von allem **als dasselbe zugegriffen** werden

--- 
## Beispiel: java.lang.Runtime

* Runtime: eine Java Klasse
* System.getRuntime(): ist ein Singleton
* benutzt static Methode
* wer baut das eine Runtime Objekt?

* Kann ich dasselbe mit Shop?
--- 

## Handcrafted Method: static

* ein `static` Feld
	* damit Java-Aufrufe zur Instanz mit `getInstance` kommen
* ... und `@ApplicationScoped`
	* damit UEL-Aufrufe zur Instanz kommen 
* dann sollen alle Instanzen immer dieselbe sein
* Problem: static Fehlschlag => ClassNotFound
* Problem: "sollen"
- --

## Bessere Methode: Inject
* `@Application Scoped` Class
* ... und Felder die mit `@Inject` geladen werden
* ... und UEL geht auch
* Siehe die Shop Klassen in der Jakarta Branch

- - - 

## Singletons sind einfach oder?

* Ja... in Prinzip
* Aber ein Singleton braucht einen anderen Singleton wer...
* das kann Zyklen geben...
* ... dann sind keine Injektion mehr möglich
* ... fast so dunkel wie ein ClassNotFoundException
* Die Entstehung also in CDI richtig andenken:
	* Meist ist der Rahmen der Thread des ersten Aufrufes...