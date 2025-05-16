---
title: Identitetssammanfogning i AEP
description: Upprätta identitetskoppling mellan en känd användare (CRMID) och en anonym besökare (ECID), vilket möjliggör enhetliga profiler för personalisering i realtid och beslut om erbjudanden i Adobe Journey Optimizer (AJO).
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---


# Använd fallbeskrivning

I moderna kundupplevelser är det viktigt att sammanföra användaridentiteter över olika enheter och kanaler. I det här exemplet visas hur du implementerar identitetskarammanfogning i Adobe Experience Platform (AEP) genom att länka ett känt CRM-ID - som tagits in vid användarinloggning - till det anonyma Experience Cloud-ID (ECID) som genererats av Adobe Web SDK. Genom att sammanfoga dessa identiteter i realtid kan AEP skapa en mer komplett kundprofil som omfattar både anonymt beteende och autentiserade data. Detta gör att målgruppssegmentering, personalisering och beslutsfattande blir exaktare i verktyg som Adobe Journey Optimizer (AJO).

