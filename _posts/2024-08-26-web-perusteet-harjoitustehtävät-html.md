---
layout: post
title: 'Web-perusteet: Harjoitustehtävät, HTML'
date: 2024-08-26 16:08 +0300
categories: [Opintojaksot, Web-perusteet]
---
# Johdanto
HTML on kirjainyhdistelmä sanoista _**H**yper**T**ext **M**arkup **L**anguage_. Se on niin sanottu merkintäkieli, ja sen käyttötarkoitus on määritellä **verkkosivudokumentin** _rakenne_. HTML-dokumentteja voidaan kirjoittaa millä tahansa tekstieditorilla, mutta parasta on tässäkin käyttää editoria joka tukee koodin kirjoittamista. Tällä opintojaksolla käytössä on Visual Studio Code, ja lopputulosta tarkastellaan vapaavalintaisella järjestelmän selaimella.

Lue HTML-materiaali ennen kuin jatkat harjoituksiin.

# Yleiset HTML-elementit
Aivan perusmuotoinen HTML-sivu tarvitsee vähintään kolme pääelementtiä. ```<html>```-elementti pitää sisällään (nesting) kaksi muuta, ```<head>```ja ```<body>```-elementit. Pakollinen ```<title>```-elementti sijoitetaan ```<head>```-elementin sisään, ja kaikki käyttäjälle näkyvä sisältö sijoitetaan ```<body>```-elementin sisään. Oikeasta syntaksista on muistettava pitää huoli jotta sivu toimii oikein kaikilla alustoilla ja erilaisissa ympäristöissä. Dokumentin tyyppimääritelmässä kerrotaan dokumentin kieli ja versio. Dokumentin määritelmän tulee olla ensimmäinen rivi koko dokumentissa.

Elementit on muistettava myös sulkea! Elementti suljetaan lähtökohtaisesti aina sulkevalla tagilla, esimerkiksi ```</head>```. Poikkeuksia kuitenkin on.

Otsikkoelementtejä (esimerkiksi ```<h1>``` on yhteensä kuusi tasoa. Numero elementissä kertoo otsikon tason (ei siis otsikoiden järjestystä!). Tämä tarkoittaa sitä, että dokumentissa voi olla useampia samantasoisia otsikoita.

Linkit luodaan ```href``` _attribuutilla_. Voit linkittää paikallisia tiedostoja käyttämällä _suhteellista_ linkitystä haluttuun tiedostoon, kuten vaikkapa kuvatiedostoon. Suhteellinen linkitys tarkoittaa sitä, että linkki viittaa tiedostoon suhteessa sen tiedoston sijaintiin, missä linkki on. Absoluuttista linkitystä tulee käyttää vain ja ainoastaan linkitettäessä toisille verkkosivuille tai domaineille. Absoluuttisen linkin tulee aina alkaa protokollalla, kaksoispisteellä ja tuplatakakenolla, kuten **http://**, **ftp://** tai ***https://** jota seuraa itse osoite. Esimerkiksi: **https://www.example.com/**

Jos tiedostonimeä linkissä ei anneta, selain yrittää hakea sijainnista oletusarvoisesti tiedostoa jonka nimi on ```index.html```.

## Harjoituksiin valmistautuminen
Jos et vielä ole tehnyt, luo nyt kansio esimerkiksi nimellä "webPerusteet" johonkin sopivaan kansioon. Tässä vaiheessa sijainnilla ei ole suurta merkitystä. Käytä tätä kansiota kaikille harjoituksille sekä lopputyölle. Suosittelen tekemään harjoituksille ja lopputyölle kullekin omat alikansiot "webPerusteet" -kansion alle. Voit esimerkiksi tehdä kansion "helloworld" ensimmäistä harjoitustehtävää varten "webPerusteet" -kansion alle.

## 1. Hello World
“Hello World” eli Hei maailma! on tyypillisesti ensimmäinen harjoitus, opetellaanpa sitten mitä tahansa uutta ATK-asiaa, eikä tässä tehdä poikkeusta. Avaa edellä tekemäsi "helloworld" -kansio Visual Studio Codessa ja luo sinne tavallinen tekstitiedosto jossa on seuraava sisältö:

```html
Tervetuloa [oma nimesi]n verkkosivulle.

Hello world!
```

Avaa verkkosivu käyttäen Live Server -lisäosaa ja haluamaasi selainta. Verkkosivu ei näytä samanlaiselta selaimessa. Miksei?

- Tämä johtuu siitä että verkkoselain tulkitsee HTML-merkintäkieltä. Rivinvaihdot ja kaikki muu rakenne tulee ilmaista selaimelle eksplisiittisesti merkintäkielellä jotta selain osaa näyttää tiedoston sisällön verkkosivuna toivotulla tavalla.

- Jos tiedosto ei näy selaimessa lainkaan tai Visual Studio Code ei korosta koodiasi värein, varmista että olet tallentanut tiedoston oikealla tiedostopäätteellä ```.htm``` tai ```.html```. Visual Studio Codessa on paljon erilaisia työkalusettejä sekä korostuksia (highlighting) tiedostolle joka sinulla nyt on auki.

Jatketaan seuraavaksi lisäämällä joitakin HTML-elementtejä: Käytä ```<h1>``` -elementtiä rivillä joka alkaa "Tervetuloa..." ja ```<p>```elementtiä "Hello world!" -tekstille ja tallenna tiedosto.

Live Server -lisäosan pitäisi nyt päivittää muutoksesi selaimeen saman tien kun tallennat muutokset, ja näyttää nykyisen version sivusta. Sivu näyttää nyt paremmalta, mutta ei vieläkään ole aivan kunnossa koska emme seuraa HTML-merkintäkielen määrittelyä. Validoi luomasi dokumentti [W3 Consortiumin validaattorilla](https://validator.w3.org/#validate_by_input) ja katso lopputulos. Voit leikata ja liimata koodin editorista suoraan sivulle ja ajaa validoinnin "Check" -nappia painamalla. Korjaa koodiasi validaattorin ohjeiden mukaisesti kunnes koodi menee validoinnista läpi.

>**CSS** on lyhenne sanoista Cascading Style Sheets. CSS-tiedostossa määritellään verkkosivun tyylit ja asettelu. Tyylit määrittelevät miten sivu _renderöidään_ eli näytetään selaimessa. Tyylit toimivat yhdessä HTML-elementtien kanssa. CSS-määritykset (declarations) luodaan myös tekstieditorissa, mutta syntaksi eli kirjoitusmuoto eroaa HTML:stä.
{: .prompt-info}

Lue [CSS-esittely](https://www.w3schools.com/css/css_intro.asp) ja [CSS:n syntaksi](https://www.w3schools.com/css/css_syntax.asp).

Seuraavaksi lisäämme tyylimäärityksiä Hello world! -sivulle.

Lisää tyylielementti ```<style>``` HTML-dokumenttisi ```<header>```-osioon tagin sisälle. **Muista sulkevat tagit.** Kopioi alla oleva CSS-koodi alta ja liitä se tyylielementin sisään. Päivitä sivusi selaimessa ja tarkista tapahtuiko mitään. Jos ei, ja Visual Code Studio näyttää virheitä, tarkista VS Coden näyttämät virheet ja tee korjaukset sen antamien ohjeiden mukaisesti. Tämän jälkeen voit validoida sivun koodin, myös CSS-koodin, validaattorilla.

```css
h1 {
  font-family: arial, verdana, sans-serif;
  font-size: 20pt;
  colour: #ccbbcc;
}
```

Muuta samaan tapaan kappaleen (paragraph, ```<p>```) tekstin väriä (käytä vaikkapa väriä ```#ccbbcc```) käyttämällä tyylimääritystä ```<p>```-elementille. Lopuksi aseta sivun taustaväriksi musta koko dokumentille asettamalla property background-color ```<body>```-elementille. VS Code helpottaa työskentelyä värien kanssa merkittävästi koska käytettävissä on sisäänrakennettu värityökalu.

## 2. Harjoittelua lukemalla ja kommentoimalla
Kuvaile kaikki eri osat joita on mukana alla olevassa HTML–koodinpätkässä (snippet). Kuvaile jokainen elementin osa. Vastaus voi olla kaavio tai piirros tai lista elementeistä kuvauksineen.

```html
<h1 id="heading1">This <strong>is</strong> header 1</h1>
```
Lue seuraavat dokumentaatiot. Pyri ymmärtämään niiden sisältö ja tee muistiinpanoja lukemastasi.

- [Ensimmäinen dokumentaatio](https://developer.mozilla.org/en-US/docs/Glossary/HTML)
- [Toinen dokumentaatio](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started)

Nämä dokumentaatiot toimivat pohjana seuraavalle luennolle.

## Jatketaan tehtävien parissa!
Nouda zip-tiedosto tehtäviä varten [täältä](https://tiko.jamk.fi/~hsateila/files/exc1.zip). Tiedostoista muodostuvan nettisivun voi nähdä myös nettisivuna [täällä](https://tiko.jamk.fi/~polkte/webui/assets/samples/exc1/index.html). **Selvitä ja hae [MDN-dokumentaatiosta](https://developer.mozilla.org/en-US/) miten HTML-koodiin tehdään _kommentteja_.**

Pura zip-tiedosto sopivaan paikkaan, esimerkiksi aiemmin tekemääsi opintojaksokansioon. Tehtäväsi on avata tiedosto ja selvittää mitä eri elementit, tagit ja CSS-säännöt tekevät ja kommentoida selvityksen tulos lyhyesti suoraan tiedostoon. Mukana on jo esimerkin omaisesti muutama kommentti. Itse sivun sisällön _EI_ tulisi muuttua. Kirjoita ```<head>```-osioon kommentti jossa kerrot mitä kommentit ovat ja miksi niitä käytetään.

## MHOO 1. (Minä Haluan Oppia ja Osata): Selaimet
Selvitä useimmin käytetyt selaimet ja erityisesti selainmoottorit (engine) joita nämä selaimet käyttävät. Mitä moottoreita selaimet käyttävät milläkin eri alustoilla (mobiili, tablet, konsolit, Windows, macOS, Linux)?

Voiko selaimen moottori vaikuttaa sivun ulkoasuun?

Tee muistiinpanot itsellesi!

## 3. Verkkosivun luominen tyhjästä
Aloitetaan alusta luomalla perusmuotoinen HTML5 -verkkosivu tyhjästä. Tähän sinulla pitäisi jo edellisten perusteella ollakin mallipohja, mutta jos ei, tarkista perusteet [MDN:stä](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics). Harjoitusten 2-8 jälkeen sivun tulisi näyttää [tältä](https://tiko.jamk.fi/~hsateila/files/2-8.png) Ensimmäiseksi, lisää tyhjään dokumenttiin doctype ja kaikki tarvittavat rakenteelliset elementit (html, head, jne). Seuraavaksi lisää sivun pääotsikko (h1, ja sisällöksi "Basic Web Page") ja pari tekstikappaletta (elementti p). Voit generoida niin sanotuksi placeholder-tekstiksi munkkilatinaa helposti joko [lorem ipsum -generaattorilla](https://loremgenerator.io/) tai [Emmet-lisäosalla](https://docs.emmet.io/abbreviations/lorem-ipsum/).

Validoi verkkosivukoodisi W3C-validaattorilla johon löydät linkin ylempää. Jos saat virheitä, korjaa ne yksi kerrallaan ja validoi sivu uudelleen kunnes validointi menee läpi.

## 4. Otsikoiden lisääminen
Lisää kolme alemman tason otsikkoa (h2, sisältö "First Chapter", "Second Chapter" ja "Third Chapter") ja lisää pari tekstikappaletta kunkin otsikon jälkeen. Lisää vapaavalintainen linkki jollekin sivulle jonkin kappaleen tekstin sisään. Validoi sivu.

## 5. Linkkien opettelua
Selvitä kuinka luot linkin _paikalliseen_ sivuun, eli sivuun joka sijaitsee samalla tietokoneella ja samalla nimialueella (domain). Selvitä kuinka tällainen sivun sisäinen linkki eroaa ulkoisesta linkistä.

Luo sivun alaosaan linkki, joka linkittää _sivuun itseensä_ eli juuri siihen sivuun jota parhaillaan muokkaat. Laita linkin tekstiksi "To the top >>>". Suurempi kuin -merkit sisällössä tulisi tuottaa _entiteettien_ avulla jotta ne varmasti renderöityvät oikein.

## 6. Kommentit
Lisää sivutiedostoon sivun puoliväliin _useammalle riville jakautuva kommentti_ jota ei näytetä selaimessa.

## 7. Ylätunniste (superscript), alatunniste (subscript) ja tekstin painottaminen
Muokkaa h2-otsikoita siten että "First Chapter" on muokkauksen jälkeen "1^st^ Chapter". Tee myös seuraavat muutokset:

Lisää alatunniste-esimerkki jonnekin dokumenttiin (katso esimerkkikuvan kappale kolme).

Lue elementtien ```<i>```, ```<b>``` ja ```<strong>```_semantiikasta_. Käytä sopivia elementtejä painottamaan joitakin sanoja.

## 8. Kuvia sivulle
Etsi sopivia, sopivan kokoisia (pieniä) kuvia sivulle. Pyri etsimään materiaalia jota saat luvallisesti käyttää: [kuvat jotka on lisensoitu Creative Commons -lisenssillä](https://search.creativecommons.org/) ovat oikein hyviä tähän. Tallenna kuvatiedosto samaan kansioon jossa muokattavana oleva verkkosivutiedosto on, ja lisää kuva sivulle img-tagin avulla. Tarkista dokumentaatiosta (MDN) miten img-tagia tulee käyttää.

[Lorem Picsum](https://picsum.photos/) on hyvä sivusto joka tarjoaa "placeholder" -kuvia sivuston kehittämisen tueksi. Näiden avulla voit käyttää kuvalinkkejä, eikä näitä kuvia tarvitse tallentaa paikalliseen kansioon ellei välttämättä halua. Lisää sivulle seuraava kuva https://picsum.photos/400/200/ jota klikkaamalla pääsee Jamk:n kotisivulle. Validoi koodi.

## 9. Kuvat ja kansiorakenne
Luo kansio nimeltä ```ìmg``` samaan kansioon jossa muokkaamasi html-tiedosto sijaitsee. Siirrä kuvatiedostot tähän uuteen kansioon ja korjaa kuvaviitteet HTML-koodissasi. Muista käyttää _suhteellista_ eikä absoluuttista linkitystapaa jotta kuvat edelleen toimivat muuallakin kuin omalla koneellasi!

## MHOO 2. Emmet-lisäosan opettelua
Emmet on työkalu Visual Studio Codessa, ja se voi nopeuttaa kehitystyötä merkittävästi. Erityisesti jos (ja kun) käytät paljon toistuvia koodirakenteita, Emmet auttaa hommissa merkittävästi. Lue Emmetin käytöstä [Emmetin dokumentaatiossa](https://docs.emmet.io/) ja [VSCoden dokumentaatiossa.](https://code.visualstudio.com/docs/editor/emmet). Emmetin käytön opettelu helpottaa työtäsi jatkossa merkittävästi joten se on erittäin suotavaa!

Luo uusi tiedosto nimeltä ```emmet_experiment.html```ja testaa siinä työkalua. Käytä Emmetiä kaikissa seuraavissa tehtävissä. [Tältä sivulta](https://tiko.jamk.fi/~hsateila/emmet_exc.html) voit tarkistaa miltä alla olevan kolmen tehtävän lopputuloksen tulisi näyttää.
1. Luo HTML-sivun perusrakenne VSCode-editorissa käyttäen vain yhtä merkkiä
2. HTML body -tagin sisällä: luo ```<div>``` jossa on yksi ```<h1>```sisällä. ```<h1>```pitäisi olla "Hello Emmet!" -teksti sisältönä.
3. Luomasi ```<div>``` -elementin sisällä, ```<h2>``` -elementin alle, luo kolme ```<section>```-elementtiä, joissa kaikissa on sisällä ```<h2>```-elementti sisällä ja näiden kaikkien sisällä kaksi ```<p>```-elementtiä. Yhdessä ```<p>``` -elementeistä tulisi olla luokka (class) nimeltä "outbound". Lisähaasteena, käytä sisäänrakennettua "lorem" -komentoa tuottaaksesi sisältöä ```<p>```-elementtien sisään luodessasi niitä.

# Listat, taulukot, ankkurit ja metaelementit
Näihin palaamme seuraavilla luennoilla!
<!---
Lists, tables, destination anchors and meta elements
Important information below!

Lists allow the author of a document to generate automatically bulleted or numbered lists. An advantage of using lists over manually generating the list elements is that the list bullets or numbers don’t have to be modified manually.

The bulleted list elements are nested within ```<ul>``` tags. Each list element is identified with opening and closing tags for ```<li>``` element. The default bullet in a bulleted is the disc. The bullets may be switched with CSS. The type of an element for a numbered list is ```<ol>```. See examples.

Tables begin with ```<table>``` opening tag and that is where the existance of a border is defined. Each row must be opened and closed separately with ```<tr>``` tags. Each cell is defined with ```<th>``` and ```<td>``` elements. Should cells be combined it may be achieved with rowspan or colspan attributes. More detailed description.

Example of exercises (“Creating a site from scratch” to “Metadata”)

## 10. Lists 1: Bullets and Numbers
Add a bulleted list and a numbered list. Add also a definition list (use appropriate elements, not ul or ol) in which you define terms HTML, CSS and JavaScript.

## 11. Lists 2: Inception Boogaloo
Add a few sublists to the bulleted list. For example

```text
* this is the first main item
  * first sub item
  * second sub item
* this is the second main item
  * first sub item
      * a sub item of a sub item
  * second sub item
```
## 12. Taulukot
[Lue HTML-taulukoista](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics) ja lisää seuraavanlaiset taulukot sivuillesi:

![Taulukkomallit](/assets/media/tables1.png)

## 13. Identifying singular elements
Create unique ids for each heading with id attribute.

Just after the h1 heading insert an unordered list of links pointing to the h2 headings (ie, links to specific parts of a page). Modify the “to the top” link you created earlier in a way that it points to the h1 heading.

## 14. Hello world again??
Insert your favourite Hello World code snippet to your document. Code snippets should be displayed without any formation - for example, the tabs and line breaks are preserved. Search the net for an appropriate element for this purpose.

## 15. Metadata
Insert meta elements (at least charset, author, description, keywords) to your document. Define character encoding as utf-8 (if needed) and set also the same file encoding. Add a couple of non-english characters (eg, cyrillic, greek, simplified chinese etc) to your document. View the page on your browser and make sure that your browser detects the encoding and displays all the characters correctly.

Grouping elements, ids and classes
Important information below!

Div and span elements are used to group elements together to create sections or subsections of a page. Actually, they don’t have any affect the appearance but with CSS they play an important role in designing the layout of a page. Div element is used to group block-level elements whereas span is used to group inline elements only. Also, span elements are typically used to attach special styles to some parts of content.

HTML5 and semantic elements
Important information below!

HTML5 is the current phase of web development. Initial version HTML5 standard was released in October 2014. HTML5 introduced a dozens of new elements and attributes which enhance semantic philosohpy behind the markup. For example, new structural elements can be used to determine different sections of a web page and therefore many “meaningless” div elements are replaced with the semantic elements. New elements include, for example, the following.

header - for page headers, section headers, article headers and such.
nav - for major navigational elements.
section - for sections of the page (usually with a heading).
article - for content that makes sense on its own (eg, news and blog entry).
figure - for images, videos, tables and such which are required in order to understand the content but can be moved away from the primary content.
aside - for support content on a page such as related links and ads.
footer - for footer information at the bottom of other elements
Read Mike Robinson’s article “Let’s Talk about Semantics” to get an idea where to use new elements. Read also Avoiding common HTML5 mistakes. HTML5 Element Flowchart is a handy cheatsheet to start with.

Take your time and read through the following links to get a better picture of HTML5: Dive Into HTML5, HTML5 For Web Designers and HTML-5-tutorial.

## 16. Adding meaning to the tags
Place a wide banner-like (wide and flat) image atop of the page. You don’t have to study PhotoShop, GIMP or any other graphic processing software at this point since you can easily create a banner with online tools, for example Banner Fans is pretty good. Group the banner image and the main header with a semantically correct HTML element.

Insert a semantically correct HTML element to nest the list of links and group the rest of the elements together. Create to the bottom of the page a new semantically correct HTML in which you put copyright information, such as “© copyright by XY”.

Now you should have a document in which the root element (html) consists of four semantic elements (see an example). Refresh your browser. Nothing seems to happen, right? Check the sections of the page with the browsers web developer tools. In order to see those sections in a browser without extensions we need to define some styles (don’t worry, we will be pretty soon there).

## MHOO 3. Developer tools and debugging HTML
Read a few tutorials and articles about Developer Tools built into different web browsers.

EVEN THOUGH THIS IS MHOO, ITS HIGHLY RECOMMENDED YOU DO THIS EXERCISE

Read these:

What are devtools (You can stop at the JavaScript part)
Nira: Chrome Developer tools
Inspecting HTML and CSS
Do the following tutorial from MDN

USE THIS FILE/LINK TO CHECK THAT YOUR ASSIGNMENTS ARE CORRECT BEFORE MOVING ONTO CSS. READY MADE EXC 16 --->