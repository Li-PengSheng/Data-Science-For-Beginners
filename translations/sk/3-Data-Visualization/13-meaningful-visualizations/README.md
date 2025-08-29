<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "4ec4747a9f4f7d194248ea29903ae165",
  "translation_date": "2025-08-26T16:44:36+00:00",
  "source_file": "3-Data-Visualization/13-meaningful-visualizations/README.md",
  "language_code": "sk"
}
-->
# Tvorba zmysluplných vizualizácií

|![ Sketchnote od [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/13-MeaningfulViz.png)|
|:---:|
| Zmysluplné vizualizácie - _Sketchnote od [@nitya](https://twitter.com/nitya)_ |

> "Ak budete dáta mučiť dostatočne dlho, priznajú sa k čomukoľvek" -- [Ronald Coase](https://en.wikiquote.org/wiki/Ronald_Coase)

Jednou zo základných zručností dátového vedca je schopnosť vytvoriť zmysluplnú vizualizáciu dát, ktorá pomáha odpovedať na otázky, ktoré máte. Predtým, než začnete vizualizovať svoje dáta, je potrebné zabezpečiť, aby boli vyčistené a pripravené, ako ste to robili v predchádzajúcich lekciách. Potom môžete začať rozhodovať, ako najlepšie prezentovať dáta.

V tejto lekcii si prejdete:

1. Ako vybrať správny typ grafu
2. Ako sa vyhnúť zavádzajúcim grafom
3. Ako pracovať s farbami
4. Ako upraviť grafy pre lepšiu čitateľnosť
5. Ako vytvoriť animované alebo 3D grafy
6. Ako vytvoriť kreatívnu vizualizáciu

## [Kvíz pred lekciou](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/24)

## Vyberte správny typ grafu

V predchádzajúcich lekciách ste experimentovali s vytváraním rôznych zaujímavých vizualizácií dát pomocou knižníc Matplotlib a Seaborn. Vo všeobecnosti môžete vybrať [správny typ grafu](https://chartio.com/learn/charts/how-to-select-a-data-vizualization/) pre otázku, ktorú si kladiete, pomocou tejto tabuľky:

| Potrebujete:               | Mali by ste použiť:            |
| -------------------------- | ------------------------------- |
| Ukázať trendy dát v čase   | Čiarový graf                    |
| Porovnať kategórie         | Stĺpcový, Koláčový graf         |
| Porovnať celkové hodnoty   | Koláčový, Stohovaný stĺpcový    |
| Ukázať vzťahy              | Bodový, Čiarový, Facet, Dual Line |
| Ukázať distribúcie         | Bodový, Histogram, Boxplot      |
| Ukázať proporcie           | Koláčový, Donut, Waffle         |

> ✅ V závislosti od zloženia vašich dát môže byť potrebné previesť ich z textového formátu na číselný, aby ste mohli použiť konkrétny typ grafu.

## Vyhnite sa zavádzaniu

Aj keď dátový vedec starostlivo vyberie správny graf pre správne dáta, existuje mnoho spôsobov, ako môžu byť dáta prezentované tak, aby podporili určitý názor, často na úkor samotných dát. Existuje veľa príkladov zavádzajúcich grafov a infografík!

[![Ako klamú grafy od Alberta Caira](../../../../translated_images/tornado.9f42168791208f970d6faefc11d1226d7ca89518013b14aa66b1c9edcd7678d2.sk.png)](https://www.youtube.com/watch?v=oX74Nge8Wkw "Ako klamú grafy")

> 🎥 Kliknite na obrázok vyššie pre konferenčný prejav o zavádzajúcich grafoch

Tento graf otočil os X, aby ukázal opak pravdy na základe dátumu:

![zlý graf 1](../../../../translated_images/bad-chart-1.93130f495b748bedfb3423d91b1e754d9026e17f94ad967aecdc9ca7203373bf.sk.png)

[Tento graf](https://media.firstcoastnews.com/assets/WTLV/images/170ae16f-4643-438f-b689-50d66ca6a8d8/170ae16f-4643-438f-b689-50d66ca6a8d8_1140x641.jpg) je ešte zavádzajúcejší, pretože oko je priťahované doprava, aby dospelo k záveru, že počet prípadov COVID v rôznych okresoch časom klesal. Ak sa však pozriete bližšie na dátumy, zistíte, že boli preusporiadané, aby vytvorili tento zavádzajúci klesajúci trend.

![zlý graf 2](../../../../translated_images/bad-chart-2.c20e36dd4e6f617c0c325878dd421a563885bbf30a394884c147438827254e0e.sk.jpg)

Tento notoricky známy príklad používa farbu A otočenú os Y na klamanie: namiesto záveru, že počet úmrtí na strelné zbrane vzrástol po prijatí legislatívy podporujúcej zbrane, oko je oklamané, aby si myslelo, že opak je pravdou:

![zlý graf 3](../../../../translated_images/bad-chart-3.6865d0afac4108d737558d90a61547d23a8722896397ec792264ee51a1be4be5.sk.jpg)

Tento zvláštny graf ukazuje, ako môže byť proporcia manipulovaná, a to až do komického efektu:

![zlý graf 4](../../../../translated_images/bad-chart-4.68cfdf4011b454471053ee1231172747e1fbec2403b4443567f1dc678134f4f2.sk.jpg)

Porovnávanie neporovnateľného je ďalší pochybný trik. Existuje [úžasná webová stránka](https://tylervigen.com/spurious-correlations) venovaná 'falošným koreláciám', ktorá zobrazuje 'fakty' korelujúce veci ako rozvodovosť v Maine a spotrebu margarínu. Skupina na Reddit tiež zbiera [škaredé použitia](https://www.reddit.com/r/dataisugly/top/?t=all) dát.

Je dôležité pochopiť, ako ľahko môže byť oko oklamané zavádzajúcimi grafmi. Aj keď je zámer dátového vedca dobrý, výber zlého typu grafu, ako je koláčový graf zobrazujúci príliš veľa kategórií, môže byť zavádzajúci.

## Farba

Videli ste v grafe 'Florida gun violence', ako farba môže poskytnúť ďalšiu vrstvu významu grafom, najmä tým, ktoré nie sú navrhnuté pomocou knižníc ako Matplotlib a Seaborn, ktoré obsahujú rôzne overené farebné knižnice a palety. Ak vytvárate graf ručne, urobte si malú štúdiu o [teórii farieb](https://colormatters.com/color-and-design/basic-color-theory).

> ✅ Pri navrhovaní grafov si uvedomte, že prístupnosť je dôležitým aspektom vizualizácie. Niektorí vaši používatelia môžu byť farboslepí - zobrazuje sa váš graf dobre pre používateľov so zrakovým postihnutím?

Buďte opatrní pri výbere farieb pre váš graf, pretože farba môže prenášať význam, ktorý ste možno nezamýšľali. 'Ružové dámy' v grafe 'výška' vyššie prenášajú výrazne 'ženský' pridelený význam, ktorý pridáva k bizarnosti samotného grafu.

Zatiaľ čo [význam farieb](https://colormatters.com/color-symbolism/the-meanings-of-colors) môže byť odlišný v rôznych častiach sveta a má tendenciu meniť sa podľa odtieňa, vo všeobecnosti zahŕňa:

| Farba  | Význam              |
| ------ | ------------------- |
| červená| sila                |
| modrá  | dôvera, lojalita    |
| žltá  | šťastie, opatrnosť   |
| zelená | ekológia, šťastie, závisť |
| fialová| šťastie             |
| oranžová| živelnosť          |

Ak máte za úlohu vytvoriť graf s vlastnými farbami, zabezpečte, aby vaše grafy boli prístupné a farba, ktorú vyberiete, zodpovedala významu, ktorý sa snažíte preniesť.

## Úprava grafov pre čitateľnosť

Grafy nie sú zmysluplné, ak nie sú čitateľné! Venujte chvíľu úprave šírky a výšky grafu tak, aby dobre zodpovedali vašim dátam. Ak je potrebné zobraziť jednu premennú (napríklad všetkých 50 štátov), zobrazte ich vertikálne na osi Y, ak je to možné, aby ste sa vyhli horizontálne posúvanému grafu.

Označte svoje osi, poskytnite legendu, ak je to potrebné, a ponúknite tooltipy pre lepšie pochopenie dát.

Ak sú vaše dáta textové a rozsiahle na osi X, môžete text nakloniť pre lepšiu čitateľnosť. [Matplotlib](https://matplotlib.org/stable/tutorials/toolkits/mplot3d.html) ponúka 3D grafy, ak vaše dáta podporujú tento formát. Sofistikované vizualizácie dát je možné vytvoriť pomocou `mpl_toolkits.mplot3d`.

![3D grafy](../../../../translated_images/3d.0cec12bcc60f0ce7284c63baed1411a843e24716f7d7425de878715ebad54a15.sk.png)

## Animácia a 3D zobrazenie grafov

Niektoré z najlepších vizualizácií dát dnes sú animované. Shirley Wu má úžasné vizualizácie vytvorené pomocou D3, ako napríklad '[film flowers](http://bl.ocks.org/sxywu/raw/d612c6c653fb8b4d7ff3d422be164a5d/)', kde každá kvetina je vizualizáciou filmu. Ďalší príklad pre Guardian je 'bussed out', interaktívna skúsenosť kombinujúca vizualizácie s Greensock a D3 plus článok vo formáte scrollytelling, ktorý ukazuje, ako NYC rieši problém bezdomovcov tým, že ich posiela autobusmi mimo mesta.

![busing](../../../../translated_images/busing.7b9e3b41cd4b981c6d63922cd82004cc1cf18895155536c1d98fcc0999bdd23e.sk.png)

> "Bussed Out: Ako Amerika presúva svojich bezdomovcov" od [Guardian](https://www.theguardian.com/us-news/ng-interactive/2017/dec/20/bussed-out-america-moves-homeless-people-country-study). Vizualizácie od Nadieh Bremer & Shirley Wu

Aj keď táto lekcia nie je dostatočne podrobná na to, aby vás naučila používať tieto výkonné knižnice na vizualizáciu, vyskúšajte si D3 v aplikácii Vue.js pomocou knižnice na zobrazenie vizualizácie knihy "Nebezpečné známosti" ako animovanej sociálnej siete.

> "Les Liaisons Dangereuses" je epistolárny román, alebo román prezentovaný ako séria listov. Napísaný v roku 1782 Choderlosom de Laclosom, rozpráva príbeh zákerných, morálne zbankrotovaných spoločenských manévrov dvoch súperiacich protagonistov francúzskej aristokracie koncom 18. storočia, vikomta de Valmonta a markízy de Merteuil. Obaja nakoniec zahynú, ale nie bez toho, aby spôsobili veľké spoločenské škody. Román sa rozvíja ako séria listov napísaných rôznym ľuďom v ich kruhoch, plánujúcich pomstu alebo jednoducho spôsobujúcich problémy. Vytvorte vizualizáciu týchto listov, aby ste objavili hlavné postavy príbehu vizuálne.

Dokončíte webovú aplikáciu, ktorá zobrazí animovaný pohľad na túto sociálnu sieť. Používa knižnicu, ktorá bola vytvorená na [vizualizáciu siete](https://github.com/emiliorizzo/vue-d3-network) pomocou Vue.js a D3. Keď aplikácia beží, môžete ťahať uzly po obrazovke a presúvať dáta.

![liaisons](../../../../translated_images/liaisons.7b440b28f6d07ea430244fdf1fc4c64ff48f473f143b8e921846eda1c302aeba.sk.png)

## Projekt: Vytvorte graf na zobrazenie siete pomocou D3.js

> Táto zložka lekcie obsahuje priečinok `solution`, kde nájdete dokončený projekt pre vašu referenciu.

1. Postupujte podľa pokynov v súbore README.md v koreňovom priečinku štartovacieho projektu. Uistite sa, že máte na svojom počítači nainštalované NPM a Node.js pred inštaláciou závislostí projektu.

2. Otvorte priečinok `starter/src`. Nájdete priečinok `assets`, kde je .json súbor so všetkými listami z románu, očíslovaný, s anotáciou 'to' a 'from'.

3. Dokončite kód v `components/Nodes.vue`, aby ste umožnili vizualizáciu. Nájdite metódu nazvanú `createLinks()` a pridajte nasledujúcu vnorenú slučku.

Prejdite cez objekt .json, aby ste zachytili údaje 'to' a 'from' pre listy a vytvorili objekt `links`, ktorý môže knižnica vizualizácie spotrebovať:

```javascript
//loop through letters
      let f = 0;
      let t = 0;
      for (var i = 0; i < letters.length; i++) {
          for (var j = 0; j < characters.length; j++) {
              
            if (characters[j] == letters[i].from) {
              f = j;
            }
            if (characters[j] == letters[i].to) {
              t = j;
            }
        }
        this.links.push({ sid: f, tid: t });
      }
  ```

Spustite svoju aplikáciu z terminálu (npm run serve) a užite si vizualizáciu!

## 🚀 Výzva

Prejdite si internet a objavte zavádzajúce vizualizácie. Ako autor klame používateľa a je to úmyselné? Skúste opraviť vizualizácie, aby ste ukázali, ako by mali vyzerať.

## [Kvíz po lekcii](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/25)

## Prehľad a samostatné štúdium

Tu sú niektoré články na čítanie o zavádzajúcich vizualizáciách dát:

https://gizmodo.com/how-to-lie-with-data-visualization-1563576606

http://ixd.prattsi.org/2017/12/visual-lies-usability-in-deceptive-data-visualizations/

Pozrite si tieto zaujímavé vizualizácie historických aktív a artefaktov:

https://handbook.pubpub.org/

Pozrite si tento článok o tom, ako animácia môže zlepšiť vaše vizualizácie:

https://medium.com/@EvanSinar/use-animation-to-supercharge-data-visualization-cd905a882ad4

## Zadanie

[Vytvorte vlastnú vizualizáciu](assignment.md)

---

**Upozornenie**:  
Tento dokument bol preložený pomocou služby AI prekladu [Co-op Translator](https://github.com/Azure/co-op-translator). Hoci sa snažíme o presnosť, prosím, berte na vedomie, že automatizované preklady môžu obsahovať chyby alebo nepresnosti. Pôvodný dokument v jeho pôvodnom jazyku by mal byť považovaný za autoritatívny zdroj. Pre kritické informácie sa odporúča profesionálny ľudský preklad. Nenesieme zodpovednosť za akékoľvek nedorozumenia alebo nesprávne interpretácie vyplývajúce z použitia tohto prekladu.