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
exl-id: c3e4f760-9b10-4a99-bc53-9245e76c1bab
source-git-commit: 95a8abd08fbf57900870826112b01a8cd375fe96
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# Skapa en kampanj

För att leverera personaliserade erbjudanden till användare på webbsidan har en kampanj skapats i Adobe Journey Optimizer och konfigurerats med rätt kanal, kodbaserad upplevelsekanal. Denna konfiguration ser till att erbjudandena levereras via realtidsbeslut till användare som interagerar med webbplatsen.

I den här kampanjen definierades en beslutspolicy för att kontrollera hur erbjudanden väljs ut. Beslutspolicyn innehåller en urvalsstrategi som består av följande:

- En samling av erbjudandeartiklar (t.ex. baserat på väderrelaterade taggar),
- Vilka regler som avgör vilka erbjudanden som gäller för en användare, och
- En rankningsformel som tilldelar poäng till berättigade erbjudanden för att prioritera de mest relevanta.

När en användare besöker webbplatsen identifieras platsen och den aktuella temperaturen hämtas med ett väder-API. Dessa temperaturdata skickas sedan till Adobe Experience Platform via Web SDK (Alloy). Baserat på dessa sammanhangsbaserade data i realtid utvärderar Adobe Journey Optimizer fördefinierade erbjudanden som är taggade för specifika väderförhållanden, till exempel varma, lindriga eller kalla. Det mest relevanta erbjudandet med hjälp av urvalsstrategin och rankningsformeln återges automatiskt på webbsidan med Adobe beslutsmotor, vilket säkerställer att användaren får personaliserat innehåll som är anpassat till det aktuella vädret i området.


## Steg på hög nivå för att skapa en kampanj i AJO

- Skapa en kanalkonfiguration
   - Definiera var och hur erbjudandena ska visas (till exempel en webbsida med kodbaserad upplevelse).
   - Logga in på Journey Optimizer
   - Navigera till _&#x200B;**Administration ->Kanaler->Skapa kanalkonfiguration**&#x200B;_
   - **Namn**: `offers-by-weather`\
     Identifierar den här konfigurationen för personlig leverans av webberbjudanden.
- **Kanal**:
  `Code-based experience`\
  Erbjudandena injiceras inte direkt i DOM. I stället returnerar AJO HTML i Raw-format, som tolkas med anpassade JavaScript.
- **Plattform**: `Web`\
  Fungerar särskilt för webbläsare. Inga mobilkanaler är aktiverade.

- **Sidans URL**: `https://gbedekar489.github.io/weather/weather-offers.html`\
  Kanalen är konfigurerad för en specifik testsida som används under utvecklingen.
- **Plats på sida**: `offerContainer`\
  Returnerade erbjudanden tolkas dynamiskt och återges i den här behållaren med hjälp av klientlogik.

- **Innehållsformat**: `HTML`\
  Erbjudandena levereras som råa HTML-fragment, vilket ger fullständig kontroll över hur de formateras, filtreras och visas.


- **Starta en ny kampanj**
   - Navigera till kampanjavsnittet och skapa en ny schemalagd marknadsföringskampanj. Namnge kampanjen korrekt.
   - **Lägg till åtgärd**
      - Lägg till kodbaserad upplevelseåtgärd och länka åtgärden till en tidigare skapad kanalkonfiguration.



   - **Målgrupp**
      - Alla besökare (standard).
      - Identitetstyp: ECID (Experience Cloud ID)
Den här inställningen använder ECID som primär identitet för att identifiera användare.


- **Skapa beslutspolicy**
   - Åtgärden är länkad till en **beslutspolicy** som definierar hur erbjudanden markeras och hur många erbjudanden som returneras för visning. Den här principen använder en **urvalsstrategi** som skapades tidigare i självstudien.
   - Om du vill infoga beslutsprincipen klickar du på **_Redigera innehåll_** i åtgärdsektionerna och sedan på **_Redigera kod_** för att öppna personaliseringsredigeraren.
   - Välj ikonen _&#x200B;**Beslutspolicy**&#x200B;_ till vänster och klicka på knappen **Lägg till beslutspolicy** för att öppna skärmen **Skapa beslutspolicy**. Ange ett beskrivande namn för beslutspolicyn och välj det antal poster som beslutspolicyn ska returnera. Standardvärdet är 1.
   - Klicka på **_nästa_** och lägg till den urvalsstrategi som skapades i det tidigare steget i beslutsprincipen och klicka på **nästa** för att slutföra processen med att skapa beslutsprincipen. Inga reserverbjudanden har kopplats till beslutspolicyn.



- **Infoga beslutspolicy**
  ![personaliseringsredigerare](assets/personalization-editor.png)

  Infoga den nyskapade beslutsprincipen genom att klicka på knappen _&#x200B;**Infoga princip**&#x200B;_ . Detta infogar en for-slinga i personaliseringsredigeraren till höger.
Placera markören mellan slingorna på rad två och infoga offerText genom att gå till erbjudandet genom att gå nedåt i `tenant name`. Lägg in erbjudandet i en Div med klassens offer-item som på skärmbilden.



- **Publicera kampanjen**\
  Aktivera kampanjen för att börja leverera personaliserade erbjudanden i realtid.
