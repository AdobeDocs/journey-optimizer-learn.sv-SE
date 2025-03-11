---
title: L535 värmepapp
description: Den här sidan innehåller text och länkar som används i L535 Summit Lab.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: 1c3f4341-1293-463d-bee0-57440fcff23a
source-git-commit: 204e03a06044d75963c6e2c749950e1e2dbc2a4f
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 0%

---

# Summit Lab L535- Cheat Sheet

Den här sidan innehåller text och länkar som används i L535 Summit Lab. Du kan kopiera och klistra in innehållet i dina Journey Optimizer-meddelanden.

## Länkar

* [SecurFinancial-webbplats](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U)
* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys)
* [L535-arbetsbok](/help/summit-lab-assets/assets/summit_lab_manual_L535-final-v3.pdf)
* [Hämta appen](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html)

## Kopiera och klistra in för övningar

### Träning 2.1 - Logga in på Journey Optimizer

Logga in med följande information:

E-postadress:    L535+*ditt platsnummer*@adobeeventlab.com

Lösenord:       Adobe4Summit!


### Utgång 2.3 - Skriv e-postmeddelandet

#### Fråga

```
Generate a welcome email for new SecurFinancial customers who just opened a new savings account. 
Add a call to action to install the SecurFinancial mobile app.
```

### Utgång 3.1 - Använd dynamiskt innehåll i SMS-meddelandet

#### Code

```
{%#if select _Push_details1 from profile.pushNotificationDetails where
_Push_details1.token.isNotNull()%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Open the
app
{%else%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Click here
to install the app: https://demo-systemnext.
s3.amazonaws.com/dxdemo/summit/index.html
{%/if%} 
```

### Utgång 4.2 - Konfigurera behandlingarna

#### Titel

```
Welcome to SecurFinancial
```

#### Brödtext

```
Did you know you can find an ATM near in the SecurFinancial app? Try it now!
```

#### URL

```
dxdemo://atm
```

### Övning 6 - Innehållskort

#### Titel

```
Welcome to SecurFinancial!
```

#### Brödtext

```
Thank you for downloading the app. You can find ATMs, track your spending and more. All within the app.
```

#### Media-URL

```
https://demo-system-next.s3.amazonaws.com/assets/securfinancial/home-loan.jpg
```

#### Knapptitel

```
Find ATMs
```

#### Mål-URL

```
dxdemo://atm
```

## Bilder

![SecureFinancial-logotyp](/help/summit-lab-assets/assets/SecureFinancial-logo.png)


![Mobiltelefon](/help/summit-lab-assets/assets/online-banking-app-01.png)


