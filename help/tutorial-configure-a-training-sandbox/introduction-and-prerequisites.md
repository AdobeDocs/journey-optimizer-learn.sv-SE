---
title: Konfigurera en utbildningssandlåda - introduktion
description: Lär dig hur du konfigurerar en sandlåda för utbildningsändamål. Gå igenom stegen som krävs för att konfigurera scheman, importera exempeldata och skapa händelser.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: f7bfe367411f2bae23631ac4ecb34ad1d250381c
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 5%

---

# Konfigurera en utbildningssandlåda - introduktion och krav

![Självstudiekurs om banderoll - Konfigurera en utbildningssandlåda](./assets/ajo-banner-configure-training-sandbox.png)

Den här självstudiekursen är utformad för administratörer och datatekniker som har till uppgift att tillhandahålla en Adobe [!DNL Journey Optimizer] utbildningsmiljö. Lär dig stegen som krävs för att konfigurera scheman, importera exempeldata och skapa händelser. Du kan också skapa tre testprofiler som eleverna kan använda för att kontrollera sina arbeten.

De tillhandahållna exempeluppgifterna bygger på ett fiktivt sportklädföretag som kallas _[!DNL Luma]_. [!DNL Luma] har butiker i flera länder, en online-närvaro med en webbplats och mobilappar. [!DNL Luma] använder Adobe Journey Optimizer för att leverera sammankopplade, kontextuella och personaliserade upplevelser till sina kunder.

I slutet av den här självstudiekursen har du en sandlåda som har stöd för [!DNL Luma] de fall som omfattas av praktiska övningar i [Journey Optimizer Challenges](/help/challenges/introduction-and-prerequisites.md) -avsnitt.

## Förutsättningar

Kontrollera att du har:

1. En dedikerad utveckling [sandlåda](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).

1. [E-postmeddelandeförinställningar](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=en) konfigurerad för marknadsföring och transaktionsmeddelanden.

1. **[!UICONTROL Reseadministratör]** och **[!UICONTROL Datahanteraren]** rättigheter till utbildningshandlådan.

1. Dina [organisations-ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=sv).

1. JSON-filerna med exempeldata, konfigurerade till din Journey Optimizer-instans:

   1. Ladda ned `luma-sample-data.zip` fil [här](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip), som innehåller alla JSON-filer som krävs för den här självstudiekursen.

   1. Flytta `luma-data.zip` till önskad plats på datorn och packa upp den.

      De här filerna innehåller exempeldata för din träningssandlåda.

   1. Öppna varje fil och sök efter **`yourOrganizationID`** och ersätta den med [organisations-ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=sv).

   1. Spara filerna.

## Kom så börjar vi

Börja med [Manuell datainställning](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md).

I det här steget definierar du den obligatoriska datastrukturen. När du är klar med datauppsättningen kan du importera data till sandlådan och sedan ställa in händelser.
