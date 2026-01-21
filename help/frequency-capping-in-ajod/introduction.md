---
title: Implementera frekvensbegränsning för Adobe Journey Optimizer (AJO) Erbjudanden via AJO Decisioning
description: Den här självstudiekursen utökar en befintlig implementering av Adobe Journey Optimizer (AJO) genom att aktivera frekvensbegränsning för erbjudanden som hanteras med AJO Decisioning. Här beskrivs hur man fångar in intrycks- och interaktionshändelser som används vid frekvensbegränsning.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# Implementera frekvensbegränsning för Adobe Journey Optimizer (AJO) Erbjudanden via AJO Decisioning

Den här självstudiekursen visar hur man använder frekvensbegränsning för erbjudanden i Adobe Journey Optimizer för att styra hur ofta användare ser samma erbjudande över tiden.

Genom att fånga in decisioning.propositionDisplay- och decisioning.propositionInteract-händelser via Adobe Web SDK och mappa dem till XDM-scheman i Adobe Experience Platform (AEP), kan Adobe Journey Optimizer noggrant spåra offertvisningar och interaktioner, vilket gör det möjligt att begränsa hur ofta ett erbjudande visas för en användare.

## Krav för den här självstudien

Innan du fortsätter måste du se till att du har en giltig Adobe Journey Optimizer-kampanj med hjälp av Decisioning som aktivt visar erbjudanden på en webbsida.

I den här självstudiekursen antas att erbjudandeleveransen redan fungerar och att fokus enbart ligger på att konfigurera och validera beteendet för frekvensbegränsning.


