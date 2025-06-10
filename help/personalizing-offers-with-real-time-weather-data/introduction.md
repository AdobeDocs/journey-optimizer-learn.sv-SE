---
title: Anpassa erbjudanden med Weather-data i realtid i Adobe Journey Optimizer med Web SDK
description: Den här självstudiekursen visar hur du kan leverera dynamiska, vädermedvetna erbjudanden i Adobe Journey Optimizer med hjälp av sammanhangsberoende data i realtid och Adobe Web SDK Personalization API. Du får lära dig att skicka väderattribut (som temperatur och förhållanden) från din webbplats till Adobe Experience Platform, mappa dem till ditt eventschema och använda dem i beslutsregler och rankningsformler för att anpassa erbjudanden när sidan läses in. Idealiskt för marknadsförare och utvecklare som vill förbättra digitala upplevelser med miljösammanhang i realtid.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18258
source-git-commit: c04a15418e31dc82597b7759386907013728bb0d
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Använd fallbeskrivning

Genom att använda väderrelaterade data i Adobe Journey Optimizer (AJO) för att leverera erbjudanden kan företag personalisera kundupplevelser baserat på miljöförhållanden i realtid. Väder är en kraftfull sammanhangsberoende signal. Folks behov och beteende förändras beroende på vädret. Genom att använda väderdata:

Leverera relevanta erbjudanden som är anpassade efter kundernas stämning och miljö

Visa ett erbjudande om kalldryck eller AC-enheter på en varm dag. På en regnig dag, främja schaker eller paraplyer

Exempel på väderbaserat erbjudande


![vädererbjudanden](assets/offers-use-case.png)



## Krav för den här självstudien

* Tillgång till Experience Platform

* Grundläggande förståelse för Adobe Experience Platform-taggar

* Grundläggande förståelse för Experience Platform koncept (profiler, målgrupper, datauppsättningar)

* Välbekant med Journey Optimizer

* Grundläggande JavaScript-kunskap (att läsa och skriva enkla funktioner)

* Möjlighet att använda DevTools för webbläsare (flikarna Konsol och Nätverk)
