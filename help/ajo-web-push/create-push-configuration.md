---
title: Skapa push-kanal
description: Push-kanalskonfigurationen definierar hur push-meddelanden på webben levereras, inklusive programinställningar och plattformsspecifik information. Den länkar även din push-konfiguration till de nödvändiga inloggningsuppgifterna, som VAPID-nycklarna, så att AJO kan skicka meddelanden till prenumererade användare.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Skapa push-kanal

Det första steget är att skapa en push-kanal i Adobe Journey Optimizer. Som en del av den här konfigurationen måste du generera VAPID-nycklar, som krävs för att autentisera och aktivera push-meddelanden på webben. Dessa nycklar används sedan i push-kanalkonfigurationen, vilket gör att AJO säkert kan skicka meddelanden till prenumererade användare.

## Generera VAPID-nycklar

VAPID (Voluntary Application Server Identification) är en web push-standard som gör att servern kan identifiera sig för push-tjänster (som Chrome, Edge osv.) med publika/privata nyckelpar, så att push-providern vet vem som skickar meddelandet.

Den genereras med ett verktyg som web-push generate-vapid-keys, som skapar en offentlig nyckel (som delas med webbläsaren) och en privat nyckel (som finns på servern) som används tillsammans för att autentisera och skicka push-meddelanden på ett säkert sätt.

I den här självstudiekursen har vi använt Node.js för att generera VAPID-nycklarna.

Kontrollera att du har installerat Node.js. Skicka sedan följande kommando
```npm install web-push -g ```

![web-push](assets/install-web-push.png)

```web-push generate-vapid-keys```

![vapid](assets/vapid-keys.png)

## Skapa push-autentiseringsuppgifter

* Logga in på Journey Optimizer

* Navigera till Administration | Kanaler | PUSH SETTINGS | Push Credentials| Skapa push-autentiseringsuppgifter

* ![push-autentiseringsuppgifter](assets/push-credential.png)

## Skapa kanalkonfiguration

* Logga in på Journey Optimizer

* Navigera till Administration | Kanaler | Skapa kanalkonfiguration
  ![channel-configuration](assets/push-channel.png)
