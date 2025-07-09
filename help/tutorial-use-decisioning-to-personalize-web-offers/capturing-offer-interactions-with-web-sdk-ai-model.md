---
title: Samla in erbjudandeinteraktioner med Adobe Web SDK for AI Model Training
description: I den här artikeln fokuserar vi på att hämta in interaktionsdata från användare - t.ex. erbjudanden och klickningar - med Adobe Experience Platform Web SDK (alloy.js). Dessa data är grunden för utbildning i AI-modeller i Adobe Journey Optimizer (AJO) för att på ett intelligent sätt rangordna erbjudanden baserat på användarbeteende och sammanhangsbaserade signaler.
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
source-git-commit: dfb280df3453e7811dffd95b9af664b873a9af31
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---


# Samla in erbjudandeinteraktioner med Adobe Web SDK for AI Model Training

I den här artikeln beskrivs hur du fångar upp interaktionshändelser (som visningar eller klickningar) med hjälp av Adobe Experience Platform Web SDK genom att anropa alloy(&quot;sendEvent&quot;, ...) direkt i JavaScript-koden. Data kommer att hämtas in i AEP och användas för att utbilda AI-modeller i Adobe Journey Optimizer (AJO) för smartare rangordning av erbjudanden baserat på beteenden i realtid.

## Förhandskrav

Kontrollera följande innan du börjar:

- En fungerande Adobe Launch-egenskap med tillägget Adobe Experience Platform Web SDK installerat.

- En [datastream](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset) har konfigurerats och mappats till din AEP-sandlåda.

- En webbplats där Launch distribueras.


## Skapa schema och datauppsättning för offerthändelser

Om du vill samla in upplevelsehändelser måste du först skapa en datauppsättning där dessa händelser skickas.

Följ stegen som nämns i den här [artikeln för att skapa det schema och den datauppsättning som krävs](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset)

## Skapa ett datastream i AEP

![data-stream](assets/ai-model-data-stream.png)
Lägg till Adobe Experience Platform Service i datastream
![data-stream-service](assets/data-stream-service.png)

## Konfigurera Adobe Experience Platform Tag med Web SDK

I tilläggsinställningarna:

Konfigurera Adobe Experience Platform Web SDK-tillägget för att använda det datastream som skapats
