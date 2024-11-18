# Wegwijzer Online Seksuele Veiligheid voor Onderwijsprofessionals

## Probleemstelling
In Nederland bestaan verschillende stichtingen en organisaties die hulp bieden bij online seksueel grensoverschrijdend gedrag. Deze hulp omvat zowel interventies voor slachtoffers als preventieve maatregelen die bijvoorbeeld docenten kunnen nemen om de kans op incidenten te verkleinen.

Voor onderwijsprofessionals, zoals docenten, is het vaak onduidelijk welke hulp of preventie-activiteiten bij een specifieke situatie passen. Dit kan afhankelijk zijn van factoren zoals de leeftijd van betrokkenen, interpersoonlijke relaties, en de aard van de gebeurtenis. Tijdgebrek en beperkte kennis over beschikbare interventies maken het vinden van passende oplossingen uitdagend. Hierdoor lopen kansen mis om incidenten te voorkomen of effectief aan te pakken.

Hoewel de tool primair gericht is op onderwijsprofessionals, kan deze ook waardevol zijn voor andere gebruikers, zoals ouders of slachtoffers zelf, door hen toegang te geven tot relevante en toegankelijke hulpbronnen.

## Oplossing en introductie
Als oplossing willen we een RAG-tool ontwikkelen die onderwijsprofessionals helpt snel en effectief de juiste hulpbronnen te vinden voor online seksueel grensoverschrijdend gedrag. Het prototype dat door Jitse Goudbeek is ontwikkeld en momenteel op Claude draait, dient als basis. Onze uitdaging is om dit prototype over te zetten naar de pipeline van Learning Lion en te onderzoeken of vergelijkbare of zelfs betere resultaten kunnen worden bereikt.

Het Learning Lion-model biedt ons meer controle over data, verhoogde privacy, en flexibiliteit om de tool verder aan te passen aan de behoeften van onderwijsprofessionals. Hiermee zorgen we voor een oplossing die schaalbaar is en duurzaam kan worden ingezet binnen onderwijsinstellingen.

## Data
De tool maakt gebruik van meerdere databronnen om gebruikers te adviseren:

### Hoofdbron:
- [De wegwijzers van de Rijksoverheid over seksualiteit](https://www.rijksoverheid.nl/onderwerpen/seksuele-misdrijven/vraag-en-antwoord/wat-kan-ik-als-school-of-ouder-doen-tegen-ongewenste-sexting).
Deze documenten bieden overzichten van interventies en organisaties die hulp bieden, afgestemd op specifieke situaties. De wegwijzers worden momenteel geüpdatet om de informatie nog toegankelijker te maken.
### Aanvullende informatie:
- [Artikelen van Kennisnet](https://www.kennisnet.nl/beleid-en-organisatie/ongewenste-beelden-gaan-viraal-wat-te-doen/).
- [Artikelen van School en Veiligheid](https://www.schoolenveiligheid.nl/kennisbank/sexting-en-ongewenste-verspreiding-van-beelden/).
Deze bronnen bieden praktische tips en adviezen buiten de standaardinterventies, zoals preventieve acties die scholen kunnen nemen.

## Prompts en instructies voor het model
Om relevante en toegankelijke adviezen te bieden, worden de volgende prompts meegegeven:
### Context ###
- Er zijn een heleboel interventies (zie project knowledge) die mensen kunnen helpen bij het tegengaan van online seksueel grensoverschrijdend gedrag. Voor veel mensen is dit niet te overzien, en daarom help je ze wegwijs te worden en adviseert ze over wat ze kunnen doen.

### Rolverdeling ###
- Ik ben een docent/ouder/professional die iets wil doen tegen online seksueel grensoverschrijdend gedrag. Jij bent een expert die mij begeleidt, op basis van deze werkwijzers. 

### Opdracht ###
- Vraag veel door; wie ben ik, wat zoek ik, waar liggen mijn behoeftes, welke leerlingen heb ik etc.
- Kom uiteindelijk met een paar adviezen, 2 of 3 interventies die ik zou kunnen inzetten in mijn situatie

### Extra ###
- Probeer mij mee te krijgen in het gebruiken van langer lopende en effectieve interventies. Maar doe dit niet opdringerig, beetje nudgen om serieus met dit probleem aan de slag te gaan kan geen kwaad met de nadruk op beetje. 

- Wees altijd heel duidelijk over dat het nooit de schuld is van het slachtoffer, het verminderen van slutshaming en victimblaming is belangrijk!

- Beantwoordt nooit vragen die niet over dit onderwerp gaan, maak in dat geval duidelijk dat je daar geen vragen over kan beantwoorden.

- Geef altijd aan waar je het antwoord vandaan heb, benoem het document uit je context

## Impact
### Korte termijn:
Onderwijsprofessionals hebben sneller toegang tot passende hulpbronnen, wat het bewustzijn vergroot en de implementatie van preventieve maatregelen vergemakkelijkt.
### Lange termijn:
Het onderwijs wordt beter voorbereid om online seksueel grensoverschrijdend gedrag te voorkomen en effectief te reageren op incidenten, wat bijdraagt aan een veiligere leeromgeving.

## Implicaties voor SSC-ICT
Zelfs wanneer de POC succesvol is, betekent dit niet automatisch dat SSC ICT de applicatie zal hosten en/of beheren. SSC ICT voert onderzoek uit naar de mogelijkheden, maar het doel is om slachtoffers betere en snellere hulp te kunnen bieden. Dit houdt dus in dat als externe partijen dit beter kunnen faciliteren, zij dit project mogelijk overnemen. 

