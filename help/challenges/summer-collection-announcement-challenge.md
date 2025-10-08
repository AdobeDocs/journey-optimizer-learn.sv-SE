---
title: Skapa en annons för sommarsamlingen - utmaning
description: Skicka ett meddelande till en publik med kunder om att de vill marknadsföra nya Luma Summer Collection.
jira: KT-8109
feature: Segments, Journeys, Email
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 0%

---

# Skapa en annons för sommarsamlingen - utmaning

| Utmaning | Skapa ett meddelande om en sommarsamling |
|---|---|
| Persona | Resechef |
| Nödvändiga färdigheter | <ul><li>[Skapa segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [Importera och redigera e-postinnehåll från HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[Användningsfall - Lässegment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journeys/use-case-read-segment.html?lang=en)</li> |
| Assets att ladda ned | [E-postfiler för säsongssamling](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

{style="table-layout:auto"}

## Artikeln

Luma, ett fiktivt sportklädföretag, marknadsför sin senaste uppsättning kläder och utrustning och driver försäljningen för befintliga kunder. Luma lanserar den nya sommarsamlingen och vill särskilt rikta sig till olika målgrupper.

## Utmaningen

Marknadsföringsteamet på Luma ber er att implementera en marknadsföringskampanj för sommar Collection i Journey Optimizer. Utmaningen är att

* Skapa en målgrupp som definierar vilka profiler som är kvalificerade att ta emot kampanjen.
* Bygg resan.

### Steg 1: Definiera målgruppen - aktiva kunder

>[!BEGINTABS]

>[!TAB Uppgift]

#### Skapa en målgrupp i [!DNL Journey Optimizer]

* Skapa en målgrupp i [!DNL Journey Optimizer] som kallas *Aktiva kunder*.
* Segmentet får endast innehålla aktiva Luma-kunder.
* Aktiva kunder definieras som kunder som har ett skikt i Lumas lojalitetsprogram (brons, silver, guld eller platinum).


>[!TAB Slutförandevillkor]

I segmentbyggaren ser du det uppskattade antalet kvalificerade profiler. Om du arbetar med träningssandlådans data har du cirka 753 kvalificerade profiler av 1,29 K.

>[!NOTE]
>Det kan ta upp till 24 timmar innan segmentmedlemskapet visas för befintliga profiler, eftersom de befintliga profilerna behöver fyllas i i baklänges.

**En kvalificeringsprofil har lagts till i segmentet:**

Du kan kontrollera vilka profiler som har lagts till i segmentet genom att navigera till en av dem i profilerna som listas i segmentets detaljvy.

På profilsidan kontrollerar du fliken [!UICONTROL Attribut] för att bekräfta att de är kvalificerade: Nivån ska vara silver, guld, platina eller diamant.

![Profilattribut](assets/C1-S1-profile-attributes.png)

Du kan även kontrollera fliken [!UICONTROL Segmentmedlemskap]: Ditt segment ska listas.

![Segmentmedlemskap](assets/C1-S1-profile-segment-membership.png)

>[!TAB Kontrollera ditt arbete]

Segmentfält: **[!UICONTROL Attribut]** > **[!UICONTROL XDM individuell profil]** > **[!UICONTROL Lojalitet]** > **[!UICONTROL Nivå]**

Så här ska ditt segment se ut:

![Segment - aktiva kunder](/help/challenges/assets/C1-S1.png)

Koden ska se ut så här:

```javascript
stringCompare("equals", loyalty.tier, ["diamond", "gold", "platinum", "silver"], false)
```

>[!ENDTABS]


### Steg 2: Skapa meddelandet om resan - sommarsamlingen

>[!BEGINTABS]

>[!TAB Uppgift]

#### Skicka sommarCollection

En byrå försåg dig med fyra HTML-filer med design för e-postmeddelanden:

* `SeasonalCollectionEmail.html`
* Luma Men&#39;s Collection email
* Luma Women&#39;s Collection email
* Luma - 20 % rabatt på e-post för samling

1. [Ladda ned e-postfilerna för säsongssamlingen](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip).

1. Skapa en resa med namnet *Luma - Meddelande om sommarsamling* baserat på följande riktlinjer:

   1. Skicka *Luma - nytt sommarsamlingsmeddelande* till segmentet *Aktiva kunder*, där 10 % av publiken hålls som en kontrollgrupp
      * Meddelanderubrik *Luma - Meddelande om sommarsamling*
      * Ärenderad *(mottagarens förnamn), den nya Luma-sommarsamlingen är här!*
      * Använd den tillhandahållna HTML-filen `SeasonalCollectionEmail.html` för e-postbrödtexten.
   1. Vänta i två dagar och skicka sedan ett uppföljningsmejl med mer riktat innehåll:
      * Manliga kunder bör få e-postmeddelandet **Luma Men&#39;s Collection**.
         * Meddelanderubrik: *Luma Men&#39;s Collection*
         * Ämnesrad: *(mottagarens förnamn), utforska Men&#39;s New sportkugghjulet!*
         * E-postbrödtext: `MensCollectionEmail.html` för e-postbrödtexten.
      * Kunder som är kvinnor bör få e-postmeddelandet **Luma Women&#39;s Collection**.
         * Meddelanderubrik: *Luma Women&#39;s Collection*
         * Ämnesrad: *(mottagarens förnamn), utforska Lumas Women Collection!*
         * E-postbrödtext: `WomensCollectionEmail.html`
      * Andra kunder bör få e-postmeddelandet **Luma - 20 % rabatt på Collection**.
      * Meddelanderubrik: *Luma - 20 % rabatt på samling*
      * Ärenderad: *(mottagarens förnamn), få 20 % rabatt!*
      * E-postbrödtext: `20OOffCollectionEmail.html`
   1. När du har skickat de riktade e-postmeddelandena ovan väntar du två dagar på att e-postmeddelandet ska öppnas
   1. Om det riktade e-postmeddelandet inte öppnas inom 2 dagar skickar du **Luma - 20 %av e-postmeddelandet om samlingen** som ett slutligt återmarknadsföringsförsök


>[!TAB Slutförandevillkor]

#### Förhandsgranska e-postmeddelanden

**E-postmeddelande nr 1 - Luma - Meddelande om sommarkollektion**

Förhandsgranska e-postmeddelandet:

1. Lägg till en testprofil: Louise Petti:
   * Identitetsnamnrymd: *Luma CRM ID*
   * Identitetsvärde: *d1f132f9f9502bba047a6ec86c4b61f9*

Resultat:

* Subject line should read: Louise, the new Luma collection is here!

**E-postmeddelande nr 2 - Luma Men&#39;s Collection**

Skicka ett bevis till dig själv:

1. Lägg till en testprofil: Stanleigh Stooke:
   * Identitetsnamnrymd: *Luma CRM ID*
   * Identitetsvärde: `4f34057d9d9e792c28ba18ecae378e98`
2. Välj testprofil: Stanleigh Stooke.
3. Skicka ett bevis till dig själv.

Resultat:\
Du bör få ett e-postmeddelande. Ämnesraden ska vara *Stanleigh, utforska Men&#39;s New sportkugghjulet!* och e-postmeddelandetexten ska matcha det du har sett i förhandsgranskningen.

>[!NOTE]
>Det kan ta några minuter innan du får beviset.

**E-postmeddelande nr 3 - Luma Women&#39;s Collection**

Förhandsgranska e-postmeddelandet med testprofilen *Louise Petti.*

* Ämnesraden ska vara: *Louise, explore Luma&#39;s Women Collection!*

**E-postmeddelande nr 4 - Luma 20 % rabatt på samling**

Förhandsgranska e-postmeddelandet med testprofilen *Louise Petti.*

* Ämnesraden ska vara: *Lupp, få 20 % rabatt!*

#### Testa din resa

>[!IMPORTANT]
>
>Innan du ställer in resan i testläge:
>
>1. Kontrollera att namnområdet [!UICONTROL Luma CRM ID(lumaCrmId)] har angetts för **Läs segmentaktiviteten**
>1. För varje e-postadress åsidosätter du e-postens standardparametrar så att de skickas till din e-postadress:
>    * Visa dolda värden genom att klicka på ögonsymbolen.
>    * Klicka på T-symbolen (aktivera åsidosättning av parameter) i e-postparametrarna.
>
>      ![Åsidosätt e-postparametrar](/help/challenges/assets/c3-override-email-paramters.jpg)
> 
>    * Klicka i fältet [!UICONTROL Adress]
>    * På nästa skärm lägger du till din e-postadress inom parentes: `"yourname@yourdomain"` i uttrycksredigeraren och klickar på OK.
>

Testa resan och få e-postmeddelandena skickade till ditt eget konto:

1. Förvandla resan till testläge.
1. Välj **[!UICONTROL En profil åt gången]**.
1. Vänta: Ställ in timern på 120 sekunder (skriv in den i fältet).
1. Ingång till utlösarprofil
1. Du kan testa varje gren genom att använda något av följande *Luma CRM-ID:n* som profilidentifierare:
   * Kvinna: Leora Dietsche, identitetsvärde:`a8f14eab3b483c2b96171b575ecd90b1`
   * Man: Stanleigh Stooke, identitetsvärde: `4f34057d9d9e792c28ba18ecae378e98`
   * Inget kön har angetts: Louise Petti, identitetsvärde: `d1f132f9f9502bba047a6ec86c4b61f9`

1. När du har utlöst profilingången bör du få det första e-postmeddelandet. Huvudet ska anpassas efter den profil du väljer.
1. Resan bör fortsätta till respektive gren och du bör få det relaterade e-postmeddelandet (om du t.ex. väljer *Jenna* bör du få e-postmeddelandet *Luma Women&#39;s Collection* ).
1. Öppna det andra e-postmeddelandet så avslutas resan.
1. Du kan upprepa steg 4. - 7. för alla tre profilerna för att kontrollera om grenarna fungerar som de ska.
1. Om du vill testa timeout-värdena ställer du in väntetiden på 30 sekunder och utlöser inmatningen igen.
1. Öppna inte de e-postmeddelanden som du får (förhandsgranska inte e-postmeddelandet (!)) och låt väntetiden vara kvar.

Du bör få följande e-postmeddelanden:

* Luma - Meddelande om ny säsongssamling
* Beroende på vilken testprofil du använde bör du få något av följande e-postmeddelanden:
   * Leora: Luma Women&#39;s Collection
   * Stanleigh: Luma Men&#39;s Collection
   * Luma: 20 % rabatt på samling
* Om du inte öppnade det andra e-postmeddelandet: Luma - 20 % rabatt

>[!TAB Kontrollera ditt arbete]

Så här ska din resa se ut:

![Resa](/help/challenges/assets/c3-j1-journey.png)

**Villkor - Kontrollgrupp:**

![Kontrollgrupp](/help/challenges/assets/c3-j1-condition-control-group.png)

**Villkor - kön:**\

![Villkor - Kön](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
