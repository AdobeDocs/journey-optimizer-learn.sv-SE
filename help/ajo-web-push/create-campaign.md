---
title: Skapa kampanj
description: Skapa en kampanj för målanvändare som har valt att ta emot push-meddelanden och leverera meddelandet vid den schemalagda tidpunkten.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%

---

# Skapa kampanj

I det här steget skapar du en kampanj i Adobe Journey Optimizer för att skicka schemalagda push-meddelanden till användare som har valt att vara med. Kampanjen riktar sig till en berättigad målgrupp och levererar meddelanden vid en fördefinierad tidpunkt, vilket möjliggör planerat och målgruppsbaserat engagemang.

* Logga in på Journey Optimizer
* Navigera till Resehantering | Kampanjer | Skapa kampanjer

## Ange kampanjinställningar


Ange kampanjnamnet

![campaign-name](assets/campign-push-notification.png)

## Associera åtgärd med kampanjen

Associera den push-kanalskonfiguration som skapades tidigare i den här självstudien

![kampanj-action](assets/campign-push-notification-action.png)

## Associera målgrupp med kampanjen

Associera målgruppen `AudienceForPush` med kampanjen

![kampanjmålgrupp](assets/campign-push-notification-audience.png)

## Skapa innehåll för push-meddelanden

Skapa enkelt push-innehåll för testning av push-meddelanden. Ange rubrik och brödtext för meddelandet enligt nedan

![content-for-push-notification](assets/campign-push-notification-content.png)

## Schemalägg kampanjen

Schemalägg kampanjen efter era behov

![schema-camping](assets/campign-push-notification-schedule.png)

Se slutligen till att du aktiverar kampanjen.

## Testa kampanjen

Om du vill testa kampanjen aktiverar du först meddelanden på [webbsidan genom att välja ](http://localhost:3000) när du uppmanas till det. När du har valt att delta väntar du tills kampanjen körs vid den schemalagda tidpunkten. När kampanjen körs bör du få push-meddelandet i webbläsaren.




