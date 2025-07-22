---
title: Spåra och rapportera erbjudanden om Adobe Journey Optimizer (AJO) via AJO Offer Decisioning
description: Den här självstudiekursen utökar en befintlig Adobe Journey Optimizer-implementering (AJO) som levererar personaliserade erbjudanden baserat på kontextuella data som temperatur. Här beskrivs hur man fångar in intrycks- och interaktionshändelser och förbereder data för rapportering inom Journey Optimizer.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
source-git-commit: 551d0d365bcb42e63910af1fae626d1bbc1fabfa
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# Spåra och rapportera erbjudanden om Adobe Journey Optimizer (AJO) via AJO Offer Decisioning

Det här användningsexemplet fokuserar på att aktivera rapportering och resultatanalys för erbjudanden som levereras via Adobe Journey Optimizer (AJO). När erbjudanden personaliseras och levereras baserat på kontextuella signaler (som väder eller plats) är det viktigt att spåra både visningar och användarinteraktioner för att utvärdera deras effektivitet.

Genom att hämta in decisioning.propositionDisplay- och decisioning.propositionInteract-händelser via Adobe Web SDK och mappa dem till strukturerade XDM-scheman i Adobe Experience Platform (AEP) blir engagemangsdata på erbjudandenivå tillgängliga för analys. Dessa data kan sedan användas i Customer Journey Analytics (CJA) för att bygga instrumentpaneler, mäta nyckeltal som klickfrekvens (CTR) och jämföra erbjudandeprestanda för olika målgruppssegment och sammanhangsbaserade villkor.

Målet är att tillhandahålla tydliga, datadrivna insikter om hur väl personaliserade erbjudanden fungerar och att informera om framtida beslutsstrategier.



![Reporting-dashboard](assets/dashboard-reporting.png)


## Krav för den här självstudien

Innan du börjar slutför du självstudiekursen [Anpassa erbjudanden med väderdata i realtid.](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction) Alla grundläggande komponenter skapas, inklusive:

- Integrering med SDK
- Erbjudandet gäller i Adobe Journey Optimizer (AJO)
- Beslut med kontextuella attribut som väder och temperatur
- Erbjudandeåtergivning i realtid på en webbsida

Den här självstudiekursen bygger direkt på den implementeringen och fokuserar specifikt på att få offertvisningar och interaktioner för rapportering och analys i Journey Optimizer.
