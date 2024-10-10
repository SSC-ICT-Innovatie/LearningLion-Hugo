---
weight: 1
bookFlatSection: true
title: "The basics of RAG / Learning Lion"
---

Learning Lion is een studie naar de mogelijke bruikbaarheid van generatieve AI binnen de Rijksoverheid. Specifieker: naar de kansen die Retrieval Augmented Generation de rijksambtenaar zou kunnen bieden in de toekomst. Dit wordt onderzocht middels verschillende case studies.

# Retrieval
Retrieval in RAG staat voor het ophalen van relevante informatie uit een database op basis van een query. Veelal gebeurt dit middels een voorgetrainde neural retriever (zgn. dense retrieval). Lees meer [Lees meer]({{%ref "retrieval.md" %}})

# Generation
In de generatie-fase wordt, op basis van de relevante documenten, een antwoord op de query gegenereerd. Het taalmodel combineert de informatie uit de documenten om een goed onderbouwd antwoord te formuleren. [Lees meer]({{%ref "generation.md" %}})

# Overview
![Een visueel overzicht van een simpele RAG-pipeline](assets/RAGCHAIN.PNG)

# Verdere cruciale onderdelen van een RAG-pipeline
## Preprocessing
Voordat een retriever zijn werk kan doen, worden documenten opgedeeld in kleine stukken, oftewel "chunks", die vervolgens klaar worden gemaakt voor opslag in een vectorstore (een specifiek type database) Dit maakt het eenvoudiger om relevante informatie snel te vinden wanneer er een vraag wordt gesteld. [Lees meer]({{%ref "preprocessing.md" %}})

## Evaluation
Het evalueren van de gegenereerde antwoorden blijft een cruciale stap. Voor de kwaliteit van de retrieval worden andere evaluatiecriteria gehanteerd dan voor de kwaliteit van het gegenereerde antwoord. Voor RAG is het verstandig om zowel kwalitatieve, als kwantitatieve metrics te gebruiken voor het evalueren van de effectiviteit van een pipeline. [Lees meer]({{%ref "preprocessing.md" %}})
