---
title: "Versiebeheer use case Kamervragen"
---

## Versie 0.5 (17-10-2024)

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Beschrijving
</div>
<div style="flex: 2;">
AI ondersteunt bij het opstellen van antwoorden op Kamervragen, wat de efficiëntie van het werk kan bevorderen. AI doorzoekt een database met kamerstukken (en nieuwsberichten) om relevante documenten te verzamelen, en genereert een concept antwoord gebaseerd op deze relevante documenten. Het concept antwoord van de Kamervraag kan de stafmedewerker gebruiken als voorwerk voor de dossierhouder die de Kamervraag daadwerkelijk beantwoordt.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Primary Actor
</div>
<div style="flex: 2;">
Parlementair staff medewerker  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Secondary Actor(s)
</div>
<div style="flex: 2;">
<strong>Secondary Actor 1 (Scenario 1):</strong>
  
Azure OpenAI (GenAI oplossing op Azure met AOAI service – data staat in Azure: SSC-ICT faciliteert het Azure platform voor o.a. de AOAI diensten en geeft ontwikkelaars van Microsoft of partner daar toegang toe)

<strong>Secondary Actor 2 (Scenario 1):</strong>

LearningLion (Opensource genAI on-premise oplossing ontwikkeld door SSC-ICT)  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Preconditions
</div>
<div style="flex: 2;">
Het systeem bevat (neartime) open data vanuit de kamerstukken uit de <a href="https://opendata.tweedekamer.nl/">Open data van de Tweede Kamer</a>.

- Enkel Kamervragen van 01-01-2024 tot 01-07-2024 worden gebruikt voor deze use case, nog specifieker de 50 recentste vanaf 30-07-2024.
- Alleen Kamervragen die door DGPenV worden beantwoord.
- De knowledge base is gevuld met data vanaf 2010.  

</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Postconditions
</div>
<div style="flex: 2;">
Het gegenereerde antwoord is zichtbaar, inclusief referenties naar de brondocumenten waarop het antwoord is gebaseerd. De historie van gegenereerde antwoorden staan in dezelfde chat/tab.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Triggers
</div>
<div style="flex: 2;">
Primaire actor typt -de Kamervraag- in het systeem en drukt op ENTER.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Main Succes Scenario
</div>
<div style="flex: 2;">
Primaire actor typt -de Kamervraag- in het systeem en drukt op ENTER. Het systeem produceert een lijst met relevante documenten voor deze vraag, met een gegenereerd concept-antwoord op een schriftelijke kamervraag, welke alleen informatie gebruikt die uit deze data te herleiden is.

Requirements uitkomst antwoord:
- Gemiddeld 50-250 aantal woorden;
- Het antwoord is in dezelfde toon als die van de eerder beantwoorde vragen uit de dataset;
- Door het systeem geraadpleegde bronnen worden met een voetnoot aan het antwoord gekoppeld. Deze bronnen zijn in hetzelfde systeem inzichtelijk.   
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Extensions
</div>
<div style="flex: 2;">
Primaire actor vraagt aan het systeem of er een Kamervraag met een bepaald onderwerp eerder is gesteld en wat het antwoord daarvan was. Het systeem genereert een uitkomst met Kamervragen en de daarbij behorende antwoorden die betrekking hebben op dit bepaalde onderwerp (deze Kamervragen en antwoorden zijn onbewerkt door het systeem!)  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Frequency of Use
</div>
<div style="flex: 2;">
DG-breed ca. 100 keer per jaar. (Dit is een zeer lage schatting, aangezien er dagelijks tientallen kamervragen gesteld worden. Het daadwerkelijke gebruik zal afhangen van JenV).  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Owner
</div>
<div style="flex: 2;">
Ministerie van Justitie en Veiligheid, Dienstencentrum.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Priority
</div>
<div style="flex: 2;">
Hoog  
</div>
</div>

## Versie 0.4 (02-10-2024)

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Beschrijving
</div>
<div style="flex: 2;">
AI ondersteunt bij het opstellen van antwoorden op Kamervragen, wat de efficiëntie van het werk kan bevorderen. AI doorzoekt een database met kamerstukken (en nieuwsberichten) om relevante documenten te verzamelen, en genereert een concept antwoord gebaseerd op deze relevante documenten. Het concept antwoord van de Kamervraag kan de stafmedewerker gebruiken als voorwerk voor de dossierhouder die de Kamervraag daadwerkelijk beantwoordt.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Primary Actor
</div>
<div style="flex: 2;">
Parlementair staff medewerker  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Secondary Actor(s)
</div>
<div style="flex: 2;">
<strong>Secondary Actor 1 (Scenario 1):</strong>
  
Azure OpenAI (GenAI oplossing op Azure met AOAI service – data staat in Azure: SSC-ICT faciliteert het Azure platform voor o.a. de AOAI diensten en geeft ontwikkelaars van Microsoft of partner daar toegang toe)

<strong>Secondary Actor 2 (Scenario 1):</strong>

LearningLion (Opensource genAI on-premise oplossing ontwikkeld door SSC-ICT)  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Preconditions
</div>
<div style="flex: 2;">
Het systeem bevat (neartime) open data vanuit de kamerstukken uit de <a href="https://opendata.tweedekamer.nl/">Open data van de Tweede Kamer</a>.

- Enkel Kamervragen van 01-01-2024 tot 01-07-2024 worden gebruikt voor deze use case, nog specifieker de 50 recentste vanaf 30-07-2024.
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Postconditions
</div>
<div style="flex: 2;">
Het gegenereerde antwoord is zichtbaar, inclusief referenties naar de brondocumenten waarop het antwoord is gebaseerd. De historie van gegenereerde antwoorden staan in dezelfde chat/tab.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Triggers
</div>
<div style="flex: 2;">
Primaire actor typt -de Kamervraag- in het systeem en drukt op ENTER.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Main Succes Scenario
</div>
<div style="flex: 2;">
Primaire actor typt -de Kamervraag- in het systeem en drukt op ENTER. Het systeem produceert een lijst met relevante documenten voor deze vraag, met een gegenereerd concept-antwoord op een schriftelijke kamervraag, welke alleen informatie gebruikt die uit deze data te herleiden is.

Requirements uitkomst antwoord:
- Gemiddeld 50-250 aantal woorden;
- Het antwoord is in dezelfde toon als die van de eerder beantwoorde vragen uit de dataset;
- Door het systeem geraadpleegde bronnen worden met een voetnoot aan het antwoord gekoppeld. Deze bronnen zijn in hetzelfde systeem inzichtelijk.   
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Extensions
</div>
<div style="flex: 2;">
Primaire actor vraagt aan het systeem of er een Kamervraag met een bepaald onderwerp eerder is gesteld en wat het antwoord daarvan was. Het systeem genereert een uitkomst met Kamervragen en de daarbij behorende antwoorden die betrekking hebben op dit bepaalde onderwerp (deze Kamervragen en antwoorden zijn onbewerkt door het systeem!)  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Frequency of Use
</div>
<div style="flex: 2;">
DG-breed ca. 100 keer per jaar. (Dit is een zeer lage schatting, aangezien er dagelijks tientallen kamervragen gesteld worden. Het daadwerkelijke gebruik zal afhangen van JenV).  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Owner
</div>
<div style="flex: 2;">
Ministerie van Justitie en Veiligheid, Dienstencentrum.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Priority
</div>
<div style="flex: 2;">
Hoog  
</div>
</div>

## Versie 0.3 (19-09-2024)

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Beschrijving
</div>
<div style="flex: 2;">
AI ondersteunt bij het opstellen van antwoorden op Kamervragen, wat de efficiëntie van het werk kan bevorderen. AI doorzoekt een database met kamerstukken (en nieuwsberichten) om relevante documenten te verzamelen, en genereert een concept antwoord gebaseerd op deze relevante documenten. Het concept antwoord van de Kamervraag kan de stafmedewerker gebruiken als voorwerk voor de dossierhouder die de Kamervraag daadwerkelijk beantwoordt.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Primary Actor
</div>
<div style="flex: 2;">
Parlementair staff medewerker  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Secondary Actor(s)
</div>
<div style="flex: 2;">
<strong>Secondary Actor 1 (Scenario 1):</strong>
  
Azure OpenAI (GenAI oplossing op Azure met AOAI service – data staat in Azure: SSC-ICT faciliteert het Azure platform voor o.a. de AOAI diensten en geeft ontwikkelaars van Microsoft of partner daar toegang toe)

<strong>Secondary Actor 2 (Scenario 1):</strong>

LearningLion (Opensource genAI on-premise oplossing ontwikkeld door SSC-ICT)  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Preconditions
</div>
<div style="flex: 2;">
Het systeem bevat (neartime) open data vanuit de kamerstukken uit de <a href="https://opendata.tweedekamer.nl/">Open data van de Tweede Kamer</a>.
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Postconditions
</div>
<div style="flex: 2;">
Het gegenereerde antwoord is zichtbaar, inclusief referenties naar de brondocumenten waarop het antwoord is gebaseerd. De historie van gegenereerde antwoorden staan in dezelfde chat/tab.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Triggers
</div>
<div style="flex: 2;">
Primaire actor typt -de Kamervraag- in het systeem en drukt op ENTER.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Main Succes Scenario
</div>
<div style="flex: 2;">
Primaire actor typt -de Kamervraag- in het systeem en drukt op ENTER. Het systeem produceert een lijst met relevante documenten voor deze vraag, met een gegenereerd concept-antwoord op een schriftelijke kamervraag, welke alleen informatie gebruikt die uit deze data te herleiden is.

Requirements uitkomst antwoord:
- Gemiddeld 50-250 aantal woorden;
- Het antwoord is in dezelfde toon als die van de eerder beantwoorde vragen uit de dataset;
- Door het systeem geraadpleegde bronnen worden met een voetnoot aan het antwoord gekoppeld. Deze bronnen zijn in hetzelfde systeem inzichtelijk.   
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Extensions
</div>
<div style="flex: 2;">
Primaire actor vraagt aan het systeem of er een Kamervraag met een bepaald onderwerp eerder is gesteld en wat het antwoord daarvan was. Het systeem genereert een uitkomst met Kamervragen en de daarbij behorende antwoorden die betrekking hebben op dit bepaalde onderwerp (deze Kamervragen en antwoorden zijn onbewerkt door het systeem!)  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Frequency of Use
</div>
<div style="flex: 2;">
DG-breed ca. 100 keer per jaar. (Dit is een zeer lage schatting, aangezien er dagelijks tientallen kamervragen gesteld worden. Het daadwerkelijke gebruik zal afhangen van JenV).  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Owner
</div>
<div style="flex: 2;">
Ministerie van Justitie en Veiligheid, Dienstencentrum.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Priority
</div>
<div style="flex: 2;">
Hoog  
</div>
</div>

## Versie 0.2 (18-09-2024)

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Beschrijving
</div>
<div style="flex: 2;">
AI ondersteunt bij het opstellen van antwoorden op Kamervragen, wat de efficiëntie van het werk kan bevorderen. AI doorzoekt een database met kamerstukken (en nieuwsberichten) om relevante documenten te verzamelen, en genereert een concept antwoord gebaseerd op deze relevante documenten. Het concept antwoord van de Kamervraag kan de stafmedewerker gebruiken als voorwerk voor de dossierhouder die de Kamervraag daadwerkelijk beantwoordt.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Primary Actor
</div>
<div style="flex: 2;">
Parlementair staff medewerker  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Secondary Actor(s)
</div>
<div style="flex: 2;">
<strong>Secondary Actor 1 (Scenario 1):</strong>
  
Azure OpenAI (GenAI oplossing op Azure met AOAI service – data staat in Azure: SSC-ICT faciliteert het Azure platform voor o.a. de AOAI diensten en geeft ontwikkelaars van Microsoft of partner daar toegang toe)

<strong>Secondary Actor 2 (Scenario 1):</strong>

LearningLion (Opensource genAI on-premise oplossing ontwikkeld door SSC-ICT)  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Preconditions
</div>
<div style="flex: 2;">
Het systeem bevat (neartime) open data vanuit de:

- Kamerstukken (De <a href="https://opendata.tweedekamer.nl/">Open data van de Tweede Kamer</a>).
- Knipselkrant (JenV)

</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Postconditions
</div>
<div style="flex: 2;">
Het gegenereerde antwoord is zichtbaar, inclusief referenties naar de brondocumenten waarop het antwoord is gebaseerd. De historie van gegenereerde antwoorden staan in dezelfde chat/tab.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Triggers
</div>
<div style="flex: 2;">
Primaire actor typt -de Kamervraag- in het systeem en drukt op ENTER.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Main Succes Scenario
</div>
<div style="flex: 2;">
Primaire actor typt -de Kamervraag- in het systeem en drukt op ENTER. Het systeem produceert een lijst met relevante documenten voor deze vraag, met een gegenereerd concept-antwoord op een schriftelijke kamervraag, welke alleen informatie gebruikt die uit deze data te herleiden is.

Requirements uitkomst antwoord:
- Gemiddeld 50-250 aantal woorden;
- Het antwoord is in dezelfde toon als die van de eerder beantwoorde vragen uit de dataset;
- Door het systeem geraadpleegde bronnen worden met een voetnoot aan het antwoord gekoppeld. Deze bronnen zijn in hetzelfde systeem inzichtelijk.   
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Extensions
</div>
<div style="flex: 2;">
Primaire actor vraagt aan het systeem of er een Kamervraag met een bepaald onderwerp eerder is gesteld en wat het antwoord daarvan was. Het systeem genereert een uitkomst met Kamervragen en de daarbij behorende antwoorden die betrekking hebben op dit bepaalde onderwerp (deze Kamervragen en antwoorden zijn onbewerkt door het systeem!)  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Frequency of Use
</div>
<div style="flex: 2;">
DG-breed ca. 100 keer per jaar. (Dit is een zeer lage schatting, aangezien er dagelijks tientallen kamervragen gesteld worden. Het daadwerkelijke gebruik zal afhangen van JenV).  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Owner
</div>
<div style="flex: 2;">
Ministerie van Justitie en Veiligheid, Dienstencentrum.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Priority
</div>
<div style="flex: 2;">
Hoog  
</div>
</div>

## Versie 0.1 (11-09-2024)

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Beschrijving
</div>
<div style="flex: 2;">
AI ondersteunt bij het opstellen van antwoorden op Kamervragen, wat de efficiëntie van het werk kan bevorderen. AI genereert een concept antwoord op een Kamervraag.
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Primary Actor
</div>
<div style="flex: 2;">
Parlementair staff medewerker  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Secondary Actor(s)
</div>
<div style="flex: 2;">
<strong>Secondary Actor 1 (Scenario 1):</strong>
  
Azure OpenAI (GenAI oplossing op Azure met AOAI service – data staat in Azure: SSC-ICT faciliteert het Azure platform voor o.a. de AOAI diensten en geeft ontwikkelaars van Microsoft of partner daar toegang toe)

<strong>Secondary Actor 2 (Scenario 1):</strong>

LearningLion (Opensource genAI on-premise oplossing ontwikkeld door SSC-ICT)  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Preconditions
</div>
<div style="flex: 2;">
Het systeem bevat (neartime) open data vanuit de:

- Kamerstukken (De <a href="https://opendata.tweedekamer.nl/">Open data van de Tweede Kamer</a>)
- Knipselkrant (JenV)

</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Postconditions
</div>
<div style="flex: 2;">
Gegenereerd antwoord is zichtbaar.
Historie van gegenereerde antwoorden staan in dezelfde chat/tab.
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Triggers
</div>
<div style="flex: 2;">
Primaire actor typt -de Kamervraag- in het systeem en drukt op ENTER.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Main Succes Scenario
</div>
<div style="flex: 2;">
Primaire acteur typt -de Kamervraag- in het systeem en drukt op ENTER. Uit die actie komt er een gegeneerd antwoord van een mondelinge of schriftelijke Kamervraag, met gebruik van in de use case aangewezen data. -

Requirements uitkomst antwoord:
-	x grootte (50-250  aantal woorden gemiddeld);
-	dezelfde toon antwoord als die van de eerder beantwoorde vragen;
-	door het systeem geraadpleegde bronnen worden met een voetnoot aan het antwoord gekoppeld inclusief gegeneerde bronnenlijst met URL’s die verwijzen naar de locatie van de bron;
-	…
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Extensions
</div>
<div style="flex: 2;">
Primaire acteur vraagt aan het systeem of een Kamervraag met x onderwerp eerder is gesteld en wat het antwoord daarbij is.
Systeem genereert een uitkomst met Kamervragen en de daar bijhorende antwoorden die betrekking hebben met x onderwerp (deze Kamervragen en antwoorden zijn onbewerkt door het systeem!)
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Frequency of Use
</div>
<div style="flex: 2;">
DG-breed ca. 100 keer per jaar. 
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Owner
</div>
<div style="flex: 2;">
Ministerie van Justitie en Veiligheid, Dienstencentrum.  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Priority
</div>
<div style="flex: 2;">
Hoog  
</div>
</div>
