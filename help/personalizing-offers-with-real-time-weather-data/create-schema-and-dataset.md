---
title: Konfigurera XDM-schema, datauppsättning och dataström i AEP
description: Skapar XDM-schema, datauppsättning och dataström
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: 13c891c02a9a2da3ff742afaab7ceb449a417b5e
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# Konfigurera XDM-schema, datauppsättning och dataström i AEP

## Skapa XDM-schema

Om du vill använda Adobe Experience Platform Web SDK (Alloy.js) på en webbsida måste AEP-taggar vara kopplade till ett datastream som är mappat till ett XDM-händelseschema. Web SDK (alloy.sendEvent) skickar data till AEP som Experience Events, som måste överensstämma med ett XDM-schema baserat på klassen XDM ExperienceEvent.

Skapa ett XDM-schema

* Logga in på Adobe Experience Platform
* Navigera till _&#x200B;**Datahantering -> Scheman -> Skapa schema**&#x200B;_

* Skapa ett XDM-händelsebaserat schema med namnet **_Väderschema_**. Om du inte är van vid att skapa ett schema följer du den här [dokumentationen](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/tutorials/create-schema-ui)


* Kontrollera att schemat har följande fält med lämplig datatyp.

![väderschema](assets/weather-schema.png)

## Skapa en datauppsättning baserad på schemat

En **datauppsättning i Adobe Experience Platform (AEP)** är en strukturerad lagringsbehållare som används för att importera, lagra och aktivera data baserat på ett definierat XDM-schema.

* Navigera till _&#x200B;**Datahantering -> Datauppsättningar -> Skapa datauppsättning**&#x200B;_
* Skapa en datauppsättning med namnet **_Weather-schema-dataset_** baserat på XDM-schemat(_&#x200B;**Weather-Schema**&#x200B;_) som skapades i föregående steg.


## Skapa ett datastream

En datastam i Adobe Experience Platform är som en säker pipeline (eller huvudväg) som kopplar din webbplats eller app till Adobes tjänster, så att data kan flöda in och personaliserat innehåll flöda tillbaka.

* Navigera till _&#x200B;**Datasamling > Datastreams**&#x200B;_ och klicka sedan på Ny datastream. Namnge datastream **väderrelaterad-datastream**


* Ange följande information som visas på skärmbilden nedan
  ![datastream](assets/datastream.png)
* Klicka på Spara, klicka sedan på Lägg till mappning och lägg till Adobe Experience Platform-tjänsten och händelsedatauppsättningen med lämpliga kryssrutor markerade
  ![datastream-mapping](assets/datastream-service.png)

* Spara datastream.
