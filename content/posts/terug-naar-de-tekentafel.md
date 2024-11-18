---
authors: Lara Mutsaers
date: 2024-10-14
linktitle: Terug naar de technische tekentafel
title: Terug naar de technische tekentafel (week 46 update)
weight: 10
tags: [
    "proces",
    "Datascope",
    "use case Kamervragen",
    "RAG-pipeline",
    "development",
]
---

De [use case Kamervragen]({{%ref "versiebeheer_usecaseKamervragen.md" %}}) is afgelopen week vastgelegd, dus zijn we weer naar de technische tekentafel gegaan om de huidige RAG-pipeline door te ontwikkelen tot een echt bruikbare applicatie.
Na gesprekken met JenV merkte we dat de grootste pijn zat in het zoeken van de juiste bronnen. Daarom gaat het retrieval gedeelte vrij uitgebreid zijn en bovendien interactief, zodat de eindgebruiker invloed heeft op welke bronnen er worden gebruikt uit de retrieval-stap voor het tekstvoorstel. 
Bovendien is er de behoefte om als query in het systeem een hele Kamervraag in te voegen (dat betekent een inleiding plus alle subvragen). Hoe ga je deze hele Kamervragen verwerken tot iets wat logisch bruikbaar is voor de gebruiker en voor de LLM in de RAG-pipeline?
De eerste aanpak om dit te doen was proberen te matchen op basis van elke subvraag van een Kamervraag, gematcht met subvragen uit eerder beantwoorde Kamervragen. Per subvraag kan de eindgebruiker dan selecteren of dit logischerwijs past bij de gestelde vraag of niet. De vragen die de gebruiker als relevant acht, kunnen dan doorgezet worden naar de LLM. De LLM probeert dan deze context, aangevuld met gebruikerscontext (zoals een nieuwsbericht), over te zetten naar een template-suggestie voor beantwoording.

Er zijn een aantal zaken die we willen aanpassen ten opzichte van de laatste versie:

## Aanpassen van de PDF-decode library. 
We hebben in de nieuwe versie gekozen voor een andere library in Python die een pdf naar tekst converteert. Deze heeft een gestructureerder markdown als output.

## De tekst op basis van vraag-antwoord chunken op tekst-niveau en niet op token-niveau. 
Een ‘cleanere’ tekst helpt daarbij (het resultaat van de hierboven geschreven aanpassing). Deze wordt opgeslagen in een SQL-database.
We hebben in de nieuwe versie een kleine aanpassing gemaakt zodat we nu passende paren van vraag-antwoord combinaties hebben. De reguliere expressies (Regex) die we gebruiken om de tekst te interpreteren zijn nu flexibelerRegex (reguliere expressie) werkt nu flexibeler.
We kwamen in dit proces sets van Kamervragen tegen waar foutjes in zijn geslopen (bijvoorbeeld: vraag 3 staat netjes uitgetypt en gemarkeerd als vraag 3, maar antwoord 3 staat niet aangegeven en volgt na een kopie van vraag ). Dit soort afwijkingen kunnen we nog niet goed verwerken. De data lijkt wel al vrij gestructureerd op het eerste oog.

## De BM25 retriever zo ombouwen dat het ook matching scores/een treshold kan gebruiken. 
In de implementatie met Langchain komt er slechts een volgorde uit zonder score.
Dit is deze week nog niet gelukt en schuiven we door naar komende week.

## Elementen in de User Interface (UI) toevoegen 
Bijvoorbeeld het linken van pdf’s van chunks van Kamervragen.
Dit is goed gelukt. De chunks die in de user interface (UI) zichtbaar zijn, linken nu naar een API die we zelf hebben ontwikkeld waar de Kamervragen als PDF-bestanden in staan. Zo kan gemakkelijk het PDF-bestand als bron opgehaald worden vanuit de API halen om aan de eindgebruiker te laten zien. Om dit te bewerkstelligen zijn er verschillende aanpassingen gedaan. Zo zijn er nieuwe API-endpoints gemaakt om de uitwisseling van informatie te ondersteunen. 
Eerst werd tijdens de eerste communicatie vanuit de UI naar de API (als er een vraag wordt gesteld door de gebruiker) alles tegelijk opgehaald, zowel de opgehaalde Kamervragen als de reactie van de LLM. Omdat wij nu een scheiding hebben gemaakt in de retrieval- en generation stap, zijn er twee endpoints bijgekomen, namelijk die van de query en die van de LLM. De query endpoint bevat alleen de prompt van de gebruiker. De gebruiker krijgt als reactie Kamervragen terug die al bekend zijn voor het systeem. Hier kan de gebruiker beoordelen of deze relevant zijn. Vervolgens worden deze relevante vragen verstuurd naar de LLM met de prompt en bijbehorende documenten. 
Om API-communicatie te optimaliseren is er besloten om alleen het UID (unique document ID) van het document en het vraagnummer van de relevante vraag op te slaan. Zo hebben we bij het API-endpoint beschikking tot het antwoord op de vraag die eerder als relevant was beoordeeld door de gebruiker.

## Testen met verschillende LLM’s en prompts. 
We hebben echter nog geen toegang tot voldoende rekenkracht om de grotere modellen te draaien, dus dit stellen we uit. We hebben kort getest met GEITje-ultra, maar een deze bleek een RAG-prompt nog moeilijk robuust te verwerken.

# Observatie: toch zelf een embeddingsmodel finetunen?
Bij kleine testjes met de retriever zien we dat er semantische links gemaakt worden tussen een query en een chunk die wordt retrieved. Toch zal het fijn zijn als dit fijnmaziger en preciezer kan: een overall semantische overlap is vermoedelijk niet genoeg als informatiebron voor een eventueel tekstvoorstel op een Kamervraag.

Dat bracht ons op het idee om toch te kijken of we niet een embeddingsmodel te kunnen fine-tunen.

In eerdere losse verkenningen van het finetunen van embeddingsmodellen kwamen we erachter dat sentence embedders vrij ‘gemakkelijk’ gefinetuned kunnen worden door een dataset vorm te geven met een bron-zin (een anchor) een positieve zin (cq. Een semantisch matchende zin) en een negatieve zin (een zin die semantisch ver verwijderd is van de bronzin). Eerst was ik in de veronderstelling dat wij daar geen voorbeelden van hebben in onze dataset, tot tijdens sparren met chatgpt het volgende opeens een goed idee leek:
Nu hebben wij een dataset waar we een bron zin hebben (een subvraag uit een Kamervraag) en een positieve match (het antwoord op die vraag). Voor de negatieven zouden we in eerste instantie kunnen proberen om random vragen uit de lijst te kiezen en te kijken of we een betere performance krijgen dan met een voor getraind foundational embedding model.

Dit zal een zijtak worden in het optimalisatieproces van de retrieval stap. Volgende week hebben we als het goed is wat resultaten over de uitkomst van het finetunen.

We moeten goed onderzoek blijven doen naar wat het effect is van finetunen. Als basis voor het finetunen gebruiken we de volgende post:
[Training and Finetuning Embedding Models with Sentence Transformers v3](https://huggingface.co/blog/train-sentence-transformers).




