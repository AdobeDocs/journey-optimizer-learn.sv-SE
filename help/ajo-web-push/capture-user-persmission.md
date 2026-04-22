---
title: Inhämta användarbehörighet
description: Skapa en webbsida för att fånga användarens samtycke till att ta emot push-meddelanden.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Inhämta användarbehörighet

Den här webbsidan innehåller användarens samtycke till att ta emot push-meddelanden. Användaren uppmanas att aktivera meddelanden med webbläsarens Notifications API och registrerar sedan push-prenumerationen hos Adobe Experience Platform med hjälp av Web SDK när den godkänts. Detta garanterar att endast användare som har valts in kan få push-meddelanden via kampanjer och resor i Adobe Journey Optimizer.

Om du vill aktivera push-meddelanden på webben läser sidan först in en konfigurationsfil genom att anropa fetch(&quot;/config&quot;) inuti en initieringsfunktion. Den här konfigurationen hanteras av ett Node.js-program och innehåller nyckelvärden som datastream-ID, organisations-ID, offentlig VAPID-nyckel, program-ID och datauppsättnings-ID för spårning. När konfigurationen har lästs in initieras Adobe Web SDK och servicearbetaren registreras för att stödja push-meddelanden. När en användare klickar på Aktivera meddelanden ber webbläsaren dem om behörighet med API:t för webbmeddelanden. Om tillstånd beviljas skickar Web SDK push-prenumerationen till Adobe Experience Platform och användaren markeras som inloggad i 24 timmar för att undvika upprepade uppmaningar. Du kan testa det här flödet på den lokala webbsidan shop-smart.html som ingår i [exempelprogrammet](http://localhost:3000/) när du har startat servern.

![request-permissions](assets/request-notifications.png)

