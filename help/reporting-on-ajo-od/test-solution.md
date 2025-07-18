---
title: Testa lösningen
description: Skapa en enkel webbsida för att fånga upp intrycket och klicka på händelserna i erbjudandena.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18526
source-git-commit: 69bc8aace3cc502a18e691584824176833413c7e
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Testa lösningen

Om du vill testa lösningen från början till slut måste filerna [west-offers.html](assets/weather-offers.html) och [capture-imponsions-click-events.js](assets/capture-impressions-click-events.js) finnas på en webbserver eller en offentlig värdtjänst som Github Pages. Detta är nödvändigt eftersom webbläsarens geolocation-API bara fungerar över HTTPS eller localhost

## Ladda ned de medföljande filerna

[HTML-fil](assets/weather-offers.html)

[JavaScript-fil](assets/capture-impressions-click-events.js)

## Uppdatera yt-URL:en i javascript-filen

Öppna `capture-impressions-click-events.js` och uppdatera ` "web://yourdomain.com/weather/weather-offers.html#offerContainer"` genom att ersätta `yourdomain.com` med den domän där HTML-filen finns.


## Uppdatera egenskapen Adobe Experience Platform Tags

Öppna filen west-offers.html i textredigeraren och ersätt script-taggen med script-taggen för den Adobe Experience Platform Tag-egenskap som skapades i det tidigare steget i den här självstudien. Spara filen

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## Interagera med erbjudandena

- Öppna webbsidan i webbläsaren.

- Tillåt _&#x200B;**platsspårning**&#x200B;_. Detta krävs för att få väderinformation baserat på din plats.

- Klicka på knappen i erbjudandena för att utlösa en interaktionshändelse.

## Visa rapporten

- Logga in på Journey Optimizer

- Navigera till Resehantering ->Kampanjer

- Klicka på kampanjen och välj sedan lämplig rapport på rapportmenyn.
