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

[Ensimmäinen dokumentaatio](https://developer.mozilla.org/en-US/docs/Glossary/HTML)
[Toinen dokumentaatio](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started)

Nämä dokumentaatiot toimivat pohjana seuraavalle luennolle.

<!--- Still continuing
Go grab a zip file for the first assignment from here. The page in question is also available here as a web page. Search for the web on how to do comments in HTML and what they are.

Extract the zip to a folder to a some place convenient. Beside you existing assignments is a good place. Your job is to open the file and try and figure out what the different elements, tags and CSS rules do and comment your findings into the file. There are some comments already as an example. The contents of the page shouldn’t change. Use the head section to write a comment, on what comments are and why they are used.

MHOO 1. (Mä Haluan Oppia ja Osata) Browsers
Take a peek and find out what difference there are between different browser engines and browsers. What engines run on what browsers and what browsers run on different platforms (Mobile, tablet, consoles, Windows, macOS, Linux).

Can the browser engine in question change how the web page is drawn?

Take notes, and return those notes.

## 3. Creating a site from scratch
Lets start over by creating a very basic HTML 5 webpage from scratch (you have read the introduction to HTML, right?). Example of the page after exercise 9. First, add doctype and all the required structural elements (html, head, etc). Then add a main heading (h1, content “Basic Web Page”) and a couple of text paragraphs (you can easily produce dummy text with lorem ipsum generator) or with Emmet!.

Validate your webpage. If errors occur, fix them one by one and revalidate the document after each correction.

## 4. Adding headers
Add three lower level headings (h2, contents “First chapter”, “Second Chapter” and “Third Chapter”) and a few text paragraphs after each heading. Place a link to a website of your choice inside any of the paragraphs. Validate.

## 5. Learning to link
Find out how a link to a local web page (ie, web page stored in the same computer) differs from an external link. To the bottom of the page, create a link that points the file itself (as in the current file you are editing). Link text should be “To the top >>>”. Greater than signs should be produced with entities.

## 6. Comments?!
Insert a multiline comment (which is not displayed by the browser) in the middle of the document. 

## 7. Superscript and emphasis
Modify h2 headings as follows: “First Chapter” becomes “1st Chapter” and so on (HINT: superscript). Do also the following:

Add a subscript element somewhere in the document (see third chapter in the example).
Read about semantics concerning i, b, strong and em elements. Use appropriate elements to emphasize a few words.
## 8. Imagine images
Search for a nice small image (images you are allowed to use - not copyrighted material, for example, images licenced under Creative Commons are good), save it into the same folder in which your web page resides and include the image into the document.

Lorempixel and Lorem picsum are websites that provides “placeholder” pictures for your website without needing to save them locally. Add an image with the following address to your page: https://picsum.photos/400/200/ that links to the JAMK homepage. Validate.

## 9. Pictures and folder structure
Create a folder pics under the folder where the html file resides. Move the image file to the pics folder and correct the references in your code. Use relative references, not absolute.

## MHOO 2. Learning emmet
Emmet is a tool built in to the Visual Studio Code and it can speed up development by quite a bit. Especially if you are creating recurring patterns. Read up about Emmet and how to use it on the Emmet docs and VSCode docs.

Create a new file, called emmet_experiment.html and start experimenting on the tool. Use Emmet in all the following tasks. Use the view source on this page to see what the end result should look like.

Create the basic structure for HTML document with only one character
In the HTML body, create a div with h1 element in it. h1 element should have “Hello Emmet!” as its content
Inside the div element you just created, underneath the h2 create three section elements, which all have h2 and a two p elements inside them. One of the two p elements should have a element inside it, with a class named outbound. For added difficulty, use the inbuilt “lorem” command to add content to the p elements when creating them.
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