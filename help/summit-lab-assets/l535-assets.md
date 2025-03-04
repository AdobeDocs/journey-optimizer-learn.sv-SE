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
source-git-commit: 51ab40981a42b0df56d3994f1155eb4ae7575b17
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 0%

---

# Summit Lab L535- Cheat Sheet

Den här sidan innehåller text och länkar som används i L535 Summit Lab. Du kan kopiera och klistra in innehållet i dina Journey Optimizer-meddelanden.

## Länkar

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys)
* [SecurFinancial-webbplats](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U)
* [Hämta appen](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html)

## Utövningar

### Utövning 2.3

**Steg 12** Meddelande:

Generera ett välkomstmeddelande för nya SecurFinancial
kunder som just öppnat ett nytt sparkonto. Lägg till en
anrop till åtgärd för att installera mobilappen SecurFinancial.

### Utövning 3.1

**Steg 7**

```javascript
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


![SecureFinancial-logotyp](/help/summit-lab-assets/assets/SecureFinancial-logo.png)

![Mobiltelefon](/help/summit-lab-assets/assets/online-banking-app-01.png)


