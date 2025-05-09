---
title: Skapa målgrupper med Web SDK
description: I den här självstudiekursen får du lära dig att samla in användarpreferenser via ett webbformulär, skicka dessa data till Adobe Experience Platform (AEP) i realtid och dynamiskt kvalificera användare för målgrupper baserat på deras val. Genom att kombinera Adobe Tags (Launch), AEP Web SDK (Alloy.js) och Edge Segmentation kan du omedelbart skapa personaliseringsmöjligheter för kunder som är intresserade av Stock, Bonds eller Certificates of Deposit (CD).
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
exl-id: ebaa3aa5-0a08-43fd-8d06-8e4b5d8dee05
source-git-commit: 163edfb3367d03729d68c9339ee2af4a0fe3a1b3
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# Skapa målgrupper med Web SDK

I den här självstudiekursen får du lära dig att samla in användarpreferenser via ett webbformulär, skicka dessa data till Adobe Experience Platform (AEP) i realtid och dynamiskt kvalificera användare för målgrupper baserat på deras val. Genom att kombinera Adobe Tags (Launch), AEP Web SDK (Alloy.js) och Edge Segmentation kan du omedelbart skapa personaliseringsmöjligheter för kunder som är intresserade av Stock, Bonds eller Certificates of Deposit (CD).

## Krav för den här självstudien

* Tillgång till Adobe Experience Platform

* Grundläggande förståelse för Adobe Experience Platform koncept (profiler, målgrupper, datauppsättningar)

* Bekanta dig med Adobe Tags (Launch) - konfigurera dataelement och regler

* Grundläggande JavaScript-kunskap (att läsa och skriva enkla funktioner)

* Möjlighet att använda DevTools för webbläsare (flikarna Konsol och Nätverk)


## MÅL

Syftet med den här självstudiekursen är att bygga upp och kvalificera tre olika målgrupper i Adobe Experience Platform (AEP):

* Kunder som är intresserade av Stock

* Kunder som är intresserade av obligationer

* Kunder som är intresserade av CD

Användarna skickar in sina preferenser via ett webbformulär, och dessa preferenser hämtas via AEP Web SDK med Adobe Launch, vilket gör det möjligt att kvalificera målgrupper i realtid.

## Använda verktyg

* Adobe Experience Platform (AEP)

* Adobe Experience Platform-taggar

* AEP Web SDK (Alloy.js)

* AEP Edge Segmentering

* En webbsida med ett inställningsformulär
