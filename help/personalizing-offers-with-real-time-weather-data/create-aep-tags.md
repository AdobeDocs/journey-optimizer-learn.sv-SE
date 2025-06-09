---
title: Skapa Adobe Experience Platform-taggar
description: Skapa AJO-målgrupper baserat på användarnas investeringsinställningar (Stocks, Bonds, CD)
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: dac6b373226bd0be2533cf859e4f250018cf568b
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Skapa AEP-taggar

Adobe Experience Platform Tags (tidigare Adobe Launch) hjälper er att hantera och driftsätta* marknadsförings- och analystekniker på er webbplats utan att behöva ändra webbplatsens kod.

I den här [videon beskrivs processen att skapa Adobe Experience Tags](https://experienceleague.adobe.com/en/playlists/experience-platform-get-started-with-tags)

* Logga in i datainsamling
* Klicka på Taggar -> Ny egenskap
* Skapa en Adobe Experience Platform-tagg med namnet _**anpassning vid väder**_.

* Lägg till följande tillägg i taggen
  ![tags-extensions](assets/tags-extensions1.png)

* Konfigurera Adobe Experience Platform Web SDK så att rätt miljö och **väderrelaterad datastream** som skapades i det tidigare steget används.
  ![web-sdk-configuration](assets/tags-extensions.png)



## Skapa och distribuera AEP-taggar


Skapa ett nytt bibliotek och lägg till alla ändrade resurser till det, vilket visas i skärmbilderna nedan.

**Lägg till bibliotek**

![new-library](assets/tag-add-library.png)

**Skapa ett bibliotek**

Ange biblioteksnamnet och miljön på skärmen Skapa bibliotek.

Lägg till alla ändrade resurser i det här biblioteket
![tag-library](assets/tag-build-library.png)

Klicka sedan på knappen Spara och bygg till utveckling för att skapa biblioteket

## Inkludera AEP-taggar på HTML-sidan

När du publicerar en AEP Tags-egenskap ger Adobe dig en script-tagg som du måste placera i din HTML ``` <head>``` eller längst ned i ``` <body>``` -taggarna.

* Gå till taggar (anpassning vid väder).

* Klicka på Miljöer och klicka på installationsikonen för den miljö du vill ha (till exempel Utveckling, Förproduktion, Produktion).

* Notera den inbäddade koden. Det behövs i ett senare skede av den här självstudiekursen.
