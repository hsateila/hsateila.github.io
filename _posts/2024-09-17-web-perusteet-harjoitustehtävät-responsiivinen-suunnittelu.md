---
layout: post
title: 'Web-perusteet: Harjoitustehtävät, Responsiivinen suunnittelu'
date: 2024-09-17 11:12 +0300
categories: [Opintojaksot, Web-perusteet]
---
_Mahtavat kiitokset Teemu Pölkille tämän materiaalin pohjana toimineesta englanninkielisestä opetusmateriaalista._

# Responsiivisten verkkosivujen suunnittelu
Responsiivinen suunnittelu verkkosivujen yhteydessä tarkoittaa sellaista ulkoasusuunnittelua, jossa sivupohja sopeutuu laitteeseen ja ruutukokoon jolla sivustoa tarkastellaan. Muutamia esimerkkejä responsiivisesta suunnittelusta ovat [Fazer](https://www.fazer.fi/), [The Boston Globe](https://www.bostonglobe.com/) ja [Helsingin Sanomat](https://www.hs.fi/). Selaa sivuja ja muuta selainikkunan kokoa jolloin näet miten sivu käyttäytyy pienemmässä ikkunakoossa. Tarkastele sivuja myös puhelimellasi.

Selaimen kehittäjätyökaluilla voi myös tarkastella sivuja simuloiden näkymää erilaisilla laitteilla:

![Kehittäjätyökalut ja responsiivisuus](/assets/media/webtools-responsive.png){: width="400" }

Kun saat hieman käsitystä siitä mikä responsiivisen suunnittelun ajatus on, tutustu seuraavaan materiaaliin:
- [Beginner's guide to media queries (MDN)](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries)
- [Historiaa: Responsive Web Design - ensimmäisiä artikkeleita responsiivisuudesta](https://alistapart.com/article/responsive-web-design/)
- [MDN:n dokumentaatio responsiivisesta suunnittelusta](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)

[Media queryt](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries) mahdollistavat erilaisen laiteriippuvaisen ulkoasun ja tyylien luomisen samalle sivulle. Laitteiden ja ruutujen tyyppi, leveys, suunta ja tarkkuus (resoluutio) vaihtelee, joten erilaisia laitteita on huomioitava sivuston suunnittelussa. Lähtökohtana on nykyisin käytännössä aina niin sanottu **_Mobile First_** -suunnittelufilosofia, joka perustuu siihen faktaan että suurinta osaa sivustoista käytetään nykyisin voittopuolisesti erilaisilla mobiililaitteilla (puhelimet, tabletit) ja niissäkin sekä pysty- että vaakatasossa.

Media queryillä voidaan sovittaa ulkoasu erilaisille laitteille, mutta jotta päästään todelliseen responsiiviseen suunnitteluun, elementtien tulee skaalautua suhteessa näyttöruudun (viewport) kokoon. Tämä saavutetaan niin sanotun **_Fluid layout_** -suunnittelutavan avulla.

> Perusajatuksena puhdas HTML-rakenne ilman tyylittelyjä on lähtökohtaisesti **Fluid layout**: se muotoutuu ruutukoon muuttuessa automaattisesti. Voit testata tätä kommentoimalla kaikki tyylitiedostot pois HTML-tiedostostasi väliaikaisesti.
{: .prompt-info }

# Box-sizing property!
> Alla oleva on syytä sisäistää hyvin, sillä se vaikuttaa kaikkeen siihen mitä jatkossa teemme!
{: .prompt-warning} 

**```box-sizing``` -CSS-propertylla määritellään se, miten elementin kokonaisleveys ja korkeus lasketaan.**

Oletusarvo propertylla on CSS:n normaali laatikkomalli, jossa antamasi leveys- ja korkeusarvot renderöidään elementin **sisältölaatikolle**. Tässä tapauksessa, jos elementillä on minkäänlaista reunaviivaa (border) tai täytettä (padding), ne _lisätään_ kokonaisleveyteen antamiesi arvojen päälle. Lopullinen, näytettävä leveys on siis suurempi kuin antamasi arvot. Tästä johtuen joudut säätämään antamiasi leveys- ja korkeusarvoja kun haluat huomioida reunaviivan ja padding-arvon koko laatikon leveydessä.

**Esimerkki:** jos asetat leveydeksi 25%, itse sisältölaatikko on kyllä tuon levyinen, mutta tähän päälle lisätään borderin ja paddingin leveys. Jos sinulla siis on neljä laatikkoa joiden leveys on 25%, ne eivät mahdu näyttöruutuun koskaan vierekkäin koska mukaan lasketaan päälle aina border ja padding.

```box-sizing: content-box``` asettaa oletusarvoisen CSS box-sizing-toiminnallisuuden. Jos asetat elementin leveydeksi 100 pikseliä, elementin sisältölaatikon leveys on tällöin 100 pikseliä leveä, ja tähän lisätään päälle border ja padding jos sellaisia on elementille annettu. Tästä muodostuu laatikon lopullinen, näytettävä leveys, jolloin lopullinen laatikko on leveämpi kuin 100px. Esimerkiksi

```css
.box {
  width: 350px;
  border: 10px solid black;
}
```
renderöi laatikon jonka leveys on 370 pikseliä.

```box-sizing: border-box``` kertoo selaimelle että leveyteen täytyy laskea mukaan border ja padding -leveydet, mikäli sellaisia on elementille annettu. Jos asetat elementin leveydeksi tässä tapauksessa 100px, 100px sisältää tällöin sekä reunan että täytteen leveyden. Sisältölaatikko sen sijaan kutistuu vastaavasti näiden leveyden verran. Esimerkiksi sama yllä oleva koodi tällä propertyn ```box-sizing:```arvolla ```border-box```

```css
.box {
  width: 350px;
  border: 10px solid black;
}
```

näyttäisi laatikon jonka leveys on 350 pikseliä, mutta itse sisältölaatikon koko olisi tällöin 330px.

## 45. Setting up towards Responsive Design.
Download rwdex.zip and extract it. The package contains a simple webpage with mobile first layout. Your job is to create a responsive website according to the specifications and layouts given to you in the following images. There are three mediqueries provided to you, to which you must make the changes.

Convert all the fonts, margins and paddings to rem (or em)
How the site looks at its default settings. Top., Bottom.

## 46. 564px
Example pictures on what you need to do. Viewport width was set to 650px. Top Bottom

Create a mediaquery, that is taken into consideration when the website is wider than 564 pixels.
The headers are quite close to the edge of the #container add a rule that sets the margin of the left side to be one root elements font size.
Hide the “Jump to navigation text”
Move the navigation element from the bottom of the site to the top of site. DO NOT MODIFY HTML! Remove the grey background. Set the list items within the navigation to be inline.
Set a margin of 0.5 rem to right side and margin of 1rem to left side
For the list items that are inside nav element add 0.5rem of padding to the top and bottom and zero the padding of the left and right side. Use :hover pseudo-class to change the background color to be lighter
Centre the images within their container

## 47. 700px
Example pictures on what you need to do. Viewport width was set to 750px. Top Bottom

The pictures are too big for the screen, its time to scale them down and float them to left and right.

- Create a mediaquery, that is taken into consideration when the website is wider than 700 pixels.
- Use float: left and float: right for the respective classes and set the width of the images to be 45%

## 48. 850px
Example pictures on what you need to do. Viewport width was set to 1200px. Top Bottom

The extra width means, that we can now move the aside element to the right side of the screen and move the navigation to top right corner of the page!

- Create a mediaquery, that is taken into consideration when the website is wider than 850 pixels.
- Move the navigation links to top right corner of the website
- Scale down the content div and the aside element using percentages. Add some percentage of margin to the aside element. The percentages should amount to 100%
- Float the elements left and right as you see fit
- Also set maximum width for the container (around 1000px is fine) and set it to automatically centre itself within its container
- Set the padding of footer element to be 1rem. Also set background color. You might find yourself an issue here with the floats and the background color. Fix it with the help of this article

# Grid and Flex

## 49. Introduction to concepts
Go play and complete these games

- [Flexbox Froggy](https://flexboxfroggy.com/)
- [Flexbox Defence](http://www.flexboxdefense.com/)
- [CSS Grid Garden](https://cssgridgarden.com/)

Go through the following tutorials on [Flexbox](https://scrimba.com/g/gflexbox) and [CSS Grid](https://scrimba.com/g/gR8PTE). You can start to modify the presented code, to test things out, at any point and then when you continue the tutorial, it will save your changes under the notes tab on the right.

## 50. New project, another HTML5 assignment
Create a new folder and copy the example XHTML code to recipes.html file. Copy also all the related images (citrus, logo, ads and recipe images) and save them in a subfolder “pics”. Correct the references to the images. Convert recipes.html into html5 (see info about declaring language in html5). Replace sectional div elements (when necessary) with new html5 elements (more information). Validate.

## 51. Weird flex, but ok
Use Flexbox to add some responsivity to the ads on the page! The images should stay on the same row until there is no more room. After that they should wrap. Add some margin for the ads inside the flex-container. Use descendant selectors!

Example 1
Example 2
Example 3

## 52. Pics in a grid

### Part 1.
Create a copy of the original file and name it “food_gallery.html”. Link the pages (create a new link to the nav section that points to the “food_gallery.html” file link back to the original page from food gallery).

Remove the main contents of the page. Leave header, navigation, footer, aside and ads.

### Part 2.
Find some food pics from ccsearch (or use these). Save them into a folder you can find ’em

Create a new CSS grid element in which you will create a picture gallery, see example (don’t mind the blue “borders”, its just firefox telling you guys where the grid borders are!). Grid should have three columns and as three rows.

Add a small gap between the rows and the columns and center the images vertically.

### Part 3.
Create a media query that decreases the amount of columns to two when the images get too small. See an example.

### Part 4.
Create a media query that turns the CSS grid into a flexbox column! See an example