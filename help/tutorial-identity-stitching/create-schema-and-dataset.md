---
title: Konfigurera XDM-schema, datauppsättning och dataström i AEP
description: Skapar XDM-schema, datauppsättning och dataström
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 8bb85ba7-3c50-4596-88f8-e112c48a8253
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Konfigurera XDM-schema, datauppsättning och dataström i AEP

## Skapa XDM-schema

Om du vill använda Adobe Experience Platform Web SDK (Alloy.js) på en webbsida måste AEP-taggar vara kopplade till ett datastream som är mappat till ett XDM-händelseschema. Web SDK (alloy.sendEvent) skickar data till AEP som Experience Events, som måste överensstämma med ett XDM-schema baserat på klassen XDM ExperienceEvent.

Skapa ett XDM-schema

* Logga in på Adobe Experience Platform
* Datahantering -> Scheman -> Skapa schema

* Skapa ett XDM-händelsebaserat schema med namnet **_Finansiella rådgivare_**. Om du inte är van vid att skapa ett schema följer du den här [dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)


* Kontrollera att schemat är aktiverat för profilen.

## Skapa en datauppsättning baserad på schemat

En **datauppsättning i Adobe Experience Platform (AEP)** är en strukturerad lagringsbehållare som används för att importera, lagra och aktivera data baserat på ett definierat XDM-schema.


* Datahantering -> Datauppsättningar -> Skapa datauppsättning
* Skapa en datauppsättning med namnet **_Datamängd för ekonomiska rådgivare_** baserat på XDM-schemat (ekonomiska rådgivare) som skapades i föregående steg.

* Kontrollera att datauppsättningen är aktiverad för profilen

## Skapa ett datastream

En datastam i Adobe Experience Platform är som en säker pipeline (eller huvudväg) som kopplar din webbplats eller app till Adobes tjänster, så att data kan flöda in och personaliserat innehåll flöda tillbaka.

* Navigera till Datainsamling > Datastreams och klicka sedan på New Datastream. Namnge datastream **_Financial Advisors DataStream_**

* Ange följande information som visas på skärmbilden nedan
  ![datastream](assets/datastream.png)
* Klicka på Spara, klicka sedan på Lägg till mappning och lägg till Adobe Experience Platform-tjänsten och händelsedatauppsättningen så som visas
  ![datastream-mapping](assets/datastream-service.png)

* Välj lämplig händelsedatamängd (skapades tidigare).

* Spara datastream.
