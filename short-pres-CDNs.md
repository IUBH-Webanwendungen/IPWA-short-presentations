# Content Distribution Networks

## Web-anwendungen IUBH
## 2021-07-14 Paul Libbrecht

--- 

## Einfaches Beispiel: Open Sans

* Du machst eine Webseite
* ... und möchtest ein Font für alle: OpenSans
* selber servieren aus deinem Server?
	* Bandbreite... aber auch keine Gemeinsamigkeit
* OpenSans ist fast überall zu finden
	* lass uns es teilen
	* zB https://www.cdnlib.net/en/Open%20Sans

--- 
## CDNs
* Jeder ist irgendwo anders auf der Welt
* eine Socket öffnen kostet Ressourcen jedermals
* ... also lass die Sockets kurz laufen und benutze ein CDN
	* für alles wo es geht
* zB ein verbreitetes Logo, CSS, JS, oder Font

---

## CDNs: Wie?

* URLs der CDNs finden
* in der HTML code einbetten
* ... und los geht's
* Browsers benutzen die nahen Ressourcen
* Browsers wiederverwenden die Ressources
	* Aber Browsers verbinden sich oft und geben also Informationen

---

## Shared CDNs? Paid CDNs?

* KeyCDN macht interessante [Vergleiche](https://www.keycdn.com/blog/google-fonts-cdn)
	* bessere Kontrolle über die Downloadzeiten
* Shared CDNs ist etwas besser für Caching
	* höhere Wahrscheinlichkeit, dass der Browser es hat
	* wenn es im Cache wiederverwendet werden kann
	* kann es?
	* => WebInspector prüfen, etwa mit [fontCDN](https://thomaspark.co/projects/fontcdn/).