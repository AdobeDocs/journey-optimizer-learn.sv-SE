---
title: Lektion 3 - Skapa en webbkampanj i appen
description: Skapa och utlösa en webbkampanj i appen.
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-13983
thumbnail: KT-13983.jpeg
exl-id: 0f84adfb-edb1-47fa-b696-58eec2b33bb1
source-git-commit: 55ba1a46c1473d94847e7fccc69ed2a33badb54c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 0%

---

# Lektion 3 - Skapa en webbkampanj i appen

Nu när ni har skapat mobilupplevelser för appen skapar ni i den här lektionen en av de upplevelser ni har sett på Fréscopas webbplats. Du skapar en webbkampanj i appen. Du utformar och anpassar ett meddelande och definierar en utlösare som utlöser meddelandet.

## Utbildningsmål

* Lär dig skapa en kampanj i appen för webben.
* Utlös ett meddelande i appen.

## Exercise 3.1 Skapa en kampanj i appen för webben

I den här övningen skapar du kampanjen och definierar vilken webbsida meddelandet i appen ska visas på.

1. I Journey Optimizer väljer du **Kampanjer** under **RESURSHANTERING** i den vänstra navigeringen.

1. Klicka på **Skapa kampanj**.

   ![CreateCampaign](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-create-campaign.png)

1. På sidan **Skapa kampanj** markerar du kryssrutan **Meddelande i appen** i avsnittet **Åtgärd**.

1. I listrutan **Skicka till** väljer du **Webb.**

1. Ange följande URL: **https://dsn.adobe.com/web/adobe-summit-2024/exercise** - *Det här är den webbsida som ditt meddelande kommer att visas på.*

   ![URL i appen](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-1-in-app-url.png)

1. Klicka på **[!UICONTROL Skapa]**.

## Exercise 3.2 Konfigurera din kampanj

På den här sidan definierar du kampanjens egenskaper och händelsen som utlöser att meddelandet i appen visas på webbsidan. Låt alla andra inställningar vara kvar som standard. För den här övningen behöver ni inte definiera en specifik målgrupp.

### 3.2.1 [!UICONTROL Avsnittet Egenskaper]

1. I avsnittet **Egenskaper** ger du kampanjen ett unikt **namn**:

   >[!NOTE]
   > Se till att du börjar med ditt platsnummer så att du enkelt kan
   > hitta kampanjen senare.
   > 
   > Om till exempel ditt platsnummer är 99: 
   >
   > ![Egenskapsnamn](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-properties-name.png)


### 3.2.2 Konfigurera en anpassad utlösarregel

I det här avsnittet definierar du vilka utlösare som ska användas för att visa meddelandet på webbplatsen. Du definierar en unik utlösare som gör att du kan skicka meddelandet precis till dig själv.

1. Bläddra ned till avsnittet **[!UICONTROL Utlösare]** och klicka sedan på **[!UICONTROL Redigera utlösare]**.

   ![Ändra](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. Klicka på **[!UICONTROL Programstart]** i regelbyggaren och välj *Skickade data till plattform* i listrutan.
   ![utlösarhändelse-listruta](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Lägg till ett villkor genom att klicka på **[!UICONTROL + Lägg till villkor]**.

   ![Lägg till villkorsknapp](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. Välj **[!UICONTROL XDM-händelsetyp]** i listrutan **[!UICONTROL Välj en egenskap]**.

   ![XDM-händelsetyp](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)


1. Lägg till en *`<custom string value>`* som du kommer ihåg i följande textfält och tryck på **[!UICONTROL Lägg till]** `<custom string value>` för att spara värdet.

   Det här anpassade strängvärdet används senare för att utlösa ett meddelande.

   >[!TIP]
   > Om du lägger till ditt platsnummer i det anpassade strängvärdet blir det unikt och lättare att komma ihåg.
   > 
   > Till exempel: `99web`
   > 

   ![lägg till ett anpassat strängvärde för utlösare](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-add-custom-trigger-dropdown.png)

1. Tryck på knappen **[!UICONTROL Klar]** längst upp till höger.

>[!SUCCESS]
>
>Du har nu definierat ditt webbaserade meddelande i appen med en anpassad utlösarhändelse.
>
>![Webbkampanj med anpassad utlösare definierad](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-2-web-campaign-with-custom-trigger.png)


### 3.2.3 Redigera innehållet i meddelandet i appen

I det här avsnittet definierar du innehållet, utformningen och layouten för meddelandet.

1. Klicka på knappen **Redigera innehåll** i avsnittet **Åtgärd** för att komma åt redigeringskonstruktionen.

   ![Knappen Redigera innehåll](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

1. Redigeringsprocessen är samma process som du slutförde i övningarna i appen Mobile. Redigera ditt meddelande med din egen titel, ditt eget innehåll och ditt eget mediematerial.

   Om du använder modal- eller helskärmslayout kan du lägga till en knapp. Du kan använda den här URL:en för att öppna produktsidan: **https://dsn.adobe.com/web/adobe-summit-2024/P2WsaDPf_**

1. När du är klar med redigeringen av meddelandet klickar du på **[!UICONTROL Granska för att aktivera]**.

1. Om allt ser bra ut på granskningsskärmen klickar du på **[!UICONTROL Aktivera]** för att publicera webb-i-app-meddelandet.

1. Du kommer tillbaka till Campaign Dashboard.

   Vänta tills kampanjstatusen ändras till **Live** innan du går till 4.1.4.

## Exercise 3.3 Trigger the web in-app message

1. Gå till Fréscopa-webbplatsen och navigera till sidan **Öva** i webbläsaren.

   ![Länk för webbövningar](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-2-frescopa-web-exercise-link.png)

1. Uppdatera webbsidan.

1. Skriv det unika strängvärdet som du definierade i kampanjen.

   ![träningssida](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-2-exercise-page.png)

1. Klicka på **[!UICONTROL Skicka]**.

>[!SUCCESS]
>
>Om du klickar på knappen Skicka med ditt unika värde aktiveras webb-i-appmeddelandet. Och du bör se ditt webbaserade meddelande i appen visas på skärmen.
>
>Den här övningen simulerade en anpassad XDM-sändningshändelse som du såg genom din Fréscopa-kundupplevelse.


## Ytterligare resurser

**Så här gör du för videoklipp:**

* [Skapa en kampanj i appen](/help/channels/create-an-in-app-campaign.md)
* [Skriv ett meddelande i appen](/help/channels/author-in-app-messages.md)

**Produktdokumentation:**

* [Kom igång med kanalen i appen](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/get-started-in-app)
* [Skapa ett meddelande i appen för webben](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/create-in-app-web)
* [Designa ditt innehåll i appen](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/design-in-app)
* [Kontrollera och skicka meddelanden i appen](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/send-in-app)
