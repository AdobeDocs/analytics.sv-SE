---
description: Fältbeskrivningar för den schemalagda aktivitetshanteraren.
title: Schemalagd aktivitetshanterare
uuid: dec259f0-2a04-4c94-abbc-5008cf2f1cb8
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---


# Schemalagd aktivitetshanterare

Med Schemalagd Task Manager kan du visa en lista över befintliga schemalagda rapporter, tillsammans med deras mottagare, schemainformation och filformat. Du kan även återaktivera schemalagda arbetsböcker som inte kunde köras.

| Fält | Beskrivning |
| --- | --- |
| **Fliken Schemalagda rapporter** |  |
| Rapportnamn | Anger namnet på den schemalagda aktiviteten. |
| E-post/FTP | Mottagarens e-postadress eller FTP-adress. **Obs!** Om du väljer e-post bifogas rapporter som är större än 1 MB automatiskt till e-postmeddelandet som en ZIP-fil. Den här funktionen gör att storleken på bifogade filer hålls liten och inte kan inaktiveras. |
| Publiceringsalternativ | Den här kolumnen visar Power BI om något av [publiceringsalternativen för Power BI](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/publish-powerbi/power-bi.html) är markerat. |
| Schema | Typen av schemalagd leverans. |
| Filformat | Rapportens leveransformat, t.ex. Excel, PDF, HTML och så vidare. |
| Återaktivera | När en schemalagd arbetsbok inte kan köras försöker Report Builder att köra arbetsboken ytterligare två gånger var femtonde minut. Efter tre misslyckade försök inaktiverar Report Builder schemat och visar knappen Återaktivera. När du återaktiverar en arbetsbok startar den schemalagda leveransen om från den tidpunkt den inaktiverades.  Om en schemalagd arbetsbok till exempel inaktiverades för 14 dagar sedan och du återaktiverar den i dag, körs den för varje dag som saknas och levereras 14 gånger. Om du inte vill att arbetsboken ska levereras för de dagar som saknas kan du ta bort den schemalagda arbetsboken och sedan skapa en ny schemalagd arbetsbok med samma schemaläggningsparametrar.   Obs!  Du bör inte återaktivera en arbetsbok om du inte vet varför den har inaktiverats. En felsökningslösning är att ladda ned en inaktiverad arbetsbok och uppdatera den på klientsidan. Om du inte ser några fel bör du kunna återaktivera det. |
| Senast skickat | Datum och tid då rapporten senast skickades. |
| **Fliken Mottagare** |  |
| Mottagarens e-postadress | Rapportens e-postmottagare. |
| Rapporter | Rapporten eller rapporterna som skickades till varje mottagare. |
| **Fliken Rapporthistorik** |  |
| Filnamn | Anger namnet på den schemalagda aktiviteten. |
| Datum | Datum och tid då rapporten senast skickades. |
| Status | Statusen anger om rapporten skickades eller inte skickades. |
| E-post/FTP | E-postadressen eller FTP-adressen till rapportmottagarens adress. |
| Filformat | Rapportens leveransformat, t.ex. Excel, PDF, HTML och så vidare. |

