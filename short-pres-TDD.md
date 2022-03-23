# Test-Driven-Development

## Web-anwendungen IUBH
## 2022-03-23 Paul Libbrecht CC-BY

--- 

## Grundidee

* Kleine Entwicklung: Du kickst dir durch und prüfe es sei ok
	* Bis auf... deine Auge sind müde
	* Aufmerksamkeit auf Details ist super-wichtig
* Eigentlich gibt es einen Auftrag an dem Programm:
	* es soll das und das mit diesem machen
	* Testing: 
		* Formuliere den Auftrag als Test an den Softwarefunktionen
		* Lass die Maschine prüfen, dass sie den Auftrag richtig erfüllt
		* Am Ende will mann ein OK
		* ... dazwischen liegt eine "pregnante" Darstellung eines Auftrags
--- 

## Auftragsspezifikation

* Software als Input-Output sehen:
	* Gib das ein
	* Erhalte so etwas
* Beispiel Code
```language=java 
testFFunction() {
  String a = "bla", b = "bla";
  String result = f(a,b);
  assertEqual(result, "blabla")
}
```
* Typischerweise mit solchen Aussagen gemacht wie:
	* "It should", "assert"
	* Versuch es laut lesbar zu machen
--- 



## Unterschiedliche Ebene der Testung

* "Dein Software soll das machen":
	* fröhliche Benutzern?
		* Satisfaction Testing
		* A/B Testing
	* Funktionen liefern, die den Benutzer ermöglicht
		* Usability Testing
		* A/B Testing
	* Funktionen liefern, die DAS machen, wenn DAS gemacht wird
		* Integration Testing
		* Performance Testing
	* von Teilen gemacht werden, die genau das machen
		* Unit-Testing
---

## Wann wird getestet?

* Ohne Benutzer: 
	* soviel wie möglich
	* Unit: bei jedem CI Build
	* Integration: einmal am Tag
* Test-Reporting:
	* Sammlung von Yes/No
	* Benachrichtung, wenn eine Änderung, ein Testfehler verursacht hat (typisch bei Jenkins)
	* Performanzzahlen
* Mit Benutzern:
	* soviel die kommen
	* ... aber Mode beobachten (etwa: Wahlperiode => mehr Zeitunglesen)

---
## Testing Frameworks

* Viele viele viele verfügbar:
	* Grosser Klassiker für Java: jUnit
	* Klassiker für Web Integration Testing: Selenium
* Zutate:
	* Test-Spezifikation (kann eine Sprache sein, etwa Cucumber, kann ein "Aufnahme"-Prozess sein
	* Reporting: Berichte in HTML
* Beispiele:
	* jUnit-Maven: einfache Berichte in der Konsole, IDE Integration
	* WebDriverIO-[Allure](https://github.com/allure-framework/allure2)
	* Cucumber & Gherkin: Behaviour-Driven-Development
	* Eggplant: KI um Tests zu reproduzieren

---

## Unit Test Beispiel: Jedes Maven Projekt

* zB `    mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-simple -DarchetypeVersion=1.4`
* laufen mit `mvn  -Dexec.mainClass=org.iu.App exec:java`
* testen mit `mvn test`

--- 

## IntegrationTesting: Beispiel SeleniumProjekt

* Ein Web-Browser wird pilotiert
	* setzt ein bereites Server voraus
	* läßt die Aktionen anhand Selektoren wählen
* Maven Projekt zu versuchen:
	* Ein _executable_: [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/) oder [GeckoDriver](https://github.com/mozilla/geckodriver/releases)
	* Die nötige Jars:
		* zB durch Maven generiert
		* Zuerst `mvn archetype:generate -Dfilter=quickstart -Dfilter=selenium`
		* dann SeleniumHQ Dependencies
		
<dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-java</artifactId>
        <version>3.141.59</version>
    </dependency>

