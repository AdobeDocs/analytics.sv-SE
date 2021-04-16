---
description: Fältbeskrivningar för de allmänna inställningarna i dynamisk tagghanterare för distribution av Adobe Analytics.
keywords: Analysimplementering;implementeringsmetod;dynamisk tagghantering;dtm;allmänna inställningar;eu-kompatibilitet;teckenuppsättning;valutakod;spårningsserver;ssl tracking server
title: Allmänt
topic-fix: Developer and implementation
uuid: 93008719-6fb6-4e39-9a75-c937fe3247b9
exl-id: f63e83bf-be87-4ea2-ba04-5c152e5d16d3
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 1%

---

# Allmänt

Fältbeskrivningar för de allmänna inställningarna i DTM för distribution av Adobe Analytics.

**[!UICONTROL *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL General]**

<table id="table_DD8DA303698041D296DD5DB080AF7971"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Aktivera EU-kompatibilitet för <span class="keyword"> Adobe Analytics </span> </p> </td> 
   <td colname="col2"> <p> Aktiverar eller inaktiverar spårning baserat på EU:s sekretess-cookie. </p> <p>När en sida läses in kontrollerar systemet om en cookie med namnet <span class="filepath"> sat_track </span> är inställd (eller om det anpassade cookie-namnet som anges på sidan <span class="wintitle"> Redigera egenskap </span>). Tänk på följande information: </p> 
    <ul id="ul_42A6D728F0BC4FBABB0069EFB66DCB01"> 
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> Om cookien inte finns eller om cookien finns och är inställd på något annat än <span class="term"> true </span>, hoppas verktygsinläsningen över när den här inställningen är aktiverad. Detta innebär att alla delar av en regel som använder verktyget inte kommer att gälla. </p> <p>Om en regel har analyser på EU-kompatibilitet och tredjepartskod, och cookien är inställd på <span class="term"> false </span>, körs fortfarande tredjepartskoden. Analysvariablerna kommer dock inte att anges. </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> Om cookien finns men är inställd på <span class="term"> true </span> läses verktyget in normalt. </li> 
    </ul> <p>Du ansvarar för att ställa in <span class="filepath"> sat_track </span>-cookien (eller anpassad namngiven) till <span class="term"> false </span> om en besökare väljer bort. Du kan göra detta med anpassad kod: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"false"); 
     </code> </p> <p> Du måste också ha en mekanism för att ange att cookien ska vara <span class="term"> true </span> om du vill att en besökare ska kunna anmäla sig senare: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"true"); 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Teckenuppsättning </p> </td> 
   <td colname="col2"> <p>Visar tillgängliga teckenkodningsuppsättningar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valutakod </p> </td> 
   <td colname="col2"> <p>Visar valutakoder som stöds för markering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spårningsserver </p> </td> 
   <td colname="col2"> <p>Domänen där bildbegäran och cookie-filen skrivs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL-spårningsserver </p> </td> 
   <td colname="col2"> <p>Domänen där bildbegäran och cookie-filen skrivs. Används för säkra sidor. Om det inte definieras går SSL-data till <span class="term"> trackingServer </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datacenter </p> </td> 
   <td colname="col2"> <p>Datacentret Adobe som används för datainsamling. </p> </td> 
  </tr> 
 </tbody> 
</table>
