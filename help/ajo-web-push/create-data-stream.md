---
title: Skapa dataström
description: På den här sidan får du hjälp med att skapa en datastam i Adobe Experience Platform som behövs för att samla in data från Web SDK och skicka dem till AEP och Adobe Journey Optimizer. Datastream fungerar som en anslutning mellan ditt webbprogram och Adobes tjänster, vilket gör att push-prenumerationer och händelsedata kan bearbetas.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# Skapa dataström

En datastream i Adobe Experience Platform (AEP) fungerar som slutpunkt för data som skickas från Web SDK. Data dirigeras till konfigurerade tjänster som AEP, Adobe Analytics eller Adobe Journey Optimizer. I den här självstudiekursen används datastream för att skicka web push-prenumerationsdata och price.drop-händelser till AEP för aktivering.

## Skapa händelseschema för att spåra push-meddelanden

Skapa ett nytt XDM ExperienceEvent-schema med namnet `SchemaForPushNotification`. Lägg till fältgrupperna `Push Notification Tracking` och `Commerce Details` i schemat. Fälten i fältgruppen Commerce Details används för att samla in produktinformation och utlösa händelsen price.drop.

![event-schema](assets/event-schema.png)

## Skapa profilschema för att spara användarens samtycke

I den här självstudiekursen använder vi `AJO Push Profile Schema` som är färdig. Det här schemat lagrar användarens push-prenumerationsinformation, inklusive den push-token som krävs för att leverera push-meddelanden på webben.

![profile_schema](assets/profile-schema.png)

## Skapa datauppsättningar för schemat

Skapa en datauppsättning med namnet `DataSetForPushNotification` med händelseschemat som skapades tidigare. För profildata använder du den körklara `AJO Push Profile Dataset` som är kopplad till push-profilschemat. Anteckna `DataSetForPushNotification`-ID:t, vilket krävs senare i självstudiekursen när du konfigurerar programmet via .env-filen.

## Skapa dataström med hjälp av händelse- och profildatauppsättningen

Skapa en ny datastam med namnet WebPushDataStream med hjälp av händelse- och profildatamängder som skapades i föregående steg. Anteckna ditt dataström-ID, eftersom det kommer att behövas senare i självstudiekursen när du konfigurerar programmet via .env-filen.

![datastream](assets/datastream.png)
