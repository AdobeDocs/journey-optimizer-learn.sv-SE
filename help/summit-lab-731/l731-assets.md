---
title: L731 värmepapp
description: Den här sidan innehåller text och länkar som används i L731 Summit Lab.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
source-git-commit: c0b7fa47fac1ad16121d0f568de358c83de44a90
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---

# Summit Lab L731 - Cheat Sheet

Den här sidan innehåller text och länkar som används i L731 Summit Lab. Du kan kopiera och klistra in innehållet i dina Journey Optimizer-meddelanden.

## Utgång 1.1 - Hämta och installera appen

Skanna QR-koden för att hämta appen

>[!BEGINTABS]

>[!TAB iOS]

![QR-kod för iOS](/help/assets/lab731-ios-qr-code.png)

>[!TAB Android]

![QR-kod för Android](/help/assets/lab731-android-qr-code.png)

>[!ENDTABS]

## Utövning 1.3: Logga in på Adobe Journey Optimizer

[Klicka här för att logga in på Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**Inloggningsinformation:**

* **Användarnamn:** `L731+<your seat number>@summitlab.us` (exempel: L731+001@summitlab.us)
* **Lösenord:** Adobe2023!


## Exercise 2.1 Skapa en kampanj i appen

| Fält | Text | Länkar |
|----|----|----|
| Kampanjnamn | `<your seat number> March Vegas Campaign` |  |
| Matcher | känga |  |
| Alternativet Media URL |  | https://mcfadyen.com/wp-content/uploads/2023/01/Adobe-Summit-2023-Banner.png |
| Titel | Det är Händelse och det är Live! |  |
| Brödtext | Adobe Summit återvänder till Las Vegas 21-23 mars 2023. Gör dig redo för inspirerande talare, spännande sessioner och nya kontakter. |  |
| Knapp | Boka hotell nu och spara 10 % | lab://booking?suite=presidential&amp;discount=10 |
| Knapp: Interaktiv händelse | CTA i appen |  |
| Bas-URL |  | iOS: lab:// <br>Android: https://lab |


## Lektion 3 Skapa en flerkanalig resa

>[!BEGINTABS]

>[!TAB Push-meddelande]

**Titel:**\
Välkommen till Vegas!

**Brödtext:**\
Hoppa över raden och checka in med mobilappen

**Deeplink:** lab://checkin

**Media:**

https://experienceleague.adobe.com/docs/journey-optimizer-learn/assets/vegas_online_check_in.jpg?lang=en


Det här är bilden som vi använder för push-meddelanden:

![Incheckning online](/help/assets/vegas_online_check_in.jpg)

>[!TAB SMS-meddelande]

**Meddelande:**
Välkommen till Vegas. Hoppa över raden och checka in med mobilappen: lab://checkin

>[!TAB E-postmeddelande]

**Ämnesrad:**
{{profile.person.name.firstName}}, du är incheckad, kolla in våra erbjudanden för din vistelse!

>[!ENDTABS]