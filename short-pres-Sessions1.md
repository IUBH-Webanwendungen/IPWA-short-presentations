# Server Sessions

## Web-anwendungen IUBH
## 2021-02-24 Paul Libbrecht [CC-BY](https://creativecommons.org/licenses/by/4.0/) 

--- 

## Basics

* Remember the HTTP Network Inspector:
	* request and response headers
	* especially: Set-Cookies
	* but possibly also "If-Modified-Since"
* HTTP is Stateless...
* Idee eines Cookies:
	* Schreibbare Etikette, für wenn du vorbeischaust
--- 

## Wiedererkennung

* Server-Programmcode: Code dass bei jeder Anfrage läuft
* Erwartung eines Benutzers: _Ich bin es_
	* Anhand der IP?
	* Anhand der Verbindung?
	* Anhand JavaScript (zB Anhand URLs, Tokens)
	* Anhand Cookies

--- 

## Idee einer Sitzung (Session)

* Benutzer kommt und _sitzt_ gegenüber den Server
	* deswährend wird er erkannt
* Lösung: Session-ID
	* zB Set-Cookie: JSESSIONID, Cookie-Header
	* Eine Random Zahl, die eine Zahl am Server entspricht
* Programm-Code des Servers kann Session-Objekte einfügen
	* etwa ein Benutzername
	* etwa ein Shopping-Basket
	* Objekte sind bei jeder Anfrage vorrätig

--- 

## Sessions mit HttpServlet oder JSF

* `session = request.getSession()`
* `FacesContext facesContext = FacesContext.getCurrentInstance();`
`HttpSession session = (HttpSession)` `facesContext.getExternalContext().getSession(false);`

* Objekt: [HttpSession](https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpSession.html)
* Task: debug that
--- 

## Discussion

* Session verloren... was dann?
* JavaScript und Sessions
* Sessions durch Restarts
* Sessions in einem Cluster

--- 
