---
title: Skapa en beslutspolicy
description: Använd en beslutspolicy för att definiera logiken för att avgöra vilka erbjudanden som skickas till en användare under personaliseringen.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 186e4a7d-6077-401f-9958-2f955214bc35
source-git-commit: 9a35160921988103182815efd3551151c09b9bb4
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# Skapa en beslutspolicy

Beslutsprinciper är behållare för dina erbjudanden som utnyttjar motorn [!UICONTROL Decisioning] för att välja det bästa innehållet som ska levereras, beroende på målgruppen.

1. Klicka på objektet **[!UICONTROL Beslutsprincip]** i den vänstra navigeringsredigeraren och klicka sedan på **[!UICONTROL Lägg till beslutsprincip]**.

   ![create-Decision-policy](assets/decision-policy.png)

1. Klicka på **[!UICONTROL Lägg till]** för att välja urvalsstrategi.

   ![beslutspolicy](assets/decision-policy2.png)

1. Klicka på **[!UICONTROL Välj reservlösning]** för att välja reserverbjudandet.
1. Klicka på **[!UICONTROL Nästa]** om du vill granska beslutsprincipen.
1. Klicka på **[!UICONTROL Skapa]** för att slutföra processen att skapa beslutsprincipen.

## Använd beslutsprincipen i kodredigeraren

1. Klicka på **[!UICONTROL Infoga princip]** i personaliseringsredigeraren.

   Koden som motsvarar beslutspolicyn läggs till.

   I det här skedet kan du inkludera alla obligatoriska beslutsattribut direkt i koden. Dessa attribut definieras i det schema som används av katalogen Offers. Standardattribut ordnas under namnutrymmet `__experience`, medan anpassade attribut som är specifika för din organisation lagras under namnutrymmet `_<imsOrg>`.

   ![using_Decision_policy](assets/Insert-policy.png)

   Den här koden går igenom en lista med personliga erbjudanden som valts ut för användaren och visar texten för varje erbjudande på webbsidan. Det visar meddelandet (kallat `offerText`) från varje erbjudande inuti ett stycke, så att användarna kan se sitt skräddarsydda innehåll tydligt.

   Om det inte finns något personligt erbjudande visas ett reserverbjudande som säkerställer att utrymmet inte lämnas tomt.

1. Klicka på **[!UICONTROL Spara]** och aktivera sedan kampanjen.
