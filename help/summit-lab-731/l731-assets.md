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
source-git-commit: 6580652b9c28d51c03944362a0fb848a0a8194e2
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 2%

---

# Summit Lab L731 - Cheat Sheet

Den här sidan innehåller text och länkar som används i L731 Summit Lab. Du kan kopiera och klistra in innehållet i dina Journey Optimizer-meddelanden.

## Utgång 1.1 - Hämta och installera appen

Skanna QR-koden för att hämta appen

>[!BEGINTABS]

>[!TAB iOS]

![QR-kod för iOS](/help/assets/lab731-ios-qr-code.png)

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
      <b>Steg 6 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-6.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>Steg 7 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-7.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>Steg 8 </b>
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

![Android-varningsskärm](/help/assets/lab731-install-android.png)

Klicka **Installera ändå**

>[!ENDTABS]

## Utövning 1: Logga in på Adobe Journey Optimizer

[Klicka här för att logga in på Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**Inloggningsinformation:**

* **Användarnamn:** `L731+<your seat number>@summitlab.us` (exempel: L731+001@summitlab.us)
* **Lösenord:** Adobe2023!


## Utgång 2 Skapa en kampanj i appen

| Fält | Text | Länkar |
|----|----|----|
| Kampanjnamn | `<your seat number> Vegas Stay Campaign` |  |
| Matcher | känga |  |
| Alternativet Media URL |  | https://experienceleague.adobe.com/docs/journey-optimizer-learn/assets/adobemax.jpg |
| Titel | Få rabatt på fåglar tidigt! |  |
| Brödtext | Adobe Max återvänder till Las Vegas. Gör dig redo för inspirerande talare, spännande sessioner och nya kontakter. Boka din svit nu och få 10 % rabatt. |  |
| Knapp | Boka nu | lab://booking?suite=presidential&amp;discount=10 |
| Knapp: Interaktiv händelse | CTA i appen |  |
| Bas-URL som ska användas för förhandsvisning på enheten |  | **iOS:** lab:// <br>**Android**: https://lab |


## Utövning 3: Skapa ett push-meddelande

| Fält | Text | Länkar |
|----|----|----|
| Kampanjnamn | `<your seat number> Max Push Campaign` |  |
| Alternativet Media URL |  | https://experienceleague.adobe.com/docs/journey-optimizer-learn/assets/adobemax.jpg |
| Titel | Hej! |  |
| Brödtext | Visste du att Adobe Max kommer tillbaka till Vegas? Boka ditt rum nu och få 10 % rabatt. |  |
