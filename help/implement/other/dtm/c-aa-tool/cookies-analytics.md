---
description: Fältbeskrivningar för de globala cookies-inställningarna som används för att distribuera dynamisk tagghantering i Adobe Analytics.
keywords: Dynamic Tag Management;cookies;visitor id;visitor namespace;domain periods;fp domain periods;transaction id;cookie lifetime
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Cookies
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Cookies

Fältbeskrivningar för de globala Cookies-inställningarna som används för distribution [!UICONTROL Dynamic Tag Management] i Adobe Analytics.

*`Property`* > Redigera > Cookies

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Besökar-ID </td> 
   <td colname="col2"> <p>Unikt värde som representerar en kund både online och offline. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Namnutrymme för besökare </td> 
   <td colname="col2"> <p>Variabel som identifierar den domän som cookies är inställda på. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Domänperioder </td> 
   <td colname="col2"> <p>Domänen som Analytics-cookien <code> s_cc</code> och - <code> s_sq</code> koden ställs in på genom att bestämma antalet punkter i domänen för sidans URL. Den här variabeln används även av vissa plugin-program för att fastställa rätt domän för att ange plugin-programmets cookie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FP-domänperioder </td> 
   <td colname="col2"> <p>Variabeln <span class="term"> fpCookieDomainPeriods</span> är för cookies som anges av JavaScript (<code> s_sq</code>, <code> s_cc</code>, plugin-program) som är cookies från första part, även om implementeringen använder domänerna 2o7.net <span class="filepath"> eller</span> omtrdc.net <span class="filepath"></span> från tredje part. </p> <p>Se <a href="/help/implement/vars/config-vars/fpcookiedomainperiods.md"  > s.fpCookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transaktions-ID </td> 
   <td colname="col2"> <p>Unikt värde som representerar en onlinetransaktion som resulterade i offlineaktivitet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cookie-livstid </td> 
   <td colname="col2"> <p>Bestämmer en cookies livslängd. </p> </td> 
  </tr> 
 </tbody> 
</table>

