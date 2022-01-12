# Web-Analytics

## Web-anwendungen IUBH
## 2022-01-12 Paul Libbrecht

--- 

## Bedarf

* Ich will wissen:
	* Wie viel mein Website verwendet wird?
	* Wie (welche Seite / Aktionen / ...)?
	* Welche Benutzer?
	* Wie kommt mann zu mir?
* ... damit ich das beinflussen kann
* Analytics: Besucheranalysewerkzeug
--- 

## Geschichte

* Bildzählern (jeder Bildaufruf)
	* (think: ApplicationScoped)
* Apache Logs, [AWStats](https://www.awstats.org/)
	* ... deiner und meiner Logformat
* Idee von [Transclusion](https://en.wikipedia.org/wiki/Transclusion)
* Mashups, Web-Werbung...
--- 

## Moderne Analytics

* Ein dedizierte Service
* ... kennt allen Browsermodellen
* ... idealerweise: kann alle IPs orten
* präsentiert die Frequentierung
* lässt Rückschlüsse führen:
	* über die Sorte von Benutzer
	* über deren Verhalten
	* über den Wert einziger Seiten

- - -

## Beispiel Analytics-Service: Google Analytics

* Google, auch mit AdWords, hat die Verwendung eines besseren Loggers erfahren
	* Urchin... der hört alles in der Webseite
	* Urchin konnte mann dann kaufen
* Jetzt kann mann sich ein freies Konto mit Google bei [Google Analytics](https://analytics.google.com/) beantragen
* ... und klebt einfach ein Stück JavaScript in den Headers

---
## Praktisch Google Analytics

- Stück JS in seinem HTML
- Im Netzwerktab prüfen (Google wird aufgerufen)
- Im "real Time" prüfen
- Lass uns erproben

--- 

## Google Analytics eine gute Idee?

* Als Webmaster füttert mann Google dadurch
* Ja... Der Service ist frei und von vielen Marketers beliebt
	* kann aber nicht komplett eine eigene Datenkollektion ersetzen
	* etwa um Machine-Learning oder einfach Tabellen zu ziehen
* Pflicht: Im Impressum muss es stehen
	* und eine Opt-Out muss es geben (durch iframes)

---
## Google Analytics: Weshalb?
* BusinessModell: 
	* Durch Profilierung bessere Ads
	* So gross dadurch geworden, dass sie den halben Web beobachten
* Allegmein: Data-brokers ein Problem
* Think: _The social dilemma_ oder _Verdeckt unter Datenhändlern_
* Vieles im Web funktioniert damit
---

## Konkurrierende

* Siehe [alternativeTo](https://alternativeto.net/software/google-analytics/)
* Bekannteste: [Matomo](https://matomo.org/)
	* PHP + MySQL; reiche UI; Firma zum Support
* Auch: [Piwik Pro](https://piwik.pro/) (Deutsche Firma), [Ackee](https://github.com/electerious/Ackee), ...

---

## Zu Betrachten

* Welche Datenkrake füttern Sie?
	* ... und wofür (etwa: gut platzierete Werbung?)
* Welche Clients werden verfolgt?
	* auch diese alte Monster ohne JavaScript?
* Ist das Hosting schnell genug?
	* Verlangsamt es ihre Webseite?
* Welches Tracking ist erwünscht?
	* zB... keine Sequenz wie bei [shynet](https://github.com/milesmcc/shynet#features)?