---
title: Utlösa Adobe Journey Optimizer Journey med Adobe Web SDK
description: Lär dig hur du påbörjar en Adobe Journey Optimizer-resa från sajthändelser som användarinloggningar genom att utnyttja AEP Web SDK som konfigurerats via Adobe Experience Platform Tags
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-09-24T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-19287
source-git-commit: c9d62ef509d557b2dfa49c698580df7c4942d299
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Utlösa Adobe Journey Optimizer Journey med Adobe Web SDK

I den här utökningen av självstudiekursen om identitetskorrigering utlöses en Adobe Journey Optimizer-resa som skickar e-post till den inloggade användaren med hjälp av deras sammanslagna profil. **I den här artikeln förutsätts det att du känner till e-postkanalen och skapar innehåll för e-postkanalen.**

## Skapa konfiguration av e-postkanal

* Logga in på _**Journey Optimizer**_
* Navigera till _**Administration -> Kanaler -> Skapa kanalkonfiguration**_
* Välj **E-post** i kanallistan. Ange ett beskrivande namn och en beskrivning.
* Fyll i e-postinställningarna.
* Ange körningsinformation enligt nedan. E-postadressen skickas till profilens e-postadress som lagras i fältet
* ![e-postkanal](assets/email-channel-execution.png)
* Aktivera e-postkanalskonfigurationen

## Skapa händelse

* Logga in på _**Journey Optimizer**_
* Navigera till _**Administration -> Konfigurationer**_
* Klicka på knappen Hantera på händelsekortet och klicka på Skapa händelse. Ange värdena enligt nedan
* ![progress-event](assets/journey-event.png)

* Kontrollera om händelsens eventType är lika med UserLoggedIn. I det här fallet är händelsenamnet och händelsetypen desamma för enkelhetens skull.`in(@event{event1.eventType}, ['UserLoggedIn'])`
* Spara händelsen

## Skapa resa

* Logga in på _**Journey Optimizer**_
* Navigera till _**Resehantering -> Resor -> Skapa resa**_
* Dra och släpp _**UserLoggedIn**_ -händelsen på arbetsytan
* Dra och släpp e-post från åtgärdsmenyn. Konfigurera e-poståtgärden så att den använder e-postkanalkonfigurationen som skapades tidigare
* Publicera resan

## Hur resan utlöses

Resan aktiveras när händelsenyttolasten som skickas via Web SDK matchar det som är konfigurerat under resan. I det här exemplet är händelsetypen **UserLoggedIn**



