---
title: Konfigurera händelser
description: Konfigurera tre händelser som krävs för de praktiska Journey Optimizer-utmaningarna
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: fd9d277be00449155c49b3809fe647d7342b6acd
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 4%

---

# Konfigurera händelser

I det här avsnittet ställer du in de tre händelser som krävs för övningar med praktiska övningar i [Journey Optimizer-utmaningar](/help/challenges/introduction-and-prerequisites.md).

I följande video förklaras hur du skapar händelser:

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12&learn=on){transcript=true}

## Skapa onlineköp för Luma

När du använder den här händelsen får Journey Optimizer information när en person köper lumaprodukter online.

1. Skapa en händelse med följande parametrar:

   | [!UICONTROL Parameter] | [!UICONTROL Värde] |
   |-------------|-----------|
   | [!UICONTROL NAMN] | `LumaOnlinePurchase` |
   | [!UICONTROL TYP] | [!UICONTROL Unitär] |
   | [!UICONTROL Typ av händelse-ID] | [!UICONTROL Regelbaserad] |
   | [!UICONTROL Schema] | `Luma Web Events Schema` |
   | [!UICONTROL Fält] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

1. Lägg till villkoret [!UICONTROL Händelse-ID]: `LumaOnlinePurchase.eventType is commerce.purchases`:

   1. Markera pennikonen om du vill redigera fältet.

   1. Dra och släpp `eventType` på arbetsytan på **[!UICONTROL Lägg till ett händelse-id-villkor]**.
   1. Välj `commerce.purchases`.
   1. Välj **[!UICONTROL OK]** på arbetsytan.
   1. Välj **[!UICONTROL OK]** på spärren.

   ![Lägg till händelsevillkor](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. Välj [!UICONTROL NAMNUTRYMME]: `Luma CRM ID (lumaCrmId)`

1. Välj **[!UICONTROL Spara]**.

## Skapa *[!DNL Luma Product Restock]*-händelse

| [!UICONTROL Parameter] | [!UICONTROL Värde] |
|-------------|-----------|
| [!UICONTROL NAMN] | `LumaProductRestock` |
| [!UICONTROL TYP] | [!UICONTROL Företag] |
| [!UICONTROL Schema] | [!DNL Luma Product Inventory Event Schema] |
| [!UICONTROL Fält] | SKU <br> stockEventType<br><b>LumaProductCatalogSchema._yourOrganizationID.product :</b> <br>name<br>price<br> ImageURL<br>description |
| [!UICONTROL Villkor] | LumaProductRestock._`your organization's ID`.layerEvent.stockEventType återskapas |

Grattis! Din sandlåda är nu klar att användas.
