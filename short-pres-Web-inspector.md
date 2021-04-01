# Intro to web-inspector

## Web-anwendungen IUBH
## 2020-04-06 Paul Libbrecht

--- 

## Wo?

* Rechts-Klick => Element-Untersuchen
	* In Firefox, Chrome
* Safari: 
	* Einstellungen: Entwicklerwerkzeuge aktivieren
	* Menü Entwicklerkonsole
* IE & Edge: F12

--- 

## Aspekte einer Webseite im Inspector

* Inspector/Elements: Aktuell dargestelltes DOM Baum
* Netzwerk/Resources: HTTP-Anfragen
* Console: Eingabe und Antworten, Fehlermeldungen
* Storage/Accessibility/Timeline/Debugger/Security...
* Immer nur eine _lokale Spielerei_: Reload und alles ist verloren

* Wieso? Jedes Browsermaker hat Interesse jede Webseit zu können

--- 

## Anwendungen: Cooles Ding verstehen

* "Wie ist das in HTML gemacht?"
* "Wie reagiert die Darstellung, wenn diese CSS Regel weggeht?"
* Ich will eine JSF-Seite schreiben... wie sieht das HTML aus?
* Ein Bisschen JavaScript in der Console
	* ... so kann ich das Elemnt finden...

--- 

## Anwendungen: Datenschutz überprüfen
* Netzwerk 
	* Welche Domäne werden aufgerufen
	* Welche Information wird geschickt?
* Cross-Domain-Schutz:
	* Kann dieses Skript diese Information lesen?

--- 

## Anwendungen: Performanz optimieren
* Cascade View in dem Netzwerk
	* zeigt Ressourcen die langsam laden
* Mit Recording oder nur Network
	* zeigt Folge der JS-Events

--- 

## Anwendungen: Automatisieren
* zB bei der Bibliothek durchblättern
* Der Cache mit Liederdateien füllen
* _Screenscraping_
	* soweit wie Selenium