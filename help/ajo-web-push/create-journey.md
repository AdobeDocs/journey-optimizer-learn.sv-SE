---
title: Skapa resa
description: Skapa resa som utlöses vid händelsen price.drop
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Skapa resa

I det här steget skapar du en resa i Adobe Journey Optimizer som utlöses av händelsen price.drop. När den här händelsen tas emot startar resan i realtid och skickar ett push-meddelande till användare som har valt att delta, vilket möjliggör händelsestyrt engagemang.

Så här skapar du en resa som utlöses av händelsen price.drop:

* Logga in på Journey Optimizer
* Navigera till resehantering | Resor | Skapa resa

![skapa-resa](assets/create-journey.png)

## Lägg till PriceDropEvent

Dra `PriceDropEvent` från händelseavsnittet till arbetsytan
![&#x200B; price-drop-event &#x200B;](assets/add-price-drop-event.png)

## Lägg till penselåtgärd

Expandera avsnittet Åtgärder. Dra och släpp aktiviteten `Action` på arbetsytan och välj Push som åtgärdstyp
![&#x200B; push-action &#x200B;](assets/add-push-action.png)

## Konfigurera push-åtgärden

Välj aktiviteten för push-meddelanden och klicka på konfigurationsåtgärden

![configure-push-action](assets/configure-push-action.png)

## Konfiguration av push-meddelandekanal

Associera konfigurationen `MyFirstWebPushChannel` som skapades tidigare i självstudiekursen med det här push-meddelandet

![channel-configuration](assets/journey-actions.png)

## Skriv push-meddelandemeddelande

Lägg till en kombination av statiskt och dynamiskt innehåll i push-meddelandet med personaliseringsredigeraren för att göra meddelandet mer engagerande och relevant.

Om du vill börja komponera meddelandet klickar du på `Content` för att öppna fliken Innehåll, där du kan definiera både den fasta texten och de dynamiska fält som härleds från händelsedata.
![content-push](assets/compose-message.png)

Ange push-meddelandets titel och öppna sedan anpassningsredigeraren för att skapa meddelandetexten. Innehållet kommer dynamiskt att innehålla namnen på de produkter vars priser har sjunkit. För att uppnå detta använder du varje [hjälpfunktion](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/functions/helpers#each)
för att iterera över produktlistan och återge namnen i meddelandet.

## Skriv meddelandetexten

Markera och infoga funktionen `Each` på hjälpfunktionens meny.
![helper-function](assets/journey-content-helper-function.png)

Markera kontextattributen | Journey Orchestration | Händelser | PriceDropEvent | productListItems | Namn

Klicka på plusikonen (+) för att infoga arrayen i varje slinga i personaliseringsredigeraren. Uppdatera sedan meddelandeinnehållet så att det matchar formatet som visas på skärmbilden med referenser. Observera att det händelse-ID som visas i din miljö kan skilja sig från det som visas.

![contextual-attributes](assets/journey-content-context-attributes.png)

Spara slutligen alla ändringar och publicera resan. När den publicerats blir resan aktiv och lyssnar efter inkommande price.drop-händelser. Varje gång en sådan händelse tas emot utlöses resan i realtid och ett push-meddelande skickas till användare som har valt att ta emot meddelanden, vilket garanterar att de engagerar sig i rätt tid.

## Testa lösningen

Om du vill utlösa händelsen price.drop öppnar du sidan för utlösare för [pris/släpp, &#x200B;](http://localhost:3000/price-drop-trigger.html) markerar en eller flera produkter och klickar på utlösare för pris. Detta skickar händelsen via Adobe datalager med AEP-taggar, som sedan initierar resan och skickar push-meddelandet i realtid.



