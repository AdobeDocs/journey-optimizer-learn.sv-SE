---
title: Skapa ett e-postmeddelande med orderbekräftelse
description: Testa dina kunskaper om hur du skapar och personaliserar transaktionsmeddelanden
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: eb31a78738ec32e4f468f620a96525714997ad04
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 0%

---


# Skapa ett e-postmeddelande med orderbekräftelse

![Orderbekräftelse](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| Utmaning | Skapa en orderbekräftelse via e-post |
|---|---|
| Persona | Resechef |
| Nödvändiga färdigheter | <ul><li>[Skapa e-postinnehåll med meddelanderedigeraren](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[Använd sammanhangsbaserad händelseinformation för personalisering](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[Använd hjälpfunktioner för personalisering](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| Resurser att hämta | [Orderbekräftelsetillgångar](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## The Story

Luma lanserar sin webbutik och vill säkerställa en bra kundupplevelse genom att skicka en orderbekräftelse via e-post när kunden har gjort en beställning.



## Din utmaning

Skapa en resa som skickar ett e-postmeddelande med en orderbekräftelse när en Luma-kund slutför en onlinebeställning.

>[!BEGINTABS]

>[!TAB Uppgift]

1. Skapa en resa med namnet&quot;ditt namn_orderbekräftelse&quot;
2. Använd händelsen: [!DNL LumaOnlinePurchase] som utlösare

3. Skapa e-post för orderbekräftelse:

* Kategoritransaktion - se till att du väljer transaktionens e-postyta
* Ämnesraden måste anpassas efter mottagarens förnamn och innehålla frasen&quot;Tack för ditt köp&quot;

I enlighet med Lumas varumärkesriktlinje ska e-postmeddelandet struktureras enligt följande - du kan använda **Luma - ordersammanfattning** och ändra den:

<table>
<tr>
<td>
  <div>
     <strong> Rubrikavsnitt</strong>
      </div>
  </td>
  <td>
    <strong>Luma logo</strong>
      <p>
     <li>luma_logo.png</li>
    <li>Storlek 35 %, centrerad vit bakgrund </li>
    <li>Den ska ha en länk till lumas webbplats: https://publish1034.adobedemo.com/content/luma/us/en.html</li>
    <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>Bekräftelsesektion
    </strong>
  </td>
  <td>
    <strong>Bild</strong><p>
    <li>luma-transactional-order-confirmation-2.jpg </li>
    <li>Marginal: Överkant, nederkant (10)<div>
    <p>
    <strong>Text</strong><p>
    <em>Hej {förnamn}</em><p>
    <li>Justering: vänster  </li>
   <li>Textfärg: rgb(101, 106, 119), font-size:14px</li>
    <li>Utfyllnad: vänster (95), höger (95)</li><div>
    <p>
     <em>Din beställning har lagts.
    <p>När ditt paket har skickats skickar vi ett e-postmeddelande med ett spårningsnummer så att du kan spåra din beställning.</p></em>
    </strong><p>
    <li>Justering: vänster  </li>
    <li>Textfärg: rgb(101, 106, 119), font-size:14px </li>
    <li>Utfyllnad: vänster (95), höger (95)</li><div>
    </a><p>
    <em>Leverera till:<p>
    <p>Förnamn Efternamn</p>
    Gata<p>
    Ort, delstat, postnummer</p></em>
    <strong>Knapp:</strong></p>
   <p><em>Visa order</em></p>
      <li>Bakgrundsfärg: rgb(25, 121, 195)</li>
      <li>Textfärg: Vit</li>
      <li>Ingen kantlinje</li>
      <li>Höjd: 40</li>
      <li>Lägg till en länk till en webbplats som du väljer </li>
      <li>Vänsterjustera mot texten ovan (spets: använd behållarmarginalen)</li>
  </td>
 <tr>
<td>
  <div>
     <strong>Avsnittet Orderinformation</strong>
      </div>
      <p>Tips:
      <li>Det här är sammanhangsbaserad händelseinformation.</li>
      <li>Använd hjälpfunktionen: Varje</li>
      <li>Växla till kodredigeringsformatet för att lägga till kontextdata. <li>
      <li>Lägg in informationen i behållare med DIV-taggar.</li>
  </td>
  <td>
    <strong>Sidhuvud</strong>
    <p>
    <em>Order {Purchase Order Number}</em>
    </p>
    <strong>Lista över beställda produkter:
  </strong>
  <p>Alla objekt ska formateras så här:
   <img alt="order" src="./assets/c2-order.png"> 
</p>
<strong>Produktbild:</strong>
<li>klass: vagnsstol
<li>format: border-box: min-height:40px</li>
<li>utfyllnad upptill och nedtill:20px</li>
<li>padding-left:80px</li>
<li>border-radius:0px</li>
<li>Använd som bakgrundsbild för behållaren</li>
<li>background-position: 0 % 50 %</li>
<li>bakgrundsstorlek: 60px</li>
<li>background-repeat: ingen upprepning</li>
<p>
<strong>Pris:</strong>
<li>Format = H5</li>
<li>style = box-size:border-box</li>
<li>margin-bottom:5px</li>
<li>margin-top:0px;</li>
<p>
<strong>Namn och antal:</strong>
<li>class=text-small</li>
<li>style=box-size: border-box</li>
<li>padding-top: 5 px</li>
<li>färg: rgb(101, 106, 119)</li>
<li>font-size:14px</li>
<p>
</td>
  </tr>
</table>


>[!TIP]
>
>För att du ska kunna felsöka dina resor bör du lägga till en alternativ sökväg till alla meddelandeåtgärder om en timeout eller fel inträffar.


>[!TAB Kontrollera ditt arbete]

Trigga den resa du skapade i testläge och skicka e-postmeddelandet till dig själv:

1. Visa dolda värden genom att klicka på ögonsymbolen:
   1. Klicka på T-symbolen (aktivera åsidosättning av parameter) i e-postparametrarna
      ![Åsidosätt e-postparametrar](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. Klicka i adressfältet
   3. På nästa skärm lägger du till din e-postadress inom parentes: *yourname@yourdomain* i uttrycksredigeraren och klicka på OK.
2. Testa resan
3. Utlös händelsen med följande parametrar:
   * Ange profilidentifieraren till: Jenna_Palmer9530@emailsim.io
   * Händelsetyp: commerce.purchase
   * Namn: Sprite Yoga Companion Kit
   * Antal: 1
   * Pris totalt: 61
   * Ordernummer: 6253728
   * SKU: 24-WG080
   * productImageURL: <https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/luma-yoga-kit-2.jpg>

Du bör få det personliga bekräftelsemeddelandet via e-post med den angivna produkten.

* Ämnesraden ska börja med din testprofils förnamn: Jenna
* Orderdetaljavsnittet ska fyllas i med den orderinformation du angav vid testningen
* Kundinformationen ska ha din testprofils ort och postnummer:

   43913 Thierer Terrace, Washington DC 2009


>[!TAB Godtagandevillkor]

** Resa

![Resa](/help/challenges/assets/c2-journey.png)


** E-post

**Ärenderad:**

{{ profile.person.name.firstName }}, tack för ditt köp!


**Mer detaljerad information:**

![Avsnittet Orderinformation](/help/challenges/assets/c2-order-detail-section.png)

Så här ska koden se ut:

Sidhuvud:

```javascript
Order: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

Produktförteckning:

Använd hjälpfunktionen &quot;each&quot; för att skapa produktlistan. Så här ska koden se ut:

```javascript
{{#each context.journey.events.1911672547.productListItems as|product|}}
<div class="cart-item-chair" style="box-sizing:border-box;min-height:40px;padding-top:20px;padding-bottom:20px;padding-left:80px;border-radius:0px;background-image:url({{product._wwfovlab065.productImageURL}});background-position:0% 50%;background-size:60px;background-repeat:no-repeat;">
<h5 style="box-sizing:border-box;margin-bottom:5px;font-size:16px;line-height:20px;margin-top:0px;">${{product.priceTotal}}.00</h5>
<div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">{{product.name}}</div><div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">Quantity: {{product.quantity}}</div></div><div class="divider-small" style="box-sizing:border-box;height:1px;margin-top:10px;margin-bottom:10px;background-color:rgb(209, 213, 223);"> </div>
{{/each}}

Total: ${{context.journey.events.1627840522.commerce.order.priceTotal}} 
```

**Kundinformationssektion**

![Kundadress](assets/c2-customer-information.png)

Personaliseringen bör se ut så här:

```javascript
{{profile.homeAddress.street1}}
{{profile.homeAddress.city}},{{profile.homeAddress.state}} {{profile.homeAddress.postalCode}}
```

>[!ENDTABS]