---
title: "Versiebeheer use case Kamervragen"
weight: 2
---

## Versie 0.7 (06-11-2024)

Het doen van tekstvoorstellen voor het beantwoorden van schriftelijke Kamervragen
<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Beschrijving
</div>
<div style="flex: 2;">
Het AI-systeem ondersteunt bij het opstellen van antwoorden op Kamervragen, wat de efficiëntie van het werk kan bevorderen. 

<strong>Retrieval</strong>
Op basis van de query (gehele Kamervraag plus eventuele extra relevante informatie (bijvoorbeeld de titel, een beschrijving van, of keywords uit een bijbehorend nieuwsartikel)) van de gebruiker doorzoekt het AI-systeem de schriftelijke Kamervragen (met beantwoording). Het AI-systeem geeft op basis van de query relevante stukken tekst uit de schriftelijke Kamervragen (met beantwoording) terug. 

<strong>Tussenstap</strong>
De primaire actor (gebruiker) beslist welke brondocumenten er wel en niet worden meegegeven in de generation-stap. De gebruiker heeft in deze stap opnieuw de mogelijkheid om zelf extra relevante informatie toevoegen die ook meegenomen moet worden bij het genereren van het antwoord. 

<strong>Generation</strong>
Op basis van de brondocumenten van de opgehaalde (retrieved) relevante stukken tekst uit de schriftelijke Kamervragen (met beantwoording) plus eventuele extra toegevoegde eigen bronnen (zoals nieuwsartikelen of sentiment) wordt een tekstvoorstel gegenereerd voor het beantwoorden van de query.
N.B. De aanvullende eigen bronnen/informatie mogen uitsluitend aan het taalmodel worden verstrekt indien dit juridisch is toegestaan.

Voor deze PoC willen we in de query alleen Kamervragen gebruiken waar één bewindspersoon van JenV beantwoorder is (eenvoudigste situatie) en verder gebruiken we alleen Kamervragen waar een van de bewindslieden van DPGenV de primaire beantwoorder is.

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
LearningLion (Opensource genAI on-premise oplossing ontwikkeld door SSC-ICT)

<strong>Secondary Actor 2 (Scenario 2):</strong>
Azure OpenAI (GenAI oplossing op Azure met AOAI service – data staat in Azure: SSC-ICT faciliteert het Azure platform voor o.a. de AOAI diensten en geeft ontwikkelaars van Microsoft of partner daar toegang toe)

<strong>Secondary Actor 3 (Scenario 3):</strong>
Codi (De virtuele beleidsassistent van Joinseven:  Kamervragen snel beantwoorden | Bespaar tijd en moeite met Codi (joinseven.nl)). Ontstaan vanuit een ministerie-overstijgende pilot samen met de directies van Financiën, EZK, VWS, Belastingdienst, RVO en Douane.   
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Preconditions
</div>
<div style="flex: 2;">
De retriever put uit:

Kamerstukken (De open data van de Tweede Kamer | Open Data Portaal / Kamerstukdossier | <a href="https://opendata.tweedekamer.nl/">Open data van de Tweede Kamer</a>.)
- De Kamervragen met beantwoording  van alle ministeries en departementen.
- Alleen Kamervragen met beantwoording tot en met eind 2023. Drie opties voor tijdsscope:
  - Vanaf 2010
  - Vanaf 2018
  - Vanaf 2021
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Postconditions
</div>
<div style="flex: 2;">
  
- De opgehaalde relevante (sub)Kamervragen met beantwoording uit de retriever zijn zichtbaar inclusief de gehele brondocumenten.
- Gebruiker beslist welke brondocumenten er wel en niet worden meegegeven in de generatorstap. De gebruiker kan in deze stap zelf extra relevante informatie toevoegen. 
- Het gegenereerde antwoord is zichtbaar, inclusief referenties naar de brondocumenten waarop het antwoord is gebaseerd. De historie van ingevoerde queries en daarbij behorende gegenereerde antwoorden blijven zichtbaar voor de gebruiker, en worden opgeslagen.
  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Triggers
</div>
<div style="flex: 2;">
  
- Primaire actor typt -de Kamervraag (query)- in het systeem en drukt op ENTER. Zie het kopje beschrijving voor specificering van de query.
We testen met een serie van 50 Kamervragen, verdeeld in drie batches van respectievelijk 20, 15 en 15 Kamervragen. Deze 50 Kamervragen komen uit begin 2024.
- Primaire actor cureert opgehaalde Kamervragen met beantwoording, opgehaald door de retriever, en voegt eventuele extra relevante informatie toe en drukt op ENTER.
  
</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Main Succes Scenario
</div>
<div style="flex: 2;">
De applicatie ondersteunt bij het opstellen van antwoorden op schriftelijke Kamervragen. Daarbij is alleen informatie gebruikt die uit de brondocumenten van de relevante stukken tekst te herleiden is en eventueel relevante informatie dat is toegevoegd door de gebruiker. Deze brondocumenten zijn herleidbaar in de vorm van referenties. 

Vereisten uitkomst tekstvoorstel:
- Gemiddeld 50-250 aantal woorden (per subvraag);
- Als er geen (of te weinig) relevante stukken tekst zijn gevonden, wordt door het systeem aangegeven dat het systeem het antwoord niet ‘weet’. 

Nice to have:
- Het antwoord is in dezelfde toon als die van de eerder beantwoorde Kamervragen van dezelfde bewindspersoon;

</div>
</div>

<br />

<div style="display: flex; gap: 20px;">
<div style="flex: 1;">
Extensions
</div>
<div style="flex: 2;">
Eén van de beide onderdelen van deze use case werkt naar verwachting. De retriever OF de generator (eventueel zou dit kunnen leiden tot koppeling van artefacten van verschillende actoren).
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
