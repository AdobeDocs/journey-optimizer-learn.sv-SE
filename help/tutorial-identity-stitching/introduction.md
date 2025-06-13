---
title: Identitetssammanfogning i AEP
description: Upprätta identitetskoppling mellan en känd användare (CRMID) och en anonym besökare (ECID), vilket möjliggör enhetliga profiler för personalisering i realtid och beslut om erbjudanden i Adobe Journey Optimizer (AJO).
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
exl-id: d6a1201a-3779-4718-8ea8-b88f925f53b6
source-git-commit: 96d9d525a3d9be399f7fa229b67166acf8130721
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Använd fallbeskrivning

I moderna kundupplevelser är det viktigt att sammanföra användaridentiteter över olika enheter och kanaler. I det här exemplet visas hur du implementerar identitetskarammanfogning i Adobe Experience Platform (AEP) genom att länka ett känt CRM-ID - som tagits in vid användarinloggning - till det anonyma Experience Cloud-ID (ECID) som genererats av Adobe Web SDK. Genom att sammanfoga dessa identiteter i realtid kan AEP skapa en mer komplett kundprofil som omfattar både anonymt beteende och autentiserade data. Detta gör att målgruppssegmentering, personalisering och beslutsfattande blir exaktare i verktyg som Adobe Journey Optimizer (AJO).

## 🧠 färdigheter som krävs för självstudiekursen Identitetskorrigering

För att få ut det mesta av den här självstudiekursen rekommenderar vi att du är bekant med följande:

- **Adobe Experience Platform (AEP) Core Concepts**\
  Förstå scheman, datauppsättningar, identiteter, sammanfogningsprinciper och realtidsprofiler.

- **Schema- och identitetsmodellering**\
  Möjlighet att konfigurera identitetsfält i profil- och händelsebaserade scheman.

- **Adobe Launch (taggar) och Web SDK (Alloy.js)**\
  Upplev hur man konfigurerar dataelement och regler för att skicka data till AEP via Web SDK.

- **Grundläggande om JavaScript**\
  Arbeta enkelt med funktioner för att samla in användarindata, utlösa händelser och felsöka API-anrop.

- **AEP felsökningsverktyg**\
  Möjlighet att använda AEP Debugger och Identity Graph Viewer för att validera identitetssammanfogning.

- **Datainmatning i AEP**\
  Förmåga att överföra exempeldata till datauppsättningar och säkerställa datakvaliteten.


