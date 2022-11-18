---
title: Skapa ett välkomstmeddelande om lojalitetsstatus - Problem
description: Förstå grunderna för att skapa en resa på arbetsytan.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
source-git-commit: 957515149af1281d29a45b24ca499ef097656eb8
workflow-type: tm+mt
source-wordcount: '365'
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

### Skapa ett Luma Diamond-statussegment.

Skapa ett segment i Journey Optimizer som kallas **ditt namn - Luma - diamantstatus**.

### Skapa Luma - ny status - romb - e-postmeddelande för transaktioner

Skapa ett välkomstmeddelande

1. Skapa ett transaktionsmejl med namnet `(your name)_Luma – New Status – Diamond – Transactional email message`.
2. Ge e-postmeddelandet en ämnesrad `Welcome to Diamond Status, (recipient's first name)!`.
3. Använd den angivna HTML-filen **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** för e-postbrödtexten.


### **Resa nr 3 - uppgradering av diamantstatus, välkomstmeddelande**

Skicka ett e-postmeddelande när en lojalitetskund flyttar till en ny nivå för att gratulera och informera dem om deras nya fördelar.

1. Skapa en resa som utlöses när en kund flyttar sig till den nya lojalitetsnivån i Diamond (särskilt när kunden går in i det segment som definierats för en ny medlem på diamantnivå) för att skicka e-postmeddelandet&quot;Luma - New Status - Diamond - Transactional&quot;
2. När du är klar sätter du resan i testläge och utlöser resan för att skicka den till dig själv  

FRAMSTÄLLNINGSKRITERIER

Du bör få det anpassade e-postmeddelandet&quot;Luma - New Status - Diamond-Transactional&quot;.
