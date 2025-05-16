---
title: Skicka CRMID till Adobe Experience Platform
description: Skapa Adobe Experience Platform-taggar för att skicka CRMID som tagits emot från webbläsaren till Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 68bd0a65e7d7f2d57f9620e76555485a1a79b4ae
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Skicka CRMID till Adobe Experience Platform

Adobe Launch (taggar) används för att skicka CRMID till Adobe Experience Platform (AEP) eftersom det är en flexibel, händelsestyrd mekanism för överföring av identitetsdata direkt från webbläsaren. Genom att skicka CRMID efter användarinloggning kan AEP länka det anonyma ECID:t till den kända CRM-profilen, vilket möjliggör korrekt identitetssammanfogning. Denna länk utgör grunden för att skapa enhetliga kundprofiler, kvalificerade målgrupper och leverera personaliserade upplevelser i realtid i Adobe Journey Optimizer (AJO).

En AEP Tags-egenskap med namnet FinWise skapas. Följande tillägg har lagts till i taggegenskapen

![tags-extensions](assets/tags-extensions.png)

Konfigurera AEP Web SDK-tillägget med hjälp av DataStream för finansiella rådgivare som skapades i den tidigare kursen.
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

Skapa en regel med namnet userLoggin med följande händelse och åtgärder

Händelse
![event](assets/data-pushed-event.png)

Uppdatera variabelåtgärd
![update-variable](assets/update-variable.png)
Skicka händelseåtgärd
![send-event](assets/send-event.png)

## Spara och bygg

Spara ändringarna, skapa och bygg biblioteket.

