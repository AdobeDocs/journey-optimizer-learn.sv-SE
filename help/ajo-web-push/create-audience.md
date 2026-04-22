---
title: Skapa publik
description: Definiera ett segment i Adobe Experience Platform som riktar sig till användare som är berättigade att ta emot push-meddelanden.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---

# Skapa publik

Om du vill skapa en målgrupp för kampanjen definierar du ett segment i Adobe Experience Platform som riktar sig till användare som är berättigade att ta emot push-meddelanden. I den här självstudien har användare som har en aktiv push-prenumeration (Push Token finns) inte avanmält sig från meddelanden (Blockeringslista Flag är false) och är associerade med den angivna programkonfigurationen (Application Identifier är lika med `my-first-push`). De här användarna är fullt berättigade att få webbaserade push-meddelanden via kampanjer eller resor i Adobe Journey Optimizer. När målgruppen har skapats kontrollerar du att den har utvärderats så att profilerna är ifyllda och klara för målinriktning.
Den här målgruppen används sedan i kampanjen för att leverera schemalagda push-meddelanden till enbart prenumererade användare.

![skapa-målgrupp](assets/push-audience.png)

