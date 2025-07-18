---
title: Spåra och rapportera erbjudanden om Adobe Jouney Optimizer (AJO) som levereras via AJO Offer Decisioning
description: Den här självstudiekursen utökar en befintlig Adobe Journey Optimizer-implementering (AJO) som levererar personaliserade erbjudanden baserat på kontextuella data som temperatur. Här beskrivs hur du fångar in intrycks- och interaktionshändelser och förbereder data för rapportering i Optimizer.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18526
source-git-commit: fa4795d92cf290b867df23277a297c99d6222224
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Lägg till spårningstoken för att erbjuda artiklar

Gör så här för att ändra koden i personaliseringsredigeraren:

Navigera till _&#x200B;**Resehantering ->Kampanjer**&#x200B;_

Öppna lämplig kampanj och klicka på knappen _&#x200B;**Stoppa kampanj**&#x200B;_ för att stoppa kampanjen.

Öppna den stoppade kampanjen och klicka på knappen _&#x200B;**Ändra kampanj**&#x200B;_ .

Klicka på fliken _&#x200B;**Innehåll**&#x200B;_ och sedan på knappen _&#x200B;**Redigera kod**&#x200B;_ för att öppna redigeraren för anpassning.

Lägg till två nya dataattribut till diven som på skärmbilden
![tracking-token](assets/offer-item-with-tracking-code.png)

Du kan lägga till trackingToken och ItemID genom att klicka på beslutsprincipikonen i den vänstra navigeringen och gå nedåt i beslutsträdet för att välja itemID och trackingToken.
![tracking-token](assets/insert-tracking-token.png)

På så sätt säkerställs att alla renderade erbjudanden innehåller en dataspårningstoken, som är nödvändig för korrekt utskrift och klickning.

Spara ändringarna och aktivera kampanjen.
