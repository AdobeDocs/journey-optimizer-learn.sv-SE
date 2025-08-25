---
source-git-commit: 0ce6d5013bbcf55e49ae920670919f6929a142ec
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---
# Meddelanden i appen

## Vad är meddelanden i appen?

Meddelanden i appen är meddelanden som visas i en app medan användaren aktivt använder den. De är överläggsmeddelanden som visas ovanpå appen. De visas inte på låsskärmen eller utanför appen, utan visas som banners, popup-fönster eller små kort när användaren utforskar appen.

Meddelanden i appen utlöses av specifika användaråtgärder eller -villkor, som att visa en viss sida, slutföra ett köp eller vara en del av ett målgruppssegment.


Exempel:

* Ett spel kan visa ett popup-fönster som förklarar en ny funktion så fort användaren låser upp den.
* En shoppingapp kan visa en banderoll med en kupongkod när användaren bläddrar bland artiklar.
* En app för sociala medier kan visa ett meddelande som föreslår att användaren följer nya konton.

## Användningsfall

| **Fördelar** | **Varför** | **Exempel på användningsexempel** |
|----------------------------------|------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| Engagemang för stora användare | Hämtar användare medan de är aktiva i appen, vilket ger bättre synlighet och åtgärder | <ul><li>Genomgångar av introduktioner</li><li>Funktionsmeddelanden</li><li>Popup-fönster med stöd i realtid</li></ul> |
| Sammanhangsberoende relevans | Tillåter att meddelanden triggas av användarbeteende, vilket gör dem aktuella och personaliserade | <ul><li> Merförsäljning efter användning av funktioner</li><li> Inaktivitetsövningar</li><li> Fel- eller svarsmeddelanden</li></ul> |
| Leverans i realtid | Möjliggör omedelbar kommunikation för tidskänsliga eller kritiska uppdateringar | <ul><li> Systemavbrott</li><li>Transaktionsbekräftelser</li><li>Betalningsfel</li></ul> |
| Inget beroende av externa kanaler | Behåller användarupplevelsen i produkten utan att förlita sig på e-post/SMS | <ul><li> Påminnelser om slutförande av självstudier</li><li>Varningar om att testversionen har gått ut</li></ul> |
| Bättre konverteringsmöjligheter | Meddelanden som placeras i sitt sammanhang konverteras bättre än meddelanden som inte kommer från plattformen | <ul><li> Uppgraderingsmeddelanden när avtalsbegränsningar har uppnåtts</li><li>Undersökningar i appen</li></ul> |
| Anpassning och segmentering | Kan anpassas baserat på användardata eller apphändelser | <ul><li> Meddelanden anpassade efter användarnivå eller aktivitetsnivå</li><li> Rollspecifika aviseringar </li></ul> |
| Icke-påträngande (när den är väl konstruerad) | Ger en subtil och effektiv kommunikation utan att användarflödet bryts | <ul><li> Verktygstips</li><li>Bilder med uppdateringar</li><li>Chattwidget-nudd</li></ul> |


## När *inte* ska använda kommunikation i appen

* **Användaren använder inte appen aktivt**\
  Meddelanden i appen visas inte om användaren inte är inloggad eller engagerar med produkten. Använd e-post eller push i stället.
* **Kritiska eller tidskänsliga problem som kräver omedelbar åtgärd**\
  För brådskande meddelanden (t.ex. säkerhetsvarningar, betalningsfel) använder du kanaler som kan nå användaren utanför appen, t.ex. SMS eller e-post.
* **Regelbunden eller juridisk kommunikation**\
  Meddelanden som rör regelefterlevnad (t.ex. villkorsuppdateringar, policyändringar) kan kräva leverans och läsbekräftelse - bättre lämpat för e-post.
* **Återaktivering av konto eller återvinningskampanjer**\
  Om användaren är inaktiv eller hackad visas inga meddelanden i appen. Använd återengagemangskampanjer via e-post eller push-meddelanden.
* **Transaktionsuppdateringar för stora volymer**\
  Meddelanden som leveransuppdateringar eller kvitton skickas ofta bättre via e-post för arkivering och smidighet.
* **Överanvändning leder till bannerblindhet eller irritation**\
  Att bombardera användare med för många meddelanden i appen kan skada användarupplevelsen och leda till frustration eller ignorerade meddelanden.
* **Ingen anslutning/offlinescenarier**\
  I appen krävs att användaren är online och under session - det kommer inte att hjälpa i miljöer som sätter det första offline.

