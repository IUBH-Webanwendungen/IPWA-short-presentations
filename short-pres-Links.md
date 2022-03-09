# Links

## Web-anwendungen IU
## 2022-03-09 Paul Libbrecht CC-BY
--- 
## Grundidee

* HTML ist voll von Referenz:
	* a href, 
	* Bilder (und von den Aufgerufenen)
	* JavaScript (und von den Aufgerufenen)
	* stylesheets (und von den Aufgerufenen)
--- 

## Grundkonzept HTTP Ressource
* Anwesend seit HTTP/1.0
* In HTTP, ein Ressource ist eine _Repräsentation_
	* in Bytes, mit Typ (zB HTML, Bild...)
	* die ab einer Adresse abgerufen werden kann
	* meist einfach "GET", aber evtl adaptiv oder mit POST
* Adressen: URLs: 
	* Protokoll, Host, Port, Pfad, Parameter, Frag-ID
	* Pfad: Eine /-separierte Abfolge von "Ordnernamen"
	* Versuchen die Idee von Verzeichnis zu folgen


---

## Ein Link in einer Ressource ergbit ein URL

* Ein Link-string (zB a href Attributwert) beschreibt eine _Bewegung_ von URL
	* Start am URL
	* absolut (mit Protokoll): ersetzt die URL
	* Host-Relativ: (startet mit `/`): selbe Protokoll, Host, Port
	* Relativ:
		* `..`: geht ein Verzeichnis hoch
		* `.`: Bleibt da
		* `blabla`: Name (bis zum letzten `/`) wird ersetzt
	* Parametern und FragID kommen immer dazu
* Der Prozess heisst **URL-Resolution**, **Linkauflösung**

---
## Was zu tun mit einem Link?
* Jedes Link erzielt also eine andere Ressource
* Brower weisst was zu tun durch Elementname:
	* `<a href='...'>`: Klick auf dem Link macht ein GET auf der neuen URL
	* style: lädt mit GET und setzts es als Stil für die Seite
	* JavaScript: lädt mit GET und führt aus
	* CSS-Font: lädt mit GET und macht sie verfügbar
* Eventuell ist eine asynchrone Ladung möglich

---

## Best-Practice: Directories zu URL

* All das war aus der Sicht des Browsers
* Mit einem IDE? Eigentlich will mann relative Pfade hier auch
	* Bild soll daneben sein
	* JS, CSS, ... daneben
	* daneben kann auch heissen `../css/style.css`
* Ein Deployment macht eine Kopie
	* und bewährt alle Verzeichnissstrukrturen
	* Server serviert Verzeichnisse hinter `/directoryName`
* Demo

---

## Broken Referenzen: Was tun?
* Immer zuerst das gründliches probieren: 
	* einfache Bilder... eingetippte URL
* Verzeichnisse prüfen
* Suspekt mit `web.xml` (zB index-files): Kann die Parität Verzeichnisse/URLs brechen
* Im Browser: 
	* Einzelne Links (im Quellformat oder nicht) öffnen, und die Ergebnis der Auflösung ansehen
	* Get-Info
	* Inspector: Netzwerktab: Gibt es 404 oder andere nicht 200?