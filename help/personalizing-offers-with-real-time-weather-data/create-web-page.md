---
title: Testa lösningen
description: Skapa en enkel webbsida för att testa kontextuell personalisering av erbjudanden med hjälp av temperaturdata i realtid.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: a9fc14da78e1c67b01aef5dcdd417ce02d36d50a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---

# Testa lösningen

En webbsida är byggd för att testa kontextuell personalisering av erbjudanden med hjälp av temperaturdata i realtid. När en användare besöker sidan uppmanas han/hon att ange platsåtkomst. Vid godkännande hämtar sidan aktuella väderdetaljer, som temperatur, tillstånd och ort, via API:t OpenWeatherMap. Sammanhangsberoende data visas för användaren och skickas till Adobe Experience Platform med Adobe Web SDK (Alloy).

Anropet sendEvent har konfigurerats med renderDecision: false, vilket innebär att erbjudanden som returneras av Adobe Journey Optimizer hanteras manuellt. Skriptet behandlar beslutssvaret, avkodar innehållet och infogar dynamiskt det mest relevanta erbjudandet i en angiven behållare (#offerContainer).

## Vad JavaScript gör

JavaScript hämtar dynamiskt väderinformation utifrån användarens plats och använder Adobe Experience Platform (AEP) för att leverera personaliserade erbjudanden. Här följer en beskrivning av stegen:

1. **Väntar på att allokering ska läsas in**

   Skriptet ser till att Adobe Web SDK (Alloy) är fullständigt inläst innan du gör några personaliseringsbegäranden.

2. **Hämtar användarens plats**

   Det använder webbläsarens Geolocation-API för att hämta användarens aktuella latitud och longitud.

3. **Hämtar väderdata**

   API:t OpenWeatherMap anropas för att få aktuell väderinformation:

   Temperatur (i °F)

   Vädervillkor (till exempel &quot;Regn&quot;, &quot;Rensa&quot;)

   Ortsnamn

   Luftfuktighet

4. **Visa väderinformation på webbsidan**

   Uppdaterar DOM med ett meddelande som:

   &quot;Aktuell temperatur i San Diego är 72°F med klar himmel.&quot;

5. **Skickar väderkontext till AEP**

   Använder alloy(&quot;sendEvent&quot;) för att skicka sammanhangsberoende väderdata till AEP

   ```javascript
   xdm: {
   eventType: "decisioning.request",
   _techmarketingdemos: {
   temperature: temp,
   weatherConditions: condition,
   cityName: city
     }
   }
   ```

6. **Hämtar och återger erbjudanden**

   Tar emot erbjudanden från AJO.

   Avkodar HTML-innehåll.

   Lägg in erbjudandena i <div id="offerContainer"> -element.

7. **Exempel på Assets**

   Den webbsida som används för att testa lösningen är tillgänglig för hämtning

[Webbsida](assets/weather-offers.html)

[JavaScript code](assets/weather-related-offers-script.js)

