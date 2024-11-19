---
linktitle: RAG-pipeline
title: RAG-pipeline
---
Een RAG-pipeline is een keten van subprocessen die samen als doel hebben om vanuit een vraag van een gebruiker (user):
- voor de vraag relevante informatie op te halen uit een [vectorstore]({{%ref "Vectorstore.md" %}}) middels een [retriever]({{%ref "retriever.md" %}}).
- De vraag te beantwoorden met een [taalmodel]({{%ref "taalmodel.md" %}}).
