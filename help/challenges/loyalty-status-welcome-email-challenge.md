---
title: Skapa ett välkomstmeddelande om lojalitetsstatus - Problem
description: Bygg en resa som automatiskt skickar ett välkomstmeddelande till kunderna när de når lojalitetsnivån.
jira: KT-8109
feature: Journeys
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---

# Skapa ett välkomstmeddelande om lojalitetsstatus - Problem

| Utmaning | Skapa ett välkomstmeddelande om lojalitetsstatus |
|---|---|
| Persona | Resechef |
| Nödvändiga färdigheter | <ul><li>[Skapa segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html)</li> <li>[Segmentkvalificering](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journeys/use-case-read-segment-qualification.html)</li><li>[Importera HTML-innehåll](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html)</li></ul> |
| Assets att ladda ned | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

{style="table-layout:auto"}

## Artikeln

Luma erbjuder ett lojalitetsprogram som ett sätt att attrahera och behålla sina kunder. Programmet har fyra olika nivåer: Bronze, Silver, Guld och Platinum. Varje lojalitetsnivå får olika belöningar, rabatter och andra specialincitament som belöning för sin återkommande verksamhet.

För att understryka platinastatusen vill Luma skicka ett välkomstmeddelande till kunder när de når platinagruppen.

## Utmaningen

Du har ombetts att konfigurera en resa som automatiskt skickar ett välkomstmeddelande till kunder när de når platinans lojalitetsnivå.

>[!BEGINTABS]

>[!TAB Uppgift]

När en lojalitetskund kvalificerar sig för platinagruppen bör de få ett e-postmeddelande där de kan gratulera och informera om sina nya fördelar. Det kreativa teamet har tillhandahållit en HTML-fil **[Luma - statusuppgradering - välkomstmeddelande](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** med e-postbrödtexten.

1. Skapa ett [!UICONTROL segment] i Journey Optimizer med namnet `Luma - platinum status`.

1. Skapa en resa med namnet `Luma - New Status - platinum`.

   1. En kund tar sig in på resan när de kvalificerar sig för platinans lojalitetsnivå.

   1. Kunden bör få ett e-postmeddelande med etiketten `Luma - Platinum Status - Welcome`, med ämnesraden `Welcome to Platinum Status, {firstName}!`, och e-posttexten som tillhandahålls av det kreativa teamet. Det här är ett [!UICONTROL transaktionsmeddelande].

   1. När du överför HTML-filen ser du att e-postmeddelandet hänvisar till&quot;diamantstatus&quot; i stället för&quot;platina&quot;. I stället för att begära en ny fil från det kreativa teamet uppdaterar du e-postmeddelandet i [!UICONTROL e-postmeddelandet för Designer].

>[!TAB Slutförandevillkor]

Testa din resa:

1. Kontrollera att [!UICONTROL Läs segmentaktiviteten] har [!UICONTROL namespace] inställt på **[!DNL Luma CRM id(lumaCrmId)]**.

1. Åsidosätt standardparametrarna för [!UICONTROL e-post] och ange den som din egen e-postadress:
   * Klicka på T-symbolen i **[!UICONTROL e-postparametrarna]** (aktivera åsidosättning av parameter)

   * Klicka på fältet **[!UICONTROL Adress]**.

   * På nästa skärm lägger du till din e-postadress inom parentes: `"yourname@yourdomain"` i uttrycksredigeraren och klickar sedan på **[!UICONTROL OK]**.

1. Ställ in resan till testläge.

1. Välj **[!UICONTROL Utlös en händelse]**.

1. Lägg till följande `CRM ID` för `Stanleigh Stooke` i fältet **[!UICONTROL Profilidentifierare]**: `4f34057d9d9e792c28ba18ecae378e98`

**Resultat:** Du bör få det anpassade *Luma - platinumstatus - välkomstmeddelandet*.

Så här ska e-postmeddelandet se ut:

![Luma - statusuppgradering - välkomstmeddelande](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB Kontrollera ditt arbete]

Så här ska segmentet se ut:

![Luma - platinumstatus- segment](/help/challenges/assets/segment-luma-platinum-status.png)

Så här ska din resa se ut:

![platinum-status-upgrade-travel](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
