---
author: Lara Mutsaers
date: 2024-10-22
linktitle: Observaties aanscherpen van de use case Kamervragen
title: Observaties aanscherpen van de use case Kamervragen
weight: 10
---

Vanuit het bestuursdepartement van DGPenV (Directoraat-Generaal Politie en Veiligheidsregio’s), wat valt onder het ministerie van Justitie en Veiligheid (JenV), hebben wij een use case gekregen voor het beantwoorden van Kamervragen. 
Deze use case is meerdere malen aangescherpt. 

De [eerste versie]({{%ref "versiebeheer_usecaseKamervragen.md" %}}) dateert van september 2024. Deze versie hebben wij onder andere na een gesprek met beleidsmedewerkers van DGPenV aangescherpt. 
Het gesprek had als doel om het proces van de beantwoording van Kamervragen helder te krijgen en te begrijpen waar in het proces de tool eventueel gebruikt gaat worden.

Uit dit gesprek kwam naar voren dat momenteel het grootste pijnpunt vooral de tijdrovende manier van zoeken van de juiste bronnen om een Kamervraag te beantwoorden is. Het zoeken in de beschikbare databases gaat nu traag en niet alle relevante informatie wordt gevonden. 
Semantisch- of hybride zoeken, wat met RAG gebeurt, zou dus een meerwaarde kunnen zijn ten opzichte van de klassieke zoeksystemen die al bestaan. 
Verder kwam uit dit gesprek naar voren dat een dergelijke tool, die mogelijk zou kunnen voortkomen uit het onderzoeksproject Learning Lion, zou kunnen bijdragen aan het zoeken naar vergelijkbare of dezelfde vragen. Zo behoud je consistentie in het beantwoorden van vergelijkbare vragen. 

Het mogelijke generatieve deel van de tool (Generatieve AI) wordt als meerwaarde gezien voor het genereren van een conceptantwoord. Daarbij is het belangrijk dat een medewerker niet zomaar de suggestie klakkeloos overneemt zonder zelf kritisch te blijven. 
Het liefst zou de tool in eerste aanleg worden gebruikt door de staff-medewerker die aan de vraag wordt gekoppeld. Op deze manier kan de staff-medewerker het concept-antwoord en de relevante bronnen als voorbereiding meegeven aan de dossierhouder die de vraag verder oppakt. 
Deze informatie vanuit het gesprek is gebruikt om de use case verder aan te scherpen.

De drie versies van de use case die daarop volgde hebben vooral te maken met het duidelijk krijgen van de datascope. 
Ten eerste was het originele plan om, naast de openbare kamerstukken uit de API van het [Open Data Portaal](https://opendata.tweedekamer.nl/), ook de data uit de knipselkrant van JenV te gebruiken. Het archief van de knipselkrant is geen openbare data en het bleek lastig om hier de juiste licenties voor te regelen. De huidige Knipselkrant gaat tot vijf dagen terug en is op het intranet te vinden. Het is echter de vraag of we de juiste rechten hebben om deze data elke week op te slaan en aan de knowledge base toe te voegen. Voor het gemak laten we de Knipselkrant nu buiten wegen. 

Een tweede vraagstuk waar we tegenaan liepen was de datascope die we gebruiken voor de knowledge base van het model en de testset. Hier was wat verwarring ingeslopen omdat er onduidelijkheden ontstonden over de werking van het model en het vakjargon. Er werd begrijpelijkerwijs gedacht dat de tool die voortkomt uit Learning Lion een heel nieuw model zou zijn, dat daadwerkelijk getraind/gefinetuned zou worden met de aangeleverde data. Dit is echter niet het geval. We maken gebruik van bestaande modellen (waaronder een embeddingsmodel en een Large Language model (LLM)). Aan deze modellen (de pipeline) voegen we een context toe, een zogenaamde knowledge base. Dit moet je zien als een archiefkast waarin het model kan zoeken. 
Op basis van deze onduidelijkheid hebben we een korte [explainer](https://github.com/SSC-ICT-Innovatie/LearningLion-kamervragen/blob/main/!%20project_docs/Explainer%20LearningLion%20(Kamervragen).pdf) gemaakt waarin de werking van Learning Lion wordt uitgelegd. Hierbij hebben we twee vragen naar JenV uitgezet om de datascope te bepalen:

1. <strong>Hoe groot wordt de brondata waarop de database wordt gebaseerd? (de knowledge base)</strong>
Wanneer de retriever een speld in een hooiberg mag zoeken, is het makkelijker om een speld te vinden in een kleinere hooiberg dan in een grote. Wanneer de database van eerder gestelde Kamervragen groot is, zal de ruis voor de retriever toenemen en de relevantie van de opgehaalde tekststukjes in de database afnemen. Wel is het belangrijk dat de hooiberg groot genoeg is zodat de externe validiteit van de RAG-pipeline wordt gewaarborgd. Het is aan te raden om de database te baseren op de zoekwijdte die het meest wordt gebruikt door domeinexperts.

2. <strong>Hoe worden vragen bewerkt om de externe validiteit van de tool te testen?</strong><br/>
De dataset die werd voorgesteld om steeds als een inkomende Kamervraag te fungeren (testset) bestaat uit 50 eerder gestelde sub-vragen. Omdat bij nieuwe Kamervragen vaak een exact correct antwoord ontbreekt, is het mogelijk interessant voor de externe validiteit van de test om deze subvragen anders te formuleren. Als we besluiten met subvragen te werken kan de inleiding van de set vragen van cruciaal belang worden voor een correct antwoord. Deze wordt dan mogelijk gevraagd om ook op te geven in de uiteindelijke tool.

Deze vragen resulteerden uiteindelijk in de conclusie dat voor de knowledge base alle data vanaf 2010 wordt gebruikt. Voor het testen van de tool worden enkel Kamervragen gebruikt van 01-01-2024 tot 01-07-2024, specifieker: de 50 recentste Kamervragen vanaf 30-07-2024. Er worden alleen vragen behandeld die door DPGenV worden beantwoord.

Ons advies blijft hiernaast nog steeds om de validiteit van de tool te toetsen door synthetische data te gebruiken (subvragen van daadwerkelijke Kamervragen herformuleren).

