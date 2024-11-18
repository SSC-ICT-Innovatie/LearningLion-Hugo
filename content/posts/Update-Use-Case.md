---
authors: Lara Mutsaers 
date: 2024-11-12
linktitle: Update Use Case Kamervragen
title: Update Use Case Kamervragen
weight: 10
tags: [
    "proces",
    "kennis over AI",
    "use case Kamervragen",
    "Datascope",
    "Menselijk overzicht",
]
---

Vorige week hebben we gezamenlijk met de collega’s van DPGenV (Directoraat-Generaal Politie en Veiligheidsregio’s) de use case vastgesteld. Dit was noodzakelijk, omdat de databehoefte nog niet helemaal duidelijk was. Dit heeft implicaties voor de technische doorontwikkeling van de tool. Er zijn een aantal belangrijke beslissingen gemaakt:

-	De datascope is nu vastgesteld. De retriever put nu uit volledige Kamervragen met beantwoording tot en met eind 2023. Dit zijn Kamervragen van alle departementen en ministeries die binnen dit tijdsbestek vallen. Dit is belangrijk, omdat de gebruiker volledig overzicht krijgt in welke vragen er al zijn gesteld. De gebruiker krijgt hierbij drie opties voor hoever de data teruggaat: vanaf 2010, vanaf 2018 en vanaf 2021. Voor de gebruiker is dit fijn, omdat hij zo bijvoorbeeld onderscheid kan maken tussen verschillende ambtsperiodes. Voor ons is deze cut off ook interessant, omdat het ons in staat stelt te onderzoeken hoe precies de retriever is met datasets van verschillende groottes. Meer data betekent meer informatie, maar ook meer ruis. 
-	Er is vastgesteld dat de gebruiker een query gaat invoeren die bestaat uit een gehele Kamervraag (zonder beantwoording) met eventuele extra relevante informatie. Denk hierbij bijvoorbeeld aan keywords uit een nieuwsbericht. Dit kan extra semantiek toevoegen die de retriever kan gebruiken om relevante informatie op te halen. Vrijwel in elke Kamervraag wordt namelijk verwezen naar een nieuwsartikel, waar vervolgens veel subvragen op aansluiten.
-	De retrieval stap en de generation stap zijn uit elkaar getrokken. Na de retrieval stap moet de gebruiker inschatten of de opgehaalde bronnen relevant zijn voor hetgeen wat de gebruiker zoekt. Ook kan de gebruiker nog extra informatie meegeven aan de generator, zoals keywords van nieuwsberichten. Een belangrijke voorwaarde is hiervoor wel dat deze extra bronnen/informatie uitsluitend meegegeven mogen worden aan het taalmodel als dat juridisch is toegestaan. Het lostrekken van deze stappen geeft de gebruiker meer controle over het resultaat.
-	Er gaat vanuit de kant van JenV getest worden met 50 recente Kamervragen die niet in de dataset zitten die hierboven is beschreven (dus daterend van 2024). Dit zijn vragen waar DPGenV de primaire beantwoorder is. Er wordt getest in drie batches van respectievelijk 20, 15 en 15. JenV heeft hiervoor beoordelingscriteria opgesteld.
-	Er zijn twee extra secondary actors toegevoegd aan de use case om externe validiteit van onze eigen tool te kunnen toetsen. 
