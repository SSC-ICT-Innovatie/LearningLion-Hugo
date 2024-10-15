---
weight: 2
bookFlatSection: true
title: "Retrieval"
---

# Retrieval - Documentophaling

Als er een query in de retriever binnenkomt, gaat de retrieval deze tekst op semantisch niveau vergelijken met de tekst uit de knowledgebase. Dit gaat middels het vergelijken van getallenreeksen wat veelal wordt gedaan door een voorgetrainde neural retriever (zgn. dense retrieval). De getallenreeksen die worden vergeleken zijn het resultaat van vertaling door het embeddingsmodel en stellen dus stukken tekst voor. 
Als het model goed werkt, zullen er documenten opgehaald worden op basis van de query die semantisch dicht bij elkaar liggen en niet slechts alleen documenten met precies dezelfde zoekterm.
