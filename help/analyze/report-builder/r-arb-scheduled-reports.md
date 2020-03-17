---
description: Fältbeskrivningar för den schemalagda aktivitetshanteraren.
title: Schemalagd aktivitetshanterare
topic: Report builder
uuid: dec259f0-2a04-4c94-abbc-5008cf2f1cb8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Schemalagd aktivitetshanterare

Fältbeskrivningar för den schemalagda aktivitetshanteraren.

Med Schemalagd Task Manager kan du visa en lista över befintliga schemalagda rapporter, tillsammans med deras mottagare, schemainformation och filformat. Du kan även återaktivera schemalagda arbetsböcker som inte kunde köras.

<table id="table_21B07A0B5F1D4435A4E882E45A7A6B6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Schemalagda rapporter, </b>flik </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rapportnamn </p> </td> 
   <td colname="col2"> <p>Anger namnet på den schemalagda aktiviteten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> E-post/FTP </p> </td> 
   <td colname="col2"> <p>Mottagarens e-postadress eller FTP-adress. </p> <p>Obs!  Om du väljer e-post bifogas rapporter som är större än 1 MB automatiskt till e-postmeddelandet som en ZIP-fil. Den här funktionen gör att storleken på bifogade filer hålls liten och inte kan inaktiveras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Publiceringsalternativ </p> </td> 
   <td colname="col2"> <p>Den här kolumnen visar Power BI om något av publiceringsalternativen <a href="/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md"  ></a> för Power BI har valts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schema </p> </td> 
   <td colname="col2"> <p>Typen av schemalagd leverans. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Filformat </p> </td> 
   <td colname="col2"> <p> Rapportens leveransformat, t.ex. Excel, PDF, HTML och så vidare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Återaktivera </p> </td> 
   <td colname="col2"> <p>När en schemalagd arbetsbok inte kan köras försöker Report Builder köra arbetsboken ytterligare två gånger var femton minut. Efter tre misslyckade försök inaktiverar Report Builder schemat och visar knappen <span class="wintitle"> Återaktivera</span> . När du återaktiverar en arbetsbok startar den schemalagda leveransen om från den tidpunkt den inaktiverades. </p> <p>Om en schemalagd arbetsbok till exempel inaktiverades för 14 dagar sedan och du återaktiverar den i dag, körs den för varje dag som saknas och levereras 14 gånger. Om du inte vill att arbetsboken ska levereras för de dagar som saknas kan du ta bort den schemalagda arbetsboken och sedan skapa en ny schemalagd arbetsbok med samma schemaläggningsparametrar. </p> <p> <p>Obs!  Du bör inte återaktivera en arbetsbok om du inte vet varför den har inaktiverats. En felsökningslösning är att ladda ned en inaktiverad arbetsbok och uppdatera den på klientsidan. Om du inte ser några fel bör du kunna återaktivera det. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Senast skickat </p> </td> 
   <td colname="col2"> <p>Datum och tid då rapporten senast skickades. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Fliken </b>Mottagare </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mottagarens e-postadress </p> </td> 
   <td colname="col2"> Rapportens e-postmottagare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rapporter </p> </td> 
   <td colname="col2"> Rapporten eller rapporterna som skickades till varje mottagare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Fliken Rapporthistorik</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filnamn </p> </td> 
   <td colname="col2"> Anger namnet på den schemalagda aktiviteten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datum </p> </td> 
   <td colname="col2"> Datum och tid då rapporten senast skickades. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> Statusen anger om rapporten skickades eller inte skickades. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E-post/FTP </p> </td> 
   <td colname="col2"> E-postadressen eller FTP-adressen till rapportmottagarens adress. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filformat </p> </td> 
   <td colname="col2"> Rapportens leveransformat, t.ex. Excel, PDF, HTML och så vidare. </td> 
  </tr> 
 </tbody> 
</table>
