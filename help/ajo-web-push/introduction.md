---
title: Webbpush i AJO
description: I den här självstudien visas hur du implementerar push-meddelanden på webben med Adobe Journey Optimizer (AJO). Du får lära dig hur du fångar upp användarandelar med Web SDK, skickar meddelanden via schemalagda kampanjer och aktiverar push-meddelanden i realtid med en anpassad price.drop-händelse med AEP Tags.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Webbpush i Adobe Journey Optimizer

Webb-push-meddelanden är ett kraftfullt sätt att återengagera användare i realtid, och i den här självstudiekursen får du hjälp med att implementera dem med Adobe Journey Optimizer (AJO). Du börjar med att använda Web SDK för att hämta in användarinställningar för push-meddelanden, vilket ger en smidig och kompatibel prenumerationsupplevelse. Därefter skapar ni en kampanj för att skicka push-meddelanden till användare som har valt att delta, vilket möjliggör målgruppsbaserat engagemang. Slutligen får du lära dig hur du använder AEP Tags för att utlösa en anpassad prisnedladdningshändelse, som initierar en resa i AJO och levererar skräddarsydda push-meddelanden baserat på användarbeteende i realtid.

Exempelwebbsida som tillåter användare att välja om de vill få meddelanden

![enable-notifications](assets/enable-notifications.png)

Exempelwebbsida för att utlösa en prisnedgång

![utlösande prisfall](assets/trigger-price-drop-event.png)

## Förutsättningar

Den här självstudiekursen är utformad för att vara praktisk och enkel att följa. Även om det inte krävs någon djupgående kunskap, kan det vara bra att ha grundläggande kunskaper om följande koncept:

- Adobe Journey Optimizer (skapa resor eller kampanjer)
- AEP Data Collection (taggar) och Web SDK
- Grundläggande Adobe Experience Platform-koncept som scheman och evenemang
- Vissa JavaScript-koncept och allmänna webbutvecklingskoncept
- Grundläggande Node.js-kunskap (för att generera VAPID-nycklar och betjäna en enkel config-slutpunkt)

Om du inte är van vid något av dessa områden behöver du inte oroa dig - självstudiekursen vägleder dig genom de viktigaste stegen på vägen.
Den här självstudiekursen fokuserar på att implementera ett komplett användningsexempel för push-meddelanden på webben, så en fungerande kunskap om ovanstående verktyg och koncept hjälper dig att följa utvecklingen effektivt.


## 🔔 Aktivera webbläsarmeddelanden

Om meddelanden blockeras eller inte visas kan du behöva aktivera dem i webbläsarinställningarna. Se stödlinjerna nedan:

- **Google Chrome (Windows/macOS)**\
  <https://support.google.com/chrome/answer/3220216>

- **Microsoft Edge (Windows)**\
  <https://support.microsoft.com/en-us/microsoft-edge/manage-website-notifications-in-microsoft-edge>

- **Safari (macOS)**\
  <https://support.apple.com/guide/safari/customize-website-notifications-sfri40734/mac>

- **Safari (iPhone/iPad)**\
  <https://support.apple.com/en-us/HT213893>


## Exempelprogram


Ett komplett exempelprogram finns för att hjälpa dig att följa med i utvecklingen.

- [Live Demo - anmälan:](https://ajo-web-push.onrender.com/)

- [Utlösarprisfall:](https://ajo-web-push.onrender.com/price-drop-trigger.html)

- [Source-kod:](https://github.com/gbedekar489/ajo-web-push)

Du kan utforska live-demon för att se hur flödet fungerar eller klona databasen för att köra projektet lokalt.

