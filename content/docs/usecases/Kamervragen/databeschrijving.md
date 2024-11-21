---
title: "Beschrijving van de data"
weight: 1
---

## Databehoefte vanuit JenV
In de use case is vastgesteld dat er documenten gebruikt worden van Kamervragen met beantwoording uit de [De open data van de Tweede Kamer | Open Data Portaal](https://opendata.tweedekamer.nl/). Hierbij wordt geen onderscheid gemaakt in de verschillende ministeries. 

Alleen de data vanaf 2011 t/m eind 2023 worden gebruikt. Dit heeft een aantal redenen:

- De data lijkt op verschillende manieren gestructureerd. Er is een oude opmaak en een nieuwe. Deze is veranderd rond 2010/2011.
- De PoC wordt door JenV beproefd met data die voor het AI-systeem ‘onbekend’ is. Dit is een set van de 50 meest recente Kamervragen die al eerder zijn beantwoord, dus Kamervragen vanaf januari 2024.

Binnen deze scope zal ook gekeken worden naar de invloed van verschillende tijdsperiodes van de data op de performance van het AI-systeem. Daarom krijgt de gebruiker in de User Interface drie opties: data vanaf 2010, data vanaf 2018 en data vanaf 2021. 

## Hoe ziet de data eruit?
In de API zitten documenten die elk een unique document ID hebben. Deze documenten hebben verschillende formats (zoals .pdf of .docx). Deze zien er als volgt uit (met de nieuwe opmaak):

<img src="/KopKamervraag.png" alt="KopKamervraag">

Bovenaan de pagina staat een nummering in de reeks Kamervragen per vergaderjaar (in dit geval: 1314). Daarna volgt een inleiding waar onder andere de aanleiding van de vraag staat beschreven en wie de vraag stelt aan welke minister. In dit geval: “Vragen van de […] 25 maart 2024)”. Daarna volgt een opsomming van subvragen met bijbehorende antwoorden, waarbij steeds eerst de vraag wordt weergegeven en daarna het antwoord. Deze hebben hetzelfde nummer:

<img src="/vraag-antwoord.png" alt="logo">

## Uitdagingen
Er zijn verschillende uitdagingen als het om het verwerken en verwerken van deze data gaat:

- In de Kamervragen zijn soms foutjes geslopen. Bijvoorbeeld: vraag 3 staat netjes uitgetypt en gemarkeerd als vraag 3, maar antwoord 3 staat niet aangegeven en volgt na een kopie van vraag. Dit soort afwijkingen kunnen we nog niet goed verwerken.
- In de Kamervragen wordt er altijd verwezen naar een bepaald artikel. Dit artikel is erg belangrijk om de context van de Kamervraag te begrijpen en de vraag inhoudelijk goed te kunnen interpreteren. De inhoud van dit artikel staat niet in de Kamervraag zelf en moet dus op een andere manier worden meegegeven aan het AI-systeem.
