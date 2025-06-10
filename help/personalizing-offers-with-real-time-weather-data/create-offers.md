---
title: Skapa erbjudanden för att testa dynamiskt beslutsfattande och rankning.
description: Ett erbjudande i beslut representerar ett enskilt personligt innehåll, till exempel ett meddelande, en bild, en befordran eller en rekommendation, som kan levereras till en användare baserat på definierade regler och villkor.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: c04a15418e31dc82597b7759386907013728bb0d
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---


# Skapa erbjudanden för att testa dynamisk beslutsfattande och rankning

Erbjudandena är utformade för att testa dynamisk beslutsfattande och rankning baserat på sammanhangsberoende indata i realtid (som temperatur) som skickas via Adobe Web SDK (alloy(&quot;sendEvent&quot;)).

Schemat för erbjudanden utökades till att omfatta ett nytt fält: offerText innan erbjudandena skapades

![offer-schema](assets/offer-schema.png).

Skapa följande 3 erbjudanden


## Hot Weather Offer(Tag:hot)

Erbjudandetext för heta vädererbjudanden

```html
<div data-tags="weather hot skincare sunscreen" style="border: 1px solid #e0e0e0; padding: 1.5rem; border-radius: 10px; background-color: #fff3e0;">   <h2 style="color: #e65100;">Protect Your Skin This Summer</h2>   <p>High temperatures mean high UV risk. Get <strong>20% off</strong> our dermatologist-recommended sunscreens and skin protection kits.</p>   <p>Offer valid this week only for areas with temperatures over 90°F.</p>   <a href="#" style="display:inline-block; margin-top:1rem; padding:0.75rem 1.5rem; background:#e65100; color:white; border-radius:5px; text-decoration:none;">Shop Sunscreen</a> </div>
```


## Vissa vädererbjudanden (tagg:fjäder)

Erbjudandetexten för ett lindrigt väder

```html
<div data-tags="ajo offer-mild-weather">   <h2 style="color: #2e7d32;">🌤️ Enjoy the Outdoors — Gear Up Now!</h2>   <p style="font-size: 1.1rem;">Perfect weather to be outside! Check out our selection of <strong>picnic sets, walking shoes, and fitness accessories</strong> for your next outdoor adventure.</p>   <p style="font-size: 1.1rem;">Get <strong>free shipping</strong> on all outdoor gear this week.</p>   <a href="#" style="display:inline-block;padding:0.75rem 1.5rem;background:#2e7d32;color:white;border-radius:6px;text-decoration:none;margin-top:1rem;">Explore Outdoor Picks</a> </div>
```

## Erbjudande om kalla väder (tagg:kall)

Erbjudandetext för kallt väder

```html
<div class="offer-content" style="text-align: center; padding: 1rem;">   <img src="https://raw.githubusercontent.com/gbedekar489/gbedekar489.github.io/main/weather/pexels-romanp-16170.jpg"         alt="Winter clothing"         style="width: 100%; max-width: 400px; border-radius: 12px; margin-bottom: 1rem;">   <h2>Cold Weather, Hot Deals 🧤</h2>   <p>Stay warm in style with our exclusive <strong>25% off</strong> winter outerwear. From puffer jackets to wool scarves, find the perfect layers to beat the chill.</p>   <p><strong>Use code:</strong> <code>WINTER25</code> at checkout</p>   <p><em>Limited time offer. While supplies last.</em></p> </div>
```

### Skapa samling

Navigera till **_Beslut -> Kataloger ->Samling->Skapa samling_**
Namnge samlingen **Weather-Related-Offers**

Gruppera erbjudandena i den här samlingen med regelverktyget.

