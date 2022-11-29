---
title: Konfigurera händelser
description: Konfigurera tre händelser som krävs för händerna på Journey Optimizer Challenges
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: 8a2062f0719e799dd2d039488e6bba943fb458c4
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 4%

---

# Konfigurera händelser

I det här avsnittet ställer du in de tre händelser som krävs för övningar i [Journey Optimizer Challenges](/help/challenges/introduction-and-prerequisites.md).

Se videon [Skapa händelser](/help/set-up-journeys/create-events.md) för vägledning om hur du skapar händelser.

## Skapa Luma Online Purchase Event

1. Navigera till vänster [!UICONTROL ADMINISTRATION] och markera *[!UICONTROL Konfiguration]*
1. Från [!UICONTROL Kontrollpanel], markera *[!UICONTROL Hantera*]* Händelser

![Hantera händelser](assets/create-events.png)

1. Klicka *[!UICONTROL Skapa händelse]*
1. Fyll i händelseinformation och parametrar:

   | [!UICONTROL Parameter] | [!UICONTROL Värde] |
   |-------------|-----------|
   | [!UICONTROL NAMN] | `LumaOnlinePurchase` |
   | [!UICONTROL TYP] | [!UICONTROL Unitary] |
   | [!UICONTROL Typ av händelse-ID] | [!UICONTROL Regelbaserad] |
   | [!UICONTROL Schema] | Luma - produktinteraktioner |
   | [!UICONTROL Fält] | EventType <br>Order.priceTotal<br>purchaseOrderNumber<br>productListItems.quantity<br><b>I produktlisteobjekt > Luma-produkter > _*[!DNL yourOrganizationID]* > Produkt:</b> <br> Namn<br>Pris<br>ProductImageURL<br>ProductURL |

1. Lägg till [!UICONTROL Händelse-ID-villkor]: **[!DNL LumaOnlinePurchase.eventType is commerce.purchases]**

   1. Markera pennikonen för att redigera fältet
   2. På [!UICONTROL Lägg till ett händelse-id-villkor] modal, dra och släpp `eventType` på arbetsytan
   3. Välj `commerce.purchases`
   4. Välj OK på arbetsytan
   5. Välj OK på spärren

![Lägg till händelsevillkor](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. Välj [!UICONTROL NAMNUTRYMME]: `Email(Email)`

1. Välj **[!UICONTROL Spara]**.

## Skapa *[!DNL Luma Wishlist Add]* Händelse

| [!UICONTROL Parameter] | [!UICONTROL Värde] |
|-------------|-----------|
| [!UICONTROL NAMN] | `LumaWishlistAdd` |
| [!UICONTROL TYP] | [!UICONTROL Unitary] |
| [!UICONTROL Typ av händelse-ID] | [!UICONTROL Regelbaserad] |
| [!UICONTROL Schema] | `Luma Product Interactions` |
| [!UICONTROL Fält] | EventType<br>productListItem.quantity<br><b>I produktlisteobjekt > Luma-produkter > _*[!DNL yourOrganizationID]* > Produkt:</b> <br>Namn<br>Pris<br> ProductImageURL<br>ProductURL |
| [!UICONTROL Villkor] | [!DNL LumaWishlistAdd.eventType is commerce.saveForLaters] |
| [!UICONTROL Namnutrymme] | E-post (e-post) |

## Skapa *[!DNL Luma Product Restock] Händelse

| [!UICONTROL Parameter] | [!UICONTROL Värde] |
|-------------|-----------|
| [!UICONTROL NAMN] | `LumaProductRestock` |
| [!UICONTROL TYP] | [!UICONTROL Företag] |
| [!UICONTROL Schema] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL Fält] | productID <br> stockEventType<br><b>In Product > Luma Products > *[!DNL yourOrganizationID]* > Produkt:</b> <br>Namn<br>Pris<br> ProductImageURL<br>Beskrivning |
| [!UICONTROL Villkor] | LumaProductRestock._`your organization's ID`.InventEvent.stockEventType återskapas |

## Grattis

Din sandlåda är nu klar att användas!
