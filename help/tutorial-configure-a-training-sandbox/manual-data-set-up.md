---
title: Konfigurera datastrukturen manuellt
description: Skapa önskade identitetsnamnutrymmen och definiera datastrukturen för Luma-exemplet.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: d848272dba814c300aa21110316b5b37ccb719ce
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 2%

---

# Konfigurera data manuellt

I det här avsnittet skapar du de identitetsnamnutrymmen som krävs och definierar [!DNL Luma] exempeldatastrukturen genom att skapa [[!UICONTROL scheman]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html).

>[!TIP]
>Se videosjälvstudiekursen [Mappa identiteter](/help/data-management/map-identities.md) innan du börjar.

## Steg 1: Skapa identitetsnamnutrymmen

I det här steget skapar du identitetsnamnutrymmen för [!DNL Luma] anpassade identitetsfält namngivna `lumaLoyaltyId`, `lumaCrmId`och `lumaProductSKU`. Identitetsnamnutrymmen spelar en viktig roll när det gäller att skapa kundprofiler i realtid, eftersom två matchande värden i samma namnutrymme gör att två datakällor kan bilda ett identitetsdiagram.

Börja med att skapa en [!UICONTROL namespace] för [!DNL Luma Loyalty ID] schema:

1. I Journey Optimizer användargränssnitt går du till **[!UICONTROL Kund]** > **[!UICONTROL Identiteter]** i den vänstra navigeringen.

1. Välj **[!UICONTROL Skapa namnutrymme för identitet]**.

1. Ange följande information:

   | Visningsnamn | Identitetssymbol | Typ |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyaltyId` | [!UICONTROL Enhetsoberoende ID] |

1. Välj **[!UICONTROL Skapa]**.

   ![Skapa namnutrymmen](assets/createNamespace.png)

1. Skapa ytterligare två namnutrymmen enligt samma steg:

   | Visningsnamn | Identitetssymbol | Typ |
   |---|---|---|
   | `Luma CRM ID` | `lumaCrmId` | [!UICONTROL Enhetsoberoende ID] |
   | `Luma Product SKU` | `lumaProductSKU` | [!UICONTROL Identifierare för icke-personer] |

## Steg 2: Skapa scheman

I det här steget definierar du strukturen för exempeldata genom att skapa sex [[!UICONTROL scheman]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html):

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product Catalog Schema]](#create-luma-product-catalog-schema)

* [[!DNL Luma Product Inventory Events] Schema](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Web Events Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Offline Purchase Events Schema]](#create-additional-schemas)

* [[!DNL Luma Test Profiles Schema]](#create-additional-schemas)

>[!TIP]
>
>Se videosjälvstudiekursen: [Skapa ett schema](/help/data-management/create-schema.md) innan du börjar.

### Skapa [!DNL Luma Loyalty Schema] {#create-luma-loyalty-schema}

I det här avsnittet beskrivs hur du skapar [!DNL Luma Loyalty] schema och konfigurera fältgrupper.

#### Skapa schemat

1. Gå till **[!UICONTROL DATAHANTERING]** > **[!UICONTROL Scheman]** i den vänstra navigeringen.

1. Välj **[!UICONTROL Skapa schema]** överst till höger.

1. Välj **[!UICONTROL Individuell XDM-profil]**.

   Du väljer det här alternativet eftersom du modellerar attribut för en enskild kund (punkter, status och så vidare).

#### Lägg till befintliga fältgrupper

Därefter uppmanas du att lägga till fältgrupper i schemat med hjälp av grupper. Du måste lägga till befintliga fältgrupper och skapa en fältgrupp.

1. På [!UICONTROL Schema] om fältgruppernas modala inte öppnades automatiskt väljer du **[!UICONTROL Lägg till]**.

   ![Lägg till fältgrupp](assets/add_field_group.png)

1. På **[!UICONTROL Lägg till fältgrupper]** aktiverar du följande fältgrupper:

   * **[!UICONTROL Demografiska detaljer]** för grundläggande kunddata som namn och födelsedatum.

   * **[!UICONTROL Kontaktinformation, privat]** för grundläggande kontaktinformation som e-postadress och telefonnummer.

   * **[!UICONTROL Förmånsinformation]** för information om lojalitet som poäng, sammanfogat datum eller status. Fältgruppen för lojalitet ligger långt ned i listan, så det är enklast att söka efter den.

1. Välj **[!UICONTROL Lägg till fältgrupp]** om du vill lägga till alla tre fältgrupper i schemat.

   ![Välj standardfältgrupper](assets/addstandardFieldGroups.png)

1. Markera schemats översta nod.

1. Retur `Luma Loyalty Schema` som **[!UICONTROL Visningsnamn]**.

#### Skapa en [!UICONTROL fältgrupp] {#create-field-group}

Adobe rekommenderar att du hanterar alla systemidentifierare i en och samma grupp för att säkerställa konsekvens i alla scheman:

1. Från **[!UICONTROL Disposition]** avsnitt under [!UICONTROL Fältgrupper], markera **[!UICONTROL Lägg till]**.

1. Välj **[!UICONTROL Skapa ny fältgrupp]**.

1. Lägg till `Luma Identity Profile Field Group` som **[!UICONTROL Visningsnamn]**.

1. Lägg till `system identifiers for XDM Individual Profile class` som **[!UICONTROL Beskrivning]**.

1. Välj **[!UICONTROL Lägg till fältgrupper]**.

   ![Skapa ny fältgrupp](assets/addnewfieldgroup.png)

#### Lägg till fält i nya [!UICONTROL fältgrupp]

Den nya, tomma fältgruppen läggs till i ditt schema. Med +-knapparna kan du lägga till nya fält på valfri plats i hierarkin. I det här fallet måste du lägga till fält på rotnivån:

1. Välj **[!UICONTROL +]** bredvid schemats namn.

   Det här steget lägger till ett fält under **ditt klient-ID** för att hantera konflikter mellan anpassade fält och standardfält.

1. I **[!UICONTROL Fältegenskaper]** sidofältet, lägg till information om det nya fältet:

   * **Fält:** `systemIdentifier`

   * **[!UICONTROL Visningsnamn]:** `System Identifier`

   * **Typ:** Objekt

   * **[!UICONTROL Tilldela fältgrupp]:** [!DNL Luma identifiers]

1. Välj **[!UICONTROL Använd]**.

   ![Lägg till systemidentifierare](assets/addsysteidentifier.png)

   Lägg till två fält under `systemIdentifier` objekt:

   | [!UICONTROL Fieldname] | [!UICONTROL Visningsnamn] | [!UICONTROL Typ] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty Id` | [!UICONTROL Sträng] |
   | `crmId` | `CRM Id` | [!UICONTROL Sträng] |

![fält](./assets/add_fields.png)

#### Ange identiteter

Nu har du [!UICONTROL namespace] och [!DNL Luma Loyalty schema] konfigurerad. Innan du kan importera data måste du etikettera identitetsfälten. Varje schema som används med [!UICONTROL Kundprofil i realtid] måste ha en primär identitet angiven och varje inskickad post måste ha ett värde för det fältet.

1. Ange **primär identitet**:

   Från **[!DNL Luma Loyalty Schema]**:

   1. Markera **[!DNL Luma Identity Profile Field Group]**.

   2. Välj **[!DNL loyaltyId]** fält.

   3. I **[!UICONTROL Fältegenskaper]**, aktivera **[!UICONTROL Identitet]** box.

   4. Aktivera **[!UICONTROL Primär identitet]** box.

   5. Välj `Luma Loyalty Id` namnutrymme från **[!UICONTROL Identitetsnamnutrymmen]** listrutemeny.

   6. Välj **[!UICONTROL Använd]**.

      ![primär identitet](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. Ange en **sekundär identitet**:

   Från **[!DNL Luma Loyalty Schema]**:

   1. Markera **[!DNL Luma Identity Profile Field Group]**.

   2. Välj `crmId` fält.

   3. I **[!UICONTROL Fältegenskaper]**, aktivera **[!UICONTROL Identitet]** box.

   4. Välj `Luma CRM Id` namnutrymme från **[!UICONTROL Identitetsnamnutrymmen]** nedrullningsbar meny.

   5. Välj **[!UICONTROL Använd]**.

#### Aktivera för profil och spara schemat

1. Markera schemats översta nod.

1. I [!UICONTROL Fältegenskaper], aktivera **[!UICONTROL Profil]**.

   Schemat bör se ut så här:

   ![Luma Loyalty-schema](assets/lumaloyaltyschema.png)

1. Välj **[!UICONTROL Spara]**.

### Skapa [!DNL Luma Product Catalog Schema] {#create-luma-product-catalog-schema}

1. Gå till **[!UICONTROL DATAHANTERING]** > **[!UICONTROL Scheman]** i den vänstra navigeringen.

1. Välj **[!UICONTROL Skapa schema]** (överst till höger).

1. Om du vill skapa en klass väljer du **[!UICONTROL Bläddra bland alla schematyper]** i listrutan.

1. Välj **[!UICONTROL Skapa ny klass]**.

1. Lägg till visningsnamnet: `Luma Product Catalog Class`.

1. Tilldela klass.

1. Skapa en [!UICONTROL Fältgrupp]:

   * Visningsnamn `Luma Product Catalog Field Group`

1. Lägg till följande fält i **[!DNL Luma Product Catalog Field Group]**.

   * Fält: `product`

   * Visningsnamn `Product`

   * Typ: [!UICONTROL Objekt]

   * Fältgrupp: [!DNL Luma Product Catalog Field Group]

1. Välj **[!UICONTROL Använd]**.

1. Lägg till följande fält i **[!DNL Product]** objekt:

   | [!UICONTROL Fieldname] | [!UICONTROL Visningsnamn] | [!UICONTROL Typ] |
   |-------------|-----------|----------|
   | `sku` | `Product SKU` | [!UICONTROL Sträng] |
   | `name` | `Product Name` | [!UICONTROL Sträng] |
   | `category` | `Product Category` | [!UICONTROL Sträng] |
   | `color` | `Product Color` | [!UICONTROL Sträng] |
   | `size` | `Product Size` | [!UICONTROL Sträng] |
   | `price` | `Product Price` | [!UICONTROL Dubbel] |
   | `description` | `Product Description` | [!UICONTROL Sträng] |
   | `imageUrl` | `Product Image URL` | [!UICONTROL Sträng] |
   | `stockQuantity` | `Product Stock Quantity` | [!UICONTROL Sträng] |
   | `url` | `Product URL` | [!UICONTROL Sträng] |

1. Ange **[!DNL SKU]** som primär identitet.
1. Lägg till **[!UICONTROL Visningsnamn]** `Luma Product Catalog Field Group` till [!UICONTROL fältgrupp].

1. Välj **[!UICONTROL Spara]**.

### Skapa [!DNL Luma Product Inventory Event Schema] {#create-luma-product-inventory-event-schema}

1. Gå till **[!UICONTROL DATAHANTERING]** > **[!UICONTROL Scheman]** i den vänstra navigeringen.

1. Välj **[!UICONTROL Skapa schema]** överst till höger.

1. Välj **[!UICONTROL Bläddra bland alla schematyper]**.

1. Välj **[!UICONTROL Skapa ny klass]**.

1. Lägg till visningsnamnet: `Luma Business Event Class`.

1. Välj typ: *[!UICONTROL Tidsserie]*.

1. Tilldela klass.

1. Skapa en [!UICONTROL fältgrupp]:

   * Visningsnamn `Luma Product Inventory Event Details Field Group`

1. Lägg till **[!UICONTROL Visningsnamn]** `Luma Product Inventory Event Schema` till schemat.

1. Lägg till följande fält i **[!DNL Luma Product Inventory Event Details Field Group]**:

   * Fält: `inventoryEvent`

   * Visningsnamn `Inventory Event`

   * Typ: [!UICONTROL Objekt]

   * Fältgrupp: `Luma Product Inventory Event Details Field Group`

1. Lägg till följande fält i `Product Inventory Event Details` objekt:

   | [!UICONTROL Fieldname] | [!UICONTROL Visningsnamn] | [!UICONTROL Typ] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL Sträng] |
   | `stockEventType` | `Stock Event Type` | [!UICONTROL Sträng] |

   1. för att ange `stockEventType` till Enum, välj typ: `string`.

   2. Bläddra nedåt till nederkanten av **[!UICONTROL Fältegenskaper]**.

   3. Aktivera **[!UICONTROL Enum]**.

   4. Retur **[!UICONTROL values] ([!UICONTROL etikett)]**: `restock` (`Restock`).

   5. Välj **[!UICONTROL Lägg till rad]**.

   6. Retur **[!UICONTROL values] ([!UICONTROL etikett)]**: `outOfStock` (`Out of Stock`).

   7. Välj **[!UICONTROL Använd]**.

      ![enum](assets/enum.png)

1. Ange `inventory.Event.sku` fält som **[!UICONTROL primär identitet]** med **[!DNL LumaProductSKU namespace]**.

1. Välj `sku` fält och definiera en relation till `product.sku` fältet i **[!DNL Luma Product catalog Schema]** Schema:

   1. Bläddra nedåt till nederkanten av **[!UICONTROL Fältegenskaper]**.

   2. Aktivera **[!UICONTROL Relation]**.

      1. **[!UICONTROL Referensschema]**: [!DNL Luma Product Catalog Schema].

      2. **[!UICONTROL Namnutrymme för referensidentitet]**: [!DNL LumaProductSKU].

   3. Välj **[!UICONTROL Använd]**.

      Schemat bör se ut så här:

      ![SKU-relation](assets/sku_relationship.png)

1. Aktivera för **Profil**.

1. Välj [!UICONTROL Spara] för att spara schemat.

### Skapa ytterligare scheman {#create-additional-schemas}

Skapa följande ytterligare [!UICONTROL scheman]:

| [!UICONTROL Visningsnamn] | [!DNL Luma CRM Schema] | [!DNL Luma Web Events Schema] | [!DNL Luma Test Profiles schema] | [!DNL Luma Offline Purchase Events Schema] |
|  ---| ------- | ---- |----|----|
| **[!UICONTROL Klass]** | [!UICONTROL Individuell XDM-profil] | [!UICONTROL XDM Experience Event] | [!UICONTROL Individuell XDM-profil] | [IUICONTROL XDM ExperienceEvent] |
| **[!UICONTROL Lägg till befintlig fältgrupp]** | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details` | `Orchestration eventID`<br>`Consumer Experience Event`<br>`AEP Web SDK ExperienceEvent` | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details`<br>`Profile test details` | `Luma Identity Profile Field Group` <br>`Commerce Details` |
| **[!UICONTROL Relation]** |  | `productListItems.SKU`:<br> Referensschema `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |  | `productListItems.SKU`:<br> Referensschema `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |
| **[!UICONTROL Primär identitet] [!UICONTROL namespace])** | `systemIdentifier.crmId` | | `systemIdentifier.crmId` | `systemIdentifier.LoyaltyId` |
| **[!UICONTROL Aktivera för profil]** | ja | ja | ja | ja |

## Nästa steg

Nu när du har skapat datastrukturen kan du [skapa datauppsättningar och importera exempeldata](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md).
