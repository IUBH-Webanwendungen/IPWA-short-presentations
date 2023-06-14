# Quick Response Codes (QR codes)

## Web-anwendungen IUBH
## 2023-06-14 Paul Libbrecht CC-BY

--- 

## Wozu?

- Handys und Computers haben Cameras
- ... dann sollen sie auch lesen
- ... dieses verlässlich
- Starke Nachfrage der automatisierte "Bar-Code-Lesen"
	- aber grösser, und mit Kamera (nicht Laser)
- originellerweise für Autoteile produziert
- Jetzt überall

- - - 

## Zutaten

* Enkodiert ein "String", max 1800 chars
* Gemacht aus
	* 3 grosse Quadrate (Kamerakalbirierung)
	* innere Inhalt
	* viele Wiederholung und Fehlerkorrektur
* Einscannen heisst: 
	* Finden und dafür scharf machen
	* Dekodieren bis es mit der Fehlerkorrektur klappt
	* Übermitteln
* Gestalten heisst:
	* Nachricht empfangen, Kodieren, Bild produzieren, anzeigen

- - -

## QR Code Scannen: Wozu?
* jede App kann die Bibliothek aufrufen
* Buchstaben ergeben...
	* Internetadresse
		* oder eine Weiterleitung
	* Teilenummer
	* Willkürliche Zeichen...
	* die App entscheidet
* Scanning kann auch Winkelinfos geben
	* Positionierung

---
## Werkzeuge

* "zu leicht": Webseite für ein Link
	* meist ein Datenschutzproblem
* [qrencode CLI-Befehl](https://fukuchi.org/works/qrencode/): generiert PNG schnell
* generatoren: [JS-Bibliothek qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator#readme) oder [qrcode lib](https://www.npmjs.com/package/qrcode) (meist zeichnen au einem Canvas)
* [nimiq qr-scanner](https://github.com/nimiq/qr-scanner)
* lots lots more
- - - 

## Weitere Perspektive

* NFC oder RFID statt QR?
* ... oder Bluetooth
* ... oder Airtags

* QR: Nachrichtenfluss klar