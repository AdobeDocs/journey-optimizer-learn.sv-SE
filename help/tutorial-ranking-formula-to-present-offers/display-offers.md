---
title: Skapa en webbsida för att testa lösningen
description: webbsida för att testa personaliserade erbjudanden som levereras genom beslut.
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-31T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---


# Skapa en webbsida för att testa lösningen

Det här exempelprogrammet simulerar ett verkligt inloggningsflöde där inloggningsuppgifterna valideras på serversidan innan CRM-ID skickas till Adobe Experience Platform (AEP). En lokal Node.js-server används för att på ett säkert sätt hantera webbsidorna, hantera grundläggande autentiseringslogik och undvika webbläsarbegränsningar (som blockerad lokal filåtkomst eller saknade CORS-huvuden) som kan störa Adobe Launch eller Web SDK-funktioner. Med den här konfigurationen säkerställs att upplevelsen är närmare en riktig produktionsmiljö.

Personaliserade erbjudanden visas endast efter att användaren har loggat in, och då slutförs identitetssammanfogningen mellan användarens CRM ID och ECID (Experience Cloud ID). Med hjälp av den här identitetssammanfogningen kan Adobe Journey Optimizer (AJO) känna igen profilen och returnera riktade erbjudanden.

När inloggningen är klar skickas en personaliseringsbegäran till AJO för att hämta tillgängliga erbjudanden för användaren. Erbjudandena returneras som HTML-fragment, där vart och ett är inbäddat med ett data-tags-attribut - som data-tags=&quot;ajo offer-Semester-based-cd zip-92128 revenue-high&quot; - som innehåller erbjudandenamn och segmenteringsinformation som postnummer och inkomstnivå.

JavaScript tolkar sedan dessa HTML-block och kapslar in dem i en karusellobjektsbehållare. Objekten ordnas vågrätt i ett karusellspår, vilket möjliggör snabb navigering. Med knapparna Föregående och Nästa (◀ och ▶) kan användare bläddra igenom de anpassade erbjudandena en åt gången.

Den här konfigurationen ger en responsiv och skräddarsydd upplevelse som säkerställer att varje användare ser erbjudanden som är relevanta för deras ekonomiska profil - först efter att deras identitet har sammanfogats på ett säkert sätt på olika plattformar.

## Testa den här lösningen

* Skapa en mapp med namnet ranking-formula i ditt befintliga Node.js-projekt.

* Zippa upp de [tillhandahållna filerna i den här rankningsformelmappen.](assets/ranking-formula.zip)

* Kör programmet genom att gå till mappen och starta servern:
   * `cd ranking-formula`

   * `node server.js`


* Öppna webbläsaren och gå till http://localhost:3000/formula.html.

* Logga in med alias/pass123

Eftersom Alice bor i 92128-postkoden visas erbjudanden som är anpassade till den platsen.