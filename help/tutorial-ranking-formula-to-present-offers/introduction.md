---
title: Anpassa erbjudanden med rankningsformler Baserat på postnummer och intäkter
description: Använd Adobe Journey Optimizer rankningsformler för att dynamiskt leverera de mest relevanta finansiella erbjudandena - skräddarsydda efter varje användares postnummer och inkomstnivå - för högre engagemang och smartare personalisering.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-27T00:00:00Z
jira: KT-18188
exl-id: 11685f7c-8048-4318-9c28-71bd7da8f7ff
source-git-commit: 85d3def3afb1d073b133df40e4cbf32d00a3a5c9
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Anpassa erbjudanden med rankningsformler baserade på postnummer och intäkter från användare

Det här användningsexemplet visar hur ni kan leverera personaliserade ekonomiska erbjudanden genom att utnyttja användarattribut som ZIP-kod och årsintäkter inom Adobe Journey Optimizer. Genom att använda rankningsformler kan erbjudandena poängsättas och prioriteras utifrån platsspecifika kampanjer och inkomstbaserad kvalificering. Exempelvis kan CD-skivor med hög avkastning främjas för användare i välbärgade ZIP-koder, medan olika investeringsalternativ visas för nya investerare. Rankningsformler säkerställer att alla användare får erbjudanden som är både relevanta och ekonomiskt lämpliga. Rankingskriterierna definieras med hjälp av profilattribut, sammanhangsberoende signaler och valfria AI-modeller för att ytterligare förbättra beslutsprecisionen. Erbjudandena levereras i realtid via webb- eller e-postkanaler, vilket ökar engagemanget och konverteringsgraden. Detta tillvägagångssätt kombinerar affärslogik med datadriven personalisering för att höja användarupplevelsen och marknadsföringseffekten.

## Förhandskrav

Den här självstudiekursen bygger på viktiga koncept för Adobe Journey Optimizer och Adobe Experience Platform. Innan du fortsätter bör du kontrollera att följande krav är uppfyllda:

* [Självstudiekursen för identitetskorrigering](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorial-on-identity-stitching-in-aep/introduction) har slutförts, med CRM-ID:n som kopplats till ECID:n i Adobe Experience Platform.

* Bekanta dig med att skapa erbjudandeartiklar i AJO, inklusive innehållsdefinition, metadatainställningar och regler för behörighet.

* Välbekant med att konfigurera kanaler (som webb eller e-post) för leverans av erbjudanden.

* Bekanta dig med att skapa och aktivera kampanjer i AJO.

* Bekanta dig med att använda Adobe Launch (taggar) för att distribuera Web SDK och skicka händelser som innehåller identitets- och profildata.

Den här självstudiekursen handlar om nästa steg i offertbeslut:

* Skapa en rangordningsmetod med hjälp av profilattribut som postnummer och årsinkomst.

* Definiera en urvalsstrategi för att gruppera och prioritera erbjudanden.

* Bygga en beslutspolitik för att leverera det mest relevanta erbjudandet till varje enskild individ.
