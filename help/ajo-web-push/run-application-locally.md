---
title: Kör programmet lokalt
description: Konfigurera exempelprogrammet lokalt för att utforska flödet av push-meddelanden på webben med AJO.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 2635641b-5ae2-4303-bac7-02c3702950f0
source-git-commit: c339fe796af1e691cd3b1c98cd6ba8a8772551e4
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Kör programmet lokalt

På den här sidan får du hjälp med att konfigurera exempelprogrammet lokalt så att du kan testa och utforska flödet för push-meddelanden på webben med Adobe Journey Optimizer. Du klonar databasen, konfigurerar systemvariabler och kör programmet på ditt lokala system.


Följ de här stegen för att köra exempelprogrammet på din lokala dator.

## &#x200B;1. Installera Node.js

Kontrollera att **Node.js (version 16 eller senare)** är installerat på datorn.

Du kan [hämta den här:](https://nodejs.org/)

Verifiera installationen

```node -v```

```npm -v```


## &#x200B;2. Klona databasen

```git clone https://github.com/gbedekar489/ajo-web-push.git```

```cd ajo-web-push```

## &#x200B;3. Installera beroenden

```npm install```

## &#x200B;4. Konfigurera miljövariabler

Skapa en .env-fil i rotkatalogen och lägg till följande:

```
DATASTREAM_ID=your_datastream_id
ORG_ID=your_org_id
VAPID_PUBLIC_KEY=your_vapid_public_key
APP_ID=your_app_id
DATASET_ID=your_event_dataset_id
PORT=3000
```


När du kör lokalt läses dessa värden från .env-filen. I produktion (t.ex. Återgivning) konfigureras de som miljövariabler.
