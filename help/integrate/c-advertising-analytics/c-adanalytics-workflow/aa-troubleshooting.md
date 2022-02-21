---
description: Felsöka och åtgärda problem som rör Advertising Analytics.
title: Felsöka Advertising Analytics
feature: Advertising Analytics
exl-id: 29e39a15-504a-4155-8794-aceb47046a54
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 4%

---

# Felsöka Advertising Analytics

* [Jag ser inte min rapportsvit i mappningsavsnittet](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md#section_9CAACDE6445C492DBAE542BA74DE6316)
* [Jag får ett fel när jag autentiserar till Google Adwords Account...](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md#section_C99EA9A1946E4908B36778A331142B84)

## Jag ser inte min rapportsvit i mappningsavsnittet {#section_9CAACDE6445C492DBAE542BA74DE6316}

Du försöker [konfigurera ett nytt Advertising-konto](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) och du ser inte din rapportserie i **[!UICONTROL Select Report Suite]** nedrullningsbar lista. Det finns två möjliga orsaker till detta:

<table id="table_271D7E817B4C44818717A47C3223E592"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Orsak </th> 
   <th colname="col2" class="entry"> Lösning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1. Rapportsviten är inte mappad till inloggningsanvändarens Experience Cloud-Org-ID. </p> </td> 
   <td colname="col2"> <p>Kontakta kundtjänst om du vill mappa rapportsviten till en IMS-organisation.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2. Report Suite har inte etablerats för Advertising Analytics-rapportering. </p> </td> 
   <td colname="col2"> <p>Se <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md"  > Provisioneringsrapportsvit</a> för instruktioner. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Jag får ett fel vid autentisering till Google AdWords-konto {#section_C99EA9A1946E4908B36778A331142B84}

<table id="table_F1C1192BF40C43CE8600B1BB417A7269"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Orsak </th> 
   <th colname="col2" class="entry"> Lösning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Autentisering till Google AdWords med ett e-postkonto som även är länkat till ett AdWords Manager-konto fungerar inte. </p> </td> 
   <td colname="col2"> <p>Använd en annan e-postadress som är länkad till samma AdWords-konto för autentisering. </p> </td> 
  </tr> 
 </tbody> 
</table>
