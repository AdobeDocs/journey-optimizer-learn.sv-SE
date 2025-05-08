---
title: Skapa beslutspolicy
description: En beslutspolicy definierar logiken som används för att avgöra vilka erbjudanden som skickas till en användare under personaliseringen.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 186e4a7d-6077-401f-9958-2f955214bc35
source-git-commit: 6bf0c2487afff4811aa94e9591ae29c38af15d34
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# Skapa beslutspolicy

Beslutspolicyer är behållare för era erbjudanden som utnyttjar beslutsmotorn för att välja det bästa innehållet att leverera, beroende på målgruppen.

Klicka på alternativet Beslutsprincip i den vänstra navigeringsrutan i personaliseringsredigeraren och klicka sedan på Lägg till beslutsprincip

![create-Decision-policy](assets/decision-policy.png)

Klicka på Lägg till för att välja urvalsstrategi
Klicka på Välj reservlösning för att välja reserverbjudandet.
Klicka på Nästa för att granska beslutsprincipen och klicka på Skapa för att slutföra processen att skapa beslutsprincipen.


![beslutspolicy](assets/decision-policy2.png)


## Använd beslutsprincipen i kodredigeraren

Klicka på Infoga-princip i personaliseringsredigeraren. Koden som motsvarar beslutsprincipen läggs till.

I det här skedet kan du inkludera alla obligatoriska beslutsattribut direkt i koden. Dessa attribut definieras i det schema som används av katalogen Offers. Standardattribut ordnas under namnutrymmet __experience, medan anpassade attribut som är specifika för din organisation lagras under namnutrymmet `_<imsOrg>`.

![using_Decision_policy](assets/Insert-policy.png)

Den här koden går igenom en lista med personliga erbjudanden som valts ut för användaren och visar texten för varje erbjudande på webbsidan. Det visar meddelandet (så kallat offerText) från varje erbjudande inuti ett stycke, så att användarna kan se sitt skräddarsydda innehåll tydligt.
Om det inte finns något personligt erbjudande visas ett reserverbjudande som säkerställer att inget utrymme lämnas tomt.

Klicka på Spara och sedan på Aktivera kampanjen.
