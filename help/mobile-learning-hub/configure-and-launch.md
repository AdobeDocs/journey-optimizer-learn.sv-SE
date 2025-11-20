---
title: Konfigurera och starta
description: Konfigurera mobilkanalerna i Adobe Journey Optimizer (AJO) och Adobe Experience Platform (AEP), integrera med mobilappar och se till att ni är redo att genomföra marknadsföringskampanjer.
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: true
index: false
last-substantial-update: 2025-08-22T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: c0d4d95932a9f529442ac3471ee4070398e1bfa5
workflow-type: tm+mt
source-wordcount: '2463'
ht-degree: 2%

---


# Konfigurera och starta

Konfigurera mobilkanalerna i Adobe Journey Optimizer och Adobe Experience Platform, integrera med mobilappar och se till att ni är redo att genomföra marknadsföringskampanjer.

> **Obs!**\
> Om du inte har använt Journey Optimizer eller Experience Platform tidigare bör du bekanta dig med de grundläggande begreppen genom att gå följande kurs:
> - [Konfigurera och administrera Adobe Journey Optimizer](https://experienceleague.adobe.com/sv/courses/ajo-configure-and-administrate-ajo-environment)
>*I den här kursen får du lära dig att konfigurera och hantera Journey Optimizer-miljön, inklusive användarroller, behörigheter, sandlådor och e-postkanaler, vilket säkerställer effektiva och säkra åtgärder.*
> - [Ingenjörsdata för intelligent reseaktivering i Adobe Journey Optimizer](https://experienceleague.adobe.com/sv/courses/ajo-engineer-data-for-intelligent-journey-activation)
>*I den här kursen får du lära dig att konfigurera och hantera kundprofildata i realtid för Journey Optimizer med Experience Platform. Förstå datamodellering, identitetsmappning och datainmatning för att skapa enhetliga profiler för personaliserade kundresor.*


## Mobilfunktioner i Adobe Journey Optimizer

Förstå vilka mobilfunktioner Adobe Journey Optimizer erbjuder för utvecklare, marknadsförare och produktteam, inklusive push-meddelanden, meddelanden i appen och innehållspersonalisering.

>[!VIDEO](https://video.tv.adobe.com/v/342103?quality=12&learn=on){transcript=true}


## Konfigurera SDK och appar för mobiler

Mobilimplementeringar i Journey Optimizer börjar med **Adobe Experience Platform Mobile SDK** -integreringen i din app. SDK är nödvändigt för datainsamling och interaktion med Adobe Experience Platform (AEP) och dess program, till exempel Adobe Journey Optimizer (AJO).

Mobile SDK:

- Samlar in apphändelser (skärmvyer, kraschar, köp, livscykelhändelser osv.) och skickar dem till **Adobe Experience Platform Edge Network**.
- Hanterar **identitet** och **samtycke** så att Journey Optimizer kan skapa och använda kundprofiler på ett säkert sätt.
- Registrerar och uppdaterar **push-tokens** och skickar **push- och in-app tracking-händelser** tillbaka till Adobe Experience Platform.
- Integreras med **Journey Optimizer mobiltillägg** (push, in-app, innehållskort, beslutsfunktioner) så att meddelanden kan levereras, återges och mätas från början till slut.

Utan Mobile SDK som är integrerad i appen kan Journey Optimizer inte på ett tillförlitligt sätt:

- Leverera och spåra mobilmeddelanden och meddelanden i appen.
- Återge och spåra innehållskort.
- Använd beteenden i realtid i appen för att utlösa resor och personalisera upplevelser.


### Förhandskrav

Kontrollera att du har:

- Adobe Journey Optimizer (AJO) har etablerats för din organisation.
- Adobe Experience Platform har åtkomst till datainsamling och Journey Optimizer-behörigheter.
- Administratörsrättigheter i AJO för konfigurering av kanaler och konfigurationer.
- Tillgång till mobilappens källkod (iOS, Android eller ramverk för flera plattformar).
- Appen har de nödvändiga funktionerna på operativsystemnivå aktiverade (till exempel push-behörigheter, meddelandetjänsttillägg och bakgrundslägen).


### Nödvändiga Mobile SDK-komponenter för Journey Optimizer

Om du vill använda Journey Optimizer mobilkanaler (push, in-app, innehållskort, kodbaserade upplevelser) måste du installera och konfigurera en uppsättning **core**- och **kanalspecifika**-tillägg i din mobilapp:

>[!BEGINTABS]

>[!TAB Core]

#### Kärntillägg (krävs för alla mobila användningsfall)

| Syfte | Exempel på tillägg (iOS/Android) | Anteckningar |
|----------------------|-----------------------------------------------|-------|
| Händelsehubb och tjänster | Mobile Core/AEP Core, AEP Services | Foundation for all other extensions. Tillhandahåller händelsehubb, nätverk, lagring och delat tillstånd. |
| Edge Network | Adobe Experience Platform Edge Network | Skickar apphändelser till Adobe Experience Platform Edge Network. |
| Identitet | Identitet för Edge Network | Hanterar ECID och andra identiteter som används för profil och segmentering. |
| Godkännande | Godkännande för Edge Network | Samlar in och tillämpar inställningar för användargodkännande. |
| Assurance | Adobe Experience Platform Assurance | Används för att validera och felsöka SDK och kanalkonfigurationen från början till slut. |

>[!TAB Kanalspecifik]

#### Kanalspecifika tillägg för Journey Optimizer

| Kanal/kapacitet | Ytterligare nyckeltillägg (ovanpå kärnan) | Vad de aktiverar |
|------------------------|---------------------------------------------------------------------|------------------|
| Push-meddelanden | Journey Optimizer mobiltillägg (push) | Registrera och uppdatera push-tokens, skicka push-spårningshändelser, ansluta till AJO push-konfiguration. |
| Meddelanden i appen | Journey Optimizer mobiltillägg (i appen), gränssnittskomponenter för meddelanden | Hämta in och visa meddelanden i appen i rätt sammanhang, skicka visningar och interaktionshändelser. |
| Innehållskort | Skicka meddelanden till SDK med stöd för innehållskort | Hämta, rendera och spåra innehållskort för korrekt rapportering från Journey Optimizer. |
| Kodbaserade upplevelser | Journey Optimizer/beslutstillägg eller Edge Server API | Hämta beslut om specifika&quot;ytor&quot; i appen; appen styr hur innehåll återges. |

>[!ENDTABS]

#### Egenskaper och konfiguration för mobiltagg

Du konfigurerar dessa tillägg i en **[mobil taggegenskap](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)** i AEP Data Collection (taggar). This property controls:

- Vilka SDK-tillägg för mobiler som är installerade.
- Vilka händelser i din app som utlöser anrop till Edge Network.
- Hur data mappas till XDM och vidarebefordras till Adobe-lösningar (Journey Optimizer, Analytics, etc.).

Du kan skapa och konfigurera den här mobila egenskapen manuellt eller använda **[Guidad kanalkonfiguration](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)** för att automatiskt skapa den nödvändiga taggegenskapen, datastream och kanalkonfigurationen för iOS eller Android.

> **Tips**\
> För nya implementeringar rekommenderas **[Guided Channel Setup](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)** som startpunkt. Det minskar risken för felkonfigurerade datastreams eller saknade tillägg och leder dig igenom SDK-valideringen med Assurance.

#### Kom igång med Mobile SDK:

<!-- CARDS
* https://experienceleague.adobe.com/sv/docs/platform-learn/data-collection/mobile-sdk/overview
    {description = Learn how Adobe Experience Platform Mobile SDK powers end-to-end engagement in your mobile applications.}
* https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/overview
* https://experienceleague.adobe.com/sv/docs/mobile
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/platform-learn/data-collection/mobile-sdk/overview" title="Adobe Experience Platform Mobile SDK - översikt" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/28948?format=jpeg&nocache=1763594622398" alt="Adobe Experience Platform Mobile SDK - översikt"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" title="Adobe Experience Platform Mobile SDK - översikt">Adobe Experience Platform Mobile SDK - översikt</a>
                    </p>
                    <p class="is-size-6">Läs om hur Adobe Experience Platform Mobile SDK kan skapa ett heltäckande engagemang i era mobilapplikationer.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement Adobe Experience Cloud in mobile apps tutorial">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/overview" title="Implementera Adobe Experience Cloud i mobilappar, genomgång" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="Implementera Adobe Experience Cloud i mobilappar, genomgång"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="Implementera Adobe Experience Cloud i mobilappar, genomgång">Implementera Adobe Experience Cloud i mobilappar, självstudiekurs</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du implementerar Adobe Experience Cloud mobilappar. Den här självstudiekursen vägleder dig genom en implementering av Experience Cloud-program i ett exempel på ett Swift- eller Android-program.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Läs mer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK Documentation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/mobile" title="Dokumentation om mobilt SDK för Adobe Experience Platform" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://cdn.experienceleague.adobe.com/thumb/exl-cards/documentation.png" alt="Dokumentation om mobilt SDK för Adobe Experience Platform"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/mobile" target="_blank" rel="referrer" title="Dokumentation om mobilt SDK för Adobe Experience Platform">Adobe Experience Platform Mobile SDK Documentation</a>
                    </p>
                    <p class="is-size-6">Sök efter självhjälpsartiklar och självstudiekurser i mobila SDK:er för Experience Platform. Lär dig strategier och metodtips från experter via videoevent i realtid och på begäran.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/mobile" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Läs mer</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

Mer information finns också i [Adobe Experience Platform Mobile SDK Documentation](https://experienceleague.adobe.com/sv/docs/mobile)

#### Utvecklarreferenser:

- [Mobile SDK developer portal (home)](https://developer.adobe.com/client-sdks/home/)
- [Aktuella SDK-versioner](https://developer.adobe.com/client-sdks/home/current-sdk-versions/)
- [Komma igång med en mobil egenskap (taggar)](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)
- [Hämta SDK (installera i din app)](https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/)
- [Spåra händelser med Mobile SDK](https://developer.adobe.com/client-sdks/home/getting-started/track-events/)
- [Validera med Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/)

#### Kontrollista för beredskap för mobila SDK

> - [ ] Core SDK är installerat (Core, Edge, Identity, Consent, Assurance).
> - [ ] Journey Optimizer-mobiltillägg har lagts till för de kanaler du vill använda (push, in-app, innehållskort, kodbaserat).
> - [ ] Datastream är korrekt konfigurerad för händelse- och profildatauppsättningar.
> - [ ] Identitet och samtycke implementerat och validerat med Assurance.
> - [ ] Överför tokenregistrering och spårning validerat från början till slut.
> - [ ] In-app och/eller innehållskort visas verifierade på en enhet.
> - [ ] Guidad kanalkonfiguration används för nya implementeringar, eller konfigurationen justeras manuellt efter dokumenterade steg.



## Adobe Journey Optimizer Channel Configuration

### In-App, Push och WhatsApp

Konfigurera dina **mobila kanaler** med hjälp av funktionen för konfiguration av guidade kanaler. Lär dig hur du konfigurerar **whatsApp-kanalen**:

<!-- CARDS
* https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup
 {description = Learn how to quickly set up and validate web and mobile channels across Experience Platform, Journey Optimizer, and Data Collection, and configure a push notification for a sample iOS marketing app.}
* https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Guided channel setup">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" title="Inställningar för guidad kanal" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3433053/?format=jpeg&nocache=1763594622823" alt="Inställningar för guidad kanal"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" title="Inställningar för guidad kanal">Inställningar för guidad kanal</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du snabbt konfigurerar och validerar webb- och mobilkanaler i Experience Platform, Journey Optimizer och Data Collection, och konfigurerar ett push-meddelande för ett iOS-marknadsföringsprogram.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="Konfigurera WhatsApp-kanalen" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470268/?format=jpeg&nocache=1763594622814" alt="Konfigurera WhatsApp-kanalen"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" title="Konfigurera WhatsApp-kanalen">Konfigurera WhatsApp-kanalen</a>
                    </p>
                    <p class="is-size-6">I den här självstudiekursen får du hjälp med att konfigurera WhatsApp-kanalen i Adobe Journey Optimizer så att du kan skapa affärsmeddelanden i realtid.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### SMS/MMS/RCS

Konfigurera **SMS/MMS/RCS-kanaler** med standardleverantörer (Twilio, Synch eller Infobip) eller med en anpassad SMS-provider:

<!-- CARDS
* https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
* https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
{description = Learn how to configure custom SMS providers in Journey Optimizer, set up API credentials and webhooks, manage opt-in/opt-out keywords, and launch personalized campaigns.}
* https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces
* https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure SMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="Konfigurera SMS API-autentiseringsuppgifter och kanalytor" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3413355?format=jpeg&nocache=1763594624036" alt="Konfigurera SMS API-autentiseringsuppgifter och kanalytor"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="Konfigurera SMS API-autentiseringsuppgifter och kanalytor">Konfigurera SMS API-autentiseringsuppgifter och kanalytor</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du ansluter Journey Optimizer till en SMS-tjänsteleverantör och hur du skapar en SMS-kanal.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure a custom SMS provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" title="Konfigurera en anpassad SMS-provider" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1763594624067" alt="Konfigurera en anpassad SMS-provider"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" title="Konfigurera en anpassad SMS-provider">Konfigurera en anpassad SMS-provider</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du konfigurerar anpassade SMS-leverantörer i Journey Optimizer, konfigurerar API-autentiseringsuppgifter och webhooks, hanterar nyckelord för anmälan/avanmälan och startar personaliserade kampanjer.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure MMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="Konfigurera MMS API-autentiseringsuppgifter och kanalytor" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3428872/?format=jpeg&nocache=1763594624083" alt="Konfigurera MMS API-autentiseringsuppgifter och kanalytor"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" title="Konfigurera MMS API-autentiseringsuppgifter och kanalytor">Konfigurera MMS API-autentiseringsuppgifter och kanalytor</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du ansluter Journey Optimizer till en MMS-tjänsteleverantör och hur du skapar en MMS-kanalyta.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up RCS in Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" title="Konfigurera RCS i Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464755/?format=jpeg&nocache=1763594624043" alt="Konfigurera RCS i Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" title="Konfigurera RCS i Journey Optimizer">Konfigurera RCS i Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du konfigurerar och skickar varumärkesanpassade, interaktiva RCS-meddelanden i Adobe Journey Optimizer med en anpassad SMS-leverantör. Den här självstudiekursen går igenom hur du ställer in API-inloggningsuppgifter, webhooks och kanalkonfigurationer och sedan skapar en resa för att leverera avancerade, personaliserade meddelandeupplevelser - allt inifrån programmet för interna meddelanden.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Blogginlägg

- [Använder CDN-baserad klientsidans personalisering (ODD) på mobilen för snabbare personalisering.](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626)
- [Mobile Activation för Adobe Experience Cloud](https://experienceleaguecommunities.adobe.com/t5/adobe-target-blogs/mobile-activation-for-adobe-experience-cloud/ba-p/541595)

## Säkerställ att integritetslagstiftningen och plattformens riktlinjer följs.

<!-- CARDS
* https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/privacy/privacy-landing-page{image=../mobile-learning-hub/assets/privacy.webp}{title = Privacy Features in Adobe Journey Optimizer}{description = Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.}
* https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework
* https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables{cta = Watch}
* https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Privacy Features in Adobe Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/privacy/privacy-landing-page" title="Sekretessfunktioner i Adobe Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../mobile-learning-hub/assets/privacy.webp" alt="Sekretessfunktioner i Adobe Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Sekretessfunktioner i Adobe Journey Optimizer">Sekretessfunktioner i Adobe Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du hanterar sekretessförfrågningar, granskar användaråtgärder, hanterar samtycke, tillämpar styrningsregler och använder avancerade säkerhetsalternativ som kundhanterade nycklar.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Läs mer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Data Governance Framework Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" title="Datastyrningsramverk - översikt" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29708/?format=jpeg&nocache=1763594624934" alt="Datastyrningsramverk - översikt"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" title="Datastyrningsramverk - översikt">Datastyrningsramverk - översikt</a>
                    </p>
                    <p class="is-size-6">Förstå styrningsfunktionerna i Adobe Experience Platform.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Classify data using labels">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" title="Klassificera data med etiketter" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29709?format=jpeg&nocache=1763594624932" alt="Klassificera data med etiketter"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" title="Klassificera data med etiketter">Klassificera data med etiketter</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du använder etiketter i dina scheman och datauppsättningar.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create Data Usage Policies">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" title="Skapa dataanvändningsprinciper" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32977/?format=jpeg&nocache=1763594624933" alt="Skapa dataanvändningsprinciper"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" title="Skapa dataanvändningsprinciper">Skapa dataanvändningsprinciper</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du skapar och hanterar principer för dataanvändning.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Gemensamma implementeringsklyftor och hur man undviker dem

De flesta mobilproblem har sitt ursprung i **SDK eller datainsamlingskonfigurationen**, inte i Journey Optimizer resor eller kampanjer. Använd tabellen nedan för att identifiera vad som går fel och expandera sedan motsvarande avsnitt för mer information.

### Översikt över fallgropar

| # | Problem/symtom | Vanligt fallgrop | Snabbkorrigera |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | Inställningen av den guidade kanalen misslyckas; ingen eller låg trafik | [SDK-versioner eller tillägg är inte justerade](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | Uppdatera SDK-/tilläggsversioner; validera i Assurance |
| 2 | Spårning av batchar misslyckas; fel i AEP | [Felkonfigurerade dataströmmar eller datauppsättningar](#2-misconfigured-datastreams-or-datasets) | Mappa händelser till händelsedatamängd och profiler till profildatamängd |
| 3 | Resor avfyras inte; udda personalisering | [Identitet eller samtycke saknas/är inkonsekvent](#3-missing-or-inconsistent-identity-and-consent) | Implementera Edge Identity &amp; Consent; verifiera i Assurance |
| 4 | Ingen push-leverans eller öppnas i rapporter | [Push-tokenregistrering eller spårning bruten](#4-push-token-registration-and-tracking-not-wired-correctly) | Korrigera tokenregistrering och interaktionsspårning via SDK |
| 5 | Inga appintryck trots aktiva kampanjer | [Meddelanden i appen eller innehållskort visas inte](#5-in-app-messages-or-content-cards-not-displaying) | Kontrollera meddelandetillägg, utlösare och Assurance beslutssvar |

### Detaljerad vägledning per fallgrop

Öppna fallstudien som matchar dina symtom för att se vad du ska kontrollera och hur du ska åtgärda den.

<details id="1-sdk-versions-and-extensions-not-aligned-with-channel-requirements">
<summary><strong>1. SDK-versioner och tillägg är inte justerade mot kanalkraven </strong></summary>

**Vad du kommer att märka**

- Push- eller in-app-aktiviteter når inte enheten.
- Guidad kanalkonfiguration eller kanalvalidering misslyckas.
- Assurance visar saknade Journey Optimizer-, Edge- eller Identity-tillägg.

**Vad du ska kontrollera**

- Använder du de lägsta **Mobile Core**- och **Journey Optimizer**-tilläggsversionerna som krävs för installationen av den guidade kanalen?
- I **Assurance**, under tillägg och händelser:
   - Ser du de förväntade tilläggen inlästa?
   - Skickas event till Edge Network och bekräftas?

**Så här korrigerar du**

- Uppgradera till Mobile SDK och Journey Optimizer som stöds.
- Bygg om appen, återanslut till Assurance och kör installationsprogrammet för den guidade kanalen igen.

Se: [Konfigurera mobil och webb](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config)

</details>


<details id="2-misconfigured-datastreams-or-datasets">
<summary><strong>2. Felkonfigurerade datastölar eller datauppsättningar </strong></summary>

**Vad du kommer att märka**

- Händelser eller grupper för push-spårning misslyckas i plattformsdatauppsättningar.
- Fel vid dataöverföring (t.ex.&quot;Uppdateringar stöds inte för händelser&quot;).
- Push- eller in-app-rapporter visar liten eller ingen spårning.

**Vad du ska kontrollera**

- Har någon ändrat **systemscheman eller datauppsättningar** som skapats för Journey Optimizer tracking?
- I din **datastream**:
   - Mappas upplevelsehändelser till en **händelsedatamängd**?
   - Mappas profilattribut till en **profildatamängd**?

**Så här korrigerar du**

- Redigera inte systemdatauppsättningar/scheman som skapats av AJO.
- Korrigera datastream-mappningen (händelser → händelsedatamängd, profiler → profildatamängd).
- Använd Guidad kanalkonfiguration eller dokumenterade datastream-steg i stället för ad hoc-ändringar.

Se: [Push Notification flow in Adobe Journey Optimizer](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="3-missing-or-inconsistent-identity-and-consent">
<summary><strong>3. Identitet och samtycke saknas eller är inkonsekvent </strong></summary>

**Vad du kommer att märka**

- Resorna utlöses inte som förväntat för appanvändare.
- Personalization matchar inte användarens beteende i andra kanaler.
- Händelser visas i Experience Platform, men profiler ser fragmenterade ut.

**Vad du ska kontrollera**

- Är **Identitet för Edge Network** implementerat och skickar ett stabilt primärt ID (till exempel inloggnings-ID)?
- Är **Medgivande för Edge Network** implementerat och uppdaterat när inställningarna ändras?
- I **Assurance**:
   - Inkluderar utgående händelser medgivandevärden?
   - Inkluderar de ECID och dina primära ID:n konsekvent?

**Så här korrigerar du**

- Implementera eller korrigera **Identitet för Edge Network** i appen.
- Implementera **Godkännande för Edge Network** och anslut det till gränssnittet för godkännande för din app.
- Testa om i Assurance tills identitet och samtycke visas för alla relevanta händelser.

Se: [Implementera medgivande för SDK-implementeringar för plattformsmobiler](https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/app-implementation/consent)

</details>


<details id="4-push-token-registration-and-tracking-not-wired-correctly">
<summary><strong>4. Registrering och spårning av push-token har inte kopplats korrekt</strong></summary>

**Vad du kommer att märka**

- Användarna får aldrig push-meddelanden, trots att kampanjer eller resor körs.
- Push-rapporter visar inga öppningar, avbrott eller interaktioner.

**Vad du ska kontrollera**

- Registrerar appen push-token med Journey Optimizer-tillägget:
   - Vid första installationen?
   - Efter varje appuppdatering?
   - När operativsystemet uppdaterar token?
- När en användare öppnar eller stänger ett meddelande, visas spårningshändelser i Assurance?

**Så här korrigerar du**

- Lägg till eller korrigera koden som:
   - Registrerar token via Journey Optimizer mobiltillägg när den skapas eller uppdateras.
   - Skickar push-interaktionshändelser (öppna, stänga, anpassa åtgärder) via Mobile SDK.
- Använd Assurance för att bekräfta att registrerings- och spårningshändelser utlöses som förväntat.

Se: [Push Notification flow in Adobe Journey Optimizer](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="5-in-app-messages-or-content-cards-not-displaying">
<summary><strong>5. Meddelanden i appen eller innehållskort visas inte </strong></summary>

**Vad du kommer att märka**

- Meddelanden i appen eller innehållskort visas aldrig, trots aktiva kampanjer eller resor.
- Rapporten visar 0 visningar.

**Vad du ska kontrollera**

- Är **Journey Optimizer-mobilmeddelandefunktionen/tillägget i appen** och **meddelandefunktionen i SDK** installerade och registrerade i appen?
- I din **tags**-konfiguration:
   - Har du regler som utlöser begäranden för rätt händelser (till exempel skärmvyer eller anpassade händelser)?
- I **Assurance**:
   - När de här händelserna utlöses, ser du att begäranden om beslut i appen eller på innehållskortet går ut?
   - Ser du svar från Edge Network?

**Så här korrigerar du**

- Installera och registrera de meddelandetillägg som krävs.
- Lägg till eller korrigera regler som utlöser beslut för målhändelser (skärmar, anpassade händelser).
- För innehållskort måste du se till att:
   - Hämta kort via Messaging SDK API:er.
   - Rendera dem i användargränssnittet.
   - Spåra interaktioner via SDK.

Se:
- [Skapa och skicka meddelanden i appen](https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp)
- [Konfigurera stöd för innehållskort i Mobile SDK](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp)

</details>


## Kontrollista för enradig beredskap

Innan du skickar appen till marknadsförarna måste du bekräfta följande i **[Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/)**:

- Core SDK + Journey Optimizer-tilläggen är inlästa,
- Händelser flödar på rätt dataström och datauppsättningar,
- Identitet och samtycke finns för alla viktiga händelser,
- Push-tokens och interaktioner spåras, och
- Minst ett testmeddelande eller innehållskort i appen har visats och registrerats som