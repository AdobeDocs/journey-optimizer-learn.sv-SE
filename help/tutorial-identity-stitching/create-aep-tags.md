---
title: Skicka CRMID till Adobe Experience Platform
description: Skapa Adobe Experience Platform-taggar för att skicka CRMID som tagits emot från webbläsaren till Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 894ad6b7-c4b4-465e-8535-3fdcd77e00eb
source-git-commit: 667f146639635515a5572e9ace41d83ab4452bb8
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 5%

---

# Skicka CRMID till Adobe Experience Platform

Adobe Experience Platform Tags används för att skicka CRMID till Adobe Experience Platform (AEP) eftersom det är en flexibel, händelsestyrd mekanism för överföring av identitetsdata direkt från webbläsaren. Genom att skicka CRMID efter användarinloggning kan AEP länka det anonyma ECID:t till den kända CRM-profilen, vilket möjliggör korrekt identitetssammanfogning. Denna länk utgör grunden för att skapa enhetliga kundprofiler, kvalificerade målgrupper och leverera personaliserade upplevelser i realtid i Adobe Journey Optimizer (AJO).

En Experience Platform Tags-egenskap med namnet _&#x200B;**FinWise**&#x200B;_ skapas. Följande tillägg har lagts till i taggegenskapen

![tags-extensions](assets/tags-extensions.png)

Konfigurera AEP Web SDK-tillägget med hjälp av DataStream för finansiella rådgivare som skapades i föregående steg.
Experience Cloud ID-tjänsten är ett valfritt tillägg som läggs till i taggegenskapen i felsökningssyfte.

## Tagga dataelement

Skapa följande dataelement

| Dataelement | Tillägg | Dataelementtyp | Anpassade inställningar |
|--------------|-----------------------------------|---------------------------|----------------------------------------|
| krut | Adobe Client Data Layer | Datalagrets beräknade läge | user.crmid |
| ECID | Experience Cloud ID-tjänst | ECID |                                        |
| identity | Webb-SDK för Adobe Experience Platform | Identitetskarta | ![bild](assets/identity-settings.png) |
| XDMVariable | Webb-SDK för Adobe Experience Platform | Variabel | ![bild](assets/xdmvariable.png) |

## Skapa regel

Skapa en regel med namnet LoginEvent med följande händelse och åtgärder

Händelse
![event](assets/data-pushed-event1.png)

Uppdatera variabelåtgärd
![update-variable](assets/update-variable1.png)
Skicka händelseåtgärd
![send-event](assets/send-event1.png)

## Spara och bygg

Spara ändringarna, skapa och bygg biblioteket.
