---
bookFlatSection: true
title: "Auteurswet"
Author: Martha Romkes
Date: 13-11-2024
---

# Generatieve AI en auteursrecht
Op 10 oktober 2023 heeft de landsadvocaat een advies uitgebracht over het gebruik van generatieve AI-tools door medewerkers van de Staat. Dit advies gaat in op de juridische implicaties van AI-gebruik vanuit verschillende wetgevingen, waaronder auteursrecht. De samenvatting van de bevindingen met betrekking tot auteursrecht luidt als volgt:

 {{< hint info >}}
“Het gebruik van GenAI door medewerkers van de Staat is, vanuit het auteursrecht gezien, niet per definitie onrechtmatig. Tegelijkertijd komt het gebruik ervan door medewerkers van de Staat niet zonder auteursrechtelijke risico’s. Het is onduidelijk of ontwikkelaars van GenAI-toepassingen voldoende rekening houden met de rechten van auteurs wiens werken zij bij de ontwikkeling van hun diensten gebruiken. Enerzijds omdat ontwikkelaars op dit moment niet transparant zijn over de vraag welke auteursrechtelijke werken zij bij het trainen van dergelijk toepassingen wel of niet van internet (of uit andere bronnen) ‘scrapen’, en anderzijds omdat in de rechtspraak nog niet expliciet is geoordeeld over de vraag of en in welke vorm scraping ten behoeve van GenAI auteursrechtelijk gezien toelaatbaar is. 

Voor de Staat hoeft dit niet per definitie te betekenen dat gebruik van een GenAI toepassingen (door een medewerker) tot auteursrechtinbreuk leidt, al is dat risico in ieder geval in theorie wél aanwezig, en wordt dat risico bovendien vergroot door het feit dat aanbieders van veel toepassingen aansprakelijkheid in hun (standaard) algemene voorwaarden nagenoeg volledig uitsluiten. 

Een tweede risico schuilt daarnaast in het feit dat de output van een GenAI-toepassing 
auteursrechtelijk gezien inbreuk kan maken op het werk van een (eerdere) auteur, bijvoorbeeld een auteur wiens werk ooit aan de ontwikkeling van het GenAI-model ten grondslag heeft gelegen. De precieze omvang van dit risico is nu voor eindgebruikers (en dus ook de Staat) niet goed in te schatten, al was het maar omdat aanbieders van GenAI-toepassingen op dit moment (nog) niet kenbaar (hoeven te) maken welke auteursrechtelijke werken zij bij de ontwikkeling van hun tools precies gebruikt hebben. De AI-Act kan daar verandering in gaan brengen, maar is nu nog niet van toepassing. “ 
([Advies Landsadvocaat Pels Rijcken](https://open.overheid.nl/documenten/16d72572-da6b-422c-8cf8-cdc95a523093/file))
{{< /hint >}}

In de AI-act is een belangrijke toevoeging gedaan die op 25 augustus 2025 in werking treedt. Hierin wordt vastgesteld dat aanbieders van AI-modellen verplicht zijn een samenvatting te publiceren van de data die is gebruikt tijdens het trainen van het model:

{{< hint info >}}
Aanbieders van AI-modellen voor algemene doeleinden moeten [...] een voldoende gedetailleerde samenvatting opstellen en openbaar maken over de voor het trainen van het AI-model voor algemene doeleinden gebruikte content, volgens een door het AI-bureau verstrekt sjabloon. ([artikel 53 AI act](https://eur-lex.europa.eu/legal-content/NL/TXT/HTML/?uri=OJ:L_202401689))
{{< /hint >}}

Dit wordt verder toegelicht in de overwegingen 106-108 van de AI act:

{{< hint info >}}
(106) | Aanbieders die AI-modellen voor algemene doeleinden in de Unie in de handel brengen, zijn gehouden de naleving van de desbetreffende verplichtingen in deze verordening te waarborgen. Zij moeten daartoe een beleid invoeren ter naleving van het Unierecht inzake auteursrechten en naburige rechten, met name om kennis te hebben van het door rechthebbenden geuite voorbehoud van rechten op grond van artikel 4, lid 3, van Richtlijn (EU) 2019/790 en dit na te leven. Aanbieders die in de Unie een AI-model voor algemene doeleinden in de handel brengen, zijn hiertoe verplicht, ongeacht de jurisdictie waarin de auteursrechtelijke relevante handelingen plaatsvinden die helpen die AI-modellen voor algemene doeleinden te trainen. Alleen op deze manier kan gezorgd worden voor een gelijk speelveld voor aanbieders van AI-modellen voor algemene doeleinden, waar geen enkele aanbieder zich een concurrentievoordeel op de Uniemarkt mag kunnen verschaffen met lagere auteursrechtelijke normen dan de in de Unie toepasselijke normen.
(107) | Voor een grotere transparantie ten aanzien van de bij de pre-training en training van AI-modellen voor algemene doeleinden gebruikte data, met inbegrip van door het auteursrecht beschermde tekst en data, is het passend dat aanbieders van dergelijke modellen een voldoende gedetailleerde samenvatting maken en publiceren van de voor de training van het AI-model voor algemene doeleinden gebruikte content. [...]
(108) | Wat betreft de verplichtingen [...] om aan het recht van de Unie inzake auteursrecht te voldoen [...]  moet het AI-bureau controleren of de aanbieder aan die verplichtingen voldoet, zonder evenwel geval voor geval de trainingsdata te controleren of te beoordelen qua naleving van het auteursrecht. Deze verordening doet geen afbreuk aan de handhaving van de auteursrechtregels krachtens het Unierecht.
{{< /hint >}}

Dit roept vragen op over de praktische uitvoering: geldt dit met terugwerkende kracht voor reeds bestaande modellen? Wat betekent dit voor in Amerika getrainde modellen die niet voldoen aan Europese normen? En wie is aansprakelijk als blijkt dat een foundational model dat in duizenden applicaties al gebruikt wordt, auteursrechten heeft geschonden tijdens de training? 

# Auteursrecht buiten Europa.
Het merendeel van de grote taalmodellen is getraind in de Verenigde Staten, waar de [*Fair Use*-doctrine](https://www.copyright.gov/fair-use/) van toepassing is. Deze doctrine maakt het onder bepaalde voorwaarden mogelijk om auteursrechtelijk beschermd materiaal te gebruiken zonder toestemming van de rechthebbende. Het gebruik wordt als *Fair Use* beschouwd als het transformatief is, wat betekent dat het de oorspronkelijke content op een nieuwe, betekenisvolle manier gebruikt, zonder deze simpelweg te reproduceren. Cruciaal is ook dat de gebruiker geen eigendomsrecht claimt op de oorspronkelijke content. Ontwikkelaars van taalmodellen in Amerika stellen vaak dat de output van een model transformatief is, en dat het proces van modeltraining onder *Fair Use* valt. Dit maakt het legaal om openbare data te gebruiken, zelfs als deze auteursrechtelijk beschermd is.  

In Europa liggen de regels echter anders. Het auteursrecht in de Europese Unie kent strengere beperkingen op het hergebruik van beschermd materiaal, vooral wanneer dit gebeurt zonder expliciete toestemming van de rechthebbenden. Onder EU-wetgeving kan scraping van auteursrechtelijk beschermde data zonder toestemming in veel gevallen als inbreuk worden beschouwd.  

De aankomende verplichtingen van de AI-act versterken dit contrast. Vanaf augustus 2025 moeten ontwikkelaars transparant zijn over welke data is gebruikt voor de training van AI-modellen. Dit stelt strengere eisen aan de naleving van auteursrechten. Zonder aanpassing aan deze nieuwe vereisten kan het gebruik van in Amerika getrainde modellen in de EU problematisch worden, tenzij deze modellen voldoen aan de strengere Europese normen. Het is nog onduidelijk of oudere modellen retroactief aan deze regels moeten voldoen, maar het risico bestaat dat een groot aantal bestaande modellen vanaf die datum niet langer legaal bruikbaar is in Europa.  

# Gedogen? Of meebewegen?
Europa hanteert strikte regels rondom auteursrechten, maar is minder streng in de naleving ervan. Een treffend voorbeeld hiervan is het videoplatform YouTube: een groot deel van de content op dit platform hergebruikt beeldfragmenten, geluidsopnames en citaten die strikt genomen niet zonder toestemming mogen worden gebruikt onder de huidige Europese wetgeving. Hoewel dit in de Verenigde Staten wordt beschermd door de Fair Use-doctrine, is er in Europa geen vergelijkbare uitzondering, waardoor deze video's formeel in strijd zouden zijn met auteursrechten.

Toch wordt deze praktijk grotendeels gedoogd, wat wijst op een discrepantie tussen wetgeving en handhaving. Hetzelfde dreigt te gebeuren met grote taalmodellen. Strenge regels zijn alleen effectief als ze praktisch uitvoerbaar zijn en consistent worden toegepast. Mijn voorstel is daarom om de wet aan te passen aan de realiteit van digitale innovatie. In plaats van een wet die massaal overtreden wordt maar zelden wordt gehandhaafd, zou Europa moeten streven naar een auteursrechtkader dat ruimte biedt voor technologisch en maatschappelijk verantwoord gebruik van data, zonder de belangen van rechthebbenden te schaden.

