---
title: Skapa en kampanj
description: Läs om hur en AJO-kampanj kopplar samman målgrupper, beslutspolicyer och kanaler för att leverera personaliserade erbjudanden i rätt ögonblick över olika kontaktytor.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: 7d812f589172c5052a1e9bfcf6a99d0769a6c2c7
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 0%

---

# Skapa en kampanj

För att leverera personaliserade erbjudanden till användare på webbsidan har en kampanj skapats i Adobe Journey Optimizer och konfigurerats med rätt kanal, webbkanal. Denna konfiguration ser till att erbjudandena levereras via realtidsbeslut till användare som interagerar med webbplatsen.

I den här kampanjen definierades en beslutspolicy för att kontrollera hur erbjudanden väljs ut. Beslutspolicyn innehåller en urvalsstrategi som består av följande:

En samling av erbjudandeartiklar (t.ex. baserat på väderrelaterade taggar),

Vilka regler som avgör vilka erbjudanden som gäller för en användare, och

En rankningsformel som tilldelar poäng till berättigade erbjudanden för att prioritera de mest relevanta.
När en användare besöker webbplatsen identifieras platsen och den aktuella temperaturen hämtas med ett väder-API. Dessa temperaturdata skickas sedan till Adobe Experience Platform via Web SDK (Alloy). Baserat på dessa sammanhangsbaserade data i realtid utvärderar Adobe Journey Optimizer fördefinierade erbjudanden som är taggade för specifika väderförhållanden, till exempel varma, lindriga eller kalla. Det mest relevanta erbjudandet med hjälp av urvalsstrategin och rankningsformeln återges automatiskt på webbsidan med Adobe beslutsmotor, vilket säkerställer att användaren får personaliserat innehåll som är anpassat till det aktuella vädret i området.


## Steg på hög nivå för att skapa en kampanj i AJO

1. **Skapa en kanalkonfiguration**\
   Definiera var och hur erbjudandena ska visas (till exempel en webbsida med kodbaserad upplevelse).
   - Logga in på Journey Optimizer

     Navigera till Administration ->Kanaler->Skapa kanalkonfiguration
   - **Namn**: `offers-by-weather`\
     Identifierar den här konfigurationen för personlig leverans av webberbjudanden.

   - **Plattform**: `Web`\
     Fungerar särskilt för webbläsare. Inga mobilkanaler är aktiverade.

   - **Upplevelsetyp**: `Code-based experience`\
     Erbjudandena injiceras inte direkt i DOM. I stället returnerar AJO HTML i Raw-format, som tolkas med anpassade JavaScript.

   - **Sidans URL**: `https://gbedekar489.github.io/weather/weather-offers.html`\
     Kanalen är konfigurerad för en specifik testsida som används under utvecklingen.

   - **Plats på sida**: `offerContainer`\
     Returnerade erbjudanden tolkas dynamiskt och återges i den här behållaren med hjälp av klientlogik.

   - **Innehållsformat**: `HTML`\
     Erbjudandena levereras som råa HTML-fragment, vilket ger fullständig kontroll över hur de formateras, filtreras och visas.


2. **Starta en ny kampanj**\
   Navigera till kampanjavsnittet och skapa en ny schemalagd marknadsföringskampanj. Namnge kampanjen korrekt.

3. **Lägg till åtgärd**\
   Lägg till kodbaserad upplevelseåtgärd och länka åtgärden till en tidigare skapad kanalkonfiguration.



4. **Målgrupp**\
   Alla besökare (standard).

   Identitetstyp: ECID (Experience Cloud ID)
Den här inställningen använder ECID som primär identitet för att identifiera användare.


5. **Skapa beslutspolicy**

   Åtgärden är länkad till en **beslutspolicy** som definierar hur erbjudanden markeras och hur många erbjudanden som returneras för visning. Den här principen använder en **urvalsstrategi** som skapades tidigare i självstudien.

   Om du vill infoga beslutsprincipen klickar du på **_Redigera innehåll_** i åtgärdsektionerna och sedan på **_Redigera kod_** för att öppna personaliseringsredigeraren.

   Välj ikonen _**Beslutspolicy**_ till vänster och klicka på knappen **Lägg till beslutspolicy** för att öppna skärmen **Skapa beslutspolicy**. Ange ett beskrivande namn för beslutspolicyn och välj det antal poster som beslutspolicyn ska returnera. Standardvärdet är 1.
Klicka på **_nästa_** och lägg till den urvalsstrategi som skapades i det tidigare steget i beslutsprincipen och klicka på **nästa** för att slutföra processen med att skapa beslutsprincipen. Inga reserverbjudanden har kopplats till beslutspolicyn.



6. **Infoga beslutspolicy**

   ![personaliseringsredigerare](assets/personalization-editor.png)

   Infoga den nyskapade beslutsprincipen genom att klicka på knappen _**Infoga princip**_ . Detta infogar en for-slinga i personaliseringsredigeraren till höger.
Placera markören mellan slingorna på rad två och infoga offerText genom att gå till erbjudandet genom att gå nedåt i `tenant name`

   Koden Handlebars gör en slinga genom erbjudanden som returneras av en specifik beslutspolicy i Adobe Journey Optimizer.
   ![handle-bar](assets/handlebar-code.png)

7. **Publicera kampanjen**\
   Aktivera kampanjen för att börja leverera personaliserade erbjudanden i realtid.


