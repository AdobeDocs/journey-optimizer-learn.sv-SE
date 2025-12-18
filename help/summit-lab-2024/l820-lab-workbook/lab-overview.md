---
title: Lab Workbook - L820 - Bygg personliga mobilmöten med Adobe Journey Optimizer
description: Utforska olika mobilscenarier och lär dig hur ni implementerar personaliserade upplevelser för webben och mobiler med Journey Optimizer.
feature: Overview
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
jira: KT-14977
thumbnail: KT-14977.jpeg
last-substantial-update: 2024-03-26T00:00:00Z
exl-id: e6d029f9-c936-427b-9d6e-4e296fd3c3ce
source-git-commit: 7b3d668e8400d9f86c764f5dc4c4455b50cd0cdc
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# ARBETSBOK FÖR LAB

![Adobe Summit - alt text](/help/summit-lab-2024/l820-lab-workbook/assets/adobe-summit.png "Adobe Summit")

## L820 - Bygg personaliserade mobilstunder med Adobe Journey Optimizer

I detta praktiska labb utforskar ni olika mobilscenarier och lär er hur ni implementerar personaliserade upplevelser för webben och mobiler med Journey Optimizer.


>[!IMPORTANT]
>
>Var vänlig och undvik att publicera bilder eller skärmbilder från sessionen i sociala medier.
><br>
>**Adobe-sekretess**
>Den information och de produktinformation som delas ut idag under labbet är Adobe Konfidentiella information.
>Deltagare får inte återge, använda, sprida eller lämna ut konfidentiella uppgifter till någon person eller enhet.
>Produktinformation är avsedd endast för informationsändamål, utgör inte någon garanti för framtida funktioner och kan ändras när som helst. Sådana produktfunktioner är inte på något sätt en del av ditt avtal med Adobe eller på annat sätt en del av ditt avtal.
><br>
>**Ansvarsfriskrivning**
>Adobe ger dig tidig åtkomst till funktionerna, som utnyttjar den generativa AI-tekniken. Observera att dessa funktioner fortfarande är under utveckling och kan ge oväntade eller felaktiga svar. Vi välkomnar dina synpunkter när vi lanserar den här funktionen.


### Viktiga uppgifter

* Förstå de olika mobilupplevelser som stöds.
* Konfigurera en push-kampanj.
* Lär dig hur du konfigurerar kampanjer i appen för mobiler.
* Konfigurera webb-meddelanden i programmet.
* Testa era egna personaliserade scenarier.

### Förhandskrav

* Ha koll på ditt platsnummer: Du hittar ditt platsnummer på labbdatorns skrivbord:

![Platsnummer](/help/summit-lab-2024/l820-lab-workbook/assets/locate-seat-number.png)
Du måste ha tillgång till:

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"} - inloggningsinformation ges under övningarna.
* [Fréscopa-webbplatsen](https://dsn.adobe.com/p/adobe-summit-2024?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsImlzc3VlciI6InNoYXJlZC1saW5rIiwiYXJnb24iOnsiYWNjZXNzIjoicmVhZC1wcm9qZWN0IiwicHJvamVjdElkIjoiYWRvYmUtc3VtbWl0LTIwMjQifSwiaWF0IjoxNzEwNTI0MTIwLCJleHAiOjE3MTIzMzg1MjB9.q2uGVst6HjJw8SCWl-3pViNzepkdGnNCvGqZnbbkTsY){target="_blank"}


### Förstå användningsfallet

Fréscopa, ett dynamiskt och innovativt företag, är specialiserat på att revolutionera kaffeupplevelsen genom sin unika blandning av kaffeprenumerationstjänster och en mängd olika kafferelaterade produkter som finns på deras webbplats och i mobilappen. Med sitt engagemang för att leverera enastående kvalitet och smak kan Fréscopa erbjuda kaffeentusiaster som vill ha bekvämlighet och premiumalternativ.

Kärnan i Fréscopas verksamhet ligger i deras kaffeprenumerationstjänster, som ger kunderna ett välstrukturerat urval av högkvalitativa bönor som levereras direkt till deras dörrar. Detta personaliserade tillvägagångssätt gör att kaffeälskare kan njuta av en fräsch och tilltalande upplevelse som är skräddarsydd efter deras önskemål.

Som komplement till sina prenumerationstjänster erbjuder Fréscopas webbplats och mobilapp ett omfattande utbud av kafferelaterade produkter, som gör det möjligt för kunderna att utforska och förbättra sina kafferitualer. Fréscopa är en komplett butik för kaffearbetare som vill ha kvalitet och bekvämlighet, från bryggningsutrustning till artistiska tillbehör.

Fréscopas engagemang för hög kvalitet sträcker sig bortom dess produkter, eftersom företaget är hängivet att skapa en sömlös och njutbar kundresa. Kombinationen av innovativ teknik och en kundfokuserad strategi gör att Fréscopa ligger i täten i den framväxande kaffebranschen. Fréscopa bygger i själva verket på en fusion av passion och teknologi som omdefinierar det sätt på vilket individer upplever och gillar sitt kaffe. Med fokus på kvalitet, bekvämlighet och personaliserade erbjudanden bjuder Fréscopa in kaffeentusiaster att ge sig in på en smakresa som levereras direkt till deras dörrar.
