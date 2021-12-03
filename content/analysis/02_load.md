---
Title: Load
Description: Analys av laddningstid på tre olika webbplatser
---


Laddningstid
=======================

I denna rapporten tittar vi på hur lång tid det tar att ladda en webbplats. Vi undersöker tre populära webbplatser med olika webbverktyg och tittar särskilt på hur lång tid det tar att ladda dess bildmaterial.

Urval
-----------------------

De webbplatser som har valts ut är
* <a href="https://www.svt.se/">SVT Nyheter- en webbplats med svenska nyheter</a>
* <a href="https://www.youtube.com/">Youtube - en webbplats med videoklipp som vem som helst kan ladda upp</a>
* <a href="https://store.steampowered.com/">Steam - en webbplats där man kan köpa pc-spel online</a>

Dessa tre webbplatser valdes för undersökningen eftersom de använder många bilder för att fånga användarens intresse.

Metod
-----------------------

För att mäta webbplatsernas laddningstid användes webbverktyget <a href=https://pagespeed.web.dev/>Google pagespeed</a> och Chromes devtools network-flik. Med pagespeed kan man få ut flera olika tidsparametrar. För denna studie så valdes speed index som tittar på hur lång tid det tar för innehållet på sidan att renderas och bli synligt för användaren. Med devtools kan man få ut både storleken på den överförd information samt den totala storleken på sidan. För denna studie observerades båda dessa parametrar.


Resultat
-----------------------

<iframe class="spreadsheet" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vSPp0U6vPTox2ZUKu_kN33tpo5ba91dVSppeuI_wgiwXTCnqVTyJGOkT9WdJN4x-4o7-80ycMcXwDfe/pubhtml?widget=true&amp;headers=false"></iframe>

## SVT nyheter
![Skärmdump webbplats SVT Nyheter](%assets_url%/img/svtnyheter.png){.horiz-img}

SVT:s bildmaterial tog upp ca 37 % av överförda MB vilket känns rimligt. PageSpeed detekterade oanvänd Javascript och CSS-kod samt olämpligt storleksbestämda bilder.

## Youtube
![Skärmdump webbplats Youtube](%assets_url%/img/youtube.png){.horiz-img}

Youtubes bildmaterial tog upp ca 20 % av överförda MB vilket känns rimligt. PageSpeed detekterade både oanvänd Javascript och CSS-kod.

## Steam
![Skärmdump webbplats Steam](%assets_url%/img/steam.png){.horiz-img}

Steam hade överlägset störst filöverföring, både räknat i antal resurser och i överförda MB där bilder tog upp ca 75% av storleken.

Analys
-----------------------

I denna studie kunde vi utifrån data med devtools konstatera att Steam överförde överlägset mest information och SVT överförde minst. Detta speglade resultatet i överföringstiden där det tog längst tid att ladda Steam och kortast tid med SVT. Mätningen med devtool på Steams webbplats försvårades något av att det fanns en slideshow med. Data lästes av efter att sidans innehåll laddats men innan slideshow hann gå över till nästa bild. Intressant nog var Youtube den största webbplatsen sett i total storlek (men däremot inte i överförd storlek).

Data från pagespeed gav en del intressanta resultat. Bland annat var överföringstiden mätt i speed index större för Youtube än Steam vid desktop-mode. Överföringstiden försämrades dock signifikant vid mobile view och betyget för Steam gick ner med hela 50 poäng. Troligtvis är Steams webbplats mest gjord för att fungera på dator snarare än på mobil. SVT klarade sig bäst både vid desktop- och mobile-mode med kortast överföringstid och högst betyg.

Med hjälp av devtools kunde vi se att det framförallt var bilderna på Steam som tog upp mycket plats, ca 75% jämfört 37% på SVT och 20% på Youtube. Rekommendationen på Pagespeed var att göra om bildformat t.ex. från png och jpg till webp och avif. Både SVT och Youtube hade problem med oanvänd Javascript och CSS-kod som tog upp onödig plats.

Om jag själv skulle ranka webbplatserna baserat på de parametrar som presenterats i tabellen ovan så skulle jag göra det enligt hur PageSpeed gjort det. Jag hade gärna sett att det inte tar så lång tid att ladda Steams webbplats som jag besöker i stort sätt varje vecka. Däremot känner jag inte att det tar särskilt lång tid att ladda innehållet på varken SVT eller Youtube. Att SVT vinner som snabbaste webbplatsen kan dock bero på att dess innehåll är det minst avancerade. För min egen del verkar 3-4 sekunder vara gränsen för när det börjar kännas som att webbplatsen tar lång tid på sig.

Referenser
-----------------------

<a href="https://web.dev/speed-index/">Web.dev:s förklaring av Speed Index Parameter</a>

Övrigt
-----------------------

Arbetet genomfördes på egen hand.