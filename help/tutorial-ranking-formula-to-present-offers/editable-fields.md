---
title: Använda redigerbara formulärfält i AJO kodbaserade upplevelser
description: Lär dig hur du skapar redigerbara innehållsblock med hjälp av interna formulärfält i Adobe Journey Optimizer kodbaserade upplevelsemallar som ger marknadsförarna möjlighet att använda dynamiskt, återanvändbart kampanjinnehåll.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-22T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18416
source-git-commit: b9feb65fb7af8fb495f81841ab9235e4ae80ecd7
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# Använda redigerbara formulärfält i AJO kodbaserade upplevelser

På många marknadsföringsresor, särskilt inom reglerade branscher, är det viktigt att ta med en ansvarsfriskrivning som kan variera beroende på kampanj, geografi eller produkt. Genom att använda ett [redigerbart fält](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences) direkt i AJO Personalization Editor kan marknadsförare och jurister behålla fullständig kontroll över ansvarsfriskrivningstexten utan att behöva ta hjälp av utvecklare eller ändra beslutslogiken.

Detta möjliggör snabba uppdateringar och säkerställer att kampanjer är kompatibla, samtidigt som ni utnyttjar beslutat innehåll som erbjudanden.

## Infoga redigerbart fält i personaliseringsredigeraren

- Öppna kampanjen som skapades i det tidigare steget.
- Klicka på _**Ändra kampanj**_
- Navigera till fliken _**Innehåll**_
- Klicka på _**Redigera kod**_ och infoga ett redigerbart fält med namnet legalDisclaimer med ett standardvärde med följande syntax i personaliseringsredigeraren

- 
  <pre> {{#inline "legalDisclaimer" name="Legal Disclaimer"}} Friskrivningsklausul finns här {{/inline}}  </pre>

- Använd <code>{{{legalDisclaimer}}}</code> variabel i mallen enligt nedan

- ![redigerbara fält](assets/editable-fields.png)

- Marknadsförare kan enkelt redigera fältet för juridisk ansvarsfriskrivning utan att behöva öppna personaliseringsredigeraren.
- ![editable-field-marketer](assets/editable-field-marketer-view.png)



## Publicera kampanjen

Aktivera kampanjen för att börja leverera personaliserade erbjudanden i realtid.

