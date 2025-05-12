---
title: Skapa målgrupper i Adobe Journey Optimizer
description: Lär dig definiera och bygga målgrupper i AJO för att driva personaliserade kundresor och beslutsfattande i realtid
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: ba83be3caf214d2daaa8c99556d246686ff3f0cb
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Skapa målgrupper i Adobe Journey Optimizer


Målgrupper i Adobe Experience Platform är grupper med användare som skapats utifrån deras åtgärder, preferenser eller profilinformation för att leverera personaliserade upplevelser.

* Logga in på Journey Optimizer
* Navigera till Kund -> Publiker ->Skapa målgrupp
* Skapa målgrupper med metoden Skapa regel

  ![publik](assets/rule-based-audience.png)

* Skapa följande tre publiker

   * Kunder som är intresserade av lager

   * Kunder som är intresserade av obligationer

   * Kunder som är intresserade av CD


* Kontrollera att utvärderingsmetoden för varje målgrupp är inställd på _**Edge**_ för realtidskvalifikation.
  ![målgrupp](assets/audience-edge.png)

* Använd fältet PreferredFinancialInstrument för att segmentera användare baserat på deras valda investeringsintressen, till exempel aktier, obligationer eller CD

![event](assets/event-attribute.png)

![PreferredFinancialInstrument](assets/stock-customers.png)




>[!NOTE]
>
>>Om fältet PreferredFinancialInstrument inte visas på fliken Händelser klickar du på inställningsikonen och växlar till Visa hela XDM-schemat.



![toggle-full-xdm-schema](assets/show-custom-fields.png)


