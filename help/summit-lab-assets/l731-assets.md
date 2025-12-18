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
source-git-commit: 55ba1a46c1473d94847e7fccc69ed2a33badb54c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---

# Summit Lab L731 - Cheat Sheet

Den här sidan innehåller text och länkar som används i L731 Summit Lab. Du kan kopiera och klistra in innehållet i dina Journey Optimizer-meddelanden.

## Utövning 1.1 - Hämta och installera appen

Skanna QR-koden för att hämta appen

>[!BEGINTABS]

>[!TAB iOS]

![QR-kod för iOS](/help/assets/lab731-ios-qr-code.png)

>[!IMPORTANT]
>
>Om du tillfrågas om inlösenkoden stänger du appen TestFlight och skannar QR-koden igen.
>
>Tillåt meddelanden.
>

Du ombeds installera Testflight, steg 1 till 4. När du har installerat Testflight följer du steg 5-8 för att installera Vegas Keep App:

<table>
<tr>
</tr>
<tr>
<td>
 <div>
      <p>
      <b>Steg 1 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-1.png"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Steg 2 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-2.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Steg 3 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-3.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Steg 4 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-4.PNG"/>
      </a>
      </div>
  </td>
  </tr>
  <tr>
<td>
 <div>
      <p>
      <b>Steg 5 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-5.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b> Steg 6 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-6.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b> Steg 7 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-7.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b> Steg 8 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-8.PNG"/>
      </a>
      </div>
  </td>
  </tr>
</table>

>[!TAB Android]

![QR-kod för Android](/help/assets/lab731-android-qr-code.png)

Eftersom appen inte är registrerad i Google Play Store får du ett varningsmeddelande:

![Android varningsskärm](/help/assets/lab731-install-android.png)

Klicka på **Installera ändå**

>[!ENDTABS]

## Utgång 1: Logga in på Adobe Journey Optimizer

[Klicka här för att logga in på Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home){target="_blank"}

**Inloggningsinformation**

* **Användarnamn:** `L731+<your seat number>@summitlab.us` (exempel: L731+001@summitlab.us)
* **Lösenord:** Adobe2023!


## Utgång 2 Skapa en kampanj i appen

| Avsnitt | Fält | Text | Länkar |
|----|----|----|----|
| **Egenskaper** | Kampanjnamn | `<your seat number> Vegas Stay Campaign` |  |
| **Utlösare** | Läge | känga |  |
| **Redigera innehåll:** Media | Alternativet Media URL |  | https://i.ibb.co/NstLhjW/Firefly-Poster-with-heading-Adobe-Max-84773.jpg |
| **Redigera innehåll:** Innehåll | Titel | Få rabatt på fåglar tidigt! |  |
| **Redigera innehåll:** Innehåll | Brödtext | Adobe Max återvänder till Las Vegas. Gör dig redo för inspirerande talare, spännande sessioner och nya kontakter. Boka din svit nu och få 10 % rabatt. |  |
| **Redigera innehåll:**-knappar | Knapp | Få 10 % rabatt! | lab://booking?suite=presidential&amp;discount=10 |
| **Redigera innehåll:**-knappar | Interaktionshändelse | CTA i appen |  |
| **Förhandsgranska på enhet** | Bas-URL som ska användas för förhandsvisning på enheten |  | **iOS:** lab:// <br>**Android**: https://lab |

## Utgång 3: Skapa ett push-meddelande

| Fält | Text | Länkar |
|----|----|----|
| Kampanjnamn | **`<your seat number> Max Push Campaign`** |  |
| Titel | Hej! |  |
| Brödtext | Visste du att Adobe Max kommer tillbaka till Vegas? Boka ditt rum nu och få 10 % rabatt. |  |
| Alternativet Media URL |  | https://i.ibb.co/1M0BnZn/Firefly-Big-conference-big-stage-with-ADBE-text-on-screen-40178.jpg |
