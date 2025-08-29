<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8796f41f566a0a8ebb72863a83d558ed",
  "translation_date": "2025-08-28T02:46:34+00:00",
  "source_file": "1-Introduction/02-ethics/README.md",
  "language_code": "tl"
}
-->
# Panimula sa Etika ng Datos

|![ Sketchnote ni [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/02-Ethics.png)|
|:---:|
| Etika sa Agham ng Datos - _Sketchnote ni [@nitya](https://twitter.com/nitya)_ |

---

Tayo ay mga mamamayan ng datos na nabubuhay sa isang mundong puno ng datos.

Ayon sa mga trend sa merkado, sa 2022, 1 sa bawat 3 malalaking organisasyon ay bibili at magbebenta ng kanilang datos sa pamamagitan ng mga online na [Pamilihan at Palitan](https://www.gartner.com/smarterwithgartner/gartner-top-10-trends-in-data-and-analytics-for-2020/). Bilang mga **App Developers**, mas madali at mas mura para sa atin ang pagsasama ng mga insight na batay sa datos at automation na pinapatakbo ng algorithm sa pang-araw-araw na karanasan ng mga gumagamit. Ngunit habang nagiging laganap ang AI, kailangan din nating maunawaan ang mga posibleng pinsala na dulot ng [weaponization](https://www.youtube.com/watch?v=TQHs8SA1qpk) ng mga algorithm na ito sa malawakang saklaw.

Ipinapakita rin ng mga trend na makakalikha at makakakonsumo tayo ng higit sa [180 zettabytes](https://www.statista.com/statistics/871513/worldwide-data-created/) ng datos pagsapit ng 2025. Bilang mga **Data Scientists**, nagbibigay ito sa atin ng walang kapantay na antas ng access sa personal na datos. Nangangahulugan ito na maaari tayong bumuo ng mga profile ng pag-uugali ng mga gumagamit at maimpluwensyahan ang kanilang mga desisyon sa paraang lumilikha ng isang [ilusyon ng malayang pagpili](https://www.datasciencecentral.com/profiles/blogs/the-illusion-of-choice) habang maaaring itinutulak sila patungo sa mga resulta na ating nais. Nagdudulot din ito ng mas malawak na mga tanong tungkol sa privacy ng datos at proteksyon ng mga gumagamit.

Ang etika ng datos ay ngayon ay _mga kinakailangang gabay_ para sa agham at inhinyeriya ng datos, na tumutulong sa atin na mabawasan ang mga posibleng pinsala at hindi inaasahang resulta mula sa ating mga aksyon na batay sa datos. Ang [Gartner Hype Cycle para sa AI](https://www.gartner.com/smarterwithgartner/2-megatrends-dominate-the-gartner-hype-cycle-for-artificial-intelligence-2020/) ay tumutukoy sa mga kaugnay na trend sa digital ethics, responsableng AI, at pamamahala ng AI bilang mga pangunahing tagapagpatakbo para sa mas malalaking megatrend sa _demokrasya_ at _industriyalisasyon_ ng AI.

![Gartner's Hype Cycle para sa AI - 2020](https://images-cdn.newscred.com/Zz1mOWJhNzlkNDA2ZTMxMWViYjRiOGFiM2IyMjQ1YmMwZQ==)

Sa araling ito, tatalakayin natin ang kamangha-manghang larangan ng etika ng datos - mula sa mga pangunahing konsepto at hamon, hanggang sa mga case study at mga inilapat na konsepto ng AI tulad ng pamamahala - na tumutulong sa pagtatatag ng kultura ng etika sa mga koponan at organisasyon na nagtatrabaho gamit ang datos at AI.

## [Pre-lecture quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/2) 🎯

## Mga Pangunahing Depinisyon

Magsimula tayo sa pag-unawa sa mga pangunahing termino.

Ang salitang "etika" ay nagmula sa [salitang Griyego na "ethikos"](https://en.wikipedia.org/wiki/Ethics) (at ang ugat nitong "ethos") na nangangahulugang _karakter o moral na kalikasan_.

**Etika** ay tungkol sa mga pinagsasaluhang halaga at prinsipyo ng moral na gumagabay sa ating pag-uugali sa lipunan. Ang etika ay hindi batay sa mga batas kundi sa malawakang tinatanggap na mga pamantayan ng kung ano ang "tama laban sa mali". Gayunpaman, ang mga konsiderasyong etikal ay maaaring maka-impluwensya sa mga inisyatibo ng pamamahala ng korporasyon at mga regulasyon ng gobyerno na lumilikha ng mas maraming insentibo para sa pagsunod.

**Etika ng Datos** ay isang [bagong sangay ng etika](https://royalsocietypublishing.org/doi/full/10.1098/rsta.2016.0360#sec-1) na "nag-aaral at nagsusuri ng mga moral na problema na may kaugnayan sa _datos, mga algorithm at mga kaukulang gawain_". Dito, ang **"datos"** ay nakatuon sa mga aksyon na may kaugnayan sa paglikha, pagrekord, pag-aalaga, pagproseso, pagpapakalat, pagbabahagi, at paggamit; ang **"mga algorithm"** ay nakatuon sa AI, mga ahente, machine learning, at mga robot; at ang **"mga gawain"** ay nakatuon sa mga paksa tulad ng responsableng inobasyon, programming, hacking, at mga code ng etika.

**Inilapat na Etika** ay ang [praktikal na aplikasyon ng mga konsiderasyong moral](https://en.wikipedia.org/wiki/Applied_ethics). Ito ang proseso ng aktibong pagsisiyasat sa mga isyung etikal sa konteksto ng _mga aktwal na aksyon, produkto, at proseso_, at paggawa ng mga hakbang upang matiyak na ang mga ito ay nananatiling naaayon sa ating mga tinukoy na halaga ng etika.

**Kultura ng Etika** ay tungkol sa [_pagpapatakbo_ ng inilapat na etika](https://hbr.org/2019/05/how-to-design-an-ethical-organization) upang matiyak na ang ating mga prinsipyo at gawain sa etika ay naisasagawa sa isang pare-pareho at nasusukat na paraan sa buong organisasyon. Ang matagumpay na mga kultura ng etika ay nagtatakda ng mga prinsipyo ng etika sa buong organisasyon, nagbibigay ng makabuluhang insentibo para sa pagsunod, at pinapalakas ang mga pamantayan ng etika sa pamamagitan ng paghikayat at pagpapalaganap ng mga nais na pag-uugali sa bawat antas ng organisasyon.

## Mga Konsepto ng Etika

Sa seksyong ito, tatalakayin natin ang mga konsepto tulad ng **pinagsasaluhang halaga** (mga prinsipyo) at **mga hamon sa etika** (mga problema) para sa etika ng datos - at susuriin ang mga **case study** na tumutulong sa iyong maunawaan ang mga konseptong ito sa mga aktwal na konteksto.

### 1. Mga Prinsipyo ng Etika

Ang bawat estratehiya sa etika ng datos ay nagsisimula sa pagtukoy ng _mga prinsipyo ng etika_ - ang "mga pinagsasaluhang halaga" na naglalarawan ng katanggap-tanggap na mga pag-uugali, at gumagabay sa mga aksyong sumusunod, sa ating mga proyekto sa datos at AI. Maaari mong tukuyin ang mga ito sa antas ng indibidwal o koponan. Gayunpaman, karamihan sa mga malalaking organisasyon ay nagbabalangkas ng mga ito sa isang _misyon ng etikal na AI_ o balangkas na tinutukoy sa antas ng korporasyon at ipinatutupad nang pare-pareho sa lahat ng mga koponan.

**Halimbawa:** Ang misyon ng [Responsible AI](https://www.microsoft.com/en-us/ai/responsible-ai) ng Microsoft ay nagsasaad: _"Kami ay nakatuon sa pagsulong ng AI na pinapatakbo ng mga prinsipyo ng etika na inuuna ang mga tao"_ - na tumutukoy sa 6 na prinsipyo ng etika sa balangkas sa ibaba:

![Responsible AI sa Microsoft](https://docs.microsoft.com/en-gb/azure/cognitive-services/personalizer/media/ethics-and-responsible-use/ai-values-future-computed.png)

Suriin natin nang maikli ang mga prinsipyong ito. Ang _Transparency_ at _Accountability_ ay mga pundasyong halaga na pinagtatayuan ng iba pang mga prinsipyo - kaya magsimula tayo doon:

* [**Accountability**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) ay ginagawang _responsable_ ang mga practitioner para sa kanilang mga operasyon sa datos at AI, at pagsunod sa mga prinsipyong etikal na ito.
* [**Transparency**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) ay tinitiyak na ang mga aksyon sa datos at AI ay _naiintindihan_ (interpretable) ng mga gumagamit, ipinaliliwanag ang ano at bakit sa likod ng mga desisyon.
* [**Fairness**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1%3aprimaryr6) - nakatuon sa pagtiyak na ang AI ay patas sa _lahat ng tao_, tinutugunan ang anumang sistemiko o implicit na socio-technical biases sa datos at mga sistema.
* [**Reliability & Safety**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) - tinitiyak na ang AI ay kumikilos nang _pare-pareho_ sa mga tinukoy na halaga, binabawasan ang mga posibleng pinsala o hindi inaasahang resulta.
* [**Privacy & Security**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) - tungkol sa pag-unawa sa pinagmulan ng datos, at pagbibigay ng _privacy ng datos at kaugnay na proteksyon_ sa mga gumagamit.
* [**Inclusiveness**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) - tungkol sa pagdidisenyo ng mga solusyon sa AI nang may layunin, inaangkop ang mga ito upang matugunan ang _malawak na hanay ng mga pangangailangan at kakayahan ng tao_.

> 🚨 Pag-isipan kung ano ang maaaring maging misyon ng iyong etika sa datos. Suriin ang mga balangkas ng etikal na AI mula sa ibang mga organisasyon - narito ang mga halimbawa mula sa [IBM](https://www.ibm.com/cloud/learn/ai-ethics), [Google](https://ai.google/principles), at [Facebook](https://ai.facebook.com/blog/facebooks-five-pillars-of-responsible-ai/). Ano ang mga pinagsasaluhang halaga na mayroon sila? Paano nauugnay ang mga prinsipyong ito sa produktong AI o industriya na kanilang kinabibilangan?

### 2. Mga Hamon sa Etika

Kapag natukoy na ang mga prinsipyo ng etika, ang susunod na hakbang ay suriin ang ating mga aksyon sa datos at AI upang makita kung naaayon ang mga ito sa mga pinagsasaluhang halaga. Pag-isipan ang iyong mga aksyon sa dalawang kategorya: _pagkolekta ng datos_ at _disenyo ng algorithm_.

Sa pagkolekta ng datos, ang mga aksyon ay malamang na may kinalaman sa **personal na datos** o personal na makikilalang impormasyon (PII) para sa mga makikilalang buhay na indibidwal. Kasama rito ang [iba't ibang uri ng hindi personal na datos](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-personal-data_en) na _sama-samang_ makikilala ang isang indibidwal. Ang mga hamon sa etika ay maaaring may kaugnayan sa _privacy ng datos_, _pagmamay-ari ng datos_, at mga kaugnay na paksa tulad ng _may malay na pahintulot_ at _mga karapatan sa intelektwal na ari-arian_ para sa mga gumagamit.

Sa disenyo ng algorithm, ang mga aksyon ay may kinalaman sa pagkolekta at pag-aalaga ng **mga dataset**, pagkatapos ay ginagamit ang mga ito upang sanayin at i-deploy ang **mga modelo ng datos** na nagtataya ng mga resulta o nag-a-automate ng mga desisyon sa aktwal na mga konteksto. Ang mga hamon sa etika ay maaaring lumitaw mula sa _bias sa dataset_, mga isyu sa _kalidad ng datos_, _kawalan ng katarungan_, at _maling representasyon_ sa mga algorithm - kabilang ang ilang mga isyung sistemiko.

Sa parehong kaso, ang mga hamon sa etika ay nagha-highlight ng mga lugar kung saan maaaring magkaroon ng salungatan ang ating mga aksyon sa ating mga pinagsasaluhang halaga. Upang matukoy, mabawasan, mabawasan, o maalis ang mga alalahaning ito - kailangan nating magtanong ng mga moral na tanong na "oo/hindi" na may kaugnayan sa ating mga aksyon, pagkatapos ay gumawa ng mga hakbang upang maitama ang mga ito kung kinakailangan. Tingnan natin ang ilang mga hamon sa etika at ang mga moral na tanong na kanilang itinatampok:

#### 2.1 Pagmamay-ari ng Datos

Ang pagkolekta ng datos ay madalas na may kinalaman sa personal na datos na maaaring makilala ang mga paksa ng datos. Ang [pagmamay-ari ng datos](https://permission.io/blog/data-ownership) ay tungkol sa _kontrol_ at [_mga karapatan ng gumagamit_](https://permission.io/blog/data-ownership) na may kaugnayan sa paglikha, pagproseso, at pagpapakalat ng datos.

Ang mga moral na tanong na dapat nating itanong ay:
 * Sino ang nagmamay-ari ng datos? (gumagamit o organisasyon)
 * Anong mga karapatan ang mayroon ang mga paksa ng datos? (hal: access, pagbura, portability)
 * Anong mga karapatan ang mayroon ang mga organisasyon? (hal: itama ang mapanirang mga review ng gumagamit)

#### 2.2 May Malay na Pahintulot

Ang [may malay na pahintulot](https://legaldictionary.net/informed-consent/) ay tumutukoy sa kilos ng mga gumagamit na pumapayag sa isang aksyon (tulad ng pagkolekta ng datos) na may _buong pag-unawa_ sa mga kaugnay na katotohanan kabilang ang layunin, mga posibleng panganib, at mga alternatibo.

Mga tanong na dapat tuklasin dito:
 * Nagbigay ba ng pahintulot ang gumagamit (paksa ng datos) para sa pagkolekta at paggamit ng datos?
 * Naiintindihan ba ng gumagamit ang layunin kung bakit kinolekta ang datos na iyon?
 * Naiintindihan ba ng gumagamit ang mga posibleng panganib mula sa kanilang pakikilahok?

#### 2.3 Intelektwal na Ari-arian

Ang [intelektwal na ari-arian](https://en.wikipedia.org/wiki/Intellectual_property) ay tumutukoy sa mga hindi materyal na likha na resulta ng inisyatiba ng tao, na maaaring _may pang-ekonomiyang halaga_ sa mga indibidwal o negosyo.

Mga tanong na dapat tuklasin dito:
 * Ang nakolektang datos ba ay may pang-ekonomiyang halaga sa isang gumagamit o negosyo?
 * Mayroon bang intelektwal na ari-arian ang **gumagamit** dito?
 * Mayroon bang intelektwal na ari-arian ang **organisasyon** dito?
 * Kung umiiral ang mga karapatang ito, paano natin ito pinoprotektahan?

#### 2.4 Privacy ng Datos

Ang [privacy ng datos](https://www.northeastern.edu/graduate/blog/what-is-data-privacy/) o privacy ng impormasyon ay tumutukoy sa pangangalaga ng privacy ng gumagamit at proteksyon ng pagkakakilanlan ng gumagamit kaugnay ng personal na makikilalang impormasyon.

Mga tanong na dapat tuklasin dito:
 * Ang datos ba ng mga gumagamit (personal) ay ligtas laban sa mga hack at pagtagas?
 * Ang datos ba ng mga gumagamit ay naa-access lamang sa mga awtorisadong gumagamit at konteksto?
 * Ang anonymity ba ng mga gumagamit ay napapanatili kapag ang datos ay ibinabahagi o ipinapakalat?
 * Maaari bang ma-de-identify ang isang gumagamit mula sa mga anonymized na dataset?

#### 2.5 Karapatan na Maging Nakalimutan

Ang [Karapatan na Maging Nakalimutan](https://en.wikipedia.org/wiki/Right_to_be_forgotten) o [Karapatan sa Pagbura](https://www.gdpreu.org/right-to-be-forgotten/) ay nagbibigay ng karagdagang proteksyon sa personal na datos ng mga gumagamit. Partikular, binibigyan nito ang mga gumagamit ng karapatang humiling ng pagbura o pagtanggal ng personal na datos mula sa mga paghahanap sa Internet at iba pang lokasyon, _sa ilalim ng mga tiyak na kalagayan_ - na nagbibigay-daan sa kanila ng bagong simula online nang hindi hinuhusgahan ang kanilang mga nakaraang aksyon.

Mga tanong na dapat tuklasin dito:
 * Pinapayagan ba ng sistema ang mga paksa ng datos na humiling ng pagbura?
 * Dapat bang awtomatikong ma-trigger ng pag-atras ng pahintulot ng gumagamit ang pagbura?
 * Ang datos ba ay nakolekta nang walang pahintulot o sa pamamagitan ng ilegal na paraan?
 * Tayo ba ay sumusunod sa mga regulasyon ng gobyerno para sa privacy ng datos?

#### 2.6 Bias sa Dataset

Ang bias sa dataset o [Bias sa Pagkolekta](http://researcharticles.com/index.php/bias-in-data-collection-in-research/) ay tungkol sa pagpili ng isang _hindi kinatawan_ na subset ng datos para sa pagbuo ng algorithm, na lumilikha ng potensyal na kawalan ng katarungan sa mga resulta para sa iba't ibang grupo. Kasama sa mga uri ng bias ang bias sa pagpili o sampling, bias ng boluntaryo, at bias sa instrumento.

Mga tanong na
[Algorithm Fairness](https://towardsdatascience.com/what-is-algorithm-fairness-3182e161cf9f) ay tumutukoy sa pagsusuri kung ang disenyo ng algorithm ay sistematikong nagdidiskrimina laban sa partikular na mga subgroup ng data subjects, na nagdudulot ng [mga potensyal na pinsala](https://docs.microsoft.com/en-us/azure/machine-learning/concept-fairness-ml) sa _alokasyon_ (kung saan ang mga resources ay tinatanggihan o hindi ibinibigay sa grupong iyon) at _kalidad ng serbisyo_ (kung saan ang AI ay hindi kasing tumpak para sa ilang subgroup kumpara sa iba).

Mga tanong na dapat pag-isipan:
 * Nasuri ba natin ang katumpakan ng modelo para sa iba't ibang subgroup at kundisyon?
 * Sinuri ba natin ang sistema para sa mga potensyal na pinsala (hal., stereotyping)?
 * Maaari ba nating baguhin ang data o muling sanayin ang mga modelo upang mabawasan ang mga natukoy na pinsala?

Suriin ang mga mapagkukunan tulad ng [AI Fairness checklists](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4t6dA) upang matuto pa.

#### 2.9 Misrepresentation

[Data Misrepresentation](https://www.sciencedirect.com/topics/computer-science/misrepresentation) ay tumutukoy sa pagsusuri kung ang mga insight mula sa data ay tapat na iniulat o kung ito ay ipinapakita sa mapanlinlang na paraan upang suportahan ang isang nais na naratibo.

Mga tanong na dapat pag-isipan:
 * Nag-uulat ba tayo ng hindi kumpleto o hindi tumpak na data?
 * Nagpapakita ba tayo ng data sa paraang nagdudulot ng maling konklusyon?
 * Gumagamit ba tayo ng piling mga teknik sa istatistika upang manipulahin ang mga resulta?
 * Mayroon bang alternatibong paliwanag na maaaring magbigay ng ibang konklusyon?

#### 2.10 Free Choice
Ang [Illusion of Free Choice](https://www.datasciencecentral.com/profiles/blogs/the-illusion-of-choice) ay nangyayari kapag ang "choice architectures" ng sistema ay gumagamit ng mga algorithm sa paggawa ng desisyon upang itulak ang mga tao na pumili ng isang nais na resulta habang tila binibigyan sila ng mga opsyon at kontrol. Ang mga [dark patterns](https://www.darkpatterns.org/) na ito ay maaaring magdulot ng panlipunan at pang-ekonomiyang pinsala sa mga gumagamit. Dahil ang mga desisyon ng gumagamit ay nakakaapekto sa mga profile ng pag-uugali, ang mga aksyong ito ay maaaring magdulot ng mga hinaharap na pagpipilian na maaaring palalain o palawigin ang epekto ng mga pinsalang ito.

Mga tanong na dapat pag-isipan:
 * Naiintindihan ba ng gumagamit ang mga implikasyon ng paggawa ng desisyong iyon?
 * Alam ba ng gumagamit ang (mga alternatibong) opsyon at ang mga kalamangan at kahinaan ng bawat isa?
 * Maaari bang baligtarin ng gumagamit ang isang automated o naimpluwensiyahang desisyon sa hinaharap?

### 3. Mga Pag-aaral ng Kaso

Upang mailagay ang mga hamon sa etika sa mga konteksto ng totoong mundo, makakatulong ang pagtingin sa mga pag-aaral ng kaso na naglalarawan ng mga potensyal na pinsala at kahihinatnan sa mga indibidwal at lipunan kapag ang mga paglabag sa etika ay hindi napapansin.

Narito ang ilang halimbawa:

| Hamon sa Etika | Pag-aaral ng Kaso  | 
|--- |--- |
| **Informed Consent** | 1972 - [Tuskegee Syphilis Study](https://en.wikipedia.org/wiki/Tuskegee_Syphilis_Study) - Ang mga African American na lalaki na lumahok sa pag-aaral ay pinangakuan ng libreng medikal na pangangalaga _ngunit nilinlang_ ng mga mananaliksik na hindi ipinaalam sa kanila ang kanilang diagnosis o ang pagkakaroon ng paggamot. Maraming namatay, at naapektuhan ang mga asawa o anak; tumagal ang pag-aaral ng 40 taon. | 
| **Data Privacy** |  2007 - Ang [Netflix data prize](https://www.wired.com/2007/12/why-anonymous-data-sometimes-isnt/) ay nagbigay sa mga mananaliksik ng _10M anonymized movie rankings mula sa 50K customer_ upang mapabuti ang mga algorithm ng rekomendasyon. Gayunpaman, nagawa ng mga mananaliksik na iugnay ang anonymized data sa personal na makikilalang data sa _mga panlabas na dataset_ (hal., IMDb comments) - epektibong "de-anonymizing" ang ilang Netflix subscribers.|
| **Collection Bias**  | 2013 - Ang Lungsod ng Boston ay [nag-develop ng Street Bump](https://www.boston.gov/transportation/street-bump), isang app na nagpapahintulot sa mga mamamayan na mag-ulat ng mga potholes, na nagbibigay sa lungsod ng mas mahusay na data sa kalsada upang mahanap at maayos ang mga isyu. Gayunpaman, [ang mga tao sa mas mababang kita ay may mas kaunting access sa mga kotse at telepono](https://hbr.org/2013/04/the-hidden-biases-in-big-data), na ginagawang hindi nakikita ang kanilang mga isyu sa kalsada sa app na ito. Nakipagtulungan ang mga developer sa mga akademiko upang tugunan ang _pantay na access at digital divides_ para sa katarungan. |
| **Algorithmic Fairness**  | 2018 - Ang MIT [Gender Shades Study](http://gendershades.org/overview.html) ay nagsuri sa katumpakan ng mga produkto ng AI sa pag-uuri ng kasarian, na naglantad ng mga agwat sa katumpakan para sa kababaihan at mga taong may kulay. Ang isang [2019 Apple Card](https://www.wired.com/story/the-apple-card-didnt-see-genderand-thats-the-problem/) ay tila nag-aalok ng mas mababang credit sa kababaihan kaysa sa kalalakihan. Parehong nagpakita ng mga isyu sa bias ng algorithm na nagdudulot ng mga socio-economic harms.|
| **Data Misrepresentation** | 2020 - Ang [Georgia Department of Public Health ay naglabas ng mga COVID-19 chart](https://www.vox.com/covid-19-coronavirus-us-response-trump/2020/5/18/21262265/georgia-covid-19-cases-declining-reopening) na tila nililinlang ang mga mamamayan tungkol sa mga trend ng kumpirmadong kaso gamit ang hindi kronolohikal na pagkakasunod-sunod sa x-axis. Ipinapakita nito ang maling representasyon sa pamamagitan ng mga trick sa visualization. |
| **Illusion of free choice** | 2020 - Ang learning app na [ABCmouse ay nagbayad ng $10M upang ayusin ang reklamo ng FTC](https://www.washingtonpost.com/business/2020/09/04/abcmouse-10-million-ftc-settlement/) kung saan ang mga magulang ay na-trap sa pagbabayad para sa mga subscription na hindi nila ma-cancel. Ipinapakita nito ang dark patterns sa choice architectures, kung saan ang mga gumagamit ay itinulak sa mga potensyal na mapanganib na desisyon. |
| **Data Privacy & User Rights** | 2021 - Ang Facebook [Data Breach](https://www.npr.org/2021/04/09/986005820/after-data-breach-exposes-530-million-facebook-says-it-will-not-notify-users) ay naglantad ng data mula sa 530M na gumagamit, na nagresulta sa $5B na settlement sa FTC. Gayunpaman, tumanggi itong ipaalam sa mga gumagamit ang breach, na lumalabag sa mga karapatan ng gumagamit sa transparency ng data at access. |

Gusto mo bang mag-explore ng higit pang mga pag-aaral ng kaso? Tingnan ang mga mapagkukunang ito:
* [Ethics Unwrapped](https://ethicsunwrapped.utexas.edu/case-studies) - mga dilemmas sa etika sa iba't ibang industriya. 
* [Data Science Ethics course](https://www.coursera.org/learn/data-science-ethics#syllabus) - landmark na mga pag-aaral ng kaso na tinalakay.
* [Where things have gone wrong](https://deon.drivendata.org/examples/) - checklist ng deon na may mga halimbawa.

> 🚨 Pag-isipan ang mga pag-aaral ng kaso na iyong nakita - nakaranas ka na ba, o naapektuhan ng, katulad na hamon sa etika sa iyong buhay? Makakaisip ka ba ng kahit isang pag-aaral ng kaso na naglalarawan ng isa sa mga hamon sa etika na tinalakay natin sa seksyong ito?

## Applied Ethics

Napag-usapan natin ang mga konsepto ng etika, mga hamon, at mga pag-aaral ng kaso sa mga konteksto ng totoong mundo. Ngunit paano tayo magsisimula sa _paglalapat_ ng mga prinsipyo at kasanayan sa etika sa ating mga proyekto? At paano natin _maisasagawa_ ang mga kasanayang ito para sa mas mahusay na pamamahala? Tuklasin natin ang ilang mga solusyon sa totoong mundo:

### 1. Professional Codes

Ang Professional Codes ay nag-aalok ng isang opsyon para sa mga organisasyon upang "hikayatin" ang mga miyembro na suportahan ang kanilang mga prinsipyo sa etika at misyon. Ang mga code ay _moral na gabay_ para sa propesyonal na pag-uugali, na tumutulong sa mga empleyado o miyembro na gumawa ng mga desisyon na naaayon sa mga prinsipyo ng kanilang organisasyon. Ang mga ito ay epektibo lamang kung may boluntaryong pagsunod mula sa mga miyembro; gayunpaman, maraming organisasyon ang nag-aalok ng karagdagang gantimpala at parusa upang mag-udyok ng pagsunod mula sa mga miyembro.

Mga halimbawa:
 * [Oxford Munich](http://www.code-of-ethics.org/code-of-conduct/) Code of Ethics
 * [Data Science Association](http://datascienceassn.org/code-of-conduct.html) Code of Conduct (nilikha noong 2013)
 * [ACM Code of Ethics and Professional Conduct](https://www.acm.org/code-of-ethics) (mula noong 1993)

> 🚨 Miyembro ka ba ng isang propesyonal na organisasyon sa engineering o data science? Suriin ang kanilang site upang makita kung tinutukoy nila ang isang propesyonal na code of ethics. Ano ang sinasabi nito tungkol sa kanilang mga prinsipyo sa etika? Paano nila "hinihikayat" ang mga miyembro na sundin ang code?

### 2. Ethics Checklists

Habang ang mga professional codes ay tumutukoy sa kinakailangang _etikal na pag-uugali_ mula sa mga practitioner, [mayroon silang kilalang limitasyon](https://resources.oreilly.com/examples/0636920203964/blob/master/of_oaths_and_checklists.md) sa pagpapatupad, partikular sa malalaking proyekto. Sa halip, maraming eksperto sa data science ang [nagpapayo ng paggamit ng checklists](https://resources.oreilly.com/examples/0636920203964/blob/master/of_oaths_and_checklists.md), na maaaring **mag-ugnay ng mga prinsipyo sa mga kasanayan** sa mas deterministiko at maaksiyong paraan.

Ang mga checklist ay nagko-convert ng mga tanong sa "oo/hindi" na mga gawain na maaaring maisagawa, na nagpapahintulot sa mga ito na masubaybayan bilang bahagi ng karaniwang workflows sa paglabas ng produkto.

Mga halimbawa:
 * [Deon](https://deon.drivendata.org/) - isang pangkalahatang checklist sa etika ng data na nilikha mula sa [mga rekomendasyon ng industriya](https://deon.drivendata.org/#checklist-citations) na may command-line tool para sa madaling integrasyon.
 * [Privacy Audit Checklist](https://cyber.harvard.edu/ecommerce/privacyaudit.html) - nagbibigay ng pangkalahatang gabay para sa mga kasanayan sa paghawak ng impormasyon mula sa legal at panlipunang pananaw.
 * [AI Fairness Checklist](https://www.microsoft.com/en-us/research/project/ai-fairness-checklist/) - nilikha ng mga practitioner ng AI upang suportahan ang pag-aampon at integrasyon ng fairness checks sa mga development cycle ng AI.
 * [22 questions for ethics in data and AI](https://medium.com/the-organization/22-questions-for-ethics-in-data-and-ai-efb68fd19429) - mas bukas na framework, na naka-istruktura para sa paunang pagsusuri ng mga isyu sa etika sa disenyo, implementasyon, at mga konteksto ng organisasyon.

### 3. Ethics Regulations

Ang etika ay tungkol sa pagtukoy ng mga pinagsasaluhang halaga at paggawa ng tama _boluntaryo_. **Compliance** ay tungkol sa _pagsunod sa batas_ kung saan ito tinukoy. Ang **Governance** ay sumasaklaw sa lahat ng paraan kung paano nagpapatakbo ang mga organisasyon upang ipatupad ang mga prinsipyo ng etika at sumunod sa mga itinatag na batas.

Ngayon, ang pamamahala ay may dalawang anyo sa loob ng mga organisasyon. Una, ito ay tungkol sa pagtukoy ng mga prinsipyo ng **ethical AI** at pagtatatag ng mga kasanayan upang maisagawa ang pag-aampon sa lahat ng mga proyekto na may kaugnayan sa AI sa organisasyon. Pangalawa, ito ay tungkol sa pagsunod sa lahat ng mga regulasyon sa proteksyon ng data na ipinag-uutos ng gobyerno para sa mga rehiyon kung saan ito nagpapatakbo.

Mga halimbawa ng regulasyon sa proteksyon ng data at privacy:
 * `1974`, [US Privacy Act](https://www.justice.gov/opcl/privacy-act-1974) - nagre-regulate ng _federal govt._ sa koleksyon, paggamit, at paglalantad ng personal na impormasyon.
 * `1996`, [US Health Insurance Portability & Accountability Act (HIPAA)](https://www.cdc.gov/phlp/publications/topic/hipaa.html) - pinoprotektahan ang personal na data sa kalusugan.
 * `1998`, [US Children's Online Privacy Protection Act (COPPA)](https://www.ftc.gov/enforcement/rules/rulemaking-regulatory-reform-proceedings/childrens-online-privacy-protection-rule) - pinoprotektahan ang privacy ng data ng mga bata na wala pang 13 taong gulang.
 * `2018`, [General Data Protection Regulation (GDPR)](https://gdpr-info.eu/) - nagbibigay ng mga karapatan ng gumagamit, proteksyon ng data, at privacy.
 * `2018`, [California Consumer Privacy Act (CCPA)](https://www.oag.ca.gov/privacy/ccpa) - nagbibigay sa mga consumer ng mas maraming _karapatan_ sa kanilang (personal) na data.
 * `2021`, China's [Personal Information Protection Law](https://www.reuters.com/world/china/china-passes-new-personal-data-privacy-law-take-effect-nov-1-2021-08-20/) - kamakailan lamang naipasa, na lumilikha ng isa sa pinakamalakas na regulasyon sa online data privacy sa buong mundo.

> 🚨 Ang European Union na nagtakda ng GDPR (General Data Protection Regulation) ay nananatiling isa sa mga pinaka-maimpluwensiyang regulasyon sa privacy ng data ngayon. Alam mo ba na tinutukoy din nito ang [8 karapatan ng gumagamit](https://www.freeprivacypolicy.com/blog/8-user-rights-gdpr) upang protektahan ang digital na privacy at personal na data ng mga mamamayan? Alamin kung ano ang mga ito, at kung bakit mahalaga ang mga ito.

### 4. Ethics Culture

Tandaan na may natitirang hindi nakikitang agwat sa pagitan ng _compliance_ (paggawa ng sapat upang matugunan ang "letra ng batas") at pagtugon sa [mga sistematikong isyu](https://www.coursera.org/learn/data-science-ethics/home/week/4) (tulad ng ossification, information asymmetry, at distributional unfairness) na maaaring magpabilis sa weaponization ng AI.

Ang huli ay nangangailangan ng [mga collaborative na diskarte sa pagtukoy ng mga kultura ng etika](https://towardsdatascience.com/why-ai-ethics-requires-a-culture-driven-approach-26f451afa29f) na bumubuo ng emosyonal na koneksyon at pare-parehong pinagsasaluhang halaga _sa mga organisasyon_ sa industriya. Ito ay nangangailangan ng mas [pormalisadong kultura ng etika sa data](https://www.codeforamerica.org/news/formalizing-an-ethical-data-culture/) sa mga organisasyon - na nagpapahintulot sa _sinuman_ na [hilahin ang Andon cord](https://en.wikipedia.org/wiki/Andon_(manufacturing)) (upang itaas ang mga alalahanin sa etika nang maaga sa proseso) at gawing _mga etikal na pagtatasa_ (hal., sa pagkuha) isang pangunahing pamantayan sa pagbuo ng koponan sa mga proyekto ng AI.

---
## [Post-lecture quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/3) 🎯
## Review & Self Study 

Ang mga kurso at libro ay tumutulong sa pag-unawa sa mga pangunahing konsepto ng etika at mga hamon, habang ang mga pag-aaral ng kaso at mga tool ay tumutulong sa mga kasanayan sa etika sa totoong mundo. Narito ang ilang mapagkukunan upang magsimula:

* [Machine Learning For Beginners](https://github.com/microsoft/ML-For-Beginners/blob/main/1-Introduction/3-fairness/README.md) - aralin tungkol sa Fairness, mula sa Microsoft.
* [Mga Prinsipyo ng Responsableng AI](https://docs.microsoft.com/en-us/learn/modules/responsible-ai-principles/) - libreng learning path mula sa Microsoft Learn.  
* [Etika at Agham ng Datos](https://resources.oreilly.com/examples/0636920203964) - O'Reilly EBook (M. Loukides, H. Mason et. al)  
* [Etika sa Agham ng Datos](https://www.coursera.org/learn/data-science-ethics#syllabus) - online na kurso mula sa University of Michigan.  
* [Ethics Unwrapped](https://ethicsunwrapped.utexas.edu/case-studies) - mga case study mula sa University of Texas.  

# Takdang-Aralin  

[Sumulat ng Isang Case Study Tungkol sa Etika ng Datos](assignment.md)  

---

**Paunawa**:  
Ang dokumentong ito ay isinalin gamit ang AI translation service na [Co-op Translator](https://github.com/Azure/co-op-translator). Bagama't sinisikap naming maging tumpak, tandaan na ang mga awtomatikong pagsasalin ay maaaring maglaman ng mga pagkakamali o hindi pagkakatugma. Ang orihinal na dokumento sa kanyang katutubong wika ang dapat ituring na opisyal na sanggunian. Para sa mahalagang impormasyon, inirerekomenda ang propesyonal na pagsasalin ng tao. Hindi kami mananagot sa anumang hindi pagkakaunawaan o maling interpretasyon na dulot ng paggamit ng pagsasaling ito.