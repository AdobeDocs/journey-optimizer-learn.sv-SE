---
title: Skapa ett välkomstmeddelande om lojalitetsstatus - Problem
description: Förstå grunderna för att skapa en resa på researbetsytan.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: e9553da0fd85ee6e48d3089a93d51a994635de81
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 2%

---

# Skapa ett välkomstmeddelande om lojalitetsstatus - Problem

![Förmånsstatus, välkomstmeddelande - Challenge Banner](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Utmaning | Skapa ett välkomstmeddelande om lojalitetsstatus |
|---|---|
| Persona | Resechef |
| Nödvändiga färdigheter | <ul><li>[Skapa segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html)</li> <li>[Segmentkvalificering](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html)</li><li>[Importera HTML-innehåll](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html)</li></ul> |
| Resurser att hämta | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

{style=&quot;table-layout:auto&quot;}

## The story

Luma erbjuder ett lojalitetsprogram som ett sätt att attrahera och behålla sina kunder. Programmet har fyra olika nivåer: Brons, silver, guld och platina. Varje lojalitetsnivå får olika belöningar, rabatter och andra specialincitament som belöning för sin återkommande verksamhet.

För att understryka platinastatusen vill Luma skicka ett välkomstmeddelande till kunder när de når platinagruppen.

## Utmaningen

Du har ombetts att konfigurera en resa som automatiskt skickar ett välkomstmeddelande till kunder när de når platinans lojalitetsnivå.

>[!BEGINTABS]

>[!TAB Uppgift]

När en lojalitetskund kvalificerar sig för platinagruppen bör de få ett e-postmeddelande där de kan gratulera och informera om sina nya fördelar. Det kreativa teamet har tagit fram en HTML-fil **[Luma - statusuppgradering - välkomstmeddelande](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** med e-postbrödtexten.

1. Skapa en [!UICONTROL segment] i Journey Optimizer `Luma - platinum status`.

1. Skapa en anropad resa `Luma - New Status - platinum`.

   1. En kund tar sig in på resan när de kvalificerar sig för platinans lojalitetsnivå.

   1. Kunden bör få ett e-postmeddelande med etiketten `Luma - Platinum Status - Welcome`, med ämnesraden `Welcome to Platinum Status, {firstName}!` med e-postmeddelandetexten från det kreativa teamet. Det här är en [!UICONTROL transaktionsbaserad] e-post.

   1. När du överför filen HTML lägger du märke till att e-postmeddelandet hänvisar till diamantstatus, i stället för till platina. Uppdatera e-postmeddelandet i stället för att begära en ny fil från det kreativa teamet [!UICONTROL E-postdesigner].

>[!TAB Villkor för lyckade]

Testa din resa:

1. Se till att [!UICONTROL Läs segmentaktivitet] har [!UICONTROL namespace] ange till **[!DNL Luma CRM id(lumaCrmId)]**.

1. Åsidosätt standardinställningen [!UICONTROL e-postparametrar] och ange din egen e-postadress:
   * I **[!UICONTROL E-postparametrar]** klickar du på T-symbolen (aktivera åsidosättning av parameter)

   * Klicka på **[!UICONTROL Adress]** fält.

   * Lägg till din e-postadress inom parentes på nästa skärm: `"yourname@yourdomain"` i uttrycksredigeraren klickar du på **[!UICONTROL OK]**.

1. Ställ in resan till testläge.

1. Välj **[!UICONTROL Utlös en händelse]**.

1. Lägg till följande `CRM ID` for `Stanleigh Stooke` i **[!UICONTROL Profilidentifierare]** fält: `4f34057d9d9e792c28ba18ecae378e98`

**Resultat:** Du bör få den personaliserade *Luma - platinumstatus - Välkommen* e-post.

Så här ska e-postmeddelandet se ut:

![Luma - statusuppgradering - välkomstmeddelande](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB Kontrollera ditt arbete]

Så här ska segmentet se ut:

![Luma - platinumstatus - segment](/help/challenges/assets/segment-luma-platinum-status.png)

Så här ska din resa se ut:

![platinum-status-upgrade-travel](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
