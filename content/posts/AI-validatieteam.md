---
authors: Lara Mutsaers   
date: 2024-11-19
linktitle: In gesprek met het AI-validatieteam
title: In gesprek met het AI-validatieteam
weight: 10
tags: [
    "Development",
    "Finetunen",
    "Validatie",
    "Verantwoorde AI", 
]
---

Vandaag hebben we gesproken met het [AI-Validatieteam](https://minbzk.github.io/ai-validation/). Zij werken aan verschillende projecten om meer inzicht te verkrijgen in algoritmes en hun gedragingen (transparantie). Ze willen meer grip krijgen op algoritmes die ingezet worden door overheden. 

## Het benchmarken van LLM's
Eén van de projecten waar ze zich mee bezig hebben gehouden is het benchmarken van taalmodellen (LLM’s).

LLM’s kunnen worden ingezet voor verschillende taken om het reguliere werk te vergemakkelijken. Maar, er zitten ook aanzienlijke risico’s aan verbonden. Het is niet gegarandeerd dat de output van een LLM altijd juist is. Bovendien kan een LLM bias vertonen. 

Het doel van het [LLM benchmarking project](https://minbzk.github.io/ai-validation/projects/llm-benchmarks/) was onder andere om inzichtelijk te maken hoe LLM’s zich gedragen (specifiek voor de Nederlandse context, er bestaat nog niks buiten Amerikaanse context). Hierbij kan ook specifiek nog gekeken worden naar taken die de overheid vaak uitvoert (zoals dingen samenvatten, schrijven van essays etc.). Ze willen (veelgebruikte) LLM’s langs een serie van meetlatten leggen. 

Helaas is de werkstroom op pauze gezet. Nu werkt hier slechts één persoon aan. Zij is bezig met het maken van een benchmark voor bias (discriminatie), vooral in de context van het nemen van beslissingen. Kort door de bocht houdt dat in: een taalmodel maakt een ja/nee beslissing op basis van aangeleverde documenten (denk aan CV’s). De vraag hierbij is steeds is in hoeverre dit wordt gebaseerd op beschermde eigenschappen (geslacht, etniciteit, etc.). Het is natuurlijk niet de bedoeling dat dergelijke beslissingen daadwerkelijk door een taalmodel worden genomen, maar door dit te toetsen komt impliciete discriminatie binnen een taalmodel naar boven. Het idee was om een soort een matrix (leaderboard) te maken met verschillende LLM’s langs verschillende benchmarks. Hiermee zouden gebruikers, mensen die het taalmodel gaan inzetten, een weloverwogen keuze maken voor een bepaald taalmodel. Zo’n matrix maakt immers inzichtelijk hoe het taalmodel werkt op specifieke punten. De verantwoordelijkheid van de keuze voor een taalmodel blijft bij degene die het taalmodel gaat inzetten. 

## Zelf een embeddingsmodel finetunen?
Verder hebben we tijdens het gesprek wat tips gekregen voor ons idee om zelf een embeddingsmodel te gaan finetunen. De klassieke manier is om de outputs te gaan labelen op basis van relevantie (dit kan binair of graded). Idealiter heb je hier stafmedewerkers (domeinexperts) voor nodig, maar je zou ook zelf kunnen kijken hoever je komt. Als je met drie personen bent die allemaal dezelfde outputs labelen, dan kom je waarschijnlijk een heel eind. Deze techniek heet ook wel NIST TREC style evaluation en is de moeite waard om te onderzoeken. We zouden ook simultaan aan de testperiode van JenV een soort externe applicatie kunnen bouwen voor stafmedewerkers waarin ze deze outputs kunnen labelen. 

