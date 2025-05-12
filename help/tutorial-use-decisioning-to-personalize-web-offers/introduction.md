---
title: Anpassa webblösningar med beslutande
description: Lär dig använda Journey Optimizer (AJO) Decisioning för att leverera personaliserade erbjudanden på en webbsida genom att utnyttja målgruppssegmentering som är inbyggd i Experience Platform (AEP).
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
source-git-commit: 0c42bf9a9af53bf80a14d904733ae0c1f03be0ee
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Använd beslut för att personalisera webberbjudanden

Den här självstudiekursen bygger vidare på en tidigare skapad målgruppssegmentering med Adobe Experience Platform (AEP) Web SDK. I den [tidigare självstudiekursen](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction) hämtades användarpreferenser - t.ex. intresse för Stock, Obligationer och Insättningscertifikat (CD) - och användes för att segmentera individer till målgrupper inom Adobe Experience Platform (AEP). Den här självstudiekursen bygger vidare på den grunden genom att använda Adobe Journey Optimizer (AJO) Decisioning för att leverera personaliserade finansiella erbjudanden till dessa målgrupper i realtid, vilket förbättrar både engagemang och konverteringsresultat.

Du kan testa de personaliserade AJO-erbjudandena live via länken nedan.
[Klicka här om du vill se den live-demon](https://gbedekar489.github.io/finwise/welcome.html) - sidan visar erbjudanden i realtid baserat på dina investeringsinställningar.

## Krav för den här självstudien

* Tillgång till Adobe Experience Platform

* Grundläggande förståelse för Adobe Experience Platform koncept (profiler, målgrupper, datauppsättningar)

* Välbekant med Adobe Journey Optimizer

* Grundläggande JavaScript-kunskap (att läsa och skriva enkla funktioner)

* Möjlighet att använda DevTools för webbläsare (flikarna Konsol och Nätverk)


## Mål

Den här självstudiekursen vägleder dig genom att leverera skräddarsydda investeringserbjudanden - som Stock, Bonds och CD - på en webbplats med Adobe Journey Optimizer (AJO). Genom att utnyttja strategier för målgruppssegmentering och -beslutsfattande kan ni se till att varje besökare ser det mest relevanta erbjudandet baserat på deras önskemål.

## Verktyg som används

* Adobe Experience Platform (AEP)
* Adobe Journey Optimizer (AJO)
* Adobe Experience Platform-taggar
* AEP Web SDK (Alloy.js)
* AEP Edge Segmentering
* En webbsida som visar erbjudandena
