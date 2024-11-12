---
author: Daan Wijnhorst
date: 2024-10-01
linktitle: Een beschouwing op de eerste experimenten
title: Een beschouwing op de eerste experimenten
weight: 10
tags: [
    "development",
    "RAG-pipeline",
    "use case Kamervragen",
]
---

Binnen het project LearningLion werken we aan een use case voor de beantwoording van Kamervragen. Hiervoor wordt een eerder ontwikkelde RAG-pipeline doorontwikkeld. Uit eerdere documentatie hierover wordt niet meteen duidelijk waarom enkele parameters en modellen zijn gekozen in de pipeline tot nu toe. Vaak zitten er logische heuristieken achter en soms lijkt door anekdotisch experimenten besloten om voor sommige numerieke parameters te gaan. We willen steeds meer richting het op basis van experimenten kiezen voor de belangrijkste parameters in de RAG-pipeline en bijbehorende methodes om deze resultaten te vergelijken, zodat ons proces transparanter en reproduceerbaar  is.

Het blijkt echter dat het uitvoeren van deze experimenten in de praktijk lastiger is dan gedacht. De samenwerking om AI-experimenten transparant en accuraat uit te voeren gaat gepaard met een logische stroefheid om te begrijpen wat nodig is. Dit zal enerzijds te maken hebben met het gebrek aan bestaande teamvorming en anderzijds met het vallen in een bestaande (onoverzichtelijke) code-base. 

Ten eerste is er nog geen bestaand team met bestaande structuren waarmee doorgebouwd kan worden. Alle processen binnen het team moeten daarom vormgegeven worden en is het zoeken naar de juiste structuur en communicatie. Zo zijn er veel mislukte experimenten waarin er langs elkaar heen werd gepraat wat betreft de data en de scope. Goede communicatie is belangrijk waarin verschillende expertises samenkomen. 

Ten tweede is de code-base die gebruikt wordt al opgebouwd, maar niet inzichtelijk. De code-base is gebaseerd op een ander open source project (buiten LearningLion). Daarna is er steeds mee doorgewerkt totdat het spaghetticode is geworden. Door alle verschillende frameworks en libraries, wordt de exacte functionaliteit geabstraheerd. Het is daarom belangrijk om per subgebied van de code te kijken naar exact wat er inkomt en wat er uit gaat voordat er conclusies getrokken kunnen worden. 

Er zijn dus veel onvoorziene zaken die naar boven komen drijven tijdens het uitvoeren van micro-experimenten. Het is zaak om in de bestaande code-base te duiken en de materie eigen te maken om door te kunnen ontwikkelen. 

