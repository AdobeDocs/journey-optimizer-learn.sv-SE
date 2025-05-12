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
source-git-commit: 90f691b1cebb202ead66aafeb2e79087a8ae49ef
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Skapa Adobe Experience Platform-taggar

Experience Platform-taggar konfigureras på webbsidan för att läsa in Adobe Experience Platform Web SDK, vilket aktiverar API-anropet sendEvent för att aktivera personaliserade upplevelser. Med den här installationen säkerställs att nödvändiga klientbibliotek initieras korrekt, vilket möjliggör realtidsinteraktion med Adobe Journey Optimizer för leverans av erbjudanden.

1. Logga in på datainsamling.
1. Klicka på **[!UICONTROL Taggar]** > **[!UICONTROL Ny egenskap]**.
1. Skapa en Adobe Experience Platform-tagg som kallas ECID-tjänst.
1. Lägg till följande tillägg i taggen:

   ![tags-extensions](assets/ecid-tag.png)

1. Konfigurera Adobe Experience Platform Web SDK så att rätt miljö och DataStream för finansiella rådgivare som skapats i den tidigare självstudiekursen används

   ![web-sdk-configuration](assets/web-sdk-configuration.png)

Ingen ytterligare konfiguration krävs för Adobe Client Data Layer och Core Extensions

## Skapa dataelementet

ECID-dataelementet i Experience Platform-taggar skapas endast för felsökning och testning. Med dataelementet kan utvecklare visa det Experience Cloud-ID som tilldelats en användares webbläsarsession, vilket kan hjälpa till att validera identitetssammanfogning och säkerställa att `sendEvent`-anropen är kopplade till rätt profil. Det här elementet krävs inte för att personalisering ska fungera, men är användbart under implementering och kvalitetskontroll

![ecid](assets/ecid-data-element.png)


## Inkludera AEP-taggar på HTML-sidan

Bygg och publicera Adobe Experience Platform Tags.

När en AEP Tags-egenskap publiceras ger Adobe dig en script-tagg som du måste placera i din HTML ``` <head>``` eller längst ned i ``` <body>``` -taggarna.

1. Gå till egenskapen Tags (ECID Service).

1. Klicka på Miljöer och sedan på installationsikonen för den miljö du vill ha (till exempel Utveckling, Förproduktion, Produktion).

1. Lägg märke till den inbäddade koden.

   Den här koden måste placeras precis före den avslutande ```</body>```-taggen på HTML-sidan.
