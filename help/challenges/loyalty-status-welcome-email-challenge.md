---
title: Skapa ett välkomstmeddelande om lojalitetsstatus - Problem
description: Förstå grunderna för att skapa en resa på arbetsytan.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: cc9d123e4b8efd82eea348c31f5b993556438074
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Skapa ett välkomstmeddelande om lojalitetsstatus - Problem

![Förmånsstatus, välkomstmeddelande - Challenge Banner](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Utmaning | Skapa ett välkomstmeddelande om lojalitetsstatus |
|---|---|
| Persona | Resechef |
| Nödvändiga färdigheter | <ul><li>[Skapa segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html)</li> <li>[Segmentkvalificering](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html)</li><li>[Importera HTML-innehåll](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html)</li></ul> |
| Resurser att hämta | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

## The Story

Luma erbjuder ett lojalitetsprogram som ett sätt att attrahera och behålla sina kunder. Programmet har fyra olika nivåer: Brons, silver, guld och platina. Varje lojalitetsnivå får olika belöningar, rabatter och andra specialincitament som belöning för sin återkommande verksamhet.

Stryk under platinastatusen. Luma vill skicka ett välkomstmeddelande till kunderna när de når platinagruppen.

## Din utmaning

Du har ombetts att konfigurera en resa som automatiskt skickar ett välkomstmeddelande till kunder när de når platinans lojalitetsnivå.

>[!BEGINTABS]

>[!TAB Uppgift]

När en lojalitetskund kvalificerar sig för platinagruppen bör de få och e-posta för att gratulera och informera dem om sina nya fördelar. Det kreativa teamet har tagit fram en HTML-fil **[Luma - statusuppgradering - välkomstmeddelande](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** med e-postbrödtexten.

1. Skapa en [!UICONTROL segment] i Journey Optimizer `Luma – status upgrade`.
2. Skapa en anropad resa `Luma – New Status – platinum`.
   1. En kund tar sig in på resan när de kvalificerar sig för platinans lojalitetsnivå.
   2. Kunden bör få ett e-postmeddelande med etiketten `Luma – Platinum Status - Welcome`, med ämnesraden `Welcome to Platinum Status, (recipient's first name)!` med e-postmeddelandetexten från det kreativa teamet. Det här är en [!UICONTROL transaktionsbaserad] e-post.
   3. När du överför filen HTML lägger du märke till att e-postmeddelandet hänvisar till diamantstatus, i stället för till platina. Uppdatera e-postmeddelandet i e-postdesignern i stället för att begära en ny fil från det kreativa teamet.

>[!TAB Villkor för lyckade]

Testa din resa:

1. Se till att [!UICONTROL Läs segmentaktivitet] har [!UICONTROL namespace] ange till **[!DNL Luma CRM id(lumaCrmId)]**
2. Åsidosätt standardinställningen [!UICONTROL e-postparametrar] och ange din egen e-postadress
   * Visa dolda värden genom att klicka på ögonsymbolen.
   * I [!UICONTROL E-postparametrar]klickar du på T-symbolen (aktivera åsidosättning av parameter)

       ![Åsidosätt e-postparametrar](/help/challenges/assets/c3-override-email-paramters.jpg)
   
   * Klicka på [!UICONTROL Adressfält]
   * På nästa skärm lägger du till din e-postadress inom parentes: `"yourname@yourdomain"` i uttrycksredigeraren och klicka på OK.


3. Ställ in resan till testläge
4. Utlös en händelse
5. Lägg till följande [!DNL CRM ID] for [!DNL Stanleigh Stooke] till [!UICONTROL Profilidentifierare] fält: `4f34057d9d9e792c28ba18ecae378e98`

**Resultat:** Du bör få den personaliserade *Luma - platinumstatus - Välkommen* e-post.

>[!TAB Kontrollera ditt arbete]

Så här ska din resa se ut:

![platinum-status-upgrade-travel](/help/challenges/assets/journey-luma-status-upgrade.png)


Så här ska e-postmeddelandet se ut:

![Luma - statusuppgradering - välkomstmeddelande](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
