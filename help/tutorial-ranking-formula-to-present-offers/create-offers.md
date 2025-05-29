---
title: Skapa platsbaserade erbjudanden med målanpassning för postnummer
description: Ett erbjudande i beslut representerar ett enskilt personligt innehåll, till exempel ett meddelande, en bild, en befordran eller en rekommendation, som kan levereras till en användare baserat på definierade regler och villkor.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---


# Skapa platsbaserade erbjudanden med målanpassning för postnummer

Innan erbjudandena skapades utökades schemat för erbjudandeartikel så att det innehöll ett nytt fält: zipcode. Med det här anpassade fältet kan varje erbjudande taggas explicit med målets ZIP-kod, vilket möjliggör platsbaserad filtrering och rankning vid beslut.

Med schemat uppdaterat skapades två anpassade erbjudanden:

* Erbjudande 1:&quot;Flexibla investeringsplaner för Mira Mesa (92126)&quot;
Erbjudandet är skräddarsytt för unga yrkesverksamma och teknikfokuserade invånare år 92126 och främjar flexibla investeringsalternativ som ETF och gemensamma fonder som syftar till långsiktig tillväxt. Fältet för postnummer är inställt på 92126.

* Erbjudande 2:&quot;CD med hög kapacitet för Rancho Bernardo (92128)&quot;
Erbjudandet riktar sig till ekonomiskt stabila och pensionsklara individer 192128 och innehåller certifikat på hög kapacitet för insättning (CD) med garanterad avkastning. Fältet för postnummer är inställt på 92128.

Erbjudandena har nu berikats med platsmetadata, vilket gör dem berättigade till dynamiskt urval och rankning baserat på användarprofilens ZIP-koder i senare steg.

Följande skärmbild visar de anpassade attribut som lagts till i erbjudandeobjektschemat.

![offers-meta-data](assets/offers-meta-data.png)


## Erbjudande för 92126

Erbjudandetexten för erbjudanden i 92126 postnummer

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #f9f9f9; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Boost Your Financial Game with Smart Investment Options   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     In Mira Mesa (92126), ambition meets opportunity. Whether you're building wealth or just getting started, our     <strong>diversified investment plans</strong> — including <strong>tech-focused ETFs</strong> and     <strong>flexible mutual funds</strong> — are designed to grow with your goals.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Enjoy expert guidance, low fees, and strategies built for busy professionals who want more from their money — without the hassle.   </p>   <a href="#start-investing" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Start Investing Smarter   </a> </div>
```


## Erbjudande för 92128

Erbjudandetexten för erbjudanden i 92128 postnummer

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #fdfdfd; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Grow Your Savings with Confidence – Exclusive CD Rates for 92128   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Live in Rancho Bernardo? Take advantage of your financial momentum with our <strong>high-yield Certificates of Deposit</strong>, offering up to <strong>5.25% APY</strong>.     Designed for peace of mind and smart growth, our flexible CD options let you lock in guaranteed returns while enjoying the stability you deserve.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Whether you're planning retirement or simply securing your future, this offer is tailored for residents like you.   </p>   <a href="#explore-cd-options" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Explore CD Options   </a> </div>
```

## Generiskt erbjudande (Reserverbjudande)

Erbjudandetexten för det allmänna erbjudandet, utan någon postkod kopplad till erbjudandet

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #ffffff; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">
  <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">
    Invest Smarter: Build Wealth with Flexible Financial Plans
  </h2>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Looking to take control of your financial future? Our flexible investment solutions are designed to meet a wide range of goals — from growing savings to planning for retirement.
    Choose from diversified mutual funds, ETFs, and professionally managed portfolios, all with expert guidance and minimal hassle.
  </p>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Whether just starting out or optimizing an existing strategy, this offer provides the tools to invest with confidence — no matter where you live.
  </p>
  <a href="#explore-investment-plans" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">
    Explore Investment Plans
  </a>
</div>
```

Gruppera erbjudandena i en samling med namnet **_GenericOffers_**

Erbjudandena är tillgängliga för alla besökare, vilket innebär att det inte finns några strikta behörighetskrav. Därför blir rangordningsformeln avgörande för att avgöra vilket erbjudande som ska visas baserat på profilkontext.
Eftersom reglerna för behörighet inte filtrerar erbjudandena behandlas alla tre som kandidater.
Markeringsstrategin hämtar alla tre.
Rankningsformeln betygsätter dem baserat på profilattribut (som zipcode och annualIncome) för att välja den bästa.



