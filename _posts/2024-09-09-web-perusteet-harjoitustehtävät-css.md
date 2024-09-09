---
layout: post
title: 'Web-perusteet: Harjoitustehtävät, CSS'
date: 2024-09-09 15:01 +0300
categories: [Opintojaksot, Web-perusteet]
---
# CSS: käyttö

Cascading Style Sheets eli CSS-tyylit tarjoavat verkkodokumentin julkaisijalle mahdollisuuden hallita julkaisun ulkoasua hyvin tarkasti. Näitä tyylimäärittelyitä voidaan käyttää myös muualal kuin verkkosivuilla. Tyylien käyttämiseksi tarvitaan kuitenkin toimiva HTML-syntaksi ja rakenne kun sitä käytetään verkkosivuston ulkoasun rakentamiseen.

Lue [CSS:n esittely](https://tiko.jamk.fi/~polkte/webui/css.html) ensin jotta pääset jyvälle CSS:n syntaksista eli kieliopista. Seuraavaksi lisäämme tyylimäärityksiä tekemäämme HTML-dokumenttiin ulkoasun muokkaamiseksi.

## 17. Span-elementti
Seuraavan kahden harjoituksen tarkoitus on luoda [suuria alkukirjaimia (drop cap)](https://en.wiktionary.org/wiki/drop_cap). Merkkaa ensin ensimmäisen kappaleen ensimmäinen kirjain ```<span>```-elementillä. Virkistä sivu. Kuten näet, span-elementti itsessään ei vielä vaikuta ulkoasuun millään lailla. Tarvitaan tyylimäärittely jotta span-elementti vaikuttaa sisältöön jollakin tavalla. Tässä mielessä span on samankaltainen div-elementin ja semanttisten elementtien, kuten footer ja section, kanssa. Lisäämme tyylit seuraavaksi.

## 18. Suuret alkukirjaimet
Lisää style-tagin sisään tyylimäärittely span-elementille jotta saat suuren alkukirjaimen käyttöön. Lopputuloksen tulisi sivulla näyttää suurien alkukirjainten osalta [suurin piirtein tältä](https://tiko.jamk.fi/~hsateila/assets/media/ex_17_dropcaps.png). Alla listattuna tarvittavat tyylimäärittelyt. Voit lisätä tyylit kolmella tavalla, jotka on kerrottu aiemmin linkitetyssä CSS:n esittely -ohjeessa.

```css
float: left;
padding-right: 4px;
font-size: 44px;
line-height: 40px;
```

- Tapa 1: Lisää tyyli-atribuutti erikseen joka ikiseen span-elementtiin.
- Tapa 2: Lisää tyylimäärittelyt head-elementin sisässä sijaitsevaan style-elementtiin. Jos lisäsit attribuutit span-elementteihin, muista poistaa ne.
- Tapa 3: Luo tyhjä CSS-tiedosto ja linkitä se HTML-dokumenttiin. Siirrä kaikki tyylimäärittelyt erilliseen CSS-tiedostoon. Poista style-tagi head-osiosxta.

Mikä on mielestäsi paras tapa lisät tyylit HTML-dokumenttiin? Mitkä ovat kunkin menetelmän hyödyt ja haitat? Kirjoita vastaus kommenttina HTML-tiedostoosi.

## MHOO 4. CSS:n debuggaus
Tämä harjoitus jatkaa MHOO3:n pohjalta. Lue [tutoriaali MDN:stä](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Debugging_CSS).

# Marginaalit, värit ja taustakuvat

Koko dokumentille (eli verkkosivulle) marginaalit määritellään body-elementtiin. Kuten muissakin tyyleissä, asetetut marginaalit ajavat ohi niistä mitä selain renderöi oletusarvoisesti jos marginaaleja ei ole määritelty.

Muiden elementtien marginaalit määritellään samaan tapaan aina kyseessä olevalle elementille. Listaelementeille ```<ul>``` tai ```<ol>``` marginaalit tulee määritellä näihin listaelementteihin suoraan, ei yksittäisille listan jäsenille (```<li>``` -elementti).

Mittayksiköistä: CSS-määrittelyissä voi käyttää useita erilaisia mittayksiköitä. Osa näistä on koon suhteen absoluuttisia (esimerkiksi in eli tuuma, cm eli senttimetri, pixel eli pikselikoko). Osa yksiköistä on suhteellisia (esimerkiksi em, joka on suhteellinen sen elementin fonttikokoon jossa yksikköä käytetään, tai prosentti). Lisätietoa [CSS:n mittayksiköistä](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units).

[Värit](https://www.w3schools.com/cssref/css_colors.php) voidaan myös määritellä usealla eri tavalla CSS:ssä. Usein käytetään värin heksadesimaaliarvoa (esim. vaaleansininen #ADD8E6). Nyt, kun CSS3:ssa on esitelty myös läpinäkyvyys väriarvolle, voi olla järkevää tilanteesta riippuen käyttää myös värin RGB-arvoa joka sisältää tiedon läpinäkyvyydestä. Värin voi määritellä myös suoraan värin nimellä (esim. suoraan ```color: blue;```), mutta tätä tulisi käyttää vain aivan perusvärien tapauksessa. Usen värit määritellään yrityksen tai verkkosivun graafisessa ohjeistossa sekä RGB- että heksadesimaaliarvoilla.

## 19. CSS:n lisääminen ulkoiseen tiedostoon
Lisää uusia tyylimäärityksiä ulkoiseen tyylitiedostoon. Määritä koko dokumentin leveydensi 50% ja määritä 16 pikselin marginaali dokumentin ylä- sekä alalaitaan ja 30 pikselin marginaali sekä vasempaan että oikeaan laitaan. Määrittele myös _kahden tyhjän rivin korkuinen marginaali_ ennen jokaista otsikkoa. Vinkki: rivin korkeuden tulisi olla riippuvainen fontin koosta, katso suhteelliset fontit (relative fonts).

## 20. Heksadesimaalit, RGP:t ja alpha-kanava
Aseta taustan väri haluamaksesi käyttäen värin heksadesimaalimerkintää ja pääotsikolle haluamasi väri käyttäen RGB-merkintätapaa. Lopuksi määritä h2-elementtien taustaväri RGBA-arvoilla. RGBA:n avulla voit määritellä värille myös läpinäkyvyysarvon.

## 21. Pystysuorat taustat
Etsi jokin sopiva taustakuva, tallenna se img-kansioon ja aseta se taustakuvaksi koko dokumentille. Aseta taustakuva toistumaan vain vertikaalisesti (pystytasossa), ei horisontaalisesti (vaakatasossa).

Luo myös pystysuora liukuväritausta tekstikappaleille. Voit tehdä liukuväritaustakuvan vaikkapa [Gradient Image Makerilla](https://angrytools.com/gradient/image/). Määritä taustakuva toistumaan vaakatasossa ja määritä taustan väri niin että se on sama kuin taustakuvan liukuvärin alin väri. Esimerkkilopputuloksen näet [tästä](https://tiko.jamk.fi/~hsateila/assets/media/gradient_example.png).

CSS3:n avulla voi tehdä liukuvärin suoraankin. Voit etsiä tähän ohjeet nyt, mutta tähän palataan myöhemminkin.

Lisätietoa taustan ominaisuuksista löydät täältä: [Background properties](http://www.tizag.com/cssT/background.php).

## 22. Värien määrittely
Määritä fonttien värit kappaleille ja otsikoille.

# ID't, luokat ja kontekstisidonnaiset valitsimet

Jotta homma helpottuu, yllä olevat termit englanniksi ovat _id_, _class_ ja _contextual selector_.

<!--

IDs, classes and contextual selectors
Important information below!

The id attribute is used to uniquely identify any element within a page. Identifying an element enables you to create styles and scripts specific to that element. The value of the id attribute can be chosen at will and each value can appear only once in a document. Ids are specified with hash marks in CSS. For example, HTML: <div id="hero"> or <img id="big-logo">, CSS: #hero {color: black;} or #big-logo {width: 100%;}

Class attribute is used to specify that an element belongs to a class of elements. One class can contain many elements - actually different kind of elements can belong to the same class. An element can belong to more than one group. Classes are marked with a dot in CSS. For example, HTML: <h1 class="red">Header</h1><p class="red">Some text</p><h1 class="red">Second header</h1>, CSS: .red {color: red;}

Moreover, contextual selectors can be used for selective styling. In order to use the following selectors you have to understand the document object model (DOM). In a nested tag set, the outer element is called the parent and the inner element is the child. The child element and any children of that child are the parents’ descendants. Two elements in the same parent are called siblings, and two elements immediately next to each other are adjacent siblings.

a b c == descendent (c descendent of b descendent of a) / div.copy h1 em {color:red;}
a * b == universal (b within a regardless of b’s parents) / div.copy * em {color:red;}
a > b == direct child (b direct child of a) / div.copy > p > em {color:red;}
a + b == adjacent sibling (sibling b immediately after a) / p + p em {color:red;}
a ~ b == general sibling (sibling b anywhere after a) / p ~ p em {color:red;}
See an example. More examples.

Examples of exercises after exercise 35 (image 1, image 2 and image 3).

24. Semantics once again
If you haven’t already, use HTML5 elements nav, header and footer to signify those parts of the page. Header should contain the banner and main heading, nav contains the list of links and footer contains copyright information. Use a div with id content which contains the second level headings and paragraphs and all the other stuff.

25. Background for navigation
Search another nice background image and set it as a background image for the nav section. Position that background image to the top right corner of the nav element.

26. Spanners spanners
Let’s suppose that you want to emphasize certain words or sentences (for example, warnings) in your document but instead of bolding or italicizing them you want them to appear red. Select a couple of words and mark them with span element. Refresh. As you can see, you have a small problem. Solve it by creating a couple of classes: class dropcap contains style declarations for the drop caps and class “warning” contains a style declaration for displaying an element with red color. After creating CSS classes, modify your HTML document in the corresponding way.

27. Containers
Part 1.
Wrap the whole content (from the body start tag to the body end tag) within a new div element. Name it as container. This container div is typically added to nest body elements when writing a HTML document. Why?

Part 2.
Set a fixed width for the container div (remove width declaration from body element) and position it horizontally in the middle of the browser window (remove also margin declarations from body element). Note that the page should be in the middle no matter what the browser window width is.

Part 3.
Comment out (CSS uses /* and */ syntax for comments) the background-repeat: repeat-y declaration (body element) and set background color for the container div.

MHOO 5. BEM
Get to know BEM by watching this video and reading this documentation.

Grab the website at ./bem.html and convert it to use BEM.

Borders and paddings
Important information below!

Border style, width and color may be set simultaneously or with separate parameters. There are different border types (solid, dotted, etc) available. If separate colors or widths are desired then separate declarations are required.

When an element should have space within and outside the element, both margin and padding values ought to be set. The default margin and padding values may differ in various browsers. This is why it is recommended to define these values even though it might seem obsolete. To fully understand margins and paddings you should take a look at the CSS Box model link which can be found at the material folder.

28. Borders & Paddings
Set 1px solid border for the container div. Also, add some padding to the container to give it a bit more air.

What is the actual width of the container div now? Use your browsers developer tools to find out!

29. Tables 2: Electric Boogaloo!
Modify tables in the following way:

add caption HTML element for each table
set a different background color for each table
set a different background color for odd and even rows
decrease the font size of the captions (use percentages, for example, 75%)
decorate caption text as you wish (background color, font color)
change the placement of a caption to the bottom of the table
set margins equating to one lines height above and below caption
30. Borders borders borders
Surround the text paragraphs with a solid 4px border. Embed the text paragraphs, thus set a light color to the top border, some shade for sides and darker color for the bottom.

Set paddings that equal two times the fonts size for left and right sides of paragraphs and 1x root elements font size paddings above and below paragraphs. Use shorthand properties for margins and paddings.

31. Links with dotted borders
Give all images which are also links a dotted border (in our case only the Tiko (if done like the example, but it is the one from exercise 9) logo but write a general declaration by using descendant (contextual) selectors). Leave some space between the image and border and also set small margins around the border.

Pseudo-classes
Important information below!

Many HTML elements have special states associated with them, for example the link tag has at least four different states that can be styled separately. A pseudo-class is a predefined state or use of an element that can be styled independently.

Links: pseudo-classes are used to style normal state of the link (link), how the link appears after it has been visited (visited), how the link appears while a user hovers mouse over it (hover) and how the link appears when a user is clicking it.
Dynamic: pseudo-classes can be applied to any element to define how it appears when a user hovers over it, clicks it or selects it.
Structural: pseudo-classes are similar to the sibling combinatory selectors but allow you to specifically style elements based on an exact or computed numeric position.
32. links with pseudoclasses
Add style definitions for links. Make sure you have defined the following:

link
active
hover
focus
visited
33. Woah
Previously you defined dotted borders to the images which are also links. Now add hover pseudo-class which changes dotted borders to solid borders and displays only top and bottom borders when a user hovers over the image.

34. Structural pseudo classes
Add structural pseudo-class that displays the rightmost cells of each table row with red (or other suitable) background color. Do not touch HTML code this time (ie, do not create classes) but add only CSS stuff.

See an example.

Earlier you set different background color for odd and even rows in table using classes. Now change font color for every second row using pseudo-classes (again, do not touch HTML code).

MHOO 6. Pseudo elements
Read the following tutorials

https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements
https://www.javatpoint.com/css-pseudo-elements
https://web.dev/learn/css/pseudo-elements/
Create another one of those pesky unordered lists and put four list items in it. Use a correct pseudo element to target the marker and change the default style.
Use the ::before pseudo element to change the markers style to an emoji.
Use the right proper pseudo element to change the appearance of selected text. Change the background color to, for example, green.
Positioning
Important information below!

When creating CSS-based layouts it is essential to group elements - so take your time to check your document structure. Typical rendering order can be changed with CSS. Basically, there are different ways of positioning elements and blocks: float and position properties. CSS3 offers us different methods (Grid and flexbox) but we will take a look at those features later.

See CSS positioning 101 and CSS positioning in 10 steps.

35. Disclaimer!!!
Insert the following HTML code snippet between the header and nav sections. Add also style declarations to your CSS file.

<div id="disclaimer">
<img src="http://www.1clipart.com/clipart/signs/exclamation/74-415115695.gif" alt="Note" />
This is an example document for Web Page Development course.  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Curabitur a nisi venenatis velit tempus adipiscing quis ac tellus. Suspendisse egestas luctus hendrerit. Nam pulvinar
sagittis sem a vehicula. Morbi dapibus euismod est ut blandit. Sed vel mauris sapien, vel porttitor magna. Nullam luctus,
lorem eu mattis fringilla, justo lectus malesuada risus, vel viverra ligula eros ac ipsum. Curabitur in felis odio, ut imperdiet
augue. Duis auctor interdum magna, ac porttitor felis porttitor et. Cum sociis natoque penatibus et magnis dis parturient montes,
nascetur ridiculus mus. Donec orci erat, consectetur id dignissim quis, sodales id magna. Sed aliquam accumsan nibh, nec
aliquam nulla aliquam sit amet. Quisque risus tortor, sodales a vulputate vitae, aliquet vitae dui. Integer et magna metus.
Nulla tristique lobortis sapien eu condimentum.
</div>
#disclaimer {
    border: 1px dotted red;
    background-color: #ddd;
    color: #000;
    margin-left: 2em;
    margin-right: 2em;
    margin-top: 0.5em;
    margin-bottom: 0.5em;
    padding: 1em;
}
36. Floating images
Now, make the text wrap around the exclamation sign (see an example). The task is not very complex with a float property. Add also right padding to the image.

37. Floating images pt. 2
Make the text wrap around the one with the link and the image - the same as in the previous exercise except place image on the right this time. To make it a bit challenging modify the code in the following way:

<p><a href="http://www.jamk.fi">
<img src="http://tiko.jamk.fi/~polkte/webui/images/tikoblue.png" alt="JAMK/TIKO" />
</a>JAMK
</p>
This means you have to move the link with the image inside a single “p” element. If you don’t have image with a link, use the above code as is

Add float property and take a look at the paragraph size. Probably it looks like this although it should look this. Confused? Check out a clearfix hack and others with discussion.

38. Absolute position.
Relocate the nav block near the top left corner. Use absolute positioning. Remove left margins from the content. An example. Consider in which situations absolute positioning (related to the viewport) is useful.

39. Just kidding, lets use fixed
Change the value of position property to fixed. What is the difference? When to use fixed positioning?

40. Display properties and values
Modify CSS to display list items in the nav block in a single line (hint: explore display property) and decrease the size of font.

41. Pseudo classes and content via CSS
Create CSS declarations (use pseudo-classes) which automatically adds " *** " before each list item and the same string after the last list item (the nav block looks like this: *** First Chapter *** Second Chapter *** Third Chapter ***). HINT: check content property.

Set the width in a way that it covers the whole browser window. Relocate the nav to the bottom of the web page and use fixed positioning as in the previous exercise.

See an Example.

42. Hiding things when printing
Write a CSS declaration that hides the disclaimer when printing the document. This feature is useful when creating printer friendly stylesheets: you can easily remove ads and navigation links and such from printed version. You can check the result by using browser’s print preview feature.

43. Map of Finland and Jyväskylä rock city!
Insert the map of Finland (the file is located at https://tiko.jamk.fi/~polkte/webui/images/finland.jpg and text “Jyväskylä” to the document. Move Jyväskylä text to the correct location over the map. In this case you can’t use absolute positioning so you probably want to take a closer look at relative positioning.

44. Under construction
Set min-width property for the container div. Add construction image just after the container div and declare an unique id for the element. Set element’s position in CSS so that the image is located in the right top corner of the container div. The construction image must stay in the top right corner of the container div even if the browser window is resized. This requires absolute positioning inside relative positioning.

Examples: image 1 and image 2.
-->