---
description: Läs mer om fältbeskrivningarna för den schemalagda aktivitetshanteraren.
title: Om den schemalagda aktivitetshanteraren
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 0%

---

# Schemalagd aktivitetshanterare

{{legacy-arb}}

Med [!UICONTROL Scheduled Task Manager] kan du visa en lista över befintliga schemalagda rapporter, tillsammans med deras mottagare, schemainformation och filformat. Du kan även återaktivera schemalagda arbetsböcker som inte kunde köras.

## Pausa äldre schemalagda aktiviteter

Den 21 april 2022 introducerade vi förändringar av schemalagda arbetsuppgifter i Report Builder som en del av våra insatser för optimering av prestanda och leverans. Dessa ändringar inkluderar borttagning av möjligheten att ha schemalagda leveranser som &quot;upphör efter x förekomster&quot;. Som svar på flera kundförfrågningar om mer tid att utforska och implementera alternativ har vi beslutat att återställa det här alternativet i begränsad omfattning fram till **31 januari 2023**.

Du kommer även fortsättningsvis att kunna schemalägga aktiviteter per Report Builder och låta dem sluta efter högst 99 tillfällen. Observera att återställningen endast gäller för timuppgifter. &quot;slut efter x förekomster&quot; kommer inte att vara tillgängligt för alla andra leveransintervall (dag, vecka, månad och år).

Observera att detta alternativ upphör den 31 januari 2023.
Om du har frågor eller support kan du kontakta Adobe kundtjänst.

Den här pausen gäller särskilt **alla aktiviteter som skapats före 31 januari 2020**. Inga uppgifter, arbetsböcker eller data tas bort. Aktiviteter som är äldre än två år pausas och inga ytterligare schemalagda aktiviteter skickas.

Alla uppgifter som du vill återuppta skickandet kan återaktiveras. Logga in på Report Builder och starta [!UICONTROL Scheduled Task Manager]. Klicka på **[!UICONTROL Reactivate]** för den schemalagda aktivitet som du vill fortsätta skicka. Alla uppgifter som återaktiveras har standardvärdet 18 månader - såvida inte ett kortare förfallodatum har valts.

Dessutom kommer alla uppgifter med ett skapandedatum som är kortare än två år och som inte har något aktuellt förfallodatum (eller med ett förfallodatum som är längre än två år) att ha ett standardförfallodatum på 18 månader. Det nya förfallodatumet är 15 oktober 2023. Du kan redigera det här förfallodatumet så att det är mindre än 18 månader, men inte större. Aktiviteten pausas när den upphör att gälla. Du kan dock återaktivera uppgiften med ett nytt 18-månaders förfallodatum. Inga uppgifter, arbetsböcker eller data tas bort.

Syftet med den här pausen är att effektivt hantera och underhålla vår databas för schemalagda aktiviteter för att säkerställa optimal prestanda och leverans för nödvändiga uppgifter och arbetsböcker. Detta kommer att fungera i takt med att vår nya styrningspolitik utvecklas. Efter den 31 januari 2023 får alla uppgifter ett maximalt förfallodatum på 18 månader. Efter 18 månader kommer förfallna uppgifter att pausas och kan återaktiveras efter behov.

## Konfigurera schemalagda aktiviteter

| Fält | Beskrivning |
| --- | --- |
| **[!UICONTROL Scheduled Reports tab]** | |
| [!UICONTROL Report Name] | Anger namnet på den schemalagda aktiviteten. |
| [!UICONTROL Email/FTP] | Mottagarens e-postadress eller FTP-adress. **Obs!** Om du väljer e-post bifogas rapporter som är större än 1 MB automatiskt till e-postmeddelandet som en ZIP-fil. Den här funktionen gör att storleken på bifogade filer hålls liten och inte kan inaktiveras. |
| [!UICONTROL Publishing Options] | Den här kolumnen listar Power BI om något av [Power BI-publiceringsalternativen](https://experienceleague.adobe.com/docs/analytics/analyze/legacy-report-builder/publish-powerbi/power-bi.html?lang=sv-SE) har valts. |
| [!UICONTROL Schedule] | Typen av schemalagd leverans. |
| [!UICONTROL File Format] | Rapportens leveransformat, till exempel Excel, PDF, HTML och så vidare. |
| [!UICONTROL Reactivate] | När en schemalagd arbetsbok inte kan köras försöker Report Builder att köra arbetsboken ytterligare två gånger var femtonde minut. Efter tre misslyckade försök inaktiverar Report Builder schemat och visar knappen Återaktivera. När du återaktiverar en arbetsbok startar den schemalagda leveransen om från den tidpunkt den inaktiverades.<p>Om en schemalagd arbetsbok till exempel inaktiverades för 14 dagar sedan och du återaktiverar den i dag, körs den för varje dag som saknas och levereras 14 gånger. Om du inte vill att arbetsboken ska levereras för de dagar som saknas kan du ta bort den schemalagda arbetsboken och sedan skapa en ny schemalagd arbetsbok med samma schemaläggningsparametrar.<p>**Obs!** Återaktivera inte en arbetsbok om du inte vet varför systemet inaktiverade den. Om du vill felsöka hämtar du en inaktiverad arbetsbok och uppdaterar den på klientsidan. Om du inte ser några fel bör du kunna återaktivera det. |
| [!UICONTROL Last sent] | Datum och tid då rapporten senast skickades. |
| **Fliken Mottagare** | |
| [!UICONTROL Recipient email] | Rapportens e-postmottagare. |
| [!UICONTROL Reports] | Rapporterna som skickades till varje mottagare. |
| **Fliken Rapporthistorik** | |
| [!UICONTROL File Name] | Anger namnet på den schemalagda aktiviteten. |
| [!UICONTROL Date] | Datum och tid då rapporten senast skickades. |
| [!UICONTROL Status] | Statusen anger om rapporten skickades eller inte skickades. |
| [!UICONTROL Email/FTP] | E-postadressen eller FTP-adressen till rapportmottagarens adress. |
| [!UICONTROL File Format] | Rapportens leveransformat, till exempel Excel, PDF, HTML och så vidare. |
