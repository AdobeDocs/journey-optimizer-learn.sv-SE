---
title: Aktivera frekvensbegränsning för en AJO-kampanj
description: Frekvensbegränsning i Adobe Journey Optimizer tillämpas på erbjudandenivå och är beroende av att både erbjudandeexponering och klickningshändelser fångas in. Detta kräver spårning av beslut.propositionDisplay- och decisioning.propositionInteract-händelser med Adobe Web SDK och mappning av dem till ett uppdaterat XDM Experience Event-schema i Adobe Experience Platform.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# Aktivera frekvensbegränsning för en AJO-kampanj

Så här använder du frekvensbegränsning för erbjudanden:

## Uppdatera händelseschemat

* Uppdatera det befintliga händelseschemat genom att lägga till fältgruppen som visas
* ![event-schema](assets/schema.png)

## Uppdatera erbjudandets frekvensbegränsning


* ![erbjudande](assets/offer-capping.png)

## Lägg till spårningstoken i erbjudandet

Redigera beslutsprincipen som används i kampanjen genom att lägga till ett reserverbjudande
![fallback](assets/fallback.png)

Du kan lägga till trackingToken och ItemID genom att klicka på beslutsprincipikonen i den vänstra navigeringen och gå nedåt i beslutsträdet för att välja itemID och trackingToken.

Lägg till artikel-ID och spårningstoken i diven som innehåller erbjudandet enligt nedan
![id-and-tracking-token](assets/id-and-tracking-token.png)

På så sätt säkerställs att alla renderade erbjudanden innehåller en dataspårningstoken, som är nödvändig för korrekt utskrift och klickning.


Aktivera den ändrade kampanjen.


## Skicka intryck och spåra händelser

Ändra den befintliga JavaScript-koden för att fånga in och skicka erbjudandeintryck och interaktionshändelser till Adobe Experience Platform med Adobe Web SDK. Se exempelkoden för [här.](capture-impression-click-events.md)


