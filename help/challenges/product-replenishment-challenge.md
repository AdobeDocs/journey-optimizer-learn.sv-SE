---
title: Problem med produktpåfyllnad
description: Använd det du lärt dig om att skapa segment och testa dina färdigheter.
kt: 8417
feature: Segments
role: User
level: Beginner
hide: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 0e83d8fbad6bd87ed25980251970898cb5b94bc0
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---

# Problem med produktpåfyllnad

| Utmaning | Produktpåfyllnad |
|---|---|
| Persona | Resechef |
| Nödvändiga färdigheter | <ul><li>[Skapa segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-segments.html?lang=en)</li><li> [Importera och redigera e-postinnehåll från HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/import-and-author-html-email-content.html?lang=en)</li><li>[Användningsfall - Lässegment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Resurser att hämta | [E-postfiler för säsongssamling](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## The story

När man surfar på Lumas webbplats kan man lägga in produkter man är intresserad av i en önskelista. Med det kan Luma skicka riktade marknadsföringsmeddelanden och produktinformation till kunderna.

## Din utmaning

Luma ber dig implementera en resa i Journey Optimizer som meddelar kunder som har ett objekt på sin önskelista som tidigare inte fanns på lager när det här objektet är tillbaka på lager.

## Definiera segmentet - Ej lagrad post i önskelistan

Skapa ett segment som består av kunder för att rikta sig till potentiella intresserade kunder när produkterna återställs

* Som har lagt till minst ett objekt i önskelistan (Använd händelsetyp: [!UICONTROL Spara för senare i Commerce])
* Vilken **slut på lager** de senaste tre månaderna (använd lagerkvantitet = 0)
* Och har inte köpt artikeln sedan dess.

Namnge det här segmentet: *ditt namn - Out-of-stock-Wishlist*

+++**KONTROLLERA DITT ARBETE**

Så här ska ditt segment se ut:

![Segment - objekt som inte finns i lager](/help/challenges/assets/C1-S2.png)

Kunder som har lagt till en artikel i önskelistan som inte fanns i lager de senaste tre månaderna:

* Händelse: Spara för senare
   * Inkludera minst 1
   * Där lagerkvantiteten är 0

och har inte köpt artikeln sedan dess:

* Uteslut alla Inköpshändelsetyper där SKU matchar SKU:n från **Spara för senare händelse**.

>[!TIP]
> * Välj SKU under Spara för senare i dialogrutan *Bläddra bland variabler* section
> * Använd alternativet för att jämföra när du släpper SKU:n under Spara för senare i händelsefältet


Kontrollera koden längst ned till höger på skärmen Redigera segment under Händelser. Koden ska se ut så här:

Kod:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

+++

### Skapa e-post - Luma-produktpåfyllnad

Meddela kunder som lagt till en artikel som inte finns i lager med ett anrop att börja handla nu när artikeln är tillbaka i lager.

### Skapa resan - meddelande om produktåterställning

När en artikel som inte finns i lager är tillbaka i lager ska du meddela kunder som lagt till en artikel som inte finns i lager att börja handla nu när artikeln är tillbaka i lager.

1. Skapa en resa som heter&quot;ditt namn_Luma - produktrestaurering
1. Resan bör utlösas när en produkt är tillbaka i lager
1. Skicka *Lumatprodukt-påfyllnad* mejla till
1. Användare som lagt till det här objektet i sin önskelista medan det var slut

>[!TIP]
>
> Använd den befintliga affärshändelsen. Du måste lägga till ett villkor som kontrollerar att omgrupperings-SKU:n inkluderas i (valfri) händelsetyp som sparas för senare.

+++**FRAMSTÄLLNINGSKRITERIER**

Testa din resa:

1. Kontrollera att segmentkvalificeringshändelsen har namnutrymmet = E-post
1. Åsidosätt standardparametrarna för e-post och ange den till din egen e-postadress (se e-postadress 1 för instruktioner)
1. Ställ in resan till testläge
1. Utlös en händelse - ange följande data:

   * Beskrivning: Glöm avancerade maskiner och kostsamma medlemskap - Harmony Lumaflex Strength Band Kit är allt du behöver för en fantastisk lösning. Paketet har allt du behöver för en rad förstärknings- och toningsövningar.
   * Namn: Harmoniband för lumaflex-styrka
   * Pris: 22
   * Produkt-ID: 24-UG03
   * Produktbild-URL: https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU: 24-UG03
   * Typ av Stock-händelse: restock
   * Profilidentifierare: Jenna_Palmer9530@emailsim.io

Du bör få e-postmeddelandet&quot;Luma Email Product Refillations&quot; med produktinformation och personalisering för Jenna.

+++

+++**KONTROLLERA DITT ARBETE**

Så här ska din resa se ut:

![Produktpåfyllnadsresa](/help/challenges/assets/c3-j3-journey.png)

Villkor: I önskelistan

![Villkor - i önskelista](/help/challenges/assets/c3-j3-condition.png)

Villkorskod:

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```

+++
