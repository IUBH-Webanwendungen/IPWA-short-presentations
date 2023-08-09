# Package Managers

## Web-anwendungen IU Internationale Hochschule
## 2023-08-09 Paul Libbrecht, B Ledoyen
[CC-BY](https://creativecommons.org/licenses/by/4.0/)

--- 

## Menu

- Concepts: Build system, Package, Dependencies
- Classics (makefile, ant, maven, gulp...)
- In the JS world: NPM, Yarn, PNPM
- Take-away

--- 

## Concept: Build System

- Goal: we need to build a system that's ready to run
	- web: ready to serve to (contemporary) browsers
	- desktop: ready to run on a (contemporary) OS
- libraries: ready to be integrated archives
	- ... from a set of sources:
- source code (instructions, forms, schemas, styles...)
	- resources (images, icons, ...)
	- from you: editable sources
	- from others: packaged archives (dependencies)
- a build system transforms and links => distributable archives

---
## Concept: Package Repository

- Goal: distribute archives by their name and versions
	- archives: results of build, maybe with source, may need an install
- Allows a source to reference a dependency: 
	- e.g. bootstrap: some CSS and some JS
	- e.g. [chokidar](https://www.npmjs.com/package/chokidar): watch file-system "well"
- Generally: open-source projects
- Web-page documentation: current version, docu, security warnings...
- A dependency is downloaded, and installed
	- the installed result is platform dependent
	- project-local folder, user-global folder, in the PATH

---
## Classics

- C-world: Makefile
	- only a build system, subtle syntax, script-based, dependencies as libraries (checked by configure)
	- see [Makefile book](https://www.oreilly.com/openbook/make3/book/), [GNU Make](https://www.gnu.org/software/make/manual/make.html)
- PHP: Composer, Pear; Perl: CPAN;  TeX: CTAN; Linux: Debian, Bouwer, ...
- Java world: 
	- [Apache Ant](https://ant.apache.org/): procedural, xml-based
	- [Apache Maven](https://maven.apache.org/): declarative, xml-based, repository based
	- both widespread cross-platform
	- Maven paved the way "by convention"

---

## JS Package Managers

- building web projects
- we want to:
	- reference dependencies
	- invoke build scripts
	- follow widespread best practice
	- execute any command with the proper connections to dependencies
- also: be able to build and bundle it all (=> bundlers! webpack, vite, ...)
- cross-platform
- dependencies: included or as developer-tools

---
## Package Manager for JS: NPM

- [NPM](https://docs.npmjs.com/about-npm):
	- from ~2009, as the default package manager of NodeJS (then nascent)
	- now purchased by GitHub
	- a repository
	- a command-line tool
- uses HTTPS to download dependencies or can use git
- installer tool: `node-gyp`
- uses `package.json` files
- stores dependencies in `node_modules`

---
## Package Manager for JS: Yarn

- [Yarn](https://yarnpkg.com/)
- as alternative to NPM with more readable output
- employs terminal color and...
- caches downloads
- pluggable operations (e.g. fetch or install)
- aims at _monorepos_
- developed by meta, google, ember

---
### Candidates PNPM

- [PNPM](https://pnpm.io/)
	- uses hard-links to a single store of dependencies
	- claims to be twice as fast
- Pnpm: _performant npm_
- may break if expecting a recursive `node_modules/x` ([here](https://pnpm.io/faq#pnpm-does-not-work-with-your-project-here))
- small community
- developed by independent developers

---

## Example practice
- npm init, npm run xxx
- yarn init, yarn xxx
- pnpm init, pnpm xxx
---
## Take away

- Package-managers can fetch dependencies
	- can run tasks
	- can run bundlers
	- can do so well?
- How to create an eco-system of dependencies?
	- e.g. within a company
- Alternative perspectives:
	- Some say: cross-platformness? Docker!

---