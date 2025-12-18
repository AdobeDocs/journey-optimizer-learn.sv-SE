---
title: Lektion 2 - Skapa en mobilkampanj i appen
description: Skapa och utlösa en kampanj i appen för mobiler.
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14983
thumbnail: KT-14983.jpeg
exl-id: fe18eca7-229c-4867-ab34-1862bad63124
source-git-commit: 55ba1a46c1473d94847e7fccc69ed2a33badb54c
workflow-type: tm+mt
source-wordcount: '1432'
ht-degree: 0%

---

# Lektion 2 - Skapa en mobilkampanj i appen

I den här lektionen skapar och utlöser du meddelanden i appen för mobiler.

## Utbildningsmål

* Förstå hur meddelanden i appen utlöses.
* Lär dig skapa en mobilkampanj i appen.
* Utlös ett meddelande i appen.

## Exercise 2.1 - Logga in på Journey Optimizer

1. Öppna [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}
2. Logga in med följande information:
   <br>
   **Användarnamn:** L820+**`<your seat number>`**@adobeeventlab.com
   **Lösenord:**   Adobe2024!
   <br>
Du kan hitta information om din inloggning på din labbdator. Använd Adobe ID och Lösenordet.
   ![skrivbordet](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/desk-top.png)

   ![Inloggningsskärm](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. Du kan hoppa över de två följande skärmarna:
   <br>
   ![Telefonnummer](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![Personalization-popup](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Du bör vara inloggad på Journey Optimizer och på hemsidan:
>
>![AJO hemsida](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## Exercise 2.2 Skapa en kampanj i appen för mobiler

I den här övningen skapar du en meddelandekampanj i appen, som utlöses när du öppnar appen.

1. I Journey Optimizer väljer du **[!UICONTROL Kampanjer]** i den vänstra navigeringen.

1. Klicka på **[!UICONTROL Skapa kampanj]**.

   ![Skapa kampanj](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. På sidan **[!UICONTROL Skapa kampanj]** markerar du kryssrutan **[!UICONTROL Meddelande i appen]** i avsnittet **[!UICONTROL Åtgärd]**.

1. Välj **[!UICONTROL i listrutan]** Skicka till **[!DNL Mobile]**.

1. Välj **[!UICONTROL i listrutan]** Appyta **[!DNL Frecopa Mobile App]**.

1. Klicka på **[!UICONTROL Skapa]**.

   ![Appyta](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>Nu ska du vara med i Campaign-egenskaperna:
>
> ![Kampanjegenskaper](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## Utövning 2.3 Konfigurera kampanjen

### 2.3.1 [!UICONTROL Avsnittet Egenskaper]

Ge kampanjen ett namn. Kom ihåg att börja namnet med ditt platsnummer så att du enkelt kan hitta kampanjen igen.

Om ditt platsnummer till exempel är 9: `99 - Welcome Campaign`.

![egenskapsavsnittet](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 Konfigurera en anpassad utlösarregel

1. Bläddra ned till avsnittet **[!UICONTROL Utlösare]** och klicka sedan på **[!UICONTROL Redigera utlösare]**.

   ![Ändra](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. Klicka på **[!UICONTROL Programstart]** i regelbyggaren och välj *Skickade data till plattform* i listrutan.
   ![Skickat till dataplattformen](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Lägg till ett villkor genom att klicka på **[!UICONTROL Lägg till villkor]**.

   ![Lägg till villkorsknapp](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. Välj **[!UICONTROL XDM-händelsetyp]** i listrutan **[!UICONTROL Välj en egenskap]**.

   ![XDM-händelsetyp](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. Lägg till en *`<custom string value>`* som du kan komma ihåg i följande textfält.

1. Spara värdet genom att klicka på **[!UICONTROL Lägg till**] `<custom string value>`.

   Det här anpassade strängvärdet används senare för att utlösa ett meddelande.

   >[!TIP]
   > Om du lägger till ditt platsnummer i det anpassade strängvärdet blir det unikt och lättare att komma ihåg.
   > 
   > Till exempel: `99exerciseTrigger`

   ![lägg till ett anpassat strängvärde för utlösare](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. Klicka på **[!UICONTROL Klar]** överst till höger.

>[!SUCCESS]
>
>Du har nu definierat ditt meddelande i appen med en anpassad utlösarhändelse.
>
>![Kampanj med anpassad utlösare definierad](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 Redigera innehållet i meddelandet i appen

Klicka på **[!UICONTROL Redigera innehåll]** i avsnittet **[!UICONTROL Åtgärd]**.

![Knappen Redigera innehåll](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

[!UICONTROL Redigeraren för meddelande] i appen visas, där du konfigurerar meddelandeinnehållet i appen.

#### Layout för 2.3.3.1

Välj vilken layout som ska användas i meddelandet.

Klicka till exempel på **[!UICONTROL Modal]** för att göra ditt meddelande i appen till en modal layout.

![modal knapp](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 Skriv ditt meddelande och publicera din kampanj

1. Klistra in i följande URL i mediaavsnittet: `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
När du klickar utanför värdefältet ska bilden visas.

   ![medier som visas i förhandsgranskningen](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-media.png)

2. I följande **[!UICONTROL Innehåll]** lägger du till egen, anpassad text som du vill ska visas i meddelandet för **[!UICONTROL sidhuvudet]** och **[!UICONTROL brödtexten]**.

   ![Sidhuvud och brödtext](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-content.png)

3. Ytterligare alternativ:
   1. **Knappar:**

      ![Knappavsnitt](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. I det här avsnittet av redigeraren kan du anpassa texten för CTA-knappen genom att redigera knapptextfältet.

      2. Fältet **[!UICONTROL Interaktionshändelse]** används för att definiera det värde som skickas till SDK när användaren trycker på CTA.

      3. Fältet **[!UICONTROL Mål]** används för att definiera var du vill att CTA ska ta användaren. Detta inkluderar URL:er och e-postlänkar. Du kan till exempel lägga till den här länken på en produktsida som `dxdemo://exoticVibes`.

      4. Du kan lägga till ytterligare knappar genom att trycka på **[!UICONTROL + Lägg till]**.

      5. När en andra knapp läggs till i meddelandet kan du nu ändra knapplayouten med listrutan.


   2. **Avancerad formatering**

      ![avancerad formateringsväxling](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      Om du aktiverar den här växeln får du ytterligare anpassningsalternativ i redigeraren.

      1. Mediestorlek
      1. Teckensnitt
      1. Pt-storlek
      1. Teckenfärg
      1. Justering

      ![avancerade formateringsalternativ](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **Fliken Inställningar**

      Genom att gå över till den här fliken och i avsnittet **[!UICONTROL Förhandsgranska]** kan du ändra **appförhandsvisningen**.
      <br>\
      ![Fliken Inställningar](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. Avsnittet **[!UICONTROL Layout]** ger dig möjlighet att använda en bild som bakgrund eller heltäckande färg.

      2. Avsnittet **[!UICONTROL Meddelande]** innehåller anpassade interaktioner som kan aktiveras för ditt meddelande:
         1. Anpassade gester
         2. UI Takeover
         3. Anpassad övergång till användargränssnitt
         4. Anpassad storlek
         5. Egen placering
         6. Anpassad animering
         7. Runt hörn för meddelande
   <br>
4. När du är klar med redigeringen av ditt innehåll och är nöjd med meddelandet klickar du på knappen **[!UICONTROL Granska för att aktivera]**.

   >[!SUCCESS]
   >
   > Du har nu slutfört redigeringen av ditt meddelande i appen för mobila enheter. Du bör nu vara på Campaign **[!UICONTROL Review för att aktivera]**-sidan.
   >
   >![granska och aktivera](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > Här ser du en fullständig sammanfattning av ditt meddelande.
   >
   > *Observera det anpassade värde som du använde när du utlöste regeln. Det här värdet används för att utlösa ditt meddelande i appen. Värdet som användes finns i högdagerområdet på sammanfattningssidan.*

   >[!NOTE]
   >Den aktuella utlösaren för meddelandet i appen är standardhändelsen **Programstart inträffar**, vilket innebär att meddelandet i appen utlöses när appen startas. Det här visas i avsnittet **[!UICONTROL Schema]**.

5. Om du är klar med granskningen av din kampanj trycker du på knappen Aktivera för att publicera kampanjen.
   <br>
   ![aktivera](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> Nu bör du se kontrollpanelen för kampanjer. Hitta kampanjen genom att bläddra eller genom att använda sökfunktionen. När din Campaign ändrar status till **[!UICONTROL Live]** (~1min) har din Campaign nu publicerats.
>
> ![Publicerad kampanj](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## Exercise 2.4 Trigger the mobile in-app message

Så här uppdaterar du nyttolasten och hämtar din nyligen publicerade kampanj:

1. På din mobila enhet stänger du fullständigt appen Fréscopa.
2. Öppna appen Fréscopa igen.
3. Gå till fliken Öva i appen.

   ![Knappen Öva](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. Skriv in det anpassade utlösarvärde som du definierade i Campaign i textfältet. Tryck sedan på Submit.


   ![Ändra](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>Genom att klicka på Skicka aktiveras en utlösare manuellt och meddelandet i appen som du skapade visas:
>
>![Meddelande i appen](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *Om du har problem med att utlösa ditt meddelande kan du kontrollera följande:*
> 
> * *I fältet Händelsenamn i din mobilapp måste du skriva in utlösarregelvärdet exakt så som du hade det i Campaign.*
> * *Kontrollera att skiftläget är korrekt och att du inte har något inledande eller avslutande blanksteg.*
> * *Du kan slå upp det värde för utlösarregel du använde om du går tillbaka till granskningssidan för Campaign genom att klicka tillbaka till kampanjen på Campaign Dashboard.*

Du har just skrivit och publicerat ditt första Journey Optimizer In-app-meddelande!


## Bonusövning: Duplicera kampanj och förhandsgranskning på enhet

Funktionerna **Duplicera kampanj** och **Förhandsgranska på enhet** är färdiga funktioner som gör att du kan duplicera kampanjer och testa och granska meddelanden i appen direkt på enheten innan du aktiverar den. I den här övningen får du lära dig hur du använder den här funktionen och förhandsgranska det meddelande du skapade i övning 3.1.

1. Öppna kampanjen som du just skapade genom att klicka på namnet på kampanjen på panelsidan för kampanjer för att öppna kampanjen. Du kommer nu tillbaka till sidan **[!UICONTROL Granska kampanj]**.
1. Tryck på knappen **[!UICONTROL Duplicera]**. Då öppnas en ny uppmaning om att namnge den nya kampanj som ska dupliceras. Lägg till i ett nytt namn som du lätt kommer ihåg eller använde standardnamnet där **[!DNL _copy]** läggs till som standard.

   ![duplicerad kampanj](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. När du trycker på dubblettknappen skapas en dubblettkampanj och du dirigeras tillbaka till Campaigns Dashboard.
1. Öppna den nya kampanjen när den är duplicerad.

1. Du kan komma åt funktionen Förhandsgranska på enhet på sidan **[!UICONTROL Kampanjgranskning]** eller i steget **[!UICONTROL Kampanjförfattare]**.

   ![förhandsgranska på enhetsknappen](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. Klicka sedan på **[!UICONTROL startknappen]** på skärmen för att ansluta till enheten.

   ![startknapp](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Ange bas-URL:en som har konfigurerats för att starta Fréscopa-appen: `dxdemo://`

   ![förhandsgransknings-URL](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. Följ instruktionerna på skärmen:
   1. Skanna in QR-koden med din mobila enhet så öppnas Fréscopa-appen med en skärm där du kan ange en stift som visas.
   2. Ange stiftet som visas i AJO på Assurance-skärmen på enheten och klicka på knappen Anslut som visas längst ned till höger när du har angett stiftet.


   ![ange stift](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. Det här popup-fönstret visas på datorskärmen

   ![popup](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-pop-up.png)

1. Klicka på knappen Klar. Dialogrutan stängs och telefonen är nu ansluten till Förhandsgranska på enhet.


>[!SUCCESS]
>
> Ditt meddelande i appen visas på din enhet.
>
> *När du är ansluten bör ditt meddelande i appen visas varje gång du klickar på knappen **[!UICONTROL Förhandsgranska på enhet]**.

## Ytterligare resurser

**Så här gör du för videoklipp:**

* [Skapa en kampanj i appen](/help/channels/create-an-in-app-campaign.md)
* [Skriv ett meddelande i appen](/help/channels/author-in-app-messages.md)

**Produktdokumentation:**

* [Kom igång med kanalen i appen](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/get-started-in-app)
* [Skapa ett meddelande i appen för mobiler](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/create-in-app)
* [Designa ditt innehåll i appen](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/design-in-app)
* [Kontrollera och skicka meddelanden i appen](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/send-in-app)
