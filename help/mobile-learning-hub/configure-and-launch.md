---
title: Konfigurera och starta
description: Konfigurera mobilkanalerna i Adobe Journey Optimizer (AJO) och Adobe Experience Platform (AEP), integrera med mobilappar och se till att ni är redo att genomföra marknadsföringskampanjer.
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: false
index: true
last-substantial-update: 2025-12-18T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: eab42c39d0e7b105ef36e2e2337539511f91440d
workflow-type: tm+mt
source-wordcount: '2148'
ht-degree: 0%

---


# Konfigurera och starta

För **administratörer** och **mobilappsutvecklare** visar det här avsnittet hur du konfigurerar och startar mobil- och webbkanaler i Adobe Journey Optimizer. Det innehåller förutsättningar, behörigheter och plattformsstöd och guidar dig sedan genom att skapa programspecifika konfigurationer.

>[!IMPORTANT]
>
> Om du inte har använt Journey Optimizer eller Experience Platform tidigare bör du bekanta dig med grundläggande datahantering i Journey Optimizer genom att gå den här kursen: [Ingenjörsdata för intelligent reseaktivering i Adobe Journey Optimizer](https://experienceleague.adobe.com/en/courses/ajo-engineer-data-for-intelligent-journey-activation){target="_blank"}
>


## Mobilfunktioner i Adobe Journey Optimizer

Förstå vilka mobilfunktioner Adobe Journey Optimizer erbjuder för utvecklare, marknadsförare och produktteam, inklusive push-meddelanden, meddelanden i appen och innehållspersonalisering.

>[!VIDEO](https://video.tv.adobe.com/v/342103?quality=12&learn=on){transcript=true}


## Kanalkonfiguration

### Mobilpush och appar

Mobilimplementeringar i Journey Optimizer börjar med **Adobe Experience Platform Mobile SDK** -integreringen i din app. SDK är nödvändigt för datainsamling och interaktion med Adobe Experience Platform (AEP) och dess program, till exempel Adobe Journey Optimizer (AJO).

#### Vad är Mobile SDK?

Mobilt SDK:

- Samlar in apphändelser (skärmvyer, kraschar, köp, livscykelhändelser osv.) och skickar dem till **Adobe Experience Platform Edge Network**.
- Hanterar **identitet** och **samtycke** så att Journey Optimizer kan skapa och använda kundprofiler på ett säkert sätt.
- Registrerar och uppdaterar **push-tokens** och skickar **push- och in-app tracking-händelser** tillbaka till Adobe Experience Platform.
- Integreras med **[Journey Optimizer-mobiltillägget](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer)** så att meddelanden kan levereras, återges och mätas från början till slut.

Utan Mobile SDK som är integrerad i appen kan Journey Optimizer inte på ett tillförlitligt sätt:

- Leverera och spåra mobilmeddelanden och meddelanden i appen.
- Återge och spåra innehållskort.
- Använd beteenden i realtid i appen för att utlösa resor och personalisera upplevelser.

#### Inställningar av guidade kanaler för nya implementeringar

För nya mobilimplementeringar i appen och push-implementeringar är Guidad kanalkonfiguration den rekommenderade startpunkten. Det minskar risken för felkonfigurerade datastreams eller saknade tillägg och leder dig igenom SDK-valideringen med Assurance.

>[!PREREQUISITES]
>
>Kontrollera att du har:
>
> - **Adobe Journey Optimizer** (AJO) har etablerats för din organisation.
> - Adobe Experience Platform har åtkomst med [Datainsamling och Journey Optimizer-behörigheter](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config#:~:text=Required%20permissions).
> - Administratörsrättigheter i AJO för konfigurering av kanaler och konfigurationer.
> - Tillgång till mobilappens källkod (iOS, Android eller ramverk för flera plattformar).
> - Appen har de nödvändiga funktionerna på operativsystemnivå aktiverade (till exempel push-behörigheter, meddelandetjänsttillägg och bakgrundslägen).
> - Om du använder det befintliga konfigurationsalternativet måste du kontrollera att du använder de [aktuella Adobe Experience Platform Mobile SDK-versionerna](https://developer.adobe.com/client-sdks/home/current-sdk-versions/){target="_blank"}


>[!VIDEO](https://video.tv.adobe.com/v/3433053/?learn=on)

Mer information finns i [Kom igång med konfiguration av guidade kanaler](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config.html){target="_blank"}


#### Manuell konfiguration av push-kanalen

Här följer handledningar som visar allt du behöver för att manuellt konfigurera och använda push-meddelanden effektivt, från att förstå dataflödet och integrera med tjänster som Firebase och Apple Push Notification Service (APN) till att konfigurera mobilappar och testmeddelanden.

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs
{title = Push notification data flow and components}
{description = Learn how to setup and understand key services and workflows involved with push notifications in Journey Optimizer.}
{image = https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1f6e99fa57e318230d92f5dde619c450690b5d27a.png?width=2000&format=webply&optimize=medium}
{target = _blank}

* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration
{image = https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1134ddf9b0f7d39bb365d4884a1d603fd4aa5bbdf.png?width=2000&format=webply&optimize=small}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview 
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Push notification data flow and components">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs" title="Dataflöde och komponenter för push-meddelanden" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1f6e99fa57e318230d92f5dde619c450690b5d27a.png?width=400&format=webply&optimize=medium" alt="Dataflöde och komponenter för push-meddelanden"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs" target="_blank" rel="referrer" title="Dataflöde och komponenter för push-meddelanden">Dataflöde och komponenter för push-meddelanden</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du konfigurerar och förstår viktiga tjänster och arbetsflöden som rör push-meddelanden i Journey Optimizer.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Läs mer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Push notification configuration">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration" title="Konfiguration för push-meddelanden" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1134ddf9b0f7d39bb365d4884a1d603fd4aa5bbdf.png?width=400&format=webply&optimize=small" alt="Konfiguration för push-meddelanden"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration" target="_blank" rel="referrer" title="Konfiguration för push-meddelanden">Konfiguration för push-meddelanden</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du konfigurerar miljön för att skicka push-meddelanden med Journey Optimizer</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Läs mer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement Adobe Experience Cloud in mobile apps tutorial">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview" title="Implementera Adobe Experience Cloud i mobilappar, genomgång" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="Implementera Adobe Experience Cloud i mobilappar, genomgång"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="Implementera Adobe Experience Cloud i mobilappar, genomgång">Implementera Adobe Experience Cloud i mobilappar, självstudiekurs</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du implementerar Adobe Experience Cloud mobilappar. Den här självstudiekursen vägleder dig genom en implementering av Experience Cloud-program i ett exempel på ett Swift- eller Android-program.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Läs mer</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### Ytterligare resurser


<!-- CARDS
* https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk
{target = _blank}
* https://developer.adobe.com/client-sdks/home/base/assurance
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Get the Adobe Experience Platform Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" title="Skaffa Adobe Experience Platform Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Skaffa Adobe Experience Platform Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" target="_blank" rel="referrer" title="Skaffa Adobe Experience Platform Mobile SDK">Skaffa Adobe Experience Platform Mobile SDK</a>
                    </p>
                    <p class="is-size-6">En guide som förklarar hur du installerar Adobe Experience Platform Mobile SDK i ditt program.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Läs mer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Assurance overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/base/assurance" title="Adobe Experience Platform Assurance - översikt" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Adobe Experience Platform Assurance - översikt"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" title="Adobe Experience Platform Assurance - översikt">Adobe Experience Platform Assurance - översikt</a>
                    </p>
                    <p class="is-size-6">En översikt för Adobe Experience Platform Assurance mobiltillägg.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Läs mer</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### Kontrollista för beredskap för mobila SDK

Innan du skickar appen till marknadsförarna måste du bekräfta följande i **[Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/){target="_blank"}**:

>[!SUCCESS]
> 
> [ ] Core SDK + Journey Optimizer-tillägg har lästs in,\
> [ ] händelser flödar på rätt dataström och datauppsättningar,\
> [ ]Identitet och samtycke finns för alla viktiga händelser,\
> [ ] push-tokens och interaktioner spåras, och\
> [ ] Minst ett meddelande eller innehållskort i appen har visats och registrerats som ett intryck.


### Innehållskort

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp
{title = Configure content cards support in Mobile SDK}
{description = Learn how to integrate content cards in your mobile application using Messaging SDK.}
{image = https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/media_17623afb1c5e280b7fb6861b4003d0ef8f8bea24d.jpg?width=2000&format=webply&optimize=medium}
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure content cards support in Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" title="Konfigurera stöd för innehållskort i Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/media_17623afb1c5e280b7fb6861b4003d0ef8f8bea24d.jpg?width=400&format=webply&optimize=medium" alt="Konfigurera stöd för innehållskort i Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" target="_blank" rel="referrer" title="Konfigurera stöd för innehållskort i Mobile SDK">Konfigurera stöd för innehållskort i Mobile SDK</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du integrerar innehållskort i din mobilapp med Messaging SDK.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Läs mer</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### WhatApp

Lär dig hur du konfigurerar **whatsApp-kanalen**:

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="Konfigurera WhatsApp-kanalen" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470268/?format=jpeg&nocache=1765310599408" alt="Konfigurera WhatsApp-kanalen"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" title="Konfigurera WhatsApp-kanalen">Konfigurera WhatsApp-kanalen</a>
                    </p>
                    <p class="is-size-6">I den här självstudiekursen får du hjälp med att konfigurera WhatsApp-kanalen i Adobe Journey Optimizer så att du kan skapa affärsmeddelanden i realtid.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
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
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
{description = Learn how to configure custom SMS providers in Journey Optimizer, set up API credentials and webhooks, manage opt-in/opt-out keywords, and launch personalized campaigns.}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure SMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="Konfigurera SMS API-autentiseringsuppgifter och kanalytor" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3413355?format=jpeg&nocache=1765310599850" alt="Konfigurera SMS API-autentiseringsuppgifter och kanalytor"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="Konfigurera SMS API-autentiseringsuppgifter och kanalytor">Konfigurera SMS API-autentiseringsuppgifter och kanalytor</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du ansluter Journey Optimizer till en SMS-tjänsteleverantör och hur du skapar en SMS-kanal.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure a custom SMS provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" title="Konfigurera en anpassad SMS-provider" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1765310599834" alt="Konfigurera en anpassad SMS-provider"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" title="Konfigurera en anpassad SMS-provider">Konfigurera en anpassad SMS-provider</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du konfigurerar anpassade SMS-leverantörer i Journey Optimizer, konfigurerar API-autentiseringsuppgifter och webhooks, hanterar nyckelord för anmälan/avanmälan och startar personaliserade kampanjer.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure MMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="Konfigurera MMS API-autentiseringsuppgifter och kanalytor" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3428872/?format=jpeg&nocache=1765310599863" alt="Konfigurera MMS API-autentiseringsuppgifter och kanalytor"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" title="Konfigurera MMS API-autentiseringsuppgifter och kanalytor">Konfigurera MMS API-autentiseringsuppgifter och kanalytor</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du ansluter Journey Optimizer till en MMS-tjänsteleverantör och hur du skapar en MMS-kanalyta.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up RCS in Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" title="Konfigurera RCS i Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464755/?format=jpeg&nocache=1765310600192" alt="Konfigurera RCS i Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" title="Konfigurera RCS i Journey Optimizer">Konfigurera RCS i Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du konfigurerar och skickar varumärkesanpassade, interaktiva RCS-meddelanden i Adobe Journey Optimizer med en anpassad SMS-leverantör. Den här självstudiekursen går igenom hur du ställer in API-inloggningsuppgifter, webhooks och kanalkonfigurationer och sedan skapar en resa för att leverera avancerade, personaliserade meddelandeupplevelser - allt inifrån programmet för interna meddelanden.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Säkerställ att integritetslagstiftningen och plattformens riktlinjer följs.

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent
* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page{image=../mobile-learning-hub/assets/privacy.webp}{title = Privacy Features in Adobe Journey Optimizer}{description = Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables
{cta = Watch}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement consent for Platform Mobile SDK implementations">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent" title="Implementera medgivande för implementeringar av SDK för plattformsmobiler" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent./media_12356d2400b5ad641e8356a6883441b38a129c968.png?width=400&format=png&optimize=medium" alt="Implementera medgivande för implementeringar av SDK för plattformsmobiler"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent" target="_blank" rel="referrer" title="Implementera medgivande för implementeringar av SDK för plattformsmobiler">Implementera medgivande för SDK-implementeringar för plattformsmobiler</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du implementerar samtycke i en mobilapp.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Läs mer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Privacy Features in Adobe Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page" title="Sekretessfunktioner i Adobe Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../mobile-learning-hub/assets/privacy.webp" alt="Sekretessfunktioner i Adobe Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Sekretessfunktioner i Adobe Journey Optimizer">Sekretessfunktioner i Adobe Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du hanterar sekretessförfrågningar, granskar användaråtgärder, hanterar samtycke, tillämpar styrningsregler och använder avancerade säkerhetsalternativ som kundhanterade nycklar.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Läs mer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Data Governance Framework Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" title="Datastyrningsramverk - översikt" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29708/?format=jpeg&nocache=1765310600883" alt="Datastyrningsramverk - översikt"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" title="Datastyrningsramverk - översikt">Datastyrningsramverk - översikt</a>
                    </p>
                    <p class="is-size-6">Förstå styrningsfunktionerna i Adobe Experience Platform.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Classify data using labels">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" title="Klassificera data med etiketter" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29709?format=jpeg&nocache=1765310600887" alt="Klassificera data med etiketter"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" title="Klassificera data med etiketter">Klassificera data med etiketter</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du använder etiketter i dina scheman och datauppsättningar.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Bevakning</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create Data Usage Policies">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" title="Skapa dataanvändningsprinciper" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32977/?format=jpeg&nocache=1765310600676" alt="Skapa dataanvändningsprinciper"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" title="Skapa dataanvändningsprinciper">Skapa dataanvändningsprinciper</a>
                    </p>
                    <p class="is-size-6">Lär dig hur du skapar och hanterar principer för dataanvändning.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
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

+++ &#x200B;1. SDK-versioner och tillägg som inte är anpassade efter kanalkraven
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

Se: [Konfigurera mobil och webb](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config){target="_blank"}

+++

+++ &#x200B;2. Felkonfigurerade datastreams eller datamängder
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

Se: [Push Notification flow in Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

+++

+++ &#x200B;3. Identitet och samtycke saknas eller är inkonsekvent
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

Se: [Implementera medgivande för SDK-implementeringar för plattformsmobiler](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent){target="_blank"}

+++

+++ &#x200B;4. Korrigera tokenregistrering och -spårning inte korrekt kastats
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

Se: [Push Notification flow in Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

+++

+++ &#x200B;5. Meddelanden i appen eller innehållskort visas inte
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
- [Skapa och skicka meddelanden i appen](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp){target="_blank"}
- [Konfigurera stöd för innehållskort i Mobile SDK](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp){target="_blank"}

+++

## Ytterligare resurser

- [Använder CDN-baserad klientsidans personalisering (ODD) på mobilen för snabbare personalisering (Blog)](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626){target="_blank"}
- [Hemligheten till nästa nivå av mobilappsengagemang och tillväxt (Summit Session)](https://business.adobe.com/summit/2025/sessions/the-secret-to-nextlevel-mobile-app-engagement-s603.html)
