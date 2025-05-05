---
title: Konfigurera en utbildningssandlåda - introduktion
description: Lär dig hur du konfigurerar en sandlåda för utbildningsändamål. Gå igenom stegen som krävs för att konfigurera scheman, importera exempeldata och skapa händelser.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: 81f5cc22d46f89ee1c7164a92988311ca6036b8b
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Konfigurera en utbildningssandlåda - introduktion och krav

![Självstudiekurs om banderoll - Konfigurera en utbildningstandlåda](./assets/ajo-banner-configure-training-sandbox.png)

Den här självstudiekursen är utformad för administratörer och datatekniker som har till uppgift att tillhandahålla en utbildningsmiljö i Adobe [!DNL Journey Optimizer]. Lär dig stegen som krävs för att konfigurera scheman, importera exempeldata och skapa händelser. Du kan också skapa tre testprofiler som eleverna kan använda för att kontrollera sina arbeten.

Angivna exempeldata baseras på ett fiktivt sportklädföretag med namnet _[!DNL Luma]_. [!DNL Luma] har butiker i flera länder, en onlinenärvaro med en webbplats och mobilappar. [!DNL Luma] använder Adobe Journey Optimizer för att leverera sammankopplade, kontextuella och personaliserade upplevelser till sina kunder.

I slutet av den här självstudiekursen har du en sandlåda som har stöd för de [!DNL Luma] användningsfall som ingår i praktiska övningar i avsnittet [Journey Optimizer Challenges](/help/challenges/introduction-and-prerequisites.md) .

## Förhandskrav

Innan du kan börja konfigurera din utbildningssandlåda måste du se till att du har:

1. En dedikerad [utvecklingssandlåda](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=sv-SE).

1. [Förinställningar för e-postmeddelanden](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=sv-SE) har konfigurerats för marknadsföring och transaktionsmeddelanden.

1. **[!UICONTROL Reseadministratör]** och **[!UICONTROL Datahanterare]** för utbildningssandlådan.

1. Ditt [organisations-ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=sv).

1. JSON-filerna med exempeldata, konfigurerade till din Journey Optimizer-instans:

   1. Hämta filen `luma-sample-data.zip` [här](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip), som innehåller alla JSON-filer som krävs för den här självstudiekursen.

   1. Flytta `luma-data.zip`-filen till önskad plats på datorn från hämtningsmappen och packa upp den.

      De här filerna innehåller exempeldata för din träningssandlåda.

   1. Öppna varje fil och sök efter **`yourOrganizationID`** och ersätt den med ditt [organisations-ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=sv).

   1. Spara filerna.

## Kom så börjar vi

Börja med den [manuella datauppsättningen](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md).

I det här steget definierar du den obligatoriska datastrukturen. När du är klar med datauppsättningen kan du importera data till sandlådan och sedan ställa in händelser.
