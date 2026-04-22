---
title: Skapa tagg, egenskap
description: Taggegenskapen skickar data från webbläsaren till AEP via Web SDK.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Skapa tagg, egenskap

I den andra delen av den här självstudien får du lära dig hur du aktiverar push-meddelanden i realtid genom att skicka en anpassad price.drop-händelse manuellt. På det här sättet används AEP Data Collection (taggar) för att hämta händelsen från webbsidan och skicka den till Adobe Experience Platform. När händelsen har importerats utlöses en resa i Adobe Journey Optimizer, vilket gör att du kan skicka push-meddelanden på begäran baserat på användaråtgärder eller affärshändelser.

Den här egenskapen har konfigurerats med AEP Web SDK, som är ansluten till `WebPushDataStream` som skapades tidigare i självstudiekursen. Taggegenskapen lyssnar efter `price.drop`-händelsen på Adobe datalager och mappar den relevanta produktinformationen genom att uppdatera ProductListItems-dataelementet. När data har förberetts aktiveras en regel i taggegenskapen och skickar händelsen price.drop till AEP via Web SDK. Den här händelsen fungerar sedan som ingångspunkt för en resa i Adobe Journey Optimizer, vilket gör det möjligt att omedelbart skicka push-meddelanden baserat på prisfallet.

## Märkordselement

ProductListItems för produktinformation

![tag-elements](assets/product-list-items-element.png)

xdmvariable-mappning till `schemaForPushNotification`

![xdm-variable](assets/xdmvariable-data-element.png)

## Skapa regel

Lyssna på händelsen price.drop
![data-push-event](assets/tag-rule-event.png)

Uppdatera productListItems med hjälp av uppdateringsvariabeln
![update-variable](assets/update-variable.png)
Skicka slutligen händelsen price.drop till AEP med den uppdaterade xdmvariable
![send-event](assets/send-event.png)

Följande javascript-kod skickar händelsen price.drop till AEP Tags från webbsidan

```javascript
 <script>
      window.adobeDataLayer.push({
        event: "price.drop",
        productListItems: productListItems
      });
  </script>
```



