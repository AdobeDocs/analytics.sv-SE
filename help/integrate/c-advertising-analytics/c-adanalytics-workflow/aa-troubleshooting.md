---
description: Felsöka och åtgärda problem som rör Advertising Analytics.
title: Felsöka Advertising Analytics
feature: Advertising Analytics
exl-id: 29e39a15-504a-4155-8794-aceb47046a54
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 1%

---

# Felsöka Advertising Analytics

* [Jag kan inte se min rapportserie i mappningsavsnittet](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md#section_9CAACDE6445C492DBAE542BA74DE6316)
* [Jag får ett fel vid autentisering till Google Ads-konto..](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md#section_C99EA9A1946E4908B36778A331142B84)

## Jag ser inte min rapportsvit i mappningsavsnittet {#section_9CAACDE6445C492DBAE542BA74DE6316}

Du försöker [konfigurera ett nytt Advertising-konto](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) och du ser inte din rapportsvit som visas i listrutan **[!UICONTROL Mapped report suites]**. Det finns två möjliga orsaker till detta:

<table id="table_271D7E817B4C44818717A47C3223E592"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Orsak </th> 
   <th colname="col2" class="entry"> Lösning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1. Rapportsviten är inte mappad till inloggningsanvändarens Experience Cloud Org ID. </p> </td> 
   <td colname="col2"> <p>Kontakta kundtjänst om du vill mappa rapportsviten till ett företags-ID.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2. Rapportsviten har inte etablerats för Advertising Analytics-rapportering. </p> </td> 
   <td colname="col2"> <p>Mer information finns i <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md"  > Provisionera Report Suite </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Jag får ett fel när jag autentiserar till Google Ads Account {#section_C99EA9A1946E4908B36778A331142B84}

<table id="table_F1C1192BF40C43CE8600B1BB417A7269"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Orsak </th> 
   <th colname="col2" class="entry"> Lösning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Autentisering till Google Ads med ett e-postkonto som även är länkat till ett Google Ads Manager-konto fungerar inte. </p> </td> 
   <td colname="col2"> <p>Använd en annan e-postadress som är länkad till samma Google Ads-konto för autentisering. </p> </td> 
  </tr> 
 </tbody> 
</table>
