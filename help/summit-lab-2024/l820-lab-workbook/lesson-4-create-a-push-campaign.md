---
title: Lektion 4 - Skapa en push-kampanj
description: Granska profildata och lär dig hur du skapar och skickar ett push-meddelande till målgrupper i Journey Optimizer.
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
exl-id: 0f82d6a5-18c0-45f2-968e-a678fc2d5768
source-git-commit: b5577da9a983594cb34edf5c53e2995024e30e78
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 0%

---

# Lektion 4 - Skapa en push-kampanj

I föregående övning var du en kaffeentusiast, en Fréscopa-kund. Ni interagerade med varumärket via deras webbplats och appen Fréscopa och fick många transaktionsmeddelanden. Dessa meddelanden utlöses genom att användaren interagerar med webbplatsen eller programmet.

I den här övningen kommer ni att sätta på er marknadsföringskampanj för Frésopa, som kommer att använda push-kanalen för att rikta in er på appanvändarna Fréscopa. Push-meddelanden används för att hålla appanvändare informerade, även när de inte använder appen, men även för att återengagera dem med appen. Målet är att ge kunderna incitament att köpa en företagsblandning genom att erbjuda en rabatt på 10 %.

## Utbildningsmål

* Lär dig skapa en push-kampanj.
* Lär dig hur du utformar ett push-meddelande.

<br>

## Utgång 4.1 - Skapa en push-kampanj

I den här övningen skapar du push-kampanjen, designar och anpassar push-meddelandet och skickar push-meddelandet till din egen enhet.

1. I Journey Optimizer väljer du **Kampanjer** i den vänstra navigeringen i avsnittet **[!UICONTROL RESURSHANTERING]**.

1. Klicka på **[!UICONTROL Skapa kampanj]**.

   ![Skapa kampanj](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. Markera kryssrutan **[!UICONTROL Push-meddelande]** i avsnittet **[!UICONTROL Åtgärd]** på sidan **[!UICONTROL Skapa kampanj]**.

1. Välj *[!DNL Frecopa-Push]* i listrutan **[!UICONTROL Appyta]**.

1. Klicka på **[!UICONTROL Skapa]** om du vill skapa en push-kampanj.

   ![Appyta](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>Nu ska du vara på egenskapssidan för Campaign:
> ![Kampanjegenskaper ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## Utövning 4.2 - Konfigurera din kampanj

På den här sidan konfigurerar du egenskaper, målgrupp, åtgärder och schema för din kampanj.

### 4.2.1 [!UICONTROL Avsnittet Egenskaper]

Ge kampanjen ett namn. Kom ihåg att börja namnet med ditt platsnummer så att du enkelt kan hitta kampanjen när du söker efter den.

Om ditt platsnummer till exempel är 99: `99 - 10% Discount Campaign`.

### 4.2.2 **[!UICONTROL Målgruppsavsnitt]**

1. Klicka på **[!UICONTROL Välj målgrupp]** i målgruppsavsnittet.

   ![målgruppsavsnittet](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. På skärmen **[!UICONTROL Välj publik]** söker du efter målgruppen:

   **Lab - plats`your seat number`**

1. Markera målgruppen och klicka sedan på **[!UICONTROL Spara]**.

   ![målgruppsval](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 Redigera innehållet i push-meddelandet

I den här övningen utformar och anpassar du push-meddelandet.

1. Klicka på knappen **[!UICONTROL Redigera innehåll]** i avsnittet **[!UICONTROL Åtgärd]**.

   ![Knappen Redigera innehåll](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. På nästa skärm, beroende på vilken mobil enhet du har, väljer du fliken [!DNL iOS™] eller [!DNL Android™] för att konfigurera ditt innehåll.

>[!BEGINTABS]

>[!TAB iOS]

![Fliken iOS](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![Fliken Android](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1 [!UICONTROL Disponera meddelande]

1. **Skriv ditt meddelande:** Du kan lägga till valfri text. Här är några exempel som du kan använda:

   * Titel: `Get 10% off today!`
   * Brödtext: `Today only! Get 10% off on your House Blend coffee purchase!`

     ![Disponera meddelande](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 Ändra beteendet vid klickning för meddelandet till **öppna en produktsida**

1. I avsnittet **[!UICONTROL Vid klickbeteende]** väljer du **[!UICONTROL Ta bort länk]** i listrutan **[!UICONTROL Innehållsklickningsbeteende]**.

1. Kopiera och klistra in följande URL-adress i fältet **URL**:

   `dxdemo://exoticVibes`

   ![djuplänk](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 Lägg till en bild i meddelandet

1. Klicka på **[!UICONTROL Lägg till media]** i avsnittet **[!UICONTROL Lägg till media]**.

   ![lägg till medieknappar](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. Öppna mappen **Fréscopa** i den vänstra navigeringen på skärmen **[!UICONTROL Välj Assets]** och välj en bild från den mappen.

   Till exempel: `HouseBlend.png`

1. Klicka på bilden och klicka på knappen **[!UICONTROL Välj]** för att lägga till bilden i ditt push-meddelande.

   ![välj bild](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. Klicka på **[!UICONTROL Expandera vy]** på förhandsgranskningsskärmen.
   > 1. Förhandsgranska meddelandet.
   > <br>
   >
   > ![expandera vy](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

### Bonusövning

Om du har avslutat den här delen av övningen och fortfarande har lite tid kan du prova bonusövningen:

+++ Bonusövning

#### Anpassa meddelandet som du skickar genom att lägga till mottagarens förnamn

1. Klicka på **dialogrutan för anpassning** bredvid fältet **[!UICONTROL Brödtext]**.

   ![personaliseringsknapp](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-button.png)

1. Placera markören där du vill lägga till förnamnet i texten på skärmen **i dialogrutan** för anpassning.

1. Kontrollera att **profilattributen** är markerade i den vänstra navigeringen.

   ![Profilattribut](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. Sök efter `first name` i **sökfältet**.

1. Klicka på **+** bredvid **Förnamn (Profilattribut>Person>Fullständigt namn)** för att lägga till anpassningsfältet i texten.

   ![Sök efter förnamn](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > Så här ska texten se ut:
   > 
   >![Personalization-token](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-token.png)

1. Klicka på **[!UICONTROL Spara]** för att spara personaliseringen.


   >[!SUCCESS]
   >
   > 1. Klicka på **[!UICONTROL Expandera vy]** på förhandsgranskningsskärmen.
   > 1. Förhandsgranska meddelandet.
   > 
   > ![expandera vy](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4. Granska och aktivera

Om du är nöjd med innehållet i ditt meddelande kan du aktivera meddelandet:

1. Klicka på **[!UICONTROL Granska för att aktivera]**.

   ![knappen Granska och aktivera](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. Klicka på **[!UICONTROL Aktivera]** på skärmen **[!UICONTROL Granska för att aktivera]**.

   ![granskning för att aktivera skärmen](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> På sidan **Kampanjöversikt** kan du hitta din kampanj och kontrollera statusen.
>
> ![kampanjstatus](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> Statusen ändras från bearbetning till live, till färdig - det kan ta några minuter.
> När statusen har ändrats till slutförd:
>
> ![push-resultat](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-push-notification-result.png)

## Ytterligare resurser

**Så här gör du för videoklipp:**

* [Konfigurera och skicka en push-kampanj](/help/channels/create-a-push-campaign.md)

**Produktdokumentation:**

* [Kom igång med push-meddelanden](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/push/get-started-push)
* [Skapa ett push-meddelande](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/push/create-push)
* [Designa ett push-meddelande](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/push/design-push)
* [Kontrollera och skicka push-meddelanden](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/push/send-push)
