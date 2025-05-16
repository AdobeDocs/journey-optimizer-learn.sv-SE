---
title: Skapa exempelprogrammet för att efterlikna inloggningsaktiviteten
description: Skapa ett exempel på ett Node.js-program för att simulera ett inloggningsflöde
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---


# Skapa exempelprogrammet för att efterlikna inloggningsaktiviteten

Det här exempelprogrammet, som har skapats och distribuerats på en Node.js-server, visar hur du skickar ett CRM-ID till Adobe Experience Platform (AEP) när en användare loggar in. Programmet simulerar ett inloggningsflöde där inloggningsuppgifterna valideras på serversidan. När inloggningen är klar hämtas användarens CRM-ID och skickas till adobeDataLayer, vilket aktiverar en motsvarande regel i Adobe Experience Platform Tags (tidigare Adobe Launch).

Funktionen attachLoginHandler kopplar en skicka-händelseavlyssnare till ett inloggningsformulär. När formuläret skickas förhindras standardåtgärden, inloggningsuppgifterna valideras mot en fördefinierad användares objekt och CRM-ID hämtas om det är giltigt. Funktionen överför en användarinloggad händelse med CRM-ID:t och autentiseringstillståndet till adobeDataLayer, och Adobe Experience Platform Tags hämtar den för att skicka data till Adobe Experience Platform (AEP).


```javascript
function attachLoginHandler() {
    const form = document.getElementById("loginForm");
    if (!form) return;

    form.addEventListener("submit", function(e) {
        e.preventDefault();
        const username = document.getElementById("username").value;
        const password = document.getElementById("password").value;

        if (users[username] && users[username].password === password) {
            const crmid = users[username].crmid;
            window.adobeDataLayer = window.adobeDataLayer || [];
            debugger;
            window.adobeDataLayer.push({
                event: "userloggedin",
                user: {
                    crmid: crmid,
                    authenticatedState: "authenticated"
                }
            });
        }
    });
}
```

Skriptet för Adobe Experience Platform-taggar inkluderas i HTML sidas `<head>`-avsnitt med en `<script>` -tagg, vanligtvis så här:

`<script src="https://assets.adobedtm.com/b5eu4857867/4e4d84957/launch-b69e276bb9b5-development.min.js" async crossorigin="anonymous"></script>`

Skriptet AEP Tags hämtades genom att en egenskap med Web SDK-funktioner som skapades i det tidigare steget publicerades och inbäddningskoden kopierades från fliken Miljöer.


