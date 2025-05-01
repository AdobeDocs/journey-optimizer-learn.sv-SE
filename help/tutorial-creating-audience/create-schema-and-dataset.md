---
title: Konfigurera XDM-schema, datauppsättning, dataström och målgrupper i AEP
description: Skapar XDM-schema, datauppsättning, dataström och målgrupper
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---


# Konfigurera XDM-schema, datauppsättning, dataström och målgrupper i AEP

* Logga in på Adobe Experience Platform

* Skapa ett XDM-händelsebaserat schema som kallas ekonomiska rådgivare i Journey Optimizer. Om du inte är van vid att skapa ett schema följer du den här [dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)

* Lägg till följande struktur i ditt schema. Elementet PreferredFinancialInstrument lagrar användarens inställningar för Stocks, Bonds, CD
  ![xdm-schema](assets/xdm-schema.png)

* Elementet PreferredFinancialInstrument har uppräkningsvärden som anges nedan
  ![enum-values](assets/enum-values.png)

* Kontrollera att schemat är aktiverat för profilen.

## Skapa en datauppsättning baserad på schemat

En **datauppsättning i Adobe Experience Platform (AEP)** är en strukturerad lagringsbehållare som används för att importera, lagra och aktivera data baserat på ett definierat XDM-schema.

* Skapa en datauppsättning med namnet _Datamängd för ekonomiska rådgivare_ baserat på XDM-schemat (ekonomiska rådgivare) som skapades i föregående steg.

* Kontrollera att datauppsättningen är aktiverad för profilen

## Skapa ett datastream

En datastam i Adobe Experience Platform är som en säker pipeline (eller huvudväg) som kopplar din webbplats eller app till Adobes tjänster, så att data kan flöda in och personaliserat innehåll flöda tillbaka.

* Gå till AEP > Datastreams och klicka sedan på New Datastream. Namnge datastream _Financial Advisors DataStream_

* Ange följande information som visas på skärmbilden nedan
  ![datastream](assets/datastream.png)
* Klicka på Spara, klicka sedan på Lägg till mappning och lägg till Adobe Experience Platform-tjänsten och händelsedatauppsättningen så som visas
  ![datastream-mapping](assets/datastream-service.png)

* Välj lämplig händelsedatamängd (skapades tidigare).

* Spara datastream

## Skapa målgrupper

Målgrupper i Adobe Experience Platform är grupper med användare som skapats utifrån deras åtgärder, preferenser eller profilinformation för att leverera personaliserade upplevelser.

* Navigera till Kund -> Målgrupper
* Skapa målgrupper med metoden Skapa regel

* Skapa följande tre publiker i AJO med elementet PreferredFinancialInstrument från händelseschemat.

   * Kunder som är intresserade av lager

   * Kunder som är intresserade av obligationer

   * Kunder som är intresserade av CD

Se till att utvärderingsmetoden för varje målgrupp är inställd på Edge för att ge behörighet i realtid.

Följande skärmbilder bör hjälpa dig att skapa publikerna.

![publik](assets/rule-based-audience.png)

![event](assets/event-attribute.png)


![PreferredFinancialInstrument](assets/stock-customers.png)

![målgrupp](assets/audience-edge.png)