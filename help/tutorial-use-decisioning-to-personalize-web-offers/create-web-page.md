---
title: Skapa en webbsida för att testa lösningen
description: webbsida för att testa personaliserade erbjudanden som levereras genom beslut.
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-05T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: 72a67137-303d-4dfe-9b70-322c81e5fb27
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Skapa en webbsida för att testa lösningen

Den här webbsidan skapades för att testa personaliserade erbjudanden som levereras via Adobe Journey Optimizer Decisioning. Den ger en kontrollerad miljö där sendEvent-anropet kan utlösas och det returnerade erbjudandeinnehållet återges, vilket hjälper till att validera konfigurationen av hela personaliseringen och säkerställa att besluten fungerar som förväntat.

Följande skript ansvarar för att hämta och visa ett personaliserat erbjudande på en webbsida med Adobe Journey Optimizer.

1. Avkoda HTML-enheter:

   Det finns en hjälpfunktion som på ett säkert sätt konverterar specialtecken i erbjudandeinnehållet till läsbara HTML.

1. Kör personalisering:

   När det anropas skickas en begäran (`sendEvent`) till Adobe Web SDK för att få anpassat innehåll för ett visst område på sidan (elementet `#ajo-offer`).

   Om ett erbjudande returneras avkodas HTML och infogas på sidan.

   Om inget returneras loggas en varning.

1. Vänta på SDK:

   Eftersom Adobe SDK (legering) läses in asynkront väntar skriptet tills det är helt inläst innan begäran görs.

   Den kontrollerar om det finns legeringar var 200:e millisekund, upp till 20 gånger, för att undvika fel.

1. Vid sidinläsning:

   När sidan har lästs in startas processen genom att `waitForAlloy()` anropas.



```javascript
< script >
    function decodeHtmlEntities(html) {
        const txt = document.createElement("textarea");
        txt.innerHTML = html;
        return txt.value;
    }


function runPersonalization() {
    console.log("🚀 Sending personalization request to AJO...");
    alloy("sendEvent", {
        renderDecisions: true,
        personalization: {
            surfaces: ["#ajo-offer"]
        }
    }).then(result => {
        console.log("🔍 Web SDK decision response:", result);

        const decision = result.propositions?.[0];
        const html = decision?.items?.[0]?.data?.content;

        const container = document.getElementById("ajo-offer");
        if (html && container) {
            const decodedHtml = decodeHtmlEntities(html);
            console.log("✅ Offer HTML content (decoded):", decodedHtml);
            container.innerHTML = decodedHtml;
        } else {
            console.warn("⚠️ No personalized offer returned.");
        }


    }).catch(error => {
        console.error("❌ sendEvent failed:", error);
    });
}

function waitForAlloy(callback, retries = 20) {
    if (typeof alloy === "function") {
        callback();
    } else if (retries > 0) {
        console.log("⌛ Waiting for Alloy...");
        setTimeout(() => waitForAlloy(callback, retries - 1), 200);
    } else {
        console.error("❌ alloy is not loaded after waiting.");
    }
}

// Trigger initial personalization on page load
document.addEventListener("DOMContentLoaded", function() {
    waitForAlloy(() => runPersonalization());
}); <
/script>
```

[Här kan du hämta exempelsidan för HTML och relaterade resurser](assets/web-page-assets.zip)
