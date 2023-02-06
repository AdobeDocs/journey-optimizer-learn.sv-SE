---
title: Problem med produktpåfyllnad
description: Använd det du lärt dig om att skapa segment och testa dina färdigheter.
kt: 8417
feature: Segments
role: User
level: Beginner
hide: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 7ecbed1b722d7f05ffd4a7c7071358d993cb1392
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%

---

# Problem med produktpåfyllnad

| Utmaning | Produktpåfyllnad |
|---|---|
| Persona | Resechef |
| Nödvändiga färdigheter | <ul><li>[Skapa segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [Importera och redigera e-postinnehåll från HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=en)</li><li>[Användningsfall - Lässegment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Resurser att hämta | [E-postfil för produktomställning](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip) |

## The story

När kunderna surfar på Lumas webbplats kan de lägga till produkter de är intresserade av i en önskelista, vilket gör att Luma kan skicka riktade marknadsföringsmeddelanden och produktinformation till kunderna.

## Din utmaning

Luma ber dig implementera en resa i Journey Optimizer som meddelar kunder som har ett objekt på sin önskelista som tidigare inte fanns på lager när det här objektet är tillbaka på lager. Det kreativa teamet ger dig [E-postfil för produktomställning](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip).

>[!BEGINTABS]

>[!TAB Uppgift]

## 1. Definiera segmentet - Ej lagrad post i önskelistan

För att rikta sig till potentiella intresserade kunder när produkterna återställs kan du skapa ett segment som består av kunder:

* Som har lagt till minst ett objekt i önskelistan (Använd händelsetypen: [!UICONTROL Spara för senare i Commerce])
* som inte fanns i lager de senaste tre månaderna (använd lagerkvantitet = 0)
* Och har inte köpt artikeln sedan dess.

>[!TIP]
>Uteslut alla Inköpshändelsetyper där SKU matchar SKU:n från *Spara för senare händelse*. Du hittar fältet i *Bläddra bland variabler* -avsnitt.

Namnge det här segmentet: `Out-of-stock-Wishlist`


### 2. Skapa resan - meddelande om produktåterställning

När en artikel som inte finns i lager är tillbaka i lager ska du meddela kunder som lagt till en artikel som inte finns i lager att börja handla nu när artikeln är tillbaka i lager.

1. Ring resan: `Product Restock`
2. Resan bör utlösas när en produkt är tillbaka i lager
3. Skicka *E-post för produktretur* till
4. Användare som lagt till det här objektet i sin önskelista medan det var slut

>[!TAB Villkor för lyckade]

Testa din resa:

1. Kontrollera att read-segmenthändelsen har namnutrymmet = `Luma CRM ID`
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

>[!TAB Kontrollera ditt arbete]

Så här ska ditt segment se ut:

![Segment - objekt som inte finns i lager](/help/challenges/assets/C1-S2.png)


Så här ska din resa se ut:

![Produktpåfyllnadsresa](/help/challenges/assets/c3-j3-journey.png)

Villkor: I önskelistan

![Villkor - i önskelista](/help/challenges/assets/c3-j3-condition.png)

Villkorskod:

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```


>[!TIP]
> * Välj SKU under Spara för senare i dialogrutan *Bläddra bland variabler* section
> * Använd alternativet för att jämföra när du släpper SKU:n under Spara för senare i händelsefältet


Kontrollera koden längst ned till höger på skärmen Redigera segment under Händelser. Koden ska se ut så här:

Kod:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

>[!ENDTABS]

### Skapa e-post - Luma-produktpåfyllnad

Meddela kunder som lagt till en artikel som inte finns i lager med ett anrop att börja handla nu när artikeln är tillbaka i lager.



>[!TIP]
>
> Använd den befintliga affärshändelsen. Lägg till ett villkor som kontrollerar att omställnings-SKU:n ingår i (valfri) händelsetypen save för senare.




