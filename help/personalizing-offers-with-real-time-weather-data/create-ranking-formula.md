---
title: Skapa rankningsformel
description: En rankningsformel i Adobe Journey Optimizer används vid offertbeslut, särskilt inom en urvalsstrategi för att fastställa prioriteringsordningen för giltiga erbjudanden.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: d46c5a922b8448f57b8a730188284294c3caba96
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---

# Skapa rankningsformel

En rankningsformel i Adobe Journey Optimizer används vid offertbeslut, särskilt inom en urvalsstrategi för att fastställa prioriteringsordningen för giltiga erbjudanden. Rankningsformeln spelas upp efter att behörigheten filtrerats, när flera erbjudanden kvalificerar sig för en viss profil, men endast den (eller några) som ligger överst ska presenteras baserat på affärslogik eller profilsammanhang.

* Logga in på Journey Optimizer

* Beslut ->Strategisposition ->Rankningsformler ->Skapa formel

Namnge formeln _&#x200B;**Väder - relaterat - erbjudanden**&#x200B;_



Ett kriterium i en rankningsformel refererar till en villkorsregel som används för att tilldela en poäng till ett erbjudande. Dessa kriterier jämför attribut från erbjudandet och sammanhanget för att avgöra hur relevant ett erbjudande är för en viss individ.

Följande tre kriterier definieras för att filtrera erbjudanden och sedan tilldela ett rangordningsbetyg till kvalificeringserbjudandet. Kriterierna definieras med kriteriebyggaren. Kontextdata kan också användas för att definiera villkoren som visas på skärmbilden nedan
![contxt-data](assets/context-data.png)

Alla de tre villkoren använde ett offer-attribut(tagg) och ett context-datatribute(temperatur) när villkoren definierades.

## Kriterium ett

| **Erbjudandetagg** | **Kontextdatavillkor** | **Bakgrundslogik** |
|------------------|---------------------|-------------------------------------|
| **hot** | temperatur > 80 | score=Temperatur |


## Kriterium två

| **Vädertagg** | **Kontextdatavillkor** | **Bakgrundslogik** |
|------------------|---------------------------|----------------------------------------------|
| **fjäder** | temperatur > 65 och &lt; 80 | score=temperatur × 4 |

## Kriterium tre

| **Vädertagg** | **Kontextdatavillkor** | **Bakgrundslogik** |
|------------------|---------------------------|----------------------------------------------|
| **kall** | temperatur &lt; 65 | score=temperatur |
