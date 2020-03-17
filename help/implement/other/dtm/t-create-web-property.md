---
description: En webbegenskap kan vara vilken gruppering som helst av en eller flera domäner och underdomäner med ett regelbibliotek, som ingår i en inbäddningskod.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;web property;property
title: Skapa webbegenskap
topic: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
translation-type: tm+mt
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Skapa webbegenskap

En webbegenskap kan vara vilken gruppering som helst av en eller flera domäner och underdomäner med ett regelbibliotek, som ingår i en inbäddningskod.

> [!NOTE] Endast en användare med administratörsbehörighet kan skapa en egenskap. Mer information om roller finns i [Skapa och hantera grupper i DTM](https://marketing.adobe.com/resources/help/en_US/dtm/groups.html) i produktdokumentationen för Dynamic Tag Management.

Du kan hantera och spåra dessa resurser med DTM. Anta till exempel att du har flera webbplatser som är baserade på en mall och vill spåra samma resurser på alla dessa webbplatser. Du kan använda en webbegenskap på flera domäner.

Allmän information om webbegenskaper och metodtips finns i [Webbegenskaper](https://marketing.adobe.com/resources/help/en_US/dtm/web_property.html) i produktdokumentationen för Dynamic Tag Management.

1. Navigera till din företagssida och klicka sedan på **[!UICONTROL Add Property]**.

   ![](assets/dtm-create-web-property.png)

1. Fyll i fälten:

   <table id="table_376D72251C4D4C4CA878D10C18D2532C"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Element </th> 
    <th colname="col2" class="entry"> Beskrivning </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Namn</span> </td> 
    <td colname="col2"> <p>Namnet på din egenskap. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> URL</span> </td> 
    <td colname="col2"> <p>Egenskapens bas-URL. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Den här webbplatsen sträcker sig över flera domäner </span> </td> 
    <td colname="col2"> <p>Du kan lägga till och ta bort domäner om du vill att besöksdata ska finnas kvar mellan domäner. Om det här alternativet är markerat kvarstår data för besöket i alla underdomäner. </p> <p>Med den här inställningen kan du ange hur du vill spåra trafik mellan dina associerade underdomäner eller domäner. Länkar till underdomäner behandlas som utgående länkar. Besök i underdomäner spåras separat. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. (Valfritt) Konfigurera [!UICONTROL Advanced Settings].

   <table id="table_6E687FBE6ACC4301BCCD837F4DCBB9C9"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Element </th> 
    <th colname="col2" class="entry"> Beskrivning </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Tillåt godkännande av flera regler</span> </td> 
    <td colname="col2"> <p>Tillåter flera regler för den här egenskapen att godkännas samtidigt. Standardgodkännandet tillåter endast godkännande med en regel. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Aktivera selektiv publicering</span> </td> 
    <td colname="col2"> <p>Anger om användare ska kunna välja vilka godkända regler som ska publiceras. Det här är standardalternativet. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Spårning av cookie-namn</span> </td> 
    <td colname="col2"> <p>Åsidosätter standardnamnet på spårningskakan. Du kan anpassa namnet som används i Dynamic Tag Management för att spåra din avanmälningsstatus för att ta emot andra cookies. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Timeout för tagg</span> </td> 
    <td colname="col2"> <p>Anger hur länge Dynamic Tag Management väntar på att en tagg ska utlösas innan timeout inträffar och taggbegäran avbryts. </p> <p> På grund av hur Dynamic Tag Management fungerar behöver du inte bekymra dig om att detta är ett högt antal. DTM har effektiva metoder som säkerställer att långsamma taggar inte påverkar användarupplevelsen. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Fördröjning för ankarpunkt</span> </td> 
    <td colname="col2"> <p>Anger hur länge Dynamic Tag Management väntar på att taggar ska aktiveras på klickade länkar innan de flyttas till nästa sida. Standardvärdet är 100 millisekunder. </p> <p>Längre fördröjningar ger bättre spårbarhet. Adobe rekommenderar en fördröjning på 500 millisekunder eller mindre, som användaren inte kommer att uppfatta. </p> <p>Dynamisk tagghantering väntar upp till den angivna tiden, men om beacon utlöses tidigare förkortas fördröjningen. (Det innebär att användaren inte alltid väntar hela fördröjningen.) </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Create Property]**.
