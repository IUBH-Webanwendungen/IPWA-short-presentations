# PostCSS

## Web-anwendungen IUBH
## 2023-11-22 Paul Libbrecht

--- 

## Motivation

* Jeder versteht CSS, die Syntax ist einfach
* Neue Features: nicht immer implementiert
	* und das ändert sich
* Ein CSS Prozessor ist nötig
	* auch mit Modulen
* Aber es muss dynamisch sein
	* Anforderungen ändern sich ständig
* ... das versucht PostCSS zu sein
--- 

## Die Idee von PostCSS

* Ein kleines Paar:
	* Parser => AST
		* lässt plugins darauf laufen
	* AST => CSS
* Plugins sind das Kern
* ... und sind sehr viele
* 
--- 

## Arbeitsmethoden

* integriert in meist Bundlers: inkl WebPack, Parcel, TailwindCSS, VueJS3, ...
* braucht meist ein `postcss.config.js` dabei
	* exportiert ein `config` mit `plugins` Eigenschaft
* Plugins sind mit npm verteilt
* oder mit CLI (`postcss-cli`)
	* `postcss --use autoprefixer -o main.css css/*.css`

---
## Syntax
* zB verfolgend dem Tutorial an Digital Ocean [hier](https://www.digitalocean.com/community/tutorials/css-postcss-cssnext-cssnano)
* Achtung: die Syntax kann von Plugins erweitert werden
--- 

## Dinge die sonst unmöglich sind

* inspiriert aus [A Sitnik: PostCSS The future after Sass and LESS](https://www.youtube.com/watch?v=1yUFTrAxTzg) 
	* colorblind: Ersatz der Farbnamen
	* rtlscss: Spiegelung von allen Werten
	* autoprefixer: --moz und anderen... mit Wertabbildung!
	* CSSnext: CSS4 in normalen Browsers

--- 