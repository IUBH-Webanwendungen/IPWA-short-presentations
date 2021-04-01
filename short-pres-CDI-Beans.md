# CDI Beans

## Web-anwendungen IUBH
## 2021-03-03 Paul Libbrecht [CC-BY](https://creativecommons.org/licenses/by/4.0/) 

--- 
## Beans

* einfache Java Objekte
* mit Default-Constructor
* mit _Eigenschaften_ die Feld-ähnlich sind
	* aber mit `getXX` und `setXX` gelesen und geschrieben werden
* eine eigene Logik kann noch hinzugefügt werden
	* zB ein besonderes Rendering oder Transformation
* Beispiele:
	* JSF-ManagedBeans, für JSON- oder XML-Parsing

--- 

## ManagedBeans haben ein Problem

* ... das Singelton Muster für JSF ist schräg
	* mann braucht ein `static` Feld
		* damit Java-Aufrufe zur Instanz kommen
	* ... und `@ApplicationScoped`
		* damit UEL-Aufrufe zur Instanz kommen 
* Managed-Beans brauchen Injektion...
	* Das Bean `ShoppingCart` soll _einfach_ zum `Shop` (das vom JSF) Zugang haben: Dependency injection
		* also soll es ein Feld im `ShoppingCart` geben
		* ... das direkt mit `Shop` befüllt ist

--- 


## Context-Dependency-Injection Beans

* Ein anderes Standard als ManagedBeans
* Weg von JSF, es kann viele andere Zwecke dienen
* Mit Injection
* ... und idealerweise Konfigurierbarkeit
* Verfügbar in JavaEE seid Version 6

--- 


## Wie?

... siehe JakartaEE Tutorial
https://eclipse-ee4j.github.io/jakartaee-tutorial/cdi-basic010.html


--- 


## ...

...

--- 

