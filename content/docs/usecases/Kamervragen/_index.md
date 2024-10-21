---
bookCollapseSection: true
title: "Kamervragen"
---

# Kamervragen

De Tweede Kamer der Staten-Generaal speelt een cruciale rol in de Nederlandse democratie door vragen te stellen aan de regering en verantwoording te eisen over beleid en uitvoering. 
Het beantwoorden van deze vragen is een tijdrovend proces. Wij willen onderzoeken in hoeverre generatieve AI-modellen kamervragen effectief kunnen analyseren en beantwoorden. In theorie zou Learning Lion dit proces vereenvoudigen, door beleidsmedewerkers te ondersteunen in het vinden van relevante documenten en het genereren van concept-antwoorden. Door gebruik te maken van semantisch zoeken en door eerder gestelde vragen te identificeren, levert het systeem meer consistentie en bespaart het tijd. 

## Ontwerp van Learning Lion Kamervragen
Het systeem is ontworpen om relevante informatie te verzamelen die het proces van de beantwoording van Kamervragen kan ondersteunen. De gebruiker stelt een Kamervraag aan het systeem. Op basis van deze vraag zoekt het systeem (een RAG-model) naar relevante documenten. Deze documenten worden daarna meegegeven als context aan een LLM die een concept-antwoord op de Kamervraag genereert op basis van precies deze documenten. Het systeem maakt dus een beslissing welke documenten het meest relevant zijn (de hoeveelheid documenten hangt af van een threshold die ingesteld wordt). Bij het gegenereerde concept-antwoord op de Kamervraag blijven deze documenten altijd zichtbaar als een soort bronvermelding. Hierdoor kan je als gebruiker zien op basis waarvan de output is gegenereerd waardoor transparantie in de hand wordt gewerkt. Dit wordt verder versterkt door een bijgeleverde handleiding die gebruikers kunnen lezen over de werking van het systeem.

## Verantwoord gebruik van generatieve AI voor het beantwoorden van Kamervragen
Bij het ontwerpen van deze RAG tool zien wij deze technologie als een hulpmiddel dat ondersteuning biedt aan beleidsmedewerkers en de werklast kan verlichten, maar het proces ook meer betrouwbaar en tijdsefficiënt maakt. Dit houdt echter wel in dat de beleidsmedewerker kritisch moet zijn tegenover de output die het model levert. Momenteel heeft deze technologie geen hoog risico, maar als in de toekomst de antwoorden die het model genereert direct gebruikt worden zonder dat deze gecontroleerd worden op feitelijke waarheid, wordt het risico aanzienlijk hoger. 

## Doelen 
Learning Lion Kamervragen zal op verschillende manieren de beleidsmedewerkers ondersteunen in het proces van het beantwoorden van de kamervragen:

### Het versoepelen van het zoekproces van relevante bronnen voor het beantwoorden van een kamervraag. 
In het huidige zoekproces worden niet altijd alle relevante bronnen gevonden omdat zoeken in de database van eerder behandelde kamervragen nu gaat met zoektermen die precies moeten matchen. Semantisch zoeken zou dus een meerwaarde kunnen zijn, doordat dit ook zoekresultaten oplevert die ongeveer dezelfde betekenis hebben als de zoekterm (bijvoorbeeld: ‘messen’ en ‘zwaarden’). Niet alleen worden er dus meer relevante bronnen gevonden, maar ook het zoekproces wordt hiermee versneld. 
### Consistentie in het beantwoorden van Kamervragen.
Door een RAG-model, zorg je ervoor dat eerder gestelde Kamervragen of vergelijkbare vragen worden gevonden. Op deze manier kan je ervoor zorgen dat eenzelfde of een vergelijkbare vraag op dezelfde manier wordt beantwoord.
### Een concept-antwoord genereren met bijbehorende relevante bronnen
Door aan het RAG-model een LLM te koppelen, kan er een concept-antwoord gegenereerd worden op basis van de gevonden bronnen. Dit geeft beleidsmedewerkers een richting in het beantwoorden van een Kamervraag. Door een bronvermelding toe te voegen heeft de beleidsmedewerker inzicht in welke bronnen er zijn gebruikt om het concept te genereren waardoor er controle kan plaatsvinden. 

## Condities (operationele omgeving)
De belangrijkste conditie waaraan voldaan moet worden is het beheer van lokale GPU’s die in staat zijn om dit model te laten functioneren. Dit is de fysieke operationele vereiste, en hiernaast bestaan er ook nog vereisten voor het gebruik van de tool zelf:

### Naleving van wettelijke en regelgevende normen
We moeten ervoor zorgen dat de AI-tools voldoen aan alle relevante privacy-, gegevensbeschermings- en auteurswetten. Dit kan worden bereikt door regelmatig impact assessments (bijv. DPIA en IAMA) uit te voeren om voortdurende naleving te waarborgen. Daarnaast moet het AI-systeem gegevens lokaal verwerken om te voldoen aan de overheidsvoorschriften voor gegevensbeveiliging en privacy.
### Betrouwbaarheid
Om deze technologie een levensvatbaar alternatief te maken voor bestaande AI-toepassingen, is betrouwbaarheid een van de belangrijkste vereisten. Om dit te bereiken moeten hoge prestaties worden gegarandeerd en moet het model minimale vooroordelen vertonen. De kwaliteit van de output moet goed genoeg zijn om ervoor te zorgen dat het een goed alternatief biedt voor ChatGPT zodat het gebruik hiervan door beleidsmedewerkers kan worden voorkomen. Daarnaast moeten ondersteunings- en onderhoudsprotocollen worden geïmplementeerd om problemen snel aan te pakken.
### Toegankelijkheid
Het product moet toegankelijk zijn voor alle medewerkers, met een gebruiksvriendelijke interface, uitgebreide trainingen voor medewerkers, en live ondersteuning om effectief gebruik van de AI-tools te faciliteren.
### Transparantie van de modellen
Het moet voor gebruikers duidelijk zijn hoe het systeem werkt en hoe beslissingen of antwoorden tot stand komen. 

Meer informatie over de use case 'Kamervragen' kunt u vinden op de [githubpagina](https://github.com/SSC-ICT-Innovatie/LearningLion-kamervragen).
