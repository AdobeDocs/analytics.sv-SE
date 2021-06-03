---
description: Det nya systemet för intelligenta aviseringar ger mer exakt kontroll över aviseringar och integrerar avvikelseidentifiering med varningssystemet.
title: Intelligenta aviseringar
uuid: ac8c9710-d245-46e9-b906-32d3bb0013c0
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 6%

---

# Intelligenta aviseringar

Det nya systemet för intelligenta aviseringar ger mer exakt kontroll över aviseringar och integrerar avvikelseidentifiering med varningssystemet.

## Översikt {#section_6AC8CA81DEA94E99B0F192B60D0FDF03}

>[!IMPORTANT]
>
>Intelligenta aviseringar är endast tillgängliga för Adobe [!DNL Analytics] Prime- och Adobe [!DNL Analytics] Ultimate-kunder.

Den nya Varningsbyggaren och Varningshanteraren ersätter den befintliga varningsfunktionen i Adobe [!DNL Analytics]. Med intelligenta aviseringar kan du

* Skapa aviseringar baserade på avvikelser (tröskelvärdena 90 %, 95 %, 99 %, 99,75 % och 99,9 %), % förändring, ovanför/nedanför).
* Förhandsgranska hur ofta en avisering utlöses.
* Skicka aviseringar via e-post eller SMS med länkar till automatiskt genererade Analysis Workspace-projekt.
* Skapa ”staplade” aviseringar som omfattar flera mätvärden i en enda avisering.

Det nya larmsystemet omfattar följande komponenter: Varningsbyggaren, Varningshanteraren, Förhandsgranskning av varning och bättre kontextbaserad åtkomst för att skapa varningar. Det gamla varningssystemgränssnittet kommer inte längre att vara tillgängligt, men aviseringarna kommer att migreras. Vissa äldre varningsfunktioner [är inte längre tillgängliga](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/alerts.html).

Det finns fyra sätt att komma åt Varningsverktyget:

* Genom att använda följande genväg i Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* Genom att gå direkt till Varningsverktyget:  **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]** .
* Genom att markera ett eller flera frihandtabellsradsobjekt högerklickar du och väljer **[!UICONTROL Create Alert from Selection]**. Detta öppnar varningsgeneratorn och fyller i byggaren i förväg med lämpliga mått och filter som tillämpas från tabellen. Du kan sedan redigera varningen vid behov.

   ![](assets/create-alert-from-selection.png)

* Gå till **[!UICONTROL More]** > **[!UICONTROL Add Alert]** från en [!UICONTROL Reports & Analytics]-rapport. Detta öppnar den nya varningsfunktionen och fyller i byggaren med lämpliga mått och filter från rapporten. Du kan sedan redigera varningen vid behov.

   ![](assets/add-alert.png)

## Frågor och svar: Hur aviseringar beräknas och utlöses {#section_1F3B1DAF21784306953B49AAD4C3DCAB}

Tröskelvärdena i % är standardavvikelser. Exempel: 95 % = 2 standardavvikelser och 99 % = 3 standardavvikelser. Beroende på hur lång tid du väljer används [olika modeller](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) för att beräkna hur långt bort (hur många standardavvikelser) varje datapunkt ligger från standardvärdet. Om du anger ett lägre tröskelvärde (till exempel 90 %) får du fler avvikelser än om du anger ett högre tröskelvärde (99 %). Tröskelvärdena 99,75 % och 99,99 % infördes specifikt för timgranulariteten så att den inte skulle utlösa så många avvikelser som möjligt.

<table id="table_B3AA85E1DE3543DCA34966A52E3CE4AB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>F: Hur långt tillbaka går avvikelseavkänningen för att fastställa dataavvikelser?</b> </p> </td> 
   <td colname="col2"> <p>Utbildningsperioden varierar beroende på vald granularitet. Mer information finns i Statistisk teknik som används i <a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md">avvikelseidentifiering</a>. Här är en sammanfattning: </p> 
    <ul id="ul_4F8C2A41F06C498DBF5E7AE5DE803773"> 
     <li id="li_E246091A3F1E484C8444AF4052FCA784">Månadsvis = 15 månader + samma intervall förra året </li> 
     <li id="li_CC014FB38AE1492B9647E990C29BFB3C">Vecka = 15 veckor + samma intervall förra året </li> 
     <li id="li_2517EE2097534324BE9C1B54CD181A62">Dagligen = 35 dagar + samma intervall förra året </li> 
     <li id="li_710BC8B009354542AA4962A59A646099">Varje timme = 336 timmar </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Om jag bara vill bli varnad om att jag bara uppför mig eller bara får ett visst beteende, kan jag då använda avvikelsefunktionen eller måste jag använda ett absolut värde?</b> </p> </td> 
   <td colname="col2"> <p>Om du använder ett absolut värde utlöses ändå varningar på dippar och taggar. Du kan inte isolera varningar för enbart dips eller bara spikes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Kan jag konfigurera aviseringar så att de endast utlöses under vissa timmar på dygnet (till exempel kontorstid jämfört med icke-arbetstid)?  </b> </p> </td> 
   <td colname="col2"> <p>Nej. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Kan jag få en tabell med de "förväntade värdena" som utgör den streckade linjen, eller någon typ av utdata av vad dessa värden är?  </b> </p> </td> 
   <td colname="col2"> <p>Inte på arbetsytan, men du kan göra det i Report Builder (se den här videon om <a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/report-builder/anomaly-detection-in-report-builder.html"  > Anomaly Detection i Report Builder </a>). </p> <p>Tänk på att Report Builder använder mindre sofistikerade avvikelsedetekteringsmetoder. Den använder en fast 30-dagars utbildningsperiod, fast 95-procentigt intervall. </p> </td> 
  </tr> 
 </tbody> 
</table>
