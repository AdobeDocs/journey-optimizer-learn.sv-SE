---
title: Skapa Adobe Experience Platform-taggar
description: Skapa AJO-målgrupper baserat på användarnas investeringsinställningar (Stocks, Bonds, CD)
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17923
exl-id: 6823ce13-bc77-4e2b-89e0-606e403c15f2
source-git-commit: 2ca9ffee1a2326b8ae55a8e8de496a632fea79c8
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---

# Skapa Adobe Experience Platform

Adobe Launch är konfigurerat på webbsidan för att läsa in Adobe Experience Platform Web SDK, vilket aktiverar API-anropet sendEvent för att aktivera personaliserade upplevelser. Med den här installationen säkerställs att nödvändiga klientbibliotek initieras korrekt, vilket möjliggör realtidsinteraktion med Adobe Journey Optimizer för leverans av erbjudanden.

* Logga in i datainsamling
* Klicka på Taggar -> Ny egenskap
* Skapa en Adobe Experience Platform-tagg som kallas ECID-tjänst.

* Lägg till följande tillägg i taggen
  ![tags-extensions](assets/ecid-tag.png)

* Se till att konfigurera Adobe Experience Platform Web SDK så att rätt miljö och det dataflöde för finansiella rådgivare som skapades i den tidigare självstudiekursen används
  ![web-sdk-configuration](assets/web-sdk-configuration.png)

* Ingen ytterligare konfiguration krävs för Adobe Client Data Layer och Core Extensions

## Skapa dataelement

ECID-dataelementet i Adobe Launch skapas endast för felsökning och testning. Det gör att utvecklare kan visa det Experience Cloud-ID som tilldelats en användares webbläsarsession, vilket kan hjälpa till att validera identitetssammanfogning och säkerställa att sendEvent-anropen är kopplade till rätt profil. Det här elementet krävs inte för att personalisering ska fungera, men är användbart under implementering och kvalitetskontroll

![ecid](assets/ecid-data-element.png)


## Inkludera AEP-taggar på HTML-sidan

Skapa och publicera Adobe Experience Platform-taggar

När en AEP Tags-egenskap publiceras ger Adobe dig en script-tagg som du måste placera i din HTML ``` <head>``` eller längst ned i ``` <body>``` -taggarna.

* Gå till egenskapen Tags(ECID Service).

* Klicka på Miljöer och klicka på installationsikonen för den miljö du vill ha (till exempel Utveckling, Förproduktion, Produktion).

* Notera den inbäddade koden. Den här koden måste placeras precis före den avslutande ```</body>```-taggen på HTML-sidan.
