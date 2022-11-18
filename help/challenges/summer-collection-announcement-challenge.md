---
title: Skapa ett meddelande om sommarkollektion - utmaning
description: Skicka en sommarkollektion till ett segment av befintliga kunder för att marknadsföra den nya Luma-sommarkollektionen.
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
source-git-commit: d1b4aa69e323d9a6112d2273ea5770c42b044d13
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 0%

---


# Skapa ett meddelande om sommarkollektion - utmaning

![AJO Summer Collection Announcement Banner](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| Utmaning | Skapa ett meddelande om en sommarsamling |
|---|---|
| Persona | Resechef |
| Nödvändiga färdigheter | <ul><li>[Skapa segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [Importera och redigera e-postinnehåll från HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[Användningsfall - Lässegment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Resurser att hämta | [E-postfiler för säsongssamling](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

>[!NOTE]
> Utövningarna utvecklades utifrån Lumas exempeldata. Vi rekommenderar att du konfigurerar en utbildningshandlåda som är konfigurerad med exempeldata. Gå till självstudiekursen [Importera exempeldata till Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/import-sample-data.html) för detaljerade anvisningar.

## The Story

Luma, ett fiktivt sportklädföretag, vill marknadsföra sin senaste uppsättning kläder och utrustning och öka försäljningen för befintliga kunder. Luma lanserar den nya sommarkollektionen och vill särskilt inrikta sig på olika kundsegment.

## Din utmaning

Marknadsföringsteamet på Luma ber er att implementera en marknadsföringskampanj för sommarkollektionen i Journey Optimizer.

Utmaningen är att skapa en resa i Journey Optimizer. Du måste skapa det önskade segmentet, skapa fyra meddelanden och bygga kundresan.

>[!NOTE]
> Om du arbetar i en delad utbildningssandlåda är det bäst att lägga till ditt namn eller dina initialer som ett prefix till namnet på det element du skapar.

### Steg 1: Definiera segmentet - aktiva kunder

>[!BEGINTABS]

>[!TAB Uppgift]

Skapa ett segment i Journey Optimizer som kallas **ditt namn - Aktiva kunder**.

* Segmentet får endast innehålla aktiva Luma-kunder.
* Aktiva kunder definieras som kunder som har ett skikt i Lumas lojalitetsprogram (silver, guld, platina eller diamant).


>[!TAB Godtagandevillkor]

I segmentbyggaren ser du det uppskattade antalet kvalificerade profiler. Om du arbetar i en träningssandlåda som använder Luma-exempeldata kan du [!UICONTROL uppskattade kvalificerade profiler] bör vara cirka 292 profiler på 500.

**En kvalificeringsprofil har lagts till i segmentet:**

Du kan kontrollera vilka profiler som har lagts till i segmentet genom att navigera till en av dem i profilerna som listas i segmentets detaljvy.

På profilsidan markerar du [!UICONTROL Attribut] för att bekräfta att de är kvalificerade: Skiktet ska vara silver, guld, platina eller diamant.

![Profilattribut](assets/C1-S1-profile-attributes.png)

Du kan även kontrollera [!UICONTROL Segmentmedlemskap] tab: Segmentet bör listas.

>[!NOTE]
>Det kan ta upp till 24 timmar innan segmentmedlemskapet visas för befintliga profiler, eftersom de befintliga profilerna behöver fyllas i i baklänges.

![Segmentmedlemskap](assets/C1-S1-profile-segment-membership.png)

>[!TAB Kontrollera ditt arbete]

Segmentfält: [!UICONTROL Attribut] > [!UICONTROL XDM individuell profil] > [!UICONTROL Lojalitet] > [!UICONTROL Nivå]

Så här ska ditt segment se ut:

![Segment - aktiva kunder](/help/challenges/assets/C1-S1.png)

Kontrollera koden längst ned till höger på skärmen Redigera segment under Händelser.

Koden ska se ut så här:

```javascript
loyalty.tier.equals("diamond", false) or loyalty.tier.equals("gold", false) or loyalty.tier.equals("platinum", false) or loyalty.tier.equals("silver", false)
```

>[!ENDTABS]


### Steg 2: Create the Journey - Sommarsamlingsmeddelande

>[!BEGINTABS]

>[!TAB Uppgift]

Skicka ett meddelande om sommarkollektionen till ett segment av befintliga kunders e-postmeddelanden med reklam för nya Luma-sommarkollektionen.&quot;

En byrå försåg dig med fyra HTML-filer med design för e-postmeddelanden: [Ladda ned e-postfilerna för säsongssamlingen](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip)

Skapa en anropad resa `(your name) - Summer collection announcement` baserat på följande riktlinjer:

1. Skicka Luma - Ny säsongssamling Announcement-e-post till segmentet Luma-Active Customers, där 10 % av publiken hålls som en kontrollgrupp
   * Meddelanderubrik `(your name)_Luma New Seasonal Collection Announcement`.
   * Subject line `(recipient's first name), the new Luma collection is here!`.
   * Använd den angivna HTML-filen *SäsongssamlingEmail.html* för e-postbrödtexten.
2. Vänta i två dagar och skicka sedan ett uppföljningsmejl med mer riktat innehåll:
   * Manliga kunder bör få **Luma Men&#39;s Collection email**
      * Meddelanderubrik: **(ditt namn)_Luma Men&#39;s Collection**
      * Ärenderad: **(mottagarens förnamn), utforska Men&#39;s New sportkugghjulet!**
      * E-postbrödtext: *MensCollectionEmail.html* för e-postbrödtexten.
   * Kunder som är kvinnor bör få **Luma Women&#39;s Collection email**
      * Meddelanderubrik: **(ditt namn)_Luma Women&#39;s Collection**
      * Ärenderad: **(mottagarens förnamn), utforska Lumas Women Collection!**
      * E-postbrödtext: *WomensCollectionEmail.html*
   * Andra kunder bör få **Luma - 20 % rabatt på e-post för samling**
      * Meddelanderubrik: **(ditt namn)_Luma - 20 % rabatt på Collection**
      * Ärenderad:**(mottagarens förnamn), få 20 % rabatt!**
      * E-postbrödtext: *20OffCollectionEmail.html*
3. När du har skickat de riktade e-postmeddelandena ovan väntar du två dagar på att e-postmeddelandet ska öppnas
4. Om målmeddelandet inte öppnas inom två dagar skickar du **Luma - 20 %rabatt på e-post för samling** som ett sista försök till återmarknadsföring


>[!TAB Godtagandevillkor]

#### Förhandsgranska e-postmeddelanden

**E-postmeddelande nr 1 - Meddelande om ny säsongsbunden samling**

Förhandsgranska e-postmeddelandet med identitetsnamnutrymmet: *E-post* och identitetsvärdet: *Jenna_Palmer9530@emailsim.io*

* Ämnesraden ska vara: Jenna, nya Luma-samlingen är här!
* E-postmeddelandetexten ska matcha det du har sett i förhandsgranskningen: [Nytt säsongsbaserat samlingsmeddelande](/help/challenges/assets/SeasonalCollectionEmail.html)


**E-postmeddelande nr 2 - Luma Men&#39;s Collection**

Skicka ett bevis till dig själv

* Ange din e-postadress
* Välj testprofil: Chris_Scott1244@emailsim.io

Du bör få ett e-postmeddelande. Ämnesraden ska vara &quot;Chris, explore Men&#39;s New athletic kugghjulet!&quot; och e-postmeddelandetexten ska matcha det du har sett i förhandsgranskningen: [Luma Men&#39;s Collection](/help/challenges/assets/email-assets/MensCollectionEmail.html)

**E-postmeddelande nr 3 - Luma Women&#39;s Collection**

Förhandsgranska e-postmeddelandet med identitetsnamnutrymmet: *E-post* och identitetsvärdet: *Jenna_Palmer9530@emailsim.io*

* Ämnesraden ska vara: *Jenna, utforska Lumas Women Collection!*
* E-postmeddelandetexten ska matcha det du har sett i förhandsgranskningen: [Luma Women&#39;s Collection](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**E-postmeddelande nr 4 - Luma 20 % rabatt på samling**

Förhandsgranska e-postmeddelandet med identitetsnamnutrymmet: *E-post* och identitetsvärdet: *Benny_Steer4909@emailsim.io*

* Ämnesraden ska vara: *Benny, få 20 % rabatt!*
* E-postmeddelandetexten ska matcha det du har sett i förhandsgranskningen: [Luma 20 % rabatt på samling](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)

**Glöm inte att publicera dina e-postmeddelanden!**

#### Testa din resa

>[!IMPORTANT]
>
>Innan du ställer in resan i testläge:
>
>1. Kontrollera att namnutrymmet för aktiviteten Läs segment är inställt på E-post
>1. Åsidosätt standardparametrarna för e-post för varje e-post så att de skickas till din e-postadress:
>1. Visa dolda värden genom att klicka på ögonsymbolen.
>1. Klicka på T-symbolen (aktivera åsidosättning av parameter) i e-postparametrarna

   >
   >      ![Åsidosätt e-postparametrar](/help/challenges/assets/c3-override-email-paramters.jpg)
> 
>1. Klicka i adressfältet
>1. På nästa skärm lägger du till din e-postadress inom parentes: *yourname@yourdomain* i uttrycksredigeraren och klicka på OK.

>


Testa resan och få e-postmeddelandena skickade till ditt eget konto:

1. Testa resan
2. Markera en profil åt gången
3. Väntetid: Ställ in timern på 120 sekunder (skriv in den i fältet).
4. Ingång till utlösarprofil
5. Du kan testa varje gren genom att använda någon av följande e-postadresser som profilidentifierare:
   * Kvinna: Jenna Palmer: Jenna_Palmer9530@emailsim.io
   * Man: Chris Scott: Chris_Scott1244@emailsim.io
   * Genus har inte angetts: Benny Steer: Benny_Steer4909@emailsim.io

6. När du utlöser profilentrén bör du få det första e-postmeddelandet, rubriken ska anpassas enligt den profil du väljer.
7. Resan bör fortsätta till respektive avdelning och du bör få det relaterade e-postmeddelandet (om du till exempel väljer Jenna bör du få e-postmeddelandet&quot;Luma Women&#39;s Collection&quot;).
8. Öppna det andra e-postmeddelandet så avslutas resan
9. Du kan upprepa steg 4. - 7. för alla tre profilerna för att kontrollera om alla dina grenar fungerar som de ska.
10. Om du vill testa timeout-värdena ställer du in väntetiden på 30 sekunder och utlöser inmatningen igen.
11. Öppna inte de e-postmeddelanden du får (förhandsgranska inte e-postmeddelandet (!)) och vänta lite.

Du bör få följande e-postmeddelanden:

* Luma - Meddelande om ny säsongssamling
* Beroende på vilken testprofil du använde bör du få något av följande e-postmeddelanden:
   * Jenna: Luma Women&#39;s Collection
   * Chris: Luma Men&#39;s Collection
   * Benny: Luma - 20 % rabatt på samling
* Om du inte öppnade det andra e-postmeddelandet: Luma - 20 % rabatt på samlingen

>[!TAB Kontrollera ditt arbete]

Så här ska din resa se ut:

![Resa](/help/challenges/assets/c3-j1-journey.png)

**Villkor - Kontrollgrupp:**

![Kontrollgrupp](/help/challenges/assets/c3-j1-condition-control-group.png)

**Villkor - Kön:**\

![Villkor - Kön](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
