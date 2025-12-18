---
title: Navet för mobilt lärande
description: Kom igång snabbt eller lyft upp er strategi för mobilengagemang med Adobe Journey Optimizer. Det här mobilutbildningscentret ger utvecklare, administratörer, marknadsförare och analytiker allt de behöver för att konfigurera inkommande och utgående mobilkanaler och integrera dem smidigt i kraftfulla flerkanalskampanjer och -resor. Utforska bästa praxis, lär dig hur ni kan få till stånd fler implementeringar och skapa centraliserade arbetsflöden för rapportering - allt på ett och samma ställe - för att leverera slagkraftiga, datadrivna mobilupplevelser som når kunderna när som helst, var som helst.
feature: Overview
role: User, Admin, Developer
hide: false
index: true
last-substantial-update: 2025-12-18T00:00:00Z
exl-id: f0612a1d-f919-4b67-9e33-a9fb623062dc
source-git-commit: eab42c39d0e7b105ef36e2e2337539511f91440d
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 0%

---

# Journey Optimizer - Mobile Learning Hub

Kom igång snabbt eller lyft upp er strategi för mobilengagemang med Adobe Journey Optimizer. Det här mobilutbildningscentret ger utvecklare, administratörer, marknadsförare och analytiker allt de behöver för att konfigurera inkommande och utgående mobilkanaler och integrera dem smidigt i kraftfulla flerkanalskampanjer och -resor.

Utforska bästa praxis, lär dig hur ni kan få till stånd fler implementeringar och skapa centraliserade arbetsflöden för rapportering - allt på ett och samma ställe - för att leverera slagkraftiga, datadrivna mobilupplevelser som når kunderna när som helst, var som helst.

>[!VIDEO](https://video.tv.adobe.com/v/3476998?quality=12&learn=on){transcript=true}


## Översikt över mobilkanalen

Journey Optimizer har stöd för både inkommande och utgående mobilkanaler:

### Utgående kanaler

Med utgående kanaler kan ni aktivt leverera meddelanden till kunder utan att föregående interaktion krävs. Dessa interaktioner är idealiska för kampanjer, kampanjer och transaktionshändelser.

Alla utgående kanaler i Adobe Journey Optimizer tillämpar regler för anpassat samtycke vid meddelandets sändningstid. Om samtycke inte beviljas för en viss marknadsföringsåtgärd ignoreras meddelandet automatiskt för att säkerställa korrekt leverans.

| ![Push-meddelanden](/help/mobile-learning-hub/assets/mobile-phone.webp){width=&quot;250&quot;, height=&quot;250&quot;}<br> **[Push-meddelanden](/help/mobile-learning-hub/channels/push-notifications-overview.md)** | ![SMS/MMS/RCS](/help/mobile-learning-hub/assets/SMS.png){width=&quot;250&quot;, height=&quot;250&quot;}<br> **[SMS/MMS/RCS](/help/mobile-learning-hub/channels/sms-mms-rcs-overview.md)** | ![WhatsApp](/help/mobile-learning-hub/assets/whatsapp.webp){width=&quot;250&quot;, height=&quot;250&quot;}<br> **[WhatsApp](/help/mobile-learning-hub/channels/whatsapp-overview.md)** |
|-------------------------------------|------------------------------------|-------------------------------|
| Skickat utanför appen och push-meddelanden fångar genast uppmärksamhet. De är idealiska för tidskänsliga uppdateringar och uppmuntrar användarna att återvända till appen. | Direktmeddelanden skickas till användarnas mobiltelefoner utan att appen behövs. Perfekt för brådskande aviseringar, påminnelser och multimediematerial som bilder och videor. | Konversationskanal via en allmänt använd meddelandeapp som möjliggör personaliserad tvåvägskommunikation och interaktiva kampanjer. |

### Inkommande kanaler

Inkommande kanaler stöder kundinitierade interaktioner, vilket gör att ni kan leverera personaliserade upplevelser så fort användarna interagerar med ert varumärke. De möjliggör personalisering i realtid och datainhämtning - t.ex. landningssidor eller beteenden på plats - som matas in direkt i Adobe Experience Platform (AEP) för segmentering, målinriktning och aktivering över resorna.


| ![Meddelanden i appen](/help/mobile-learning-hub/assets/frescopa-in-app.png){width=&quot;250&quot;,height=&quot;50%&quot;}<br> **[Meddelanden i appen](/help/mobile-learning-hub/channels/in-app-messages-overview.md)** | ![Innehållskort](/help/mobile-learning-hub/assets/content-card.jpeg){width=&quot;250&quot;, height=&quot;250&quot;}<br> **[Innehållskort](/help/mobile-learning-hub/channels/content-cards-overview.md)** | ![Kodbaserad upplevelse](/help/mobile-learning-hub/assets/code-based.png){width=&quot;250&quot;, height=&quot;250&quot;}<br> **[Kodbaserad upplevelse](/help/mobile-learning-hub/channels/code-based-experience-overview.md)** |
|-------------------------------------|------------------------------------|-------------------------------|
| Meddelandena levereras i realtid och är interaktiva medan användarna aktivt använder er app. De är perfekta för att engagera kunderna just nu. | Icke-påträngande, beständiga meddelanden som användare har tillgång till när som helst i appen. Innehållskort fungerar bra för att dela aktuella erbjudanden eller användbar information. | Anpassade kodmeddelanden möjliggör personaliserade och dynamiska kampanjer som integrerar realtidsdata och komplexa kundresor. |


### Hur kan mobilkanaler fungera tillsammans?

Genom att kombinera dessa kanaler kan ni skapa en smidig och effektiv kundupplevelse:

1. Använd [push-meddelanden](/help/mobile-learning-hub/channels/push-notifications-overview.md) om du snabbt vill få uppmärksamhet och återföra användare till din app (t.ex.&quot;Försäljningen börjar nu!&quot;).

2. Leverera [meddelanden i appen](/help/mobile-learning-hub/channels/in-app-messages-overview.md) med personaliserade kampanjer (t.ex.&quot;Här är din rabatt på 15 % för dagens försäljning&quot;).

3. Erbjud [innehållskort](/help/mobile-learning-hub/channels/content-cards-overview.md) så att användare kan gå tillbaka till erbjudandet när som helst innan det upphör (t.ex.&quot;Din rabatt på 15 % upphör på fredag&quot;).

4. Använd [SMS/MMS/RCS](/help/mobile-learning-hub/channels/sms-mms-rcs-overview.md) för att skicka påminnelser eller multimediaerbjudanden direkt till användare som inte finns i appen.

5. Engagera kunderna i meningsfulla konversationer med [WhatsApp](/help/mobile-learning-hub/channels/whatsapp-overview.md), idealiskt för kundsupport eller interaktiva kampanjer.

6. Använd [kodbaserade upplevelser](/help/mobile-learning-hub/channels/code-based-experience-overview.md) för att skräddarsy alla meddelanden baserat på användarbeteenden och önskemål och skapa en verkligt personaliserad resa över alla kanaler.

## Bygg din grund

Lär dig begreppen och hur du

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="configure-and-launch.md"><img src="./assets/configure-message.jpg"></a>
    <div><strong>Konfigurera och starta</strong><br/>Konfigurera mobilkanalerna och integrera med mobilappar.</div>
    </td>
    <td>
    <a href="design-and-deliver.md"><img src="./assets/create-message.webp"></a>
    <div><strong>Designa och leverera</strong><br/>Använd mobilkanaler för att skapa personaliserade resor och kampanjer som engagerar kunderna i realtid.</div>
    </td>
    <td>
    <a href="measure-and-optimize.md"><img src="./assets/reports.webp"></a>
    <div><strong>Mät och optimera</strong><br/>Få tillgång till rapporter, analysera prestanda och förfina strategier för bättre resultat.
    </div>
    </td>
  </tr>
</table>

## Vanliga användningsfall för mobilt företag

| Användningsfall | Beskrivning | Användning av mobilkanal |
|---------|-------------|----------------------|
| **App Onboarding och Adobe** | Hjälper nya användare genom de inledande faserna av appinteraktionen - installera programmet, slutföra installationen och upptäcka viktiga funktioner. Målet är att maximera kundlojaliteten och den långsiktiga användningen. | - Push-meddelanden och SMS-välkomstanvändare och snabb profilkomplettering.<br> - Meddelanden i appen sätter fokus på funktioner och uppmuntrar till första åtgärder.<br> - Djupa länkar i e-postmeddelanden eller annonser dirigerar användare till specifika appskärmar för smidig introduktion. |
| **Platsbaserat engagemang** | Levererar personaliserade meddelanden i rätt tid till användarna baserat på deras fysiska närhet till butiker, händelser eller andra relevanta platser. | - Geo-fencing och beacon-teknik utlöser push-meddelanden när användare går in i målzoner.<br>- SMS/MMS levererar lokaliserade erbjudanden och uppdateringar.<br> - Banderoller och kort i appen anpassar innehåll baserat på plats i realtid. |
| **Återkoppling av övergivna** | Rikta in er på användare som överger kundvagnar, formulär eller surfsessioner i syfte att få dem tillbaka och slutföra den tänkta åtgärden. | - Push-meddelanden påminner användarna om övergivna varukorgar eller ofullständiga åtgärder.<br>- SMS-uppföljning innehåller incitament eller direktlänkar att återuppta.<br> - Frågorna visas i appen när användarna kommer tillbaka och ger personliga rekommendationer. |
| **Kampanjer för merförsäljning och korsförsäljning** | Flyttar ut ytterligare produkter eller uppgraderingar till befintliga kunder baserat på deras beteenden, önskemål eller inköpshistorik. | - Push-meddelanden framhäver relevanta merförsäljningsmöjligheter.<br> - Meddelanden i appen och innehållskort visar kompletterande objekt.<br>- SMS-kampanjer riktar in sig på segmenterade målgrupper med exklusiva erbjudanden. |
| **Kurnförebyggande** | Identifierar användare som riskerar att lämna företaget och engagerar dem med personaliserade strategier för lojalitet. | - Prediktiv analys utlöser mobilt arbete för riskanvändare.<br> - Push-meddelanden och SMS erbjuder lojalitetsbelöningar eller personaliserat innehåll.<br> - I undersökningar i appen samlas feedback in för att förbättra strategier för kundlojalitet. |
| **Flerkanalsmeddelanden** | Samordna enhetliga meddelanden över flera mobila kanaler för att säkerställa att användarna får aktuell och relevant kommunikation. | - Push, in-app, SMS och e-post koordineras för enhetliga meddelanden.<br> - SDK:er möjliggör personalisering i realtid i alla kanaler.<br> - Innehållskort finns kvar mellan sessioner för att förstärka viktiga meddelanden. |

## Användningsexempel

* [Flyg med personalisering: Hur flygbolag kan höja sina erbjudanden med Adobe Journey Optimizer (blogg)](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/take-flight-with-personalization-how-airlines-can-elevate-offers/ba-p/767513)
