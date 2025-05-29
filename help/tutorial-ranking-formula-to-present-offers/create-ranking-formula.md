---
title: Skapa rankningsformel
description: En rankningsformel i Adobe Journey Optimizer används vid offertbeslut, särskilt inom en urvalsstrategi för att fastställa prioriteringsordningen för giltiga erbjudanden.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---


# Skapa rankningsformel

En rankningsformel i Adobe Journey Optimizer används vid offertbeslut, särskilt inom en urvalsstrategi för att fastställa prioriteringsordningen för giltiga erbjudanden. Rankningsformeln spelas upp efter att behörigheten filtrerats, när flera erbjudanden kvalificerar sig för en viss profil, men endast den (eller några) som ligger överst ska presenteras baserat på affärslogik eller profilsammanhang.

* Logga in på Journey Optimizer

* Beslut ->Strategisposition ->Rankningsformler ->Skapa formel

Rankningsformel
![name_description](assets/formuala-ranking.png)

Ett kriterium i en rankningsformel refererar till en villkorsregel som används för att tilldela en poäng till ett erbjudande. Dessa kriterier jämför attribut från erbjudandet och profilen eller sammanhanget för att avgöra hur relevant ett erbjudande är för en viss individ.



Kriterium 1
![condition_one](assets/criteria1.png)

Kriterium 1 innehåller tre kriterier:

* erbjudande._techmarketingdemos.offerDetails.zipCode == &quot;92128&quot; - kontrollerar det postnummer som är associerat med erbjudandet.

* _techmarketingdemos.zipCode == &quot;92128&quot; - kontrollerar postnumret i användarens profil.

* _techmarketingdemos.annualIncome > 100000 - kontrollerar inkomstnivån från användarens profil.

Om alla dessa kriterier uppfylls får erbjudandet poäng på 40.






Kriterium 2
![condition_two](assets/criteria2.png)

Kriterium 2 innehåller tre kriterier:

* erbjudande._techmarketingdemos.offerDetails.zipCode == &quot;92126&quot; - kontrollerar det postnummer som är associerat med erbjudandet.

* _techmarketingdemos.zipCode == &quot;92126&quot; - kontrollerar postnumret i användarens profil.

* _techmarketingdemos.annualIncome &lt; 100000 - kontrollerar inkomstnivån från användarens profil.

Om alla dessa kriterier uppfylls får erbjudandet 30 poäng.




