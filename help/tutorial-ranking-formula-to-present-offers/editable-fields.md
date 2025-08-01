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
exl-id: 0ba695d6-becb-440d-b0d0-de5b51b42562
source-git-commit: 65d91d4fb0e978e62e5d95bf40355dcb8d27efb9
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# Använda redigerbara formulärfält i AJO kodbaserade upplevelser

På många marknadsföringsresor, särskilt inom reglerade branscher, är det viktigt att ta med en ansvarsfriskrivning som kan variera beroende på kampanj, geografi eller produkt. Genom att använda ett [redigerbart fält](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences) direkt i AJO Personalization Editor kan marknadsförare och jurister behålla fullständig kontroll över ansvarsfriskrivningstexten utan att behöva ta hjälp av utvecklare eller ändra beslutslogiken.

Detta möjliggör snabba uppdateringar och säkerställer att kampanjer är kompatibla, samtidigt som ni utnyttjar beslutat innehåll som erbjudanden.

## Infoga redigerbart fält i personaliseringsredigeraren

- Öppna kampanjen som skapades i det tidigare steget.
- Klicka på _&#x200B;**Ändra kampanj**&#x200B;_
- Navigera till fliken _&#x200B;**Innehåll**&#x200B;_
- Klicka på _&#x200B;**Redigera kod**&#x200B;_ och infoga ett redigerbart fält med namnet legalDisclaimer med ett standardvärde med följande syntax i personaliseringsredigeraren

- `{{#inline "legalDisclaimer" name="Legal Disclaimer"}} Legal Disclaimer will go here {{/inline}}`

- Använd variabeln `{{{legalDisclaimer}}}` i mallen enligt nedan

- ![redigerbara fält](assets/editable-fields.png)

- Marknadsförare kan enkelt redigera fältet för juridisk ansvarsfriskrivning utan att behöva öppna personaliseringsredigeraren.
- ![editable-field-marketer](assets/editable-field-marketer-view.png)



## Publicera kampanjen

Aktivera kampanjen för att börja leverera personaliserade erbjudanden i realtid.
