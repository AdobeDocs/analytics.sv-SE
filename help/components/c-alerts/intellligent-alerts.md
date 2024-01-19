---
description: Det intelligenta larmsystemet ger mer exakt kontroll över varningar och integrerar avvikelseidentifiering med varningssystemet.
title: Intelligenta aviseringar
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 6%

---

# Intelligenta aviseringar

Det intelligenta larmsystemet ger mer exakt kontroll över varningar och integrerar avvikelseidentifiering med varningssystemet.

Här är en videoöversikt:

>[!VIDEO](https://video.tv.adobe.com/v/25446/?quality=12)

## Översikt {#section_6AC8CA81DEA94E99B0F192B60D0FDF03}

>[!IMPORTANT]
>
>Intelligenta aviseringar är tillgängliga för Adobe [!DNL Analytics] Prime och Adobe [!DNL Analytics] Endast de ultimata kunderna.

Med intelligenta aviseringar kan du

* Skapa aviseringar baserade på avvikelser (tröskelvärdena 90 %, 95 %, 99 %, 99,75 % och 99,9 %, % förändring i %, över/under).
* Förhandsgranska hur ofta en avisering utlöses.
* Skicka aviseringar via e-post eller SMS med länkar till automatiskt genererade Analysis Workspace-projekt.
* Skapa ”staplade” aviseringar som omfattar flera mätvärden i en enda avisering.

Varningssystemets komponenter är: Varningsbyggaren, Varningshanteraren, Förhandsgranska varning och bättre sammanhangsberoende åtkomst för att skapa varningar. Det gamla varningssystemgränssnittet kommer inte längre att vara tillgängligt, men aviseringarna kommer att migreras. Vissa äldre varningsfunktioner [är inte längre tillgängliga](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/alerts.html).

Det finns tre sätt att komma åt Varningsverktyget:

* Genom att använda följande kortkommando i Analysis Workspace:

  `ctrl (or cmd) + shift + a`
* Genom att gå direkt till Varningsverktyget:  **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]** .
* Genom att markera ett eller flera objekt på en frihandsritabell högerklickar och väljer du **[!UICONTROL Create Alert from Selection]**. Detta öppnar varningsgeneratorn och fyller i byggaren i förväg med lämpliga mått och filter som tillämpas från tabellen. Du kan sedan redigera varningen vid behov.

  ![](assets/create-alert-from-selection.png)


## Vanliga frågor: Hur aviseringar beräknas och utlöses {#trigger}

Tröskelvärdena i % är standardavvikelser. Exempel: 95 % = 2 standardavvikelser och 99 % = 3 standardavvikelser. Beroende på hur lång tid du väljer kan [olika modeller](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) används för att beräkna hur långt bort (hur många standardavvikelser) varje datapunkt ligger från normen. Om du anger ett lägre tröskelvärde (till exempel 90 %) får du fler avvikelser än om du anger ett högre tröskelvärde (99 %). Tröskelvärdena 99,75 % och 99,99 % infördes specifikt för timgranulariteten så att den inte skulle utlösa så många avvikelser som möjligt.

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
   <td colname="col2"> <p>Utbildningsperioden varierar beroende på vald granularitet. Se Statistiska tekniker som används i <a href="/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md">Analysidentifiering</a> för mer information. Här är en sammanfattning: </p> 
    <ul id="ul_4F8C2A41F06C498DBF5E7AE5DE803773"> 
     <li id="li_E246091A3F1E484C8444AF4052FCA784">Månadsvis = 15 månader + samma intervall förra året </li> 
     <li id="li_CC014FB38AE1492B9647E990C29BFB3C">Vecka = 15 veckor + samma intervall förra året </li> 
     <li id="li_2517EE2097534324BE9C1B54CD181A62">Dagligen = 35 dagar + samma intervall förra året </li> 
     <li id="li_710BC8B009354542AA4962A59A646099">Varje timme = 336 timmar </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Om jag bara vill bli informerad om ett beteende eller bara om ett beteende har ökat, kan jag då använda avvikelsefunktionen eller måste jag använda ett absolut värde?</b> </p> </td> 
   <td colname="col2"> <p>Om du använder ett absolut värde utlöses ändå varningar på dippar och taggar. Du kan inte isolera varningar för enbart dips eller bara spikes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Kan jag konfigurera aviseringar så att de endast aktiveras under vissa timmar på dygnet (till exempel kontorstid jämfört med icke-arbetstid)? </b> </p> </td> 
   <td colname="col2"> <p>Nej. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Kan jag få en tabell över de "förväntade värdena" som utgör den streckade linjen, eller någon typ av utdata av vad dessa värden är? </b> </p> </td> 
   <td colname="col2"> <p>Inte på arbetsytan, men du kan i Report Builder (se den här videon på <a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/report-builder/anomaly-detection-in-report-builder.html"  > Anomalidentifiering i Report Builder </a>). </p> <p>Tänk på att Report Builder använder mindre sofistikerade avvikelsedetekteringsmetoder. Den använder en fast 30-dagars utbildningsperiod, fast med 95 % intervall. </p> </td> 
  </tr> 
 </tbody> 
</table>
