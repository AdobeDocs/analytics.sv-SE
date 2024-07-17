---
description: Migrering av besökare är en process där besökar-ID-cookie migreras från en domän till en annan.
keywords: Implementering av analyser
title: Migrering av besökare
topic-fix: Developer and implementation
feature: Analytics Basics
exl-id: d44628c8-902f-4e60-b819-41d5537407d8
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 0%

---

# Migrering av besökare

>[!NOTE]
>
>Om du redan har implementerat tjänsten Experience Cloud Visitor ID är respitperiod inte tillämplig för dig och bör inte aktiveras.

Migrering av besökare är en process där besökar-ID-cookie(er_vi) migreras från en domän till en annan.

Med migrering av besökare kan du bevara cookies för identifiering av besökare när du ändrar datainsamlingsdomäner. Domäner för datainsamling kan ändras av följande skäl:

* Flyttar från `2o7.net` till `adobedc.net`.

* Du implementerar [Experience Cloud Visitor ID-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html) och går från en CNAME/första parts datainsamlingsdomän till `adobedc.net`, `2o7.net` eller `omtrdc.net`

* Flyttar till en namngiven/förstapartsdatainsamling ( [cookies från första part)](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html).

* Gå från en CNAME till en annan (föränderliga domäner).

När migrering av besökare har konfigurerats och en användare besöker den nya domänen utan en cookie för besökar-ID, dirigeras servern om till det tidigare värdnamnet för datainsamling, hämtar eventuella tillgängliga cookies för besöks-ID och dirigerar sedan om tillbaka till den nya domänen. Om inget besökar-ID hittas på det tidigare värdnamnet genereras ett nytt ID. Detta inträffar endast en gång per besökare.

## Migreringsprocess för besökare {#process}

I följande tabell visas de uppgifter som krävs för migrering av besökare:

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Uppgift </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Så här kommer du igång:</b> <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"  > Kontakta kundtjänst </a> med de domäner du vill migrera och den migreringsperiod du vill aktivera (30, 60 eller 90 dagar). Se till att du inkluderar de osäkra och säkra domänerna. </p> </td> 
   <td colname="col3"> <p>Skapa en lista med syntaxen <i>exact</i> för de domäner du vill migrera till och migrera från. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>Migreringsvärdnamnen har konfigurerats på Adobe datainsamlingsserver. Kundtjänst meddelar när ändringen är klar så att du kan planera för nästa steg. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>6+ timmar efter konfigurationsändring</b>: Uppdatera variablerna <code> s.trackingServer</code> och <code> s.trackingServerSecure</code> i din Analytics JavaScript-kod så att de använder de nya datainsamlingsservrarna. </p> </td> 
   <td colname="col3"> <p>När du har gjort den här ändringen använder du felsökaren </a> för <a href="https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html"> Experience Cloud för att verifiera att Analytics-bildbegäran kommer till den uppdaterade datainsamlingsservern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Omedelbart efter att du har uppdaterat din Analytics-kod</b>: Testa webbplatsen för att verifiera att omdirigeringen till den tidigare datainsamlingsdomänen sker. </p> </td> 
   <td colname="col3"> <p>Använd en <a href="../implement/validate/packet-monitor.md">-paketövervakare</a> för att verifiera att när du ansluter till platsen för första gången, eller efter att du har rensat cookies, visas två 302 (omdirigerings) HTTP-statuskoder före HTTP-statuskoden 200 (OK). Om någon av dessa omdirigeringar misslyckas kontaktar du kundtjänst omedelbart för att säkerställa att migreringen är korrekt konfigurerad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Under hela migreringsperioden</b>: Låt DNS-posten för det föregående värdnamnet vara aktiv. </p> </td> 
   <td colname="col3"> <p>Det tidigare värdnamnet måste matchas via DNS, annars kommer inte cookie-migreringen att ske. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Uppgift | Beskrivning |
|--- |--- |
| Så här kommer du igång: Kontakta kundtjänst för de domäner du vill migrera och den migreringsperiod du vill aktivera (30, 60 eller 90 dagar). Se till att du inkluderar de osäkra och säkra domänerna. | Skapa en lista med exakt syntax för de domäner du vill migrera till och migrera från.<ul><li>example.112.2o7.net > metrics.example.com</li><li>example.102.112.2o7.net > smetrics.example.com</li></ul>Migreringsvärdnamnen har konfigurerats på Adobe datainsamlingsserver. Kundtjänst meddelar när ändringen är klar så att du kan planera för nästa steg. |
| 6+ timmar efter konfigurationsändring: Uppdatera variablerna `s.trackingServer` och `s.trackingServerSecure` i din Analytics JavaScript-kod så att de använder de nya datainsamlingsservrarna. | När du har gjort den här ändringen använder du [Experience Cloud-felsökaren](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) för att verifiera att Analytics-bildbegäran kommer till den uppdaterade datainsamlingsservern. |
| Omedelbart efter att du har uppdaterat din Analytics-kod: Testa webbplatsen för att verifiera att omdirigeringen till den tidigare datainsamlingsdomänen sker. | Använd en [paketövervakare](../implement/validate/packet-monitor.md) för att verifiera att när du ansluter till webbplatsen för första gången, eller efter att du har rensat cookies, visas två 302 (omdirigerings) HTTP-statuskoder före HTTP-statuskoden 200 (OK). Om någon av dessa omdirigeringar misslyckas kontaktar du kundtjänst omedelbart för att säkerställa att migreringen är korrekt konfigurerad. |
| För hela migreringsperioden: Låt DNS-posten för det föregående värdnamnet vara aktiv. | Det tidigare värdnamnet måste matchas via DNS, annars kommer inte cookie-migreringen att ske. |