---
title: Testa lösningen
description: Skapa en enkel webbsida för att fånga upp intrycket och klicka på händelserna i erbjudandena.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18526
exl-id: 6b6c66d3-218d-4f5b-adb0-a2eca05989ab
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 0%

---

# Testa lösningen

## Distribuera exempelresurserna

Om du inte har installerat Node.js hämtar och [installerar du det härifrån](https://nodejs.org/)

Verifiera installationen genom att köra:

`node -v`

`npm -v`

## Konfigurera projektmappen

Skapa en ny katalog för exempelprogrammet med följande kommandon:

`mkdir frequency-capping `

`cd frequency-capping `

## Initiera projektet

`npm init -y`

## Installera nödvändiga ramverk

`npm install express`

## Kopiera resursfiler

* Zippa upp och placera innehållet i [server.zip](assets/server.zip) i mappen `frequency-capping`.
* Extrahera innehållet i [public.zip](assets/public.zip) till mappen &#39;frequency-capping&#39;

## Uppdatera yt-URL:en i javascript-filen

Öppna `frequency-capping.js` som finns i `public\scripts` och uppdatera ytegenskapen så att den matchar kanalkonfigurationen som används i kampanjen

## Start node js server

Navigera till mappen `c:\frequency-capping`. Kör kommandot `node server.js` om du vill starta nodens js-server på port 3000


## Uppdatera egenskapen Adobe Experience Platform Tags

Öppna filen `frequency-capping.html` som finns i mappen `public` i textredigeraren och ersätt script-taggen med den script-tagg för Adobe Experience Platform Tag-egenskapen som skapades i det tidigare steget i den här självstudien. Spara filen

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## Interagera med erbjudandena

* Öppna [webbsidan](http://localhost:3000) i webbläsaren.
* Interagera med erbjudandet
* Uppdatera sidan
* Beroende på reglerna för frekvensbegränsning bör du se ett nytt erbjudande

## Visa rapporten

* Logga in på Journey Optimizer
* Navigera till Resehantering ->Kampanjer
* Klicka på kampanjen och välj sedan lämplig rapport på rapportmenyn.
