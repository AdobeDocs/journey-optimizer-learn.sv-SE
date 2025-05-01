---
title: Testa lösningen
description: Metoder som felsöker lösningen
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Testa lösningen

Validera implementeringen genom att öppna webbsidan med ditt inställningsformulär. Använd webbläsarens DevTools (flikarna Konsol och Nätverk) för att övervaka formulärskickningsprocessen. När du har skickat en inställning (till exempel valt&quot;Stocks&quot;) bekräftar du att AEP Web SDK (alloy.sendEvent) har utlösts och att rätt data har skickats till Adobe Experience Platform. I AEP går du till publikavsnittet och kontrollerar att din profil uppfyller kraven för den förväntade målgruppen (till exempel&quot;Intresserad i lager&quot;) inom en stund med hjälp av Edge Segmentering. Du kan också kontrollera inkommande händelsedata i den associerade datauppsättningen för att se till att den innehåller rätt inställningsvärde. Upprepa den här processen för varje resursklass (Stocks, Bonds, CD) för att säkerställa att det fullständiga arbetsflödet fungerar korrekt.

## Felsökning - tips

Om du inte ser att profilen är giltig för den avsedda målgruppen omedelbart kontrollerar du följande:


### Verifiera push-överföring av Adobe datalager

* Öppna webbläsarens Developer Tools → Console
* Type console.log(window.adobeDataLayer);
* Bekräfta att en händelse med händelsen: &quot;assetClassSelection&quot; och rätt PreferredFinancialInstrument-värde visas när formuläret har skickats

### Bekräfta körning av startregel

* Öppna Adobe Experience Platform Debugger (Chrome Extension)
* Logga in på felsökaren
* Skicka formuläret
* Kontrollera att DataPushed-händelsen för assetClassSelection har hämtats

Följande felsökningsskärmbild bör hjälpa dig
![aep-debugger](assets/aep-debugger.png)

### Hämta ECID

ECID (Experience Cloud-ID) är en unik och beständig Adobe-identifierare som används för att identifiera och sammanföra användare mellan Experience Cloud lösningar och sessioner.

* Chrome Developer Tools → fliken Nätverk

* Filtrera efter &quot;interact&quot; eller &quot;collect&quot;

* Skicka formuläret
* Klicka på fliken Svar och notera ECID

![get-ecid](assets/get-ecid.png)

### Kontrollera realtidsprofil och målgruppskvalifikation

* Logga in på Journey Optimizer
* Gå till Kunder->Profiler->Bläddra
* Sök efter ECID som du fått från föregående steg enligt skärmbilden
  ![ecid-profile](assets/ecid-profile.png)
* Klicka på profilen och välj fliken Händelser för att kontrollera om Investment_preferences_event visas
  ![events-tab](assets/profile-events.png)
* Öppna den json som är associerad med händelsen och kontrollera om den innehåller rätt händelsedata.

### Ytterligare felsökningstips

* Kontrollera att schema- och datauppsättningsprofilen är aktiverad.
* Se till att Edge Segmentation är aktiverat för målgruppen så att kvalificeringen sker i nära realtid.
* Att vänta några minuter och uppdatera publikvyn kan också vara till hjälp, särskilt om du testar direkt efter publiceringsändringarna.
* Se till att målgruppsreglerna är korrekt definierade och referera till de exakta fältnamnen och värdena som hämtas när formuläret skickas.



