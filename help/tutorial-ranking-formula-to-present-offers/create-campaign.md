---
title: Skapa en kampanj
description: Läs om hur en AJO-kampanj kopplar samman målgrupper, beslutspolicyer och kanaler för att leverera personaliserade erbjudanden i rätt ögonblick över olika kontaktytor.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18188
exl-id: deb16dd5-23cd-495a-ac91-d22fd77f49bd
source-git-commit: 640faaf9a316b2ab3e2e7774b2c30612cf1b1dbe
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Skapa en kampanj

För att leverera personaliserade erbjudanden till användare på webbsidan har en kampanj skapats i Adobe Journey Optimizer och konfigurerats med rätt kanal, webbkanal. Denna konfiguration ser till att erbjudandena levereras via realtidsbeslut till användare som interagerar med webbplatsen.

I den här kampanjen definierades en beslutspolicy för att kontrollera hur erbjudanden väljs ut. Beslutspolicyn innehåller en urvalsstrategi som består av följande:

En samling av poster för erbjudanden (t.ex. baserat på postnummer eller intäkter),

Vilka regler som avgör vilka erbjudanden som gäller för en användare, och

En rankningsformel som tilldelar poäng till berättigade erbjudanden för att prioritera de mest relevanta.

När en inloggad användare besöker webbplatsen skickas en personaliseringsbegäran till AJO. Baserat på användarens sammanslagna attribut för identitet och profil (som ZIP-kod och årsinkomst) utvärderar beslutspolicyn alla tillgängliga erbjudanden. Den tillämpar urvalsstrategin och rangordningslogiken för att fastställa den bästa matchningen.

Resultatet är en skräddarsydd uppsättning erbjudanden som returneras som HTML-innehåll och visas för användaren i en karusell på webbplatsen, vilket skapar en sömlös, personaliserad upplevelse i realtid.


## Steg på hög nivå för att skapa en kampanj i AJO

1. **Skapa en kanalkonfiguration**\
   Definiera var och hur erbjudandena ska visas (till exempel en webbsida med kodbaserad upplevelse).
   - Logga in på Journey Optimizer
Navigera till _&#x200B;**Administration ->Kanaler->Skapa kanalkonfiguration**&#x200B;_
   - **Namn**: `finwise-web-personalization`\
     Identifierar den här konfigurationen för FinWise personliga webberbjudanden.

   - **Upplevelsetyp**: `Code-based experience`\
     Erbjudandena injiceras inte direkt i DOM. I stället returnerar AJO HTML i Raw-format, som tolkas med anpassade JavaScript.

   - **Plattform**: `Web`\
     Fungerar särskilt för webbläsare. Inga mobilkanaler är aktiverade.


   - **Sidans URL**: `http://localhost:3000/formula.html`\
     Kanalen är konfigurerad för en specifik testsida som används under utvecklingen.

   - **Plats på sida**: `offers-div`\
     Returnerade erbjudanden tolkas dynamiskt och återges i den här behållaren med hjälp av klientlogik.

   - **Innehållsformat**: `HTML`\
     Erbjudandena levereras som råa HTML-fragment, vilket ger fullständig kontroll över hur de formateras, filtreras och visas.


2. **Starta en ny kampanj**\
   Navigera till kampanjavsnittet och skapa en ny schemalagd marknadsföringskampanj. Namnge kampanjen korrekt.


3. **Lägg till åtgärd**\
   Navigera till fliken _&#x200B;**Åtgärder**&#x200B;_
Lägg till kodbaserad upplevelseåtgärd och länka åtgärden till en tidigare skapad kanalkonfiguration.



4. **Målgrupp**\
   Navigera till fliken _&#x200B;**Målgrupp**&#x200B;_
Alla besökare (standard).

   Identitetstyp: ECID (Experience Cloud ID)
Den här inställningen använder ECID som primär identitet för att identifiera användare. När identitetssammanfogning finns på plats länkas ECID till CRM ID för Personalized Targeting Select eller skapar en beslutspolicy som definierar erbjudandelogiken.

5. **Beslutspolicy**


   Åtgärden är länkad till en **beslutspolicy** som definierar hur erbjudanden markeras och hur många erbjudanden som returneras för visning. Den här principen använder en **urvalsstrategi** som skapades tidigare i självstudien.

   Om du vill infoga beslutsprincipen klickar du på **_Redigera innehåll_** på fliken _&#x200B;**Åtgärder**&#x200B;_ och sedan på **_Redigera kod_** för att öppna anpassningsredigeraren.

   Välj ikonen _&#x200B;**Beslutspolicy**&#x200B;_ till vänster och klicka på knappen **Lägg till beslutspolicy** för att öppna skärmen **Skapa beslutspolicy**. Ange ett beskrivande namn för beslutspolicyn och välj det antal poster som beslutspolicyn ska returnera. Standardvärdet är 1.
Klicka på **_nästa_** och lägg till den urvalsstrategi som skapades i det tidigare steget i beslutsprincipen och klicka på **nästa** för att slutföra processen med att skapa beslutsprincipen. Se till att välja rätt reserverbjudande.

6. **Infoga beslutspolicy**

   Infoga den nyskapade beslutsprincipen genom att klicka på knappen _&#x200B;**Infoga princip**&#x200B;_ . Detta infogar en for-slinga i personaliseringsredigeraren till höger.
Placera markören mellan slingorna på rad två och infoga offerText genom att gå till erbjudandet genom att gå nedåt i `tenant name`

   Beslutsprincip infogad i personaliseringsredigeraren

   ![personaliseringsredigerare](assets/personalization-editor.png)



   Handlebars-koden gör en slinga genom erbjudanden som returneras av en specifik beslutsprincip i Adobe Journey Optimizer och skapar en `<div>` för varje erbjudande. Varje `<div>` använder ett data-tags-attribut med erbjudandets interna namn för att hjälpa karusellgruppen att organisera erbjudandena efter kategori för smidig navigering. Innehållet i varje `<div>` visar den anpassade erbjudandetexten, vilket möjliggör dynamisk och visuellt segmenterad presentation av flera erbjudanden.

7. **Spara kampanjen**

   Spara kampanjen genom att klicka på knappen _&#x200B;**Granska för att aktivera**&#x200B;_


