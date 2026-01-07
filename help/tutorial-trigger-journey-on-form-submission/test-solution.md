---
title: Testa lösningen
description: Skapa en resa för att skicka e-post när formulär skickas
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-12-25T00:00:00Z
jira: KT-20014
source-git-commit: 043f41acd8f7f7165d9ec416d8f789f78d407ca1
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# Testa lösningen


Testa lösningen
>[!VIDEO](https://video.tv.adobe.com/v/3478546)

## Distribuera exempelresurserna

Om du inte har installerat Node.js hämtar och [installerar du det härifrån](https://nodejs.org/)

Verifiera installationen genom att köra:

`node -v`

`npm -v`

## Konfigurera projektmappen

Skapa en ny katalog för exempelprogrammet med följande kommandon:

`mkdir trigger-journey `

`cd trigger-journey`

## Initiera projektet

`npm init -y`

## Installera nödvändiga ramverk

`npm install express dotenv axios cors`

## Kopiera resursfiler

* Zippa upp och placera innehållet i [project-root.zip](assets/project-root.zip) i mappen `trigger-journey`.

* Skapa en mapp med namnet `public` i mappen `trigger-journey`
* Zippa upp innehållet i [index.zip] i den gemensamma mappen
* uppdatera filen `.env` med lämpliga värden. Dessa värden är tillgängliga från kommandot cURL som laddades ned när HTTP Source-anslutningen skapades

## Kör servern

Kontrollera att du finns i katalogen `trigger-journey`.
Kör kommandot `node server.js`
Peka webbläsaren på [webbsidan](http://localhost:3000/)
Fyll i och skicka in formuläret. Resan aktiveras och ett e-postmeddelande skickas till det e-post-ID som anges i formuläret.


