---
weight: 3
bookFlatSection: true
title: "Generation"
---

# Generation - Genereren

In de generatie-fase wordt, op basis van de relevante documenten (gevonden door de retriever), een antwoord op de query gegenereerd. Het taalmodel (LLM) combineert de informatie uit de documenten (de context), om een goed onderbouwd antwoord te formuleren. Daarbij wordt het model geïnstrueerd om zich in het genereren van een antwoord te beperken tot de vraag en de context.

De LLM is voorgetraind op grote hoeveelheden tekst. In het geval van Rag, vaak op vragen en antwoorden, zodat het model goed is in het voorspellen van taal. Ondanks dat het antwoord op de query specifiek gebaseerd is op de context, is de kans op hallucineren aannemelijk. Echter, omdat het taalmodel specifiek de taak krijgt om materiaal te genereren op basis van een vraag en expliciete tekst uit een eigen database, is (intuïtief) de kans op hallucinaties kleiner en de kans op feitelijk juiste informatie in een ander jasje (bijvoorbeeld uit meerdere bronnen samengevat) groter.
