---
title: Skicka push-meddelanden på en resa
description: Frekvensbegränsning i Adobe Journey Optimizer tillämpas på erbjudandenivå och är beroende av att både erbjudandeexponering och klickningshändelser fångas in. Detta kräver spårning av beslut.propositionDisplay- och decisioning.propositionInteract-händelser med Adobe Web SDK och mappning av dem till ett uppdaterat XDM Experience Event-schema i Adobe Experience Platform.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# Skicka push-meddelanden på en resa

Genom att utlösa en resa baserat på en prisnedgång blir det möjligt att skapa beteendestyrt engagemang i realtid med användarna. I verkliga scenarier kommer den här händelsen oftast från ett system för bakomliggande priser när en produkts pris uppdateras. I den här självstudiekursen simulerar vi det beteendet genom att skicka en anpassad price.drop-händelse via Adobe Data Layer med AEP Tags, inklusive produktinformation som name och SKU. Den här händelsen hämtas till Adobe Experience Platform och används som inresedrift för en resa i Adobe Journey Optimizer. När resan tagits emot kan den omedelbart skicka ett personligt push-meddelande till berättigade användare, som informerar dem om prisfallet och uppmuntrar till snabba åtgärder.

Så här utlöser du en resa med en anpassad händelse:

## Skapa anpassad händelse i Journey Optimizer

Logga in på Adobe Journey Optimizer och gå till Administration → Konfigurationer → Händelser och välj sedan Skapa händelse. Skapa en ny händelse med namnet PriceDropEvent och associera den med händelseschemat SchemaForPushNotification som skapades tidigare i självstudien. Kontrollera att händelseegenskaperna är konfigurerade så som visas i referensbilden.

![event-properties](assets/price-drop-event.png)

Välj de obligatoriska fälten i schemat för att göra dem tillgängliga för personalisering. Ta i synnerhet med `Name` och `SKU` från ProductListItems-objektet samt identifieraren från identityMap. Dessa fält är sedan tillgängliga i personaliseringsredigeraren, vilket gör att du dynamiskt kan skapa push-meddelanden baserat på produkt- och användarkontext.

## Skapar taggegenskap

Den här egenskapen konfigureras med AEP Web SDK, som är ansluten till WebPushDataStream som skapades tidigare i självstudiekursen. Taggegenskapen lyssnar efter händelsen price.drop i Adobe datalager och mappar den relevanta produktinformationen genom att uppdatera ProductListItems-dataelementet. När data har förberetts aktiveras en regel i taggegenskapen och skickar händelsen price.drop till AEP via Web SDK. Den här händelsen fungerar sedan som ingångspunkt för en resa i Adobe Journey Optimizer, vilket gör det möjligt att omedelbart skicka push-meddelanden baserat på prisfallet.



