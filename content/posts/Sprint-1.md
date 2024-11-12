---
author: Daan Wijnhorst
date: 2024-11-04
linktitle: Technische sprint 1
title: De uiktomsten van de eerste sprint
weight: 10
tags: [
    "development",
    "RAG-pipeline",
    "use case Kamervragen",
]
---

# Aanleiding
Op basis van de eerste experimenten en de schoongeveegde code zijn we begonnen om toe te werken naar minimale applicatie. Dit doen we op basis van twee sprints. 
In sprint 1 ligt de focus op het opbouwen van de pipeline en het werkend krijgen van alle onderdelen. In de tweede sprint ligt de focus op de optimalisatie van de pipeline.

# Doelstelling
Het doel van sprint 1 was om vanuit de opgeschoonde code deployments te creëren binnen het UbiOps-platform om zo inzicht te krijgen in de bottlenecks, zodat er effectief kan worden doorontwikkelt. 

# Waar staan we nu?
Op het moment hebben we een webapp ontwikkeld. De essentiële functies zijn getransformeerd tot deployments (microservices). De eindgebruiker kan een query sturen, er worden documenten retrieved en een LLM genereert een antwoord, welke wordt teruggestuurd naar de eindgebruiker.

Dit alles gebeurt binnen het UbiOps SaaS platform. Dit gebruiken we tijdelijk, aangezien het tot nu toe nog niet lukt om de eigen server met het UbiOps platform aan het open internet te hangen.
Om migratie zo soepel mogelijk te laten verlopen wanneer de server eenmaal in de lucht is, bouwen we onze architectuur alvast op het UbiOps platform.

Met betrekking tot de use case zijn hier nog een aantal bewegende delen. Zo is er over datascope en query nog geen akkoord.

# Observaties

- Bij gebruik van UbiOps SaaS hebben we te maken met een cold start wanneer er wordt teruggeschaald naar 0. Voor testen en ontwikkelen is dit niet erg snel. Echter, in productie zou dit geen probleem hoeven zijn. Daardoor hebben we nog niet uitgebreid kunnen testen. Door deze cold starts is genereren een trage aangelegenheid welke aandacht verdient in de verdere ontwikkeling in sprint 2.
- De database waaruit de retrieval-stap put is beperkt tot een aantal maanden (2024-1-1 t/m 2024-8-31).
- De links naar de oorspronkelijke documenten waar de retrieved documenten uit komen werken nog niet. Dit verdient aandacht voor in sprint 2. Er zijn twee opties om dit op te lossen: direct redirecten naar files uit API / Tweedekamer.nl, of de documenten zelf in een eigen database hosten.
- Het is onduidelijk hoe feitelijk de LLM genereert en hoe relevant de bronnen die nu naar boven komen daadwerkelijk zijn. Er moeten hiervoor performance metrics worden opgesteld en een test set worden vastgesteld.

# Hoe ziet de huidige pipeline eruit?
De manier hoe de huidige pipeline eruit ziet, vormt een basis voor Sprint 2:

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"> 
  Gebruikt embeddingsmodel
  </div>
  <div style="flex: 1;">
    <a href="https://huggingface.co/textgain/allnli-GroNLP-bert-base-dutch-cased">allnli-GroNLP-bert-base-dutch-cased</a>
  </div>
  </div>

<br />

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"> 
  Gebruikte LMM
  </div>
  <div style="flex: 1;">
    <a href="https://huggingface.co/BramVanroy/fietje-2-instruct">fietje-2-instruct</a>.
  </div>
  </div>

<br />

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"> 
  Gebruikte Chunker
    
  Chunksize
  
  Overlap
  </div>
  <div style="flex: 1;">
  RecursiveCharacterTextSplitter
    
  100
  
  20
  </div>
  </div>

<br />

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"> 
  Gebruikte Retriever
  </div>
  <div style="flex: 1;">
  EnsembleRetriever (BM25 from langchain + Chroma as retriever) 50/50
  </div>
  </div>

<br />

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"> 
  Similarity
  </div>
  <div style="flex: 1;">
  ‘Similarity search’ (default chroma.as_retriever (waarsch. L2 Euclidean))
  </div>
  </div>

<br />

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"> 
  Ingestion
  </div>
  <div style="flex: 1;">
  Batch size = 50 for adding to vectorstore
  </div>
  </div>

<br />

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"> 
  Omschrijving: welke data wordt er gebruikt en hoe ziet deze er precies uit?
  </div>
  <div style="flex: 1;">
  Tot nu toe wordt de periode 2024-1-1 t/m 2024-8-31 gebruikt als bron uit de <a href="https://opendata.tweedekamer.nl/">Open data API van de Tweede Kamer</a>.
  </div>
  </div>

<br />

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"> 
  Verwerking: Hoe wordt de data verwerkt? (zowel voor knowledgebase als wat er in de query binnenkomt)
  </div>
  <div style="flex: 1;">
  Zie bovenstaand. Basis RAG pipeline. Van bestand naar string, opgeknipt. 
  </div>
  </div>

<br />

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"> 
  Input: Welke data wordt er verwacht in de query?
  </div>
  <div style="flex: 1;">
  Een kamervraag / subvraag.
  </div>
  </div>

<br />

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"> 
  Algemene beschrijving van de user interface
  </div>
  <div style="flex: 1;">
  De user interface is een simpele chatbot interface waar de beantwoorder is aangegeven als Learning Lion (GenAI), welke antwoord geeft op de user input. Het is duidelijk gemaakt dat de gebruiker met een AI-systeem communiceert met een antwoord in de vorm van: "Learning Lion (genAI): Here is the information you requested". Er is in de user interface nog niet ingebouwd dat de gebruiker zich bewust is van diens menselijk toezicht op de antwoorden van het AI-systeem. Ook is er nog niet echt rekening gehouden met toegankelijkheid. De applicatie is eenvoudig te gebruiken, doordat er met een simpele interface wordt gewerkt à la de bekende chatbots, wordt er ingespeeld op patronen die gebruikers uit deze applicaties kennen. Onder het gegenereerde antwoord wordt een bronnenlijst weergegeven op basis van welke antwoorden het AI-systeem het antwoord heeft gebaseerd. 
  </div>
  </div>

<br />

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"> 
  Hoe is het systeem (RAG-pipeline) gedeployed?
  </div>
  <div style="flex: 1;">
  Via het middleware platform UbiOps, tijdelijk in hun SaaS dienst zolang er nog geen server on prem de lucht in kan. Zo kunnen we simpel en effectief alvast een kijkje krijgen in de keuken van UbiOps.
  </div>
  </div>

# Focuspunten voor Sprint 2.1

- Grote onderzoeksvraag: hoe kunnen we makkelijk migreren naar onze eigen hardware?
- Hyperlinks toevoegen aan bronnen in de bronvermelding. Zo kan je makkelijk inzien of iets semantisch relevant is aan de query.
- Clean up van de code; deze is wat vervuild doordat er gemigreerd is naar het Ubi-Ops platform
- Preprocessing van de Kamervragen (bronnen) verbeteren. Deze ook nog aanpassen op de criteria van DPGenV.
- Modulariseren van de database
- Chathistory samenvatten
- Retrieverensemble optimaliseren: hoe wordt er gezocht, wat is het meest kansrijk?
- Intern testomgevingkje bouwen. Als we 'in productie' gaan, hoe houden we inzicht in wat waar gebeurd?

