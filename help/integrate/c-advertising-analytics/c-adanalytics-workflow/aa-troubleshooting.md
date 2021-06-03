---
description: Felsöka och åtgärda problem som rör Advertising Analytics.
title: Felsöka Advertising Analytics
uuid: d0abe7cc-ed13-4d3d-87a6-f0d649c7ad2d
exl-id: 29e39a15-504a-4155-8794-aceb47046a54
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 4%

---

# Felsöka Advertising Analytics

* [Jag ser inte min rapportsvit i mappningsavsnittet](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md#section_9CAACDE6445C492DBAE542BA74DE6316)
* [Jag får ett fel vid autentisering till Google Adwords-konto..](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md#section_C99EA9A1946E4908B36778A331142B84)

## Jag ser inte min rapportsvit i mappningsavsnittet {#section_9CAACDE6445C492DBAE542BA74DE6316}

Du försöker [konfigurera ett nytt Advertising Account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) och du ser inte din rapportsvit som visas i listrutan **[!UICONTROL Select Report Suite]**. Det finns två möjliga orsaker till detta:

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
   <td colname="col2"> <p>Mer information finns i <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/report-suite-mapping.html"  > Mappa rapportsviter till en organisation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2. Report Suite har inte etablerats för Advertising Analytics-rapportering. </p> </td> 
   <td colname="col2"> <p>Mer information finns i <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md"  > Provisionera Report Suite</a>. </p> </td> 
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
