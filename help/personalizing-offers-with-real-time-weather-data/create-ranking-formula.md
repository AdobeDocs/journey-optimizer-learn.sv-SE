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
source-git-commit: c04a15418e31dc82597b7759386907013728bb0d
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# Skapa rankningsformel

En rankningsformel i Adobe Journey Optimizer används vid offertbeslut, särskilt inom en urvalsstrategi för att fastställa prioriteringsordningen för giltiga erbjudanden. Rankningsformeln spelas upp efter att behörigheten filtrerats, när flera erbjudanden kvalificerar sig för en viss profil, men endast den (eller några) som ligger överst ska presenteras baserat på affärslogik eller profilsammanhang.

* Logga in på Journey Optimizer

* Navigera till _**Beslutsfattare ->Strategi ->Rankningsformler ->Skapa formel**_

Namnge formeln _**Väder - relaterat - erbjudanden**_



Ett kriterium i en rankningsformel refererar till en villkorsregel som används för att tilldela en poäng till ett erbjudande. Dessa kriterier jämför attribut från erbjudandet och sammanhanget för att avgöra hur relevant ett erbjudande är för en viss individ.

Följande tre kriterier definieras för att filtrera erbjudanden och sedan tilldela ett rangordningsbetyg till kvalificeringserbjudandet. Kriterierna definieras med kriteriebyggaren. Kontextdata kan också användas för att definiera villkoren som visas på skärmbilden nedan
![contxt-data](assets/context-data.png)

Alla tre kriterierna använde ett offer-attribut(tagg) och ett context-datatribute(temperatur) när villkoren definierades.

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
