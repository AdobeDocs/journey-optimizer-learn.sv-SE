---
title: Skapa ett meddelande om sommarkollektion - utmaning
description: Skicka en sommarkollektion till ett segment av befintliga kunder för att marknadsföra den nya Luma-sommarkollektionen.
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: 8e79a4e474e3b6fc7692578fb2d5920e0772d9b0
workflow-type: tm+mt
source-wordcount: '1149'
ht-degree: 0%

---

# Skapa ett meddelande om sommarkollektion - utmaning

![AJO Summer Collection Announcement Banner](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| Utmaning | Skapa ett meddelande om en sommarsamling |
|---|---|
| Persona | Resechef |
| Nödvändiga färdigheter | <ul><li>[Skapa segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [Importera och redigera e-postinnehåll från HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[Användningsfall - Lässegment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Resurser att hämta | [E-postfiler för säsongssamling](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## The Story

Luma, ett fiktivt sportklädföretag, vill marknadsföra sin senaste uppsättning kläder och utrustning och öka försäljningen för befintliga kunder. Luma lanserar den nya sommarkollektionen och vill särskilt inrikta sig på olika kundsegment.

## Din utmaning

Marknadsföringsteamet på Luma ber er att implementera en marknadsföringskampanj för sommarkollektionen i Journey Optimizer. Utmaningen är att

* Skapa ett segment som definierar vilka profiler som är kvalificerade att ta emot kampanjen.
* Bygg resan

### Steg 1: Definiera segmentet - aktiva kunder

>[!BEGINTABS]

>[!TAB Uppgift]

#### Skapa ett segment i Journey Optimizer

* Skapa ett segment i Journey Optimizer som kallas `Active Customers`.
* Segmentet får endast innehålla aktiva Luma-kunder.
* Aktiva kunder definieras som kunder som har ett skikt i Lumas lojalitetsprogram (silver, guld, platina eller diamant).


>[!TAB Godtagandevillkor]

I segmentbyggaren ser du det uppskattade antalet kvalificerade profiler. Om du arbetar med data från utbildningshandlådan har du cirka 753 kvalificerade profiler av 1,29 K.

>[!NOTE]
>Det kan ta upp till 24 timmar innan segmentmedlemskapet visas för befintliga profiler, eftersom de befintliga profilerna behöver fyllas i i baklänges.

**En kvalificeringsprofil har lagts till i segmentet:**

Du kan kontrollera vilka profiler som har lagts till i segmentet genom att navigera till en av dem i profilerna som listas i segmentets detaljvy.

På profilsidan markerar du [!UICONTROL Attribut] för att bekräfta att de är kvalificerade: Skiktet ska vara silver, guld, platina eller diamant.

![Profilattribut](assets/C1-S1-profile-attributes.png)

Du kan även kontrollera [!UICONTROL Segmentmedlemskap] tab: Segmentet bör listas.

![Segmentmedlemskap](assets/C1-S1-profile-segment-membership.png)

>[!TAB Kontrollera ditt arbete]

Segmentfält: [!UICONTROL Attribut] > [!UICONTROL XDM individuell profil] > [!UICONTROL Lojalitet] > [!UICONTROL Nivå]

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

#### Skicka ett meddelande om sommarkollektionen

En byrå försåg dig med fyra HTML-filer med design för e-postmeddelanden:

* SeasonalCollectionEmail.html
* Luma Men&#39;s Collection email
* Luma Women&#39;s Collection email
* Luma - 20 % rabatt på e-post för samling

1. [Ladda ned e-postfilerna för säsongssamlingen](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip).

2. Skapa en anropad resa `Luma - Summer collection announcement` baserat på följande riktlinjer:

   1. Skicka *Luma - Meddelande om nya sommarkollektionen* e-post till *Aktiva kunder* som håller ut 10 % av publiken som kontrollgrupp
      * Meddelanderubrik `Luma - Summer Collection Announcement`.
      * Subject line `(recipient's first name), the new Luma summer collection is here!`.
      * Använd den angivna HTML-filen *SäsongssamlingEmail.html* för e-postbrödtexten.
   2. Vänta i två dagar och skicka sedan ett uppföljningsmejl med mer riktat innehåll:
      * Manliga kunder bör få **Luma Men&#39;s Collection** e-post.
         * Meddelanderubrik: `Luma Men's Collection`
         * Ärenderad: `(recipient's first name), explore Men's New athletic gear!`
         * E-postbrödtext: *MensCollectionEmail.html* för e-postbrödtexten.
      * Kunder som är kvinnor bör få **Luma Women&#39;s Collection** e-post.
         * Meddelanderubrik: `Luma Women's Collection`
         * Ärenderad: `(recipient's first name), explore Luma's Women Collection!`
         * E-postbrödtext: *WomensCollectionEmail.html*
      * Andra kunder bör få **Luma - 20 % rabatt på samling** e-post.
         * Meddelanderubrik: `Luma - 20 % off Collection`
         * Ärenderad: `(recipient's first name), enjoy 20% off sales!`
         * E-postbrödtext: *20OffCollectionEmail.html*
   3. När du har skickat de riktade e-postmeddelandena ovan väntar du två dagar på att e-postmeddelandet ska öppnas
   4. Om målmeddelandet inte öppnas inom två dagar skickar du **Luma - 20 %rabatt på e-post för samling** som ett sista försök till återmarknadsföring


>[!TAB Godtagandevillkor]

#### Förhandsgranska e-postmeddelanden

**E-postmeddelande nr 1 - Luma - Meddelande om sommarkollektion**

Förhandsgranska e-postmeddelandet:

1. Lägg till en testprofil: Louise Petti:
   1. Identitetsnamnutrymme: *Luma CRM-ID*
   2. Identitetsvärde: *d1f132f9f9502bba047a6ec86c4b61f9*

Resultat:
* Ämnesraden ska vara: Louise, nya Luma-samlingen är här!
* E-postmeddelandetexten ska matcha det du har sett i förhandsgranskningen: [Nytt säsongsbaserat samlingsmeddelande](/help/challenges/assets/email-assets/SeasonalCollectionEmail.html)


**E-postmeddelande nr 2 - Luma Men&#39;s Collection**

Skicka ett bevis till dig själv:

1. Lägg till en testprofil: Stanleigh Stooke:
   1. Identitetsnamnutrymme: *Luma CRM-ID*
   1. Identitetsvärde: `4f34057d9d9e792c28ba18ecae378e98`
1. Välj testprofil: Stanleigh Stooke
1. Skicka ett bevis till dig själv

Resultat:\
Du bör få ett e-postmeddelande. Ämnesraden ska vara &quot;Stanleigh, explore Men&#39;s New athletic>!&quot; och e-postmeddelandetexten ska matcha det du har sett i förhandsgranskningen: [Luma Men&#39;s Collection](/help/challenges/assets/email-assets/MensCollectionEmail.html)

>[!NOTE]
>Det kan ta några minuter innan du får beviset.

**E-postmeddelande nr 3 - Luma Women&#39;s Collection**

Förhandsgranska e-postmeddelandet med testprofilen &quot;Louise Petti&quot;.

* Ämnesraden ska vara: *Louise, utforska Lumas Women Collection!*
* E-postmeddelandetexten ska matcha det du har sett i förhandsgranskningen: [Luma Women&#39;s Collection](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**E-postmeddelande nr 4 - Luma 20 % rabatt på samling**

Förhandsgranska e-postmeddelandet med testprofilen &quot;Louise Petti&quot;.

* Ämnesraden ska vara: *Louise, få 20 % rabatt!*
* E-postmeddelandetexten ska matcha det du har sett i förhandsgranskningen: [Luma 20 % rabatt på samling](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)


#### Testa din resa

>[!IMPORTANT]
>
>Innan du ställer in resan i testläge:
>
>1. Kontrollera att namnutrymmet är inställt på för Läs segment-aktiviteten **Luma CRM-id (lumaCrmId)**
>1. Åsidosätt standardparametrarna för e-post för varje e-post så att de skickas till din e-postadress:
   >    * Visa dolda värden genom att klicka på ögonsymbolen.
   >    * Klicka på T-symbolen (aktivera åsidosättning av parameter) i e-postparametrarna

      >
      >      ![Åsidosätt e-postparametrar](/help/challenges/assets/c3-override-email-paramters.jpg)
   > 
   >    * Klicka i adressfältet
   >    * På nästa skärm lägger du till din e-postadress inom parentes: `"yourname@yourdomain"` i uttrycksredigeraren och klicka på OK.

>


Testa resan och få e-postmeddelandena skickade till ditt eget konto:

1. Testa resan
2. Markera en profil åt gången
3. Väntetid: Ställ in timern på 120 sekunder (skriv in den i fältet).
4. Ingång till utlösarprofil
5. Du kan testa varje gren med något av följande *Luma CRM ID* som profilidentifierare:
   * Kvinna: Leora Dietsche, identitetsvärde:`a8f14eab3b483c2b96171b575ecd90b1`
   * Man: Stanleigh Stooke, identitetsvärde: `4f34057d9d9e792c28ba18ecae378e98`
   * Genus har inte angetts: Louise Petti, identitetsvärde: `d1f132f9f9502bba047a6ec86c4b61f9&#39;

6. När du utlöser profilentrén bör du få det första e-postmeddelandet, rubriken ska anpassas enligt den profil du väljer.
7. Resan bör fortsätta till respektive avdelning och du bör få det relaterade e-postmeddelandet (om du till exempel väljer Jenna bör du få e-postmeddelandet&quot;Luma Women&#39;s Collection&quot;).
8. Öppna det andra e-postmeddelandet så avslutas resan
9. Du kan upprepa steg 4. - 7. för alla tre profilerna för att kontrollera om alla dina grenar fungerar som de ska.
10. Om du vill testa timeout-värdena ställer du in väntetiden på 30 sekunder och utlöser inmatningen igen.
11. Öppna inte de e-postmeddelanden du får (förhandsgranska inte e-postmeddelandet (!)) och vänta lite.

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
