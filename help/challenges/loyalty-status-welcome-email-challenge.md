---
title: Skapa ett välkomstmeddelande om lojalitetsstatus - Problem
description: Förstå grunderna för att skapa en resa på arbetsytan.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: bcd4e8f01ebb83444934d641d3ee3aafe420bd6b
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# Skapa ett välkomstmeddelande om lojalitetsstatus - Problem

![AJO Loyalty status welcome email - Challenge Banner](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Utmaning | Skapa ett välkomstmeddelande om lojalitetsstatus |
|---|---|
| Persona | Resechef |
| Nödvändiga färdigheter | <ul><li>[Skapa e-postinnehåll med meddelanderedigeraren](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[Använd sammanhangsbaserad händelseinformation för personalisering](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[Använd hjälpfunktioner för personalisering](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| Resurser att hämta | [Orderbekräftelsetillgångar](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## The Story

Luma erbjuder ett lojalitetsprogram som ett sätt att attrahera och behålla sina kunder. Programmet har fyra olika nivåer: Silver, guld, platina och diamant.

Varje lojalitetsnivå får olika nivåer eller belöningar, rabatter och andra specialincitament som belöning för sin återkommande verksamhet.

Om du vill stryka under den särskilda diamantstatusen. Luma vill skicka ett välkomstmeddelande till kunderna när de når diamantnivån.

## Din utmaning

Du har fått i uppdrag att skapa en resa som automatiskt skickar ett välkomstmeddelande till kunderna när de når diamantlojalitetsnivån.

>[!NOTE]
> Om du arbetar i en delad utbildningssandlåda är det bäst att lägga till ditt namn eller dina initialer som en prefix till namnet på det element du skapar.

>[!BEGINTABS]

>[!TAB Uppgift]

Skicka ett e-postmeddelande när en lojalitetskund flyttar till diamantskiktet för att gratulera och informera dem om deras nya fördelar. The

1. Skapa ett segment i Journey Optimizer som kallas **Luma - diamantstatus**
2. Skapa en resa som utlöses när en kund flyttar sig till den nya lojalitetsnivån i Diamond (särskilt när kunden går in i det segment som definierats för en ny medlem på diamantnivå) för att skicka e-postmeddelandet&quot;Luma - New Status - Diamond - Transactional&quot;
   1. Skapa ett transaktionsmejl med namnet `(your name)_Luma – New Status – Diamond – Transactional email message`.
   2. Ge e-postmeddelandet en ämnesrad `Welcome to Diamond Status, (recipient's first name)!`.
   3. Använd den angivna HTML-filen **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** för e-postbrödtexten.
3. När du är klar sätter du resan i testläge och utlöser resan för att skicka den till dig själv  

   1. Skapa ett transaktionsmejl med namnet `(your name)_Luma – New Status – Diamond – Transactional email message`.
   1. Ge e-postmeddelandet en ämnesrad `Welcome to Diamond Status, (recipient's first name)!`.
   1. Använd den angivna HTML-filen **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** för e-postbrödtexten.
4. När du är klar sätter du resan i testläge och utlöser resan för att skicka den till dig själv  

### Skapa Luma - ny status - romb - e-postmeddelande för transaktioner

Skapa ett välkomstmeddelande

### **Resa nr 3 - uppgradering av diamantstatus, välkomstmeddelande**


>[!TAB Villkor för lyckade]

Testa din resa:

1. Kontrollera att segmentkvalificeringshändelsen har namnutrymmet = E-post
1. Åsidosätt standardparametrarna för e-post och ange den som din egen e-postadress
1. Ställ in resan till testläge
1. Utlös en händelse
1. Lägg till följande e-postadress i fältet Profilidentifierare: Jenna_Palmer9530@emailsim.io

Du bör få det anpassade e-postmeddelandet&quot;Luma - New Status - Diamond-Transactional&quot;.

>[!TAB Kontrollera ditt arbete]

Så här ska din resa se ut:

![Diamond-status-upgrade-travel](/help/challenges/assets/journey-luma-diamond-status-upgrade.png)

>[!ENDTABS]
