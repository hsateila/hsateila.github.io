---
title: Mocha & Chai -testausympäristön asennus
author: Heikki
date: 2024-02-22
category: Jekyll
layout: post
---

1. Luo itsellesi hakemisto, mihin tulet tekemään testauksen tehtävät. Aja terminaalilla tässä hakemistossa komento {% highlight bash %}npm init -y{% endhighlight %} Hakemistoon pitäisi ilmestyä tiedosto `package.json`. Jos näin ei käy tai saat jonkun virheen, sinulla ei todennäköisesti ole asennettu Nodea. Asenna se haluamallasi tavalla, esim. [NodeJS:n verkkosivuilta](https://nodejs.org)

2. Aja terminaalilla luomassasi hakemistossa komento `npm i -D eslint eslint-config-google eslint-config-prettier prettier`. Nyt hakemistossa pitäisi olla myös tiedosto `package-lock.json` sekä uusi hakemisto, `node_modules`.

3. Luo hakemistoon tiedosto `.eslintrc` (huom! ei tiedostopäätettä) ja kopio siihen seuraava koodi:

{% highlight json %}
{
   "extends": ["google", "prettier"],
   "parserOptions": {
      "ecmaVersion": 2020
   },

   "env": {
      "es6": true,
      "node": true
   },

   "rules": {
      "require-jsdoc": "off",
      "max-len": "off",
      "padded-blocks": "off",
      "no-console": "off",
      "space-unary-ops": "off",
      "eol-last": "off",
      "func-names": "off",
      "no-param-reassign": "off",
      "linebreak-style": "off",
      "one-var": "off",
      "no-inline-comments": "off",
      "one-var-declaration-per-line": "off",
      "strict": "off",
      "spaced-comment": "off"
   }
}
{% endhighlight %}

Nyt sinulla tulisi olla konffit samoin kuin muilla ohjelmoinnin kursseilla.

4. Asenna mocha & chai ajamalla terminaalissa komento `npm install mocha chai --save-dev` hakemistossa.

Nyt package.json-tiedostossasi tulisi olla jotakin tämän näköistä:

{% highlight json %}
"devDependencies": {
"chai": "^4.3.7",
"eslint": "^8.35.0",
"eslint-config-google": "^0.14.0",
"eslint-config-prettier": "^8.6.0",
"mocha": "^10.2.0",
"prettier": "^2.8.4"
}
{% endhighlight %}

5. package.json tiedostossa on kohta `scripts`, jossa lukee `test: "echo \"Error: no test specified\" && exit 1`

Päivitä se alla näkyvään muotoon:

{% highlight json %}
"scripts": {
"test": "npx mocha"
}
{% endhighlight %}

6. Luo ympäristömme testausta varten uusi hakemisto päähakemiston alle, ja anna sille nimeksi vaikkapa "laskin". Lataa laskin_koodit.zip-tiedosto, jossa on tiedostot laskin.js ja laskinTest.js. Siirry laskin-hakemistoosi (tai miksikä sen nimesit), ja siirrä laskin.js sinne. Luo uusi hakemisto nimeltä "test", ja siirrä laskinTest.js-tiedosto sinne.

7. Aja terminaalissa komento "npx mocha" siinä hakemistossa, jossa laskin.js on.

8. Terminaaliin tulisi tulla tuloste, joka kertoo yhden testin onnistuneen, ja yhden epäonnistuneen.
   Tulosteen tulisi näyttää enemmän tai vähemmän tältä:

Laskimen testaus
1 + 1 = 2
√ Tarkistetaan, että plusLasku-funktio palauttaa oikean summan yhteenlaskulla 1 + 1 1) Tarkistetaan, että miinusLasku-funktio palauttaa oikean erotuksen vähennyslaskulla 5 - 2

1 passing (8ms)
1 failing

1. Laskimen testaus
   Tarkistetaan, että miinusLasku-funktio palauttaa oikean erotuksen vähennyslaskulla 5 - 2:
   ReferenceError: tulos is not defined
   at Laskin.miinusLasku (Laskin.js:27:39)
   at Context.<anonymous> (test\laskinTest.js:13:31)
   at process.processImmediate (node:internal/timers:471:21)
