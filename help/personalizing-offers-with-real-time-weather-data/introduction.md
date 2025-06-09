---
title: Anpassa erbjudanden med Weather-data i realtid i Adobe Journey Optimizer med Web SDK
description: Den här självstudiekursen visar hur du kan leverera dynamiska, vädermedvetna erbjudanden i Adobe Journey Optimizer med hjälp av sammanhangsberoende data i realtid och Adobe Web SDK Personalization API. Du får lära dig att skicka väderattribut (som temperatur och förhållanden) från din webbplats till Adobe Experience Platform, mappa dem till ditt eventschema och använda dem i beslutsregler och rankningsformler för att anpassa erbjudanden när sidan läses in. Idealiskt för marknadsförare och utvecklare som vill förbättra digitala upplevelser med miljösammanhang i realtid.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18258
source-git-commit: d46c5a922b8448f57b8a730188284294c3caba96
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---

# Använd fallbeskrivning

Genom att använda väderrelaterade data i Adobe Journey Optimizer (AJO) för att leverera erbjudanden kan företag personalisera kundupplevelser baserat på miljöförhållanden i realtid. Väder är en kraftfull sammanhangsberoende signal. Folks behov och beteende förändras beroende på vädret. Genom att använda väderdata:

    Leverera relevanta erbjudanden som är anpassade efter kundernas sinnesstämning och miljö.
    
    På en varm dag kan du visa ett erbjudande för kalla drycker eller AC-enheter. En regnig dag: befordra schaket eller paraplyets

![vädererbjudanden](assets/offers-use-case.png)