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
source-git-commit: 81f5cc22d46f89ee1c7164a92988311ca6036b8b
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 4%

---

# Konfigurera händelser

I det här avsnittet ställer du in de tre händelser som krävs för övningar i [Journey Optimizer Challenges](/help/challenges/introduction-and-prerequisites.md).

I följande video förklaras hur du skapar händelser:

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12&learn=on)

## Skapa onlineköp för Luma

När du använder den här händelsen får Journey Optimizer information när en person köper lumaprodukter online.

1. Skapa en händelse med följande parametrar:

   | [!UICONTROL Parameter] | [!UICONTROL Värde] |
   |-------------|-----------|
   | [!UICONTROL NAMN] | `LumaOnlinePurchase` |
   | [!UICONTROL TYP] | [!UICONTROL Unitary] |
   | [!UICONTROL Typ av händelse-ID] | [!UICONTROL Regelbaserad] |
   | [!UICONTROL Schema] | `Luma Web Events Schema` |
   | [!UICONTROL Fält] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

1. Lägg till [!UICONTROL Händelse-ID-villkor]: `LumaOnlinePurchase.eventType is commerce.purchases`:

   1. Markera pennikonen om du vill redigera fältet.

   1. På **[!UICONTROL Lägg till ett händelse-id-villkor]** modal, dra och släpp `eventType` på arbetsytan.
   1. Välj `commerce.purchases`.
   1. Välj **[!UICONTROL OK]** på arbetsytan.
   1. Välj **[!UICONTROL OK]** på modal.

   ![Lägg till händelsevillkor](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. Välj [!UICONTROL NAMNUTRYMME]: `Luma CRM ID (lumaCrmId)`

1. Välj **[!UICONTROL Spara]**.

## Skapa *[!DNL Luma Wishlist Add]* event

| [!UICONTROL Parameter] | [!UICONTROL Värde] |
|-------------|-----------|
| [!UICONTROL NAMN] | `LumaWishlistAdd` |
| [!UICONTROL TYP] | [!UICONTROL Unitary] |
| [!UICONTROL Typ av händelse-ID] | [!UICONTROL Regelbaserad] |
| [!UICONTROL Schema] | `Luma Product Interactions` |
| [!UICONTROL Fält] | EventType<br>productListItem.quantity<br><b>I produktlisteobjekt > Luma-produkter > _*[!DNL yourOrganizationID]* > Produkt:</b> <br>Namn<br>Pris<br> ProductImageURL<br>ProductURL |
| [!UICONTROL Villkor] | [!DNL LumaWishlistAdd.eventType is commerce.saveForLaters] |
| [!UICONTROL Namnutrymme] | E-post (e-post) |

## Skapa *[!DNL Luma Product Restock]* event

| [!UICONTROL Parameter] | [!UICONTROL Värde] |
|-------------|-----------|
| [!UICONTROL NAMN] | `LumaProductRestock` |
| [!UICONTROL TYP] | [!UICONTROL Företag] |
| [!UICONTROL Schema] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL Fält] | SKU <br> stockEventType<br><b> ditt organisations-ID > produkt:</b> <br>name<br>pris<br> ImageURL<br>description |
| [!UICONTROL Villkor] | LumaProductRestock._`your organization's ID`.InventEvent.stockEventType återskapas |

Grattis! Din sandlåda är nu klar att användas.
