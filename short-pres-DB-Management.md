# Datenbankmanagement

## Web-anwendungen IUBH
## 2022-02-09 Paul Libbrecht

--- 
## Datenbank

* Eine Speicherung von Daten
	* ... aber zugänglich
	* d.h.: mann kann die Daten _pflegen_
* Pflegen? Verwalten?
	* CRUD: Create Read Update Delete
	* at scale!
	* dafür: programmatische Methoden
	* dafür: GUIs
* DB eigentlich DBMS: Datenbank Management System

--- 

## Persistenzlösung auf DB

* Mit Schnittstellen kann mann Daten persistieren
	* ... und wieder, zweckgemäß, herstellen
	* zB JPA, aber mit JPQL Anfragen und IDs
* Persistenz heisst: Es kann zurück gefunden werden
	* Die Menge ist wichtig: zu viel oder zu wenig ein Problem
	* Dafür muss mann modellieren, damit es identifizierbar wird
	* ... und damit es speicherbar ist
* Datenmodellierung ein Beruf
	* Mit Schemas, mit Klassendiagrammen (zB UML), mit Datenassessment
	* im Kurs: einfache Klassen

---

## Datenbank-Pflege

* Starten: Richtig initialisieren
	* mit etwas nützliches
	* mache es, wenn die DB leer ist (... persistence.xml)
	* aus...?
* Sichern:
	* Backups, Exportieren (machbar?), woanders lagern
* Löschen:
	* Mit Alter, auf Anfragen, ...
* Qualität überprüfen
	* AKID nur der Anfang
	* Ist dieser Datensatz nützlich?

---
## DB-Management GUIs
* Jede DB hat seine Werkzeuge zum Zugang
	* oft SQL basiert
	* aber mit GUI
* Klassiker: PHP MyAdmin, MySQL Workbench, ij, ...
* auch Multi-DB (zB in Netbeans)
* Anfragen, blättern, 
* exportieren und importieren

---
## Knochen: Software Updates mit ORM

* Alles geht einfach mit einer JPA Implementation
	* ... bis wenn mann Datenstruktur umändert
	* zB Umbenennung eines Feldes
	* Kann JPA was tun?
* Eine Migration muss stattfinden
	* am Bestens: Low-Level, auf SQL oder CSV
	* ... mit Betracht auf den Daten
	* evtl macht die Migration keinen Sinn für manchen
* Eine der schwierigsten Operationen in Web-Server Deployment
* Ideal: Versionsnummer verwaltet und Upgraders sind für jede Version gebaut.


---
## See also

* [Short Press Backups](short-pres-Backups.md)
