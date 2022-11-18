---
title: Konfigurera en utbildningssandlåda - introduktion
description: Lär dig hur du konfigurerar en sandlåda för utbildningsändamål. Gå igenom stegen som krävs för att konfigurera scheman, importera exempeldata och skapa händelser.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
source-git-commit: 79249cf6ecd08c38c075a4e27fa9cf74073491af
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 5%

---


# Konfigurera en utbildningssandlåda - introduktion och krav

![Självstudiekurs om banderoll - Konfigurera en utbildningssandlåda](./assets/ajo-banner-configure-training-sandbox.png)

Den här självstudiekursen är avsedd för administratörer och datatekniker som har till uppgift att tillhandahålla en utbildningsmiljö i Adobe Journey Optimizer. Lär dig stegen som krävs för att konfigurera scheman, importera exempeldata och skapa händelser. Du kommer också att skapa tre testprofiler där eleverna kan kontrollera sitt arbete.

De tillhandahållna exempeluppgifterna bygger på ett fiktivt sportklädföretag som kallas _[!DNL Luma]_. [!DNL Luma] har butiker i flera länder, en online-närvaro med en webbplats och mobilappar. [!DNL Luma] använder Adobe Journey Optimizer för att leverera sammankopplade, kontextuella och personaliserade upplevelser till sina kunder.

I slutet av den här självstudiekursen har du en sandlåda som har stöd för [!DNL Luma] de fall som omfattas av praktiska övningar i [Journey Optimizer Challenges](/help/challenges/introduction-and-prerequisites.md) -avsnitt.

## Förutsättningar

Kontrollera att du har:

1. En dedikerad utveckling [sandlåda](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).
1. [E-postmeddelandeförinställningar](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/channel-configuration/set-up-email-channel.html?lang=en) konfigurerad för marknadsföring och transaktionsmeddelanden.
1. **[!UICONTROL Reseadministratör]** och **[!UICONTROL Datahanteraren]** rättigheter till utbildningshandlådan.
1. Dina [organisations-ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=sv).

1. JSON-filerna med exempeldata, konfigurerade till din Journey Optimizer-instans:

   1. Ladda ned `luma-data.zip` fil [här](/help/tutorial-configure-a-training-sandbox/assets/luma-data.zip), som innehåller alla JSON-filer som krävs för den här självstudiekursen.

   1. Flytta `luma-data.zip` till önskad plats på datorn och packa upp den.

      Det ska finnas tre JSON-filer: `luma-crm.json`, `luma-loyalty.json`, `luma-products.json`.

      Dessa filer innehåller exempeldata som du importerar till sandlådan.

   1. Öppna varje fil och sök efter **`yourOrganizationID`** och ersätta den med [organisations-ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en).

   1. Spara filerna.

## Kom så börjar vi

Börja med [Manuell datainställning](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md). I det här steget definierar du den obligatoriska datastrukturen. När du är klar med datauppsättningen kan du importera data till sandlådan och sedan ställa in händelser.
