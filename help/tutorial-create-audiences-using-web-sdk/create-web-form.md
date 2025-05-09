---
title: Skapa ett webbformulär
description: Skapa ett formulär på din HTML-sida där användarna kan välja investeringsinställningar
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 20de8dec-aac8-43ed-8305-e723f82a5dd9
source-git-commit: 163edfb3367d03729d68c9339ee2af4a0fe3a1b3
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---

# Skapa ett webbformulär

Följande HTML-formulär har skapats för att fånga upp användarinställningarna
![html-form](assets/web-form.png)

När en användare klickar på knappen på webbsidan hämtas deras valda ekonomiska inställningar (t.ex. Stock, Obligationer eller CD) och överförs till Adobe datalager. Den här händelsen (assetClassSelection) lagrar användarens val i realtid. Adobe Launch lyssnar sedan efter den här händelsen, hämtar det valda investeringsalternativet (PreferredFinancialInstrument) och kan utlösa åtgärder som att skicka data till Adobe Experience Platform (AEP) eller uppdatera personaliseringsregler

Följande JavaScript har skrivits för att hantera formuläröverföringen

```javascript
function handleSubmission() {
  window.adobeDataLayer = window.adobeDataLayer || [];

  const selectedAssetClass = document.querySelector('input[name="assetclass"]:checked');
  const errorMessage = document.getElementById("error-message");
  const messageBox = document.getElementById("message");

  if (!selectedAssetClass) {
    errorMessage.textContent = "Please select a financial instrument.";
    messageBox.textContent = "";
    return;
  }

  errorMessage.textContent = "";

  const subscriptionEvent = {
    event: "assetClassSelection",
    xdm: {
      eventType: "assetClassSelection",
      eventID: "investment_preference_event",
      timestamp: new Date().toISOString(),
      FinancialInterest: {
        PreferredFinancialInstrument: selectedAssetClass.value
      }
    }
  };

  console.log("📩 Sending asset class data to AEP:", subscriptionEvent);
  window.adobeDataLayer.push(subscriptionEvent);

  // ✅ Show thank-you message
  messageBox.textContent = `Thank you for selecting "${selectedAssetClass.value}". We'll use this to personalize your experience.`;
}
```

[Exempelformuläret för HTML ingår i denna självstudiekurs](assets/webform.zip)
