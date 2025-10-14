---
title: Importera CRM-exempeldata till datauppsättningen för AEP-profiler
description: Importera exempelposter (t.ex. med CRMID, e-post, inkomst, postnummer) för att validera om AEP kan sammanfoga dessa profiler med anonyma webbesökare baserat på delade identifierare som ECID.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 33c8c386-f417-45a8-83cf-7312d415b47a
source-git-commit: 667f146639635515a5572e9ace41d83ab4452bb8
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 3%

---

# Importera CRM-exempeldata till datauppsättningen för AEP-profiler

Importera CRM-profildata till en datauppsättning som är kopplad till ett profilaktiverat schema i Adobe Experience Platform för att börja matcha identiteter

## Skapa ett anpassat namnutrymme

* Navigera till Customer -> Identities -> Create identity namespace
* Välj Individuellt ID för olika enheter och ange visningsnamnet och identitetssymbolen så som visas på skärmbilden nedan.
  ![custom-namespace](assets/custom-namespace.png)

## Skapa ett profilaktiverat schema

Skapa ett enskilt profilschema med namnet **_FinWiseProfileSchema_**. Inkludera fält, till exempel annualIncome, email, firstName, lastName och loyaltyStatus.
Lägg till ett identitetsfält **_crmid_** som det visas. Markera det skarpa fältet som identitet och primär.


![profile-schema](assets/finwise-profile-schema.png)

## Förbered exempeldata

Uppdatera de falska e-postadresserna till riktiga. Dessa används senare när du skickar meddelanden med Adobe Journey Optimizer.

|   | crmId | firstName | lastName | e-post | loyaltyStatus | zipCode | annualIncome |
|---|--------|-----------|----------|-------------------------|---------------|---------|--------------|
|   | FIN001 | Alice | Wong | alice.wong@example.com | Guld | 92128 | 120000 |
|   | FIN002 | Bob | Smith | bob.smith@example.com | Silver | 92126 | 85000 |
|   | FIN003 | Charlie | Kim | charlie.kim@example.com | Platinum | 60614 | 175000 |
|   | FIN004 | Diana | Lee | diana.lee@example.com | Guld | 30303 | 98000 |
|   | FIN005 | Ethan | Brun | ethan.brown@example.com | Bronze | 75201 | 60000 |

## Infoga CSV-filen

* Skapa en datauppsättning med namnet **_FinWiseCustomerDataSetWithAnnualIncome_** baserat på det **_FinWiseProfileSchema_** som skapades i det tidigare. Kontrollera att datauppsättningen är aktiverad för profilen.

* Navigera till Anslutningar -> Källor -> Lokalt system
* Välj **_Lägg till data_** under den lokala filöverföringen. Se till att välja _**FinWiseCustomerDataSetWithAnnualIncome**_ som måldatamängd.
  ![ingest-csv](assets/ingest-csv-into-dataset.png)
* Gå till nästa skärm. Överför [csv-filen](assets/finwise_profiles.csv) och verifiera mappningarna
  ![mappningar](assets/mappings.png)

* Klicka på Slutför för att starta dataöverföringsprocessen

## Verifiera profil

* Navigera till Customer ->Profiles och sök efter FinWise CRM ID som är lika med FIN001 eller något annat giltigt värde
  ![verify-profile](assets/verify-profiles.png)
