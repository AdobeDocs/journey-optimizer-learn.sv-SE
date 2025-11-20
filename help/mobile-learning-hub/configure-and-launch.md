---
title: Konfigurera och starta
description: Konfigurera mobilkanalerna i Adobe Journey Optimizer (AJO) och Adobe Experience Platform (AEP), integrera med mobilappar och säkerställa beredskap för genomförande av marknadsföringskampanjer.
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

Konfigurera mobilkanalerna i Adobe Journey Optimizer och Adobe Experience Platform, integrera med mobilappar och säkerställ beredskap för genomförande av marknadsföringskampanjer.

> **Not**\
> Om du är ny på Journey Optimizer och Experience Platform, bekanta dig med kärnkoncepten genom att gå dessa kurser:
> - [Konfigurera och administrera Adobe Journey Optimizer](https://experienceleague.adobe.com/sv/courses/ajo-configure-and-administrate-ajo-environment)
>*I den här kursen får du lära dig att konfigurera och hantera Journey Optimizer-miljön, inklusive användarroller, behörigheter, sandlådor och e-postkanaler, vilket säkerställer effektiva och säkra åtgärder.*
> - [Ingenjörsdata för intelligent reseaktivering i Adobe Journey Optimizer](https://experienceleague.adobe.com/sv/courses/ajo-engineer-data-for-intelligent-journey-activation)
>*I den här kursen får du lära dig att konfigurera och hantera kundprofildata i realtid för Journey Optimizer med Experience Platform. Förstå datamodellering, identitetsmappning och datainmatning för att skapa enhetliga profiler för personaliserade kundresor.*


## Mobilfunktioner i Adobe Journey Optimizer

Förstå vilka mobilfunktioner Adobe Journey Optimizer erbjuder för utvecklare, marknadsförare och produktteam, inklusive push-meddelanden, meddelanden i appen och innehållspersonalisering.

>[!VIDEO](https://video.tv.adobe.com/v/342103?quality=12&learn=on){transcript=true}


## Konfigurera SDK och appar för mobiler

Mobila implementationer i Journey Optimizer börjar med **Adobe Experience Platform Mobile SDK-integrationen** i din app. SDK:er är avgörande för datainsamling och interaktion med Adobe Experience Platform (AEP) och dess applikationer, såsom Adobe Journey Optimizer (AJO).

Mobila SDK:n:

- Samlar in apphändelser (skärmvyer, tryck, köp, livscykelhändelser etc.) och skickar dem till **Adobe Experience Platform Edge Network**.
- Hanterar **identitet** och **samtycke**, så att Journey Optimizer säkert kan bygga och använda kundprofiler.
- Registrerar och uppdaterar **push-tokens** och skickar **push- och in-app tracking-händelser** tillbaka till Adobe Experience Platform.
- Integreras med **Journey Optimizer mobiltillägg** (push, in-app, innehållskort, beslutsfunktioner) så att meddelanden kan levereras, återges och mätas från början till slut.

Utan Mobile SDK som är integrerad i appen kan Journey Optimizer inte på ett tillförlitligt sätt:

- Leverera och spåra mobilmeddelanden och meddelanden i appen.
- Rendera och spåra innehållskort.
- Använd realtidsbeteende i appen för att trigga resor och personanpassa upplevelser.


### Förhandskrav

Se till att du har:

- Adobe Journey Optimizer (AJO) provisionerad för din organisation.
- Adobe Experience Platform-åtkomst med behörigheter för datainsamling och Journey Optimizer.
- Adminrättigheter i AJO för kanal- och konfigurationsinställningar.
- Tillgång till din mobilapps källkod (iOS, Android eller plattformsoberoende ramverk).
- Din app har de nödvändiga OS-nivåfunktionerna aktiverade (till exempel push-behörigheter, tillägg till notifikationstjänster, bakgrundslägen).


### Nödvändiga Mobile SDK-komponenter för Journey Optimizer

För att använda Journey Optimizers mobilkanaler (push, i appen, innehållskort, kodbaserade upplevelser) måste du installera och konfigurera en uppsättning **kärn-** och **kanalspecifika** tillägg i din mobilapp:

>[!BEGINTABS]

>[!TAB Core]

#### Kärntillägg (krävs för alla mobila användningsfall)

| Avsikt | Exempel på tillägg (iOS / Android) | Anteckningar |
|----------------------|-----------------------------------------------|-------|
| Evenemangsnav och tjänster | Mobilkärna / AEP Kärna, AEP-tjänster | Foundation for all other extensions. Tillhandahåller händelsehubb, nätverk, lagring och delat tillstånd. |
| Edge Network | Adobe Experience Platform Edge Network | Skickar apphändelser till Adobe Experience Platform Edge Network. |
| Identitet | Identitet för Edge Network | Hanterar ECID och andra identiteter som används för profil och segmentering. |
| Samtycke | Samtycke för Edge-nätverk | Samlar in och upprätthåller användarens samtyckespreferenser. |
| Försäkran | Adobe Experience Platform Assurance | Används för att validera och felsöka SDK och kanalkonfiguration från början till slut. |

>[!TAB Kanalspecifik]

#### Kanalspecifika tillägg för Journey Optimizer

| Kanal/kapacitet | Ytterligare nyckeltillägg (ovanpå kärnan) | Vad de aktiverar |
|------------------------|---------------------------------------------------------------------|------------------|
| Push-meddelanden | Journey Optimizer mobiltillägg (push) | Registrera och uppdatera push-tokens, skicka push-spårningshändelser, ansluta till AJO push-konfiguration. |
| Meddelanden i appen | Journey Optimizer mobiltillägg (in-app), meddelandegränssnittskomponenter | Hämta och visa meddelanden i appen i kontext, skicka visningar och interaktionshändelser. |
| Innehållskort | Meddelande-SDK med stöd för innehållskort | Hämta, rendera och spåra innehållskort för korrekt rapportering från Journey Optimizer. |
| Kodbaserade upplevelser | Journey Optimizer/beslutstillägg eller Edge Server API | Hämta beslut om specifika&quot;ytor&quot; i appen; appen styr hur innehåll återges. |

>[!ENDTABS]

#### Egenskaper och konfiguration för mobiltagg

Du konfigurerar dessa tillägg i en **[mobil taggegenskap](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)** i AEP Data Collection (taggar). This property controls:

- Vilka Mobile SDK-tillägg som är installerade.
- Vilka händelser i din app utlöser anrop till Edge Network.
- Hur data mappas till XDM och vidarebefordras till Adobe-lösningar (Journey Optimizer, Analytics, etc.).

Du kan skapa och konfigurera denna mobila egenskap manuellt, eller använda **[Guided Channel Setup](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)** för att automatiskt skapa den nödvändiga taggegenskapen, dataströmmen och kanalkonfigurationen för iOS eller Android.

> **Dricks**\
> För nya implementeringar rekommenderas **[Guided Channel Setup](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)** som startpunkt. Det minskar risken för felkonfigurerade dataströmmar eller saknade tillägg och guidar dig genom SDK-validering med Assurance.

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
                        <a href="https://experienceleague.adobe.com/sv/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" title="Översikt över Adobe Experience Platform Mobile SDK">Översikt över Adobe Experience Platform Mobile SDK</a>
                    </p>
                    <p class="is-size-6">Lär dig hur Adobe Experience Platform Mobile SDK möjliggör end-to-end-engagemang i dina mobilapplikationer.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Klocka</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement Adobe Experience Cloud in mobile apps tutorial">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/overview" title="Implementera Adobe Experience Cloud i mobilappar-handledning" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="Implementera Adobe Experience Cloud i mobilappar-handledning"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="Implementera Adobe Experience Cloud i mobilappar, genomgång">Implementera Adobe Experience Cloud i mobilappar, självstudiekurs</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du implementerar Adobe Experience Clouds mobilapplikationer. Denna handledning guidar dig genom en implementation av Experience Cloud-applikationer i ett exempel på Swift- eller Android-app.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lära sig mer</span>
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lära sig mer</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

För mer information, se även Adobe Experience Platform Mobile SDK-dokumentationen [&#128279;](https://experienceleague.adobe.com/sv/docs/mobile)

#### Utvecklarreferenser:

- [Mobil SDK-utvecklarportal (hem)](https://developer.adobe.com/client-sdks/home/)
- [Nuvarande SDK-versioner](https://developer.adobe.com/client-sdks/home/current-sdk-versions/)
- [Att komma igång med en mobil fastighet (taggar)](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)
- [Hämta SDK:n (installera i din app)](https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/)
- [Följ evenemang med Mobile SDK](https://developer.adobe.com/client-sdks/home/getting-started/track-events/)
- [Validera med Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/)

#### Kontrollista för beredskap för mobila SDK

> - [ ] Core SDK är installerat (Core, Edge, Identity, Consent, Assurance).
> - [ ] Journey Optimizer mobiltillägg har lagts till för de kanaler du kommer att använda (push, i appen, innehållskort, kodbaserat).
> - [ ] Datastream korrekt konfigurerade till händelse- och profildataset.
> - [ ] Identitet och samtycke implementeras och valideras med Assurance.
> - [ ] Överför tokenregistrering och spårning validerat från början till slut.
> - [ ] In-app och/eller innehållskort visas verifierade på en enhet.
> - [ ] Guidad kanaluppsättning som används för nya implementationer, eller konfiguration som manuellt justeras efter de dokumenterade stegen.



## Adobe Journey Optimizer Kanalkonfiguration

### In-app, Push och WhatsApp

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
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" title="Inställningar för guidad kanal">Styrning av kanaler</a>
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
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="Sätt upp WhatsApp-kanalen" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470268/?format=jpeg&nocache=1763594622814" alt="Sätt upp WhatsApp-kanalen"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" title="Konfigurera WhatsApp-kanalen">Konfigurera WhatsApp-kanalen</a>
                    </p>
                    <p class="is-size-6">Denna handledning guidar dig genom att ställa in WhatsApp-kanalen i Adobe Journey Optimizer för att möjliggöra affärsmeddelanden i realtid.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Klocka</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### SMS/MMS/RCS

Konfigurera **SMS/MMS/RCS-kanaler** med standardleverantörerna (Twilio, Synch eller Infobip) eller med en anpassad SMS-leverantör:

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
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="Konfigurera SMS API-uppgifter och kanalytor" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3413355?format=jpeg&nocache=1763594624036" alt="Konfigurera SMS API-uppgifter och kanalytor"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="Konfigurera SMS API-uppgifter och kanalytor">Konfigurera SMS API-uppgifter och kanalytor</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du ansluter Journey Optimizer till en SMS-tjänsteleverantör och hur du skapar en SMS-kanal.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Klocka</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure a custom SMS provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" title="Konfigurera en anpassad SMS-leverantör" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1763594624067" alt="Konfigurera en anpassad SMS-leverantör"
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Klocka</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure MMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="Konfigurera MMS API-uppgifter och kanalytor" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3428872/?format=jpeg&nocache=1763594624083" alt="Konfigurera MMS API-uppgifter och kanalytor"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" title="Konfigurera MMS API-uppgifter och kanalytor">Konfigurera MMS API-uppgifter och kanalytor</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du kopplar Journey Optimizer till en MMS-tjänsteleverantör och hur du skapar en MMS-kanalyta.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Klocka</span>
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
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" title="Ställ in RCS i Journey Optimizer">Ställ in RCS i Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du konfigurerar och skickar varumärkesstyrda, interaktiva RCS-meddelanden i Adobe Journey Optimizer med hjälp av en anpassad SMS-leverantör. Denna handledning går igenom att ställa in API-uppgifter, webhooks och kanalkonfigurationer, och sedan bygga en resa för att leverera rika, personliga meddelandeupplevelser – allt inom den inbyggda meddelandeappen.</p>
                </div>
                <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Klocka</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Blogginlägg

- [Använder CDN-baserad klientbaserad personalisering (ODD) på mobilen för snabbare personaliseringar.](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626)
- [Mobilaktivering för Adobe Experience Cloud](https://experienceleaguecommunities.adobe.com/t5/adobe-target-blogs/mobile-activation-for-adobe-experience-cloud/ba-p/541595)

## Säkerställ efterlevnad av integritetslagar och plattformsriktlinjer.

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
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Sekretessfunktioner i Adobe Journey Optimizer">Integritetsfunktioner i Adobe Journey Optimizer</a>
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
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" title="Översikt av Data Governance Framework" target="_blank" rel="referrer">
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Klocka</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Classify data using labels">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" title="Klassificera data med hjälp av etiketter" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29709?format=jpeg&nocache=1763594624932" alt="Klassificera data med hjälp av etiketter"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" title="Klassificera data med hjälp av etiketter">Klassificera data med hjälp av etiketter</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du applicerar etiketter på dina scheman och dataset.</p>
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
                    <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" title="Skapa policyer för dataanvändning" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32977/?format=jpeg&nocache=1763594624933" alt="Skapa policyer för dataanvändning"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" title="Skapa policyer för dataanvändning">Skapa dataanvändningsprinciper</a>
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

De flesta mobilproblem uppstår i **SDK- eller datainsamlingskonfiguration**, inte i Journey Optimizer-resorna eller kampanjerna själva. Använd tabellen nedan för att identifiera vad som går fel, och expandera sedan motsvarande sektion för detaljer.

### Fallgropar vid en snabb blick

| # | Problem/symtom | Vanligt fallgrop | Snabbkorrigera |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | Inställningen av den guidade kanalen misslyckas; ingen eller låg trafik | [SDK-versioner eller tillägg är inte justerade](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | Uppdatera SDK-/tilläggsversioner; validera i Assurance |
| 2 | Spårning av batchar misslyckas; fel i AEP | [Dataströmmar eller dataset felkonfigurerade](#2-misconfigured-datastreams-or-datasets) | Kartlägg händelser till händelsedataset och profiler till profildataset |
| 3 | Resor skjuter inte; Udda personalisering | [Identitet eller samtycke saknas / inkonsekvent](#3-missing-or-inconsistent-identity-and-consent) | Implementera Edge-identitet och samtycke; verifiera i Assurance |
| 4 | Ingen push-leverans eller öppningar i rapporter | [Push-tokenregistrering eller spårning brutet](#4-push-token-registration-and-tracking-not-wired-correctly) | Fixa tokenregistrering och interaktionsspårning via SDK |
| 5 | Inga appintryck trots aktiva kampanjer | [Meddelanden i appen eller innehållskort visas inte](#5-in-app-messages-or-content-cards-not-displaying) | Kontrollera meddelandetillägg, utlösare och Assurance beslutssvar |

### Detaljerad vägledning per fallgrop

Öppna fallgropen som matchar dina symtom för att se vad du ska kontrollera och hur du kan åtgärda det.

<details id="1-sdk-versions-and-extensions-not-aligned-with-channel-requirements">
<summary><strong>1. SDK-versioner och tillägg som inte är anpassade till kanalkraven</strong></summary>

**Vad du kommer att märka**

- Push- eller in-app-aktiviteter når inte enheten.
- Guidad kanalkonfiguration eller kanalvalidering misslyckas.
- Assurance visar att Journey Optimizer, Edge eller Identity-tillägg saknas.

**Vad du ska kontrollera**

- Använder du de lägsta **Mobile Core**- och **Journey Optimizer**-tilläggsversionerna som krävs för installationen av den guidade kanalen?
- I **Assurance**, under tillägg och händelser:
   - Ser du de förväntade tilläggen inlästa?
   - Skickas event till Edge Network och bekräftas?

**Hur man fixar**

- Uppgradera till de stödda versionerna Mobile SDK och Journey Optimizer.
- Bygg om appen, återanslut till Assurance och kör Guided Channel Setup igen.

Se: [Ställa upp mobil och webb](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config)

</details>


<details id="2-misconfigured-datastreams-or-datasets">
<summary><strong>2. Felkonfigurerade dataströmmar eller datamängder</strong></summary>

**Vad du kommer att märka**

- Händelser eller push-tracking batchar misslyckas i plattformsdatamängder.
- Fel vid datainsamling (till exempel, &quot;Uppdateringar stöds inte för händelser&quot;).
- Push- eller in-app-rapporter visar lite eller ingen spårning.

**Vad ska man kolla**

- Har någon ändrat **systemscheman eller datauppsättningar** som skapats för Journey Optimizer tracking?
- I din **dataström**:
   - Mappas upplevelsehändelser till en **händelsedataset**?
   - Mappas profilattribut till en **profildataset**?

**Hur man fixar**

- Redigera inte systemdataset/scheman skapade av AJO.
- Korrigera dataströmskartläggningen (händelser → händelsedataset, profiler → profildataset).
- Föredra guidad kanaluppsättning eller de dokumenterade dataströmsstegen istället för ad hoc-ändringar.

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
- I **försäkring:**
   - Inkluderar utgående händelser medgivandevärden?
   - Inkluderar de ECID och dina primära ID:n konsekvent?

**Så här korrigerar du**

- Implementera eller korrigera **Identitet för Edge Network** i appen.
- Implementera **Godkännande för Edge Network** och anslut det till gränssnittet för godkännande för din app.
- Testa om i Assurance tills identitet och samtycke syns på alla relevanta händelser.

Se: [Implementera samtycke för Platform Mobile SDK-implementationer](https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/app-implementation/consent)

</details>


<details id="4-push-token-registration-and-tracking-not-wired-correctly">
<summary><strong>4. Push-tokenregistrering och spårning är inte korrekt trådbunden</strong></summary>

**Vad du kommer att märka**

- Användare får aldrig pushnotiser, även om kampanjer eller resor pågår.
- Push-rapporter visar inga öppningar, avvisningar eller interaktioner.

**Vad ska man kolla**

- Registrerar appen push-token med Journey Optimizer-tillägget:
   - Vid första installationen?
   - Efter varje appuppdatering?
   - När operativsystemet uppdaterar token?
- När en användare öppnar eller stänger ett meddelande, visas spårningshändelser i Assurance?

**Så här korrigerar du**

- Lägg till eller korrigera koden som:
   - Registrerar token via Journey Optimizer mobiltillägg när den skapas eller uppdateras.
   - Skickar push-interaktionshändelser (öppna, avvisa, anpassade åtgärder) via Mobile SDK.
- Använd Assurance för att bekräfta att registrerings- och spårningshändelser aktiveras som förväntat.

Se: [Push-notifikationsflöde i Adobe Journey Optimizer](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="5-in-app-messages-or-content-cards-not-displaying">
<summary><strong>5. Meddelanden i appen eller innehållskort visas inte </strong></summary>

**Vad du kommer att märka**

- Meddelanden eller innehållskort i appen visas aldrig, trots aktiva kampanjer eller resor.
- Rapporten visar 0 visningar.

**Vad du ska kontrollera**

- Är **Journey Optimizer-mobilmeddelandefunktionen/tillägget i appen** och **meddelandefunktionen i SDK** installerade och registrerade i appen?
- I din **tags**-konfiguration:
   - Har du regler som triggar förfrågningar på rätt händelser (till exempel skärmvyer eller anpassade händelser)?
- I **försäkring:**
   - När dessa händelser aktiveras, ser du att beslutsförfrågningar skickas ut via appen eller innehållskort?
   - Ser du svar komma tillbaka från Edge Network?

**Hur man fixar**

- Installera och registrera de nödvändiga meddelandetilläggen.
- Lägg till eller rätta regler som triggar beslut om dina målhändelser (skärmar, anpassade händelser).
- För innehållskort, se till att du:
   - Hämta kort via Messaging SDK:s API:er.
   - Rendera dem i användargränssnittet.
   - Spåra interaktioner via SDK.

Se:
- [Skapa och skicka meddelanden i appen](https://experienceleague.adobe.com/sv/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp)
- [Konfigurera innehållskort i Mobile SDK](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp)

</details>


## Enradschecklista för beredskap

Innan du lämnar över appen till marknadsförare, bekräfta i **[Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/)** att:

- Core SDK + Journey Optimizer-tillägg är laddade,
- Händelser flödar på rätt dataström och datamängder,
- Identitet och samtycke finns vid alla nyckelhändelser,
- Push-tokens och interaktioner spåras, och
- Minst ett testmeddelande eller innehållskort i appen har visats och registrerats som