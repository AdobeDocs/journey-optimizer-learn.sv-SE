---
title: Skapa en annons för sommarsamlingen - utmaning
description: Skicka ett meddelande till några befintliga kunder om att de vill marknadsföra nya Luma Summer Collection.
jira: KT-8109
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: 81f5cc22d46f89ee1c7164a92988311ca6036b8b
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 0%

---

# Skapa en annons för sommarsamlingen - utmaning

![AJO Summer Collection Announcement Banner](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| Utmaning | Skapa ett meddelande om en sommarsamling |
|---|---|
| Persona | Resechef |
| Nödvändiga färdigheter | <ul><li>[Skapa segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [Importera och redigera e-postinnehåll från HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[Användningsfall - Lässegment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Resurser att hämta | [E-postfiler för säsongssamling](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

{style="table-layout:auto"}

## The story

Luma, ett fiktivt sportklädföretag, marknadsför sin senaste uppsättning kläder och utrustning och driver försäljningen för befintliga kunder. Luma lanserar den nya sommarsamlingen och vill särskilt inrikta sig på olika kundsegment.

## Utmaningen

Marknadsföringsteamet på Luma ber er att implementera en marknadsföringskampanj för sommar Collection i Journey Optimizer. Utmaningen är att

* Skapa ett segment som definierar vilka profiler som är kvalificerade att ta emot kampanjen.
* Bygg resan.

### Steg 1: Definiera segmentet - aktiva kunder

>[!BEGINTABS]

>[!TAB Uppgift]

#### Skapa ett segment i [!DNL Journey Optimizer]

* Skapa ett segment i [!DNL Journey Optimizer] anropad *Aktiva kunder*.
* Segmentet får endast innehålla aktiva Luma-kunder.
* Aktiva kunder definieras som kunder som har ett skikt i Lumas lojalitetsprogram (brons, silver, guld eller platinum).


>[!TAB Godtagandevillkor]

I segmentbyggaren ser du det uppskattade antalet kvalificerade profiler. Om du arbetar med träningssandlådans data har du cirka 753 kvalificerade profiler av 1,29 K.

>[!NOTE]
>Det kan ta upp till 24 timmar innan segmentmedlemskapet visas för befintliga profiler, eftersom de befintliga profilerna behöver fyllas i i baklänges.

**En kvalificeringsprofil har lagts till i segmentet:**

Du kan kontrollera vilka profiler som har lagts till i segmentet genom att navigera till en av dem i profilerna som listas i segmentets detaljvy.

På profilsidan markerar du [!UICONTROL Attribut] för att bekräfta att de är kvalificerade: Skiktet ska vara silver, guld, platina eller diamant.

![Profilattribut](assets/C1-S1-profile-attributes.png)

Du kan även kontrollera [!UICONTROL Segmentmedlemskap] tab: Segmentet bör listas.

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


### Steg 2: Create the Journey - Sommarsamlingsmeddelande

>[!BEGINTABS]

>[!TAB Uppgift]

#### Skicka sommarCollection

En byrå försåg dig med fyra HTML-filer med design för e-postmeddelanden:

* `SeasonalCollectionEmail.html`
* Luma Men&#39;s Collection email
* Luma Women&#39;s Collection email
* Luma - 20 % rabatt på e-post för samling

1. [Ladda ned e-postfilerna för säsongssamlingen](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip).

1. Skapa en anropad resa *Luma - Meddelande om sommarkollektionen* baserat på följande riktlinjer:

   1. Skicka *Luma - Meddelande om nya sommarkollektionen* e-post till *Aktiva kunder* som håller ut 10 % av publiken som kontrollgrupp
      * Meddelanderubrik *Luma - Meddelande om sommarkollektionen*
      * Subject line *(mottagarens förnamn) är nya Luma sommar-samlingen här!*
      * Använd den angivna HTML-filen `SeasonalCollectionEmail.html` för e-postbrödtexten.
   1. Vänta i två dagar och skicka sedan ett uppföljningsmejl med mer riktat innehåll:
      * Manliga kunder bör få **Luma Men&#39;s Collection** e-post.
         * Meddelanderubrik: *Luma Men&#39;s Collection*
         * Ärenderad: *(mottagarens förnamn), utforska Men&#39;s New sportkugghjulet!*
         * E-postbrödtext: `MensCollectionEmail.html` för e-postbrödtexten.
      * Kunder som är kvinnor bör få **Luma Women&#39;s Collection** e-post.
         * Meddelanderubrik: *Luma Women&#39;s Collection*
         * Ärenderad: *(mottagarens förnamn), utforska Lumas Women Collection!*
         * E-postbrödtext: `WomensCollectionEmail.html`
      * Andra kunder bör få **Luma - 20 % rabatt på samling** e-post.
      * Meddelanderubrik: *Luma - 20 % rabatt på samling*
      * Ärenderad: *(mottagarens förnamn), få 20 % rabatt!*
      * E-postbrödtext: `20OOffCollectionEmail.html`
   1. När du har skickat de riktade e-postmeddelandena ovan väntar du två dagar på att e-postmeddelandet ska öppnas
   1. Om målmeddelandet inte öppnas inom två dagar skickar du **Luma - 20 %rabatt på e-post för samling** som ett sista försök till återmarknadsföring


>[!TAB Villkor för lyckade]

#### Förhandsgranska e-postmeddelanden

**E-postmeddelande nr 1 - Luma - Meddelande om sommarkollektion**

Förhandsgranska e-postmeddelandet:

1. Lägg till en testprofil: Louise Petti:
   * Identitetsnamnutrymme: *Luma CRM-ID*
   * Identitetsvärde: *d1f132f9f9502bba047a6ec86c4b61f9*

Resultat:

* Ämnesraden ska vara: Louise, nya Luma-samlingen är här!

**E-postmeddelande nr 2 - Luma Men&#39;s Collection**

Skicka ett bevis till dig själv:

1. Lägg till en testprofil: Stanleigh Stooke:
   * Identitetsnamnutrymme: *Luma CRM-ID*
   * Identitetsvärde: `4f34057d9d9e792c28ba18ecae378e98`
2. Välj testprofil: Stanleigh Stooke.
3. Skicka ett bevis till dig själv.

Resultat:\
Du bör få ett e-postmeddelande. Subject line should read *Stanleigh, utforska Men&#39;s New athletic>!* och e-postmeddelandetexten ska matcha det du har sett i förhandsgranskningen.

>[!NOTE]
>Det kan ta några minuter innan du får beviset.

**E-postmeddelande nr 3 - Luma Women&#39;s Collection**

Förhandsgranska e-postmeddelandet med testprofilen *Louise Petti.*

* Ämnesraden ska vara: *Louise, utforska Lumas Women Collection!*

**E-postmeddelande nr 4 - Luma 20 % rabatt på samling**

Förhandsgranska e-postmeddelandet med testprofilen *Louise Petti.*

* Ämnesraden ska vara: *Louise, få 20 % rabatt!*

#### Testa din resa

>[!IMPORTANT]
>
>Innan du ställer in resan i testläge:
>
>1. Se till att [!UICONTROL Läs segmentaktivitet] har namnutrymmet inställt på **Luma CRM-id (lumaCrmId)**
>1. För varje e-postadress åsidosätter du e-postens standardparametrar så att de skickas till din e-postadress:
>    * Visa dolda värden genom att klicka på ögonsymbolen.
>    * Klicka på T-symbolen (aktivera åsidosättning av parameter) i e-postparametrarna.
>
>      ![Åsidosätt e-postparametrar](/help/challenges/assets/c3-override-email-paramters.jpg)
> 
>    * Klicka på [!UICONTROL Adress] fält
>    * Lägg till din e-postadress inom parentes på nästa skärm: `"yourname@yourdomain"` i uttrycksredigeraren och klicka på OK.
>

Testa resan och få e-postmeddelandena skickade till ditt eget konto:

1. Sätt resan i testläge.
1. Välj **[!UICONTROL En profil åt gången]**.
1. Väntetid: Ställ in timern på 120 sekunder (skriv in den i fältet).
1. Ingång till utlösarprofil
1. Du kan testa varje gren med något av följande *Luma CRM ID* som profilidentifierare:
   * Kvinna: Leora Dietsche, identitetsvärde:`a8f14eab3b483c2b96171b575ecd90b1`
   * Man: Stanleigh Stooke, identitetsvärde: `4f34057d9d9e792c28ba18ecae378e98`
   * Genus har inte angetts: Louise Petti, identitetsvärde: `d1f132f9f9502bba047a6ec86c4b61f9`

1. När du har utlöst profilingången bör du få det första e-postmeddelandet. Huvudet ska anpassas efter den profil du väljer.
1. Resan bör fortsätta till respektive gren och du bör få det relaterade e-postmeddelandet (till exempel om du väljer *Jenna*, bör du få *Luma Women&#39;s Collection* e-post).
1. Öppna det andra e-postmeddelandet så avslutas resan.
1. Du kan upprepa steg 4. - 7. för alla tre profilerna för att kontrollera om grenarna fungerar som de ska.
1. Om du vill testa timeout-värdena ställer du in väntetiden på 30 sekunder och utlöser inmatningen igen.
1. Öppna inte de e-postmeddelanden du får (förhandsgranska inte e-postmeddelandet (!)) och vänta lite.

Du bör få följande e-postmeddelanden:

* Luma - Meddelande om ny säsongssamling
* Beroende på vilken testprofil du använde bör du få något av följande e-postmeddelanden:
   * Leora: Luma Women&#39;s Collection
   * Stanleigh: Luma Men&#39;s Collection
   * Lupp: Luma - 20 % rabatt på samling
* Om du inte öppnade det andra e-postmeddelandet: Luma - 20 % rabatt på samlingen

>[!TAB Kontrollera ditt arbete]

Så här ska din resa se ut:

![Resa](/help/challenges/assets/c3-j1-journey.png)

**Villkor - Kontrollgrupp:**

![Kontrollgrupp](/help/challenges/assets/c3-j1-condition-control-group.png)

**Villkor - Kön:**\

![Villkor - Kön](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
