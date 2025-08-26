---
source-git-commit: 6aa7b4c72ce5bd72002ad88ba88a20f32d54c360
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 2%

---

# Översikt över push-meddelanden

## Vad är push-meddelanden?

**Push-meddelanden** är korta meddelanden som visas på en telefon, surfplatta eller dator - även när användaren inte använder appen som skickade dem. De är ett sätt för appar att&quot;knacka på dig på axeln&quot; och få din uppmärksamhet.

Exempel:

* En shoppingapp kan varna dig för en stor affär.
* En leveransapp kan tala om för dig att din beställning är på väg.
* En flygplansapp kanske meddelar att flygresan är klar att checka in.

**Viktigt!** Användaren måste ge appbehörigheten (anmälan) innan den kan skicka push-meddelanden till dig. Det här inträffar vanligtvis när programmet först öppnas efter att det har laddats ned, eller senare om programmet frågar igen under användningen. Utan användarens tillstånd kan programmet inte skicka push-meddelanden till sin enhet.

## Användningsfall

Välj push-meddelanden som den önskade meddelandekanalen när du behöver:

| # | Fördelar | Varför | Exempel på användningsfall |
|---|---------|-----|-------------------|
| 1 | Tidskänsliga uppdateringar | Push-meddelanden kan visas på låsskärmen eller som banners utan att användaren behöver öppna appen. | <ul><li> Akuta varningar (tjänstavbrott, säkerhetsvarningar)</li><li>Tidskänsliga erbjudanden (blixtförsäljning)</li><li> Uppdateringar i realtid (sportresultat, orderleverans)</ul> |
| 2 | Återengagemang | Push kan återföra inaktiva användare till appen genom att leverera personaliserade och relevanta uppmaningar. | <ul><li> Övergiven kundvagn eller påminnelser - t.ex. &quot;Du lämnade artiklar i kundvagnen - checkar ut nu för 10 % rabatt.&quot;</li></ul> |
| 3 | Minska beroendet av kostnadsbesparande kanaler | Push är vanligtvis kostnadsfri att skicka när du har byggt infrastrukturen, till skillnad från SMS eller e-post där kostnaden per meddelande är. | <ul><li> Använd push istället för betalSMS för regelbundna uppdateringar.</li></ul> |
| 4 | Leverera avancerat interaktivt material | Moderna push-API:er tillåter bilder, videor, snabbåtgärder (t.ex.&quot;Acceptera&quot;/&quot;Avvisa&quot;) eller djupa länkar till specifika appskärmar. | <ul><li>Marknadsföringskampanjer som ser bra ut</li><li>Snabba användaråtgärder utan att öppna appen helt.</li></ul> |
| 5 | Utnyttja inbyggda enhetsfunktioner | Push-meddelanden kan integreras med iOS/Android OS-funktioner som vibrationer, ljud, emblem och utlösare för geofencing. | <ul><li> Platsbaserade erbjudanden nära en butik</li><li> Påminnelser utlöses vid specifika tidpunkter.</li></ul> |
| 6 | När deltagande är sannolikt | Push fungerar bara för användare som uttryckligen har valt att göra det. Om appen har ett högt värde eller om varumärket redan har förtroende kan avanmälningsfrekvensen vara hög. | <ul><li> Appar med lojala användarbaser</li><li> Onboarding-flöden som förklarar värdet av meddelanden.</li></ul> |

## När *inte* ska använda push som primär kanal

* Låg anmälningsfrekvens eller motvilja från användaren mot meddelanden.
* Behovet av innehåll med lång form (e-post kan vara bättre).
* Känslig eller mycket privat information (push kan ses på låsskärmar).
* Användare finns oftast på datorn och inte i mobilappen.
