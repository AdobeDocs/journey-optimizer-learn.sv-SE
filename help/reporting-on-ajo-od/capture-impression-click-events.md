---
title: Fånga visningar och interaktionshändelser
description: Samla in bild- och interaktionshändelser och färdigställ data för rapportering inom Journey Optimizer.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
recommendations: noDisplay, noCatalog
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
exl-id: 7e6014b5-c5a6-467b-8e31-58c5d966464c
source-git-commit: ab60877bd5cb9eeeea45b1e1f08293d31929fc81
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# Fånga visningar och interaktionshändelser

Följande komponenter måste vara konfigurerade för att det ska gå att rapportera visningar och klickningar från AJO:
>[!NOTE]
>
> Dessa krav har redan slutförts i avsnittet Skapa schema och datauppsättning i den [tidigare självstudiekursen](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/create-schema-and-dataset)

## &#x200B;1. Datauppsättning i Adobe Experience Platform (AEP)

- En datauppsättning baserad på ett **XDM ExperienceEvent** -schema.

Schemat måste innehålla fältgruppen `Web Details` som hämtar sidans URL, referens osv.

## &#x200B;2. Datastream-konfiguration

- **Datastream** måste skapas i Adobe Experience Platform.
- Det här dataflödet måste länkas till den datauppsättning som konfigurerats ovan för att säkerställa att alla Web SDK-händelser är korrekt inkapslade i rätt mål.

## 3. Adobe Experience Platform Tags Property

- Tillägget AEP Web SDK är konfigurerat att använda den dataström som skapades i det tidigare steget.
- Experience Cloud ID-tjänsten har konfigurerats
- Ett dataelement med namnet ECID läggs till i egenskapen
- Implementeras på webbplatsen där erbjudanden återges.


För att möjliggöra rapportering om erbjudandets prestanda är det första steget att hämta in erbjudanden när de visas (visningar) och när de klickas (interaktioner). Dessa händelser utgör grunden för mätning av engagemang, beräkning av klickfrekvens och analys av erbjudandeeffektivitet inom Adobe Experience Platform.

Funktionen alloy(&quot;sendEvent&quot;) används för att logga användarinteraktioner med erbjudanden som returneras av Adobe Journey Optimizer (AJO).

Nyttolasten sendEvent erbjuder interaktioner genom att inkludera händelsetypen (decisioning.propositionDisplay för visningar eller decisioning.propositionInteract för klickningar), ett unikt händelse-ID, tidsstämpel och användaridentitet (identityMap). Den innehåller även en lista med erbjudanden (förslag) som visas eller klickas, tillsammans med spårningstoken för att säkerställa korrekt attribuering. Denna struktur möjliggör rapportering och optimering av personaliserade erbjudanden i Adobe Journey Optimizer.

Två typer av interaktionshändelser fångas:

## Impression-händelse

Ett intryck inträffar när ett erbjudande återges på sidan och blir synligt för användaren. Händelsen spåras med händelsetypen decisioning.propositionDisplay.


```javascript
 alloy("sendEvent", {
            xdm: {
              _id: generateUUID(),
              timestamp: new Date().toISOString(),
              eventType: "decisioning.propositionDisplay",
              identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "authenticated",
                      primary: true
                    }]
                  },
              _experience: {
                decisioning: {
                  propositionEventType: {
                    display: 1
                  },
                  
                   propositions: window.latestPropositions
                  
                }
              }
            }
          });
        }
```

## Erbjudandeinteraktion

En interaktion spelas in när en användare klickar på en call-to-action (CTA) i det återgivna erbjudandet. Händelsen spåras med händelsetypen decisioning.propositionInteract.

```javascript
alloy("sendEvent", {
                xdm: {
                  _id: generateUUID(),
                  timestamp: new Date().toISOString(),
                  eventType: "decisioning.propositionInteract",
                  identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "ambiguous",
                      primary: true
                    }]
                  },
                  _experience: {
                    decisioning: {
                      propositionEventType: {
                        interact: 1
                      },
                      propositionAction: {
                        id: offerId,
                        tokens: [trackingToken]
                      },
                       propositions: window.latestPropositions
                    }
                  }
                }
              })
```

Att inkludera förslag i klicknings- och tryckhändelser är nödvändigt för korrekt rapportering av erbjudanden i Adobe Journey Optimizer. Dessa förslag representerar de exakta erbjudanden som presenterades för användaren, vilket gör det möjligt för Adobe att attribuera användarinteraktioner (till exempel visningar eller klickningar) tillbaka till de specifika beslut som fattas av systemet.

Varje erbjudande i ett erbjudande innehåller en spårningstoken, som är en unik identifierare som genereras av Adobe. Denna token måste skickas exakt som den tagits emot - utan ändringar - i motsvarande click- eller intryckshändelse. Matchande spårningstoken säkerställer att Adobe kan koppla användaråtgärden till rätt erbjudande, vilket möjliggör rapportering i efterföljande led och AI-baserad optimering.
