---
description: Använd varningar i Rapporter och analyser.
subtopic: Alerts
title: Larm
uuid: e1333a9b-eba0-45b7-b7e6-46e06190db64
feature: Alerts
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 6%

---


# Larm

## Larm {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

Som det nya varningssystemet för alla Adobe Analytics kan du med intelligenta aviseringar skapa och hantera aviseringar, med förhandsgranskning av aviseringar och regelbidrag. Ni kan

* Skapa aviseringar baserade på avvikelser (tröskelvärden på 90 %, 95 % eller 99 %), procentuell förändring, över/under).
* Förhandsgranska hur ofta en avisering utlöses.
* Skicka aviseringar via e-post eller SMS med länkar till automatiskt genererade Analysis Workspace-projekt.
* Skapa ”staplade” aviseringar som omfattar flera mätvärden i en enda avisering.

Du kan komma åt det nya larmsystemet från **[!UICONTROL More]** > **[!UICONTROL Alerts]** i alla rapporter i Rapporter och analyser.

Mer information finns i Analysis Workspace-dokumentationen [Intelligent Alerts](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html).

## Lägg till en avisering {#task_51187E8BF19544DDA9EF2057E6F11D35}

Steg som beskriver hur du lägger till en avisering i Adobe Analytics.

<!-- 

t_add_an_alert.xml

 -->

Navigera till den nya Varningsverktyget på menyn **[!UICONTROL Analytics]** > **[!UICONTROL Components]**. Du kan dock fortfarande komma åt den inifrån rapporter och analyser:

1. Öppna rapporten i Rapporter och analyser där du vill ange en avisering.
1. Klicka på **[!UICONTROL More]** > **[!UICONTROL Add Alert]**.
1. Du kommer nu till [nya Alert Builder](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/alert-builder.html).

## Visa eller redigera befintliga aviseringar {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

Aktivitetskontext

1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Alerts]**. Du kommer nu till den nya [Varningshanteraren](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/alert-manager.html).

## Migrering av äldre aviseringar {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

Flera funktioner i befintliga Analytics-varningar kommer inte att ingå i den nya Alert Manager som kommer att släppas (som en del av Analysis Workspace) hösten 2016. I följande tabell visas de inaktuella varningsfunktionerna och vissa varningsfunktioner som kommer att migreras till den nya varningshanteraren i ett annat format.

<!-- 

deprecated_alerts.xml

 -->

<table id="table_9307013B16AC4AC7BFC6F4C440FCFDE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion för äldre aviseringar </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Inaktuell eller migrerad? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Summor (alla objekt) </p> </td> 
   <td colname="col2"> <p>Skapa aviseringar för alla objekt i en dimensionsrapport. </p> </td> 
   <td colname="col3"> <p>I vissa fall, oavsett om du skapar en avisering för alla objekt i en dimensionsrapport eller om du ställer in aviseringen enbart för aggregerade mätvärden (inte tillämpade på en dimension), sker samma resultat. Anta att du skapar en månadsvarning för Alla artiklar för måttet Inkomster. Du får samma resultat om du bara kör intäktsrapporten och ställer in en månadsavisering på den. </p> <p>I det här fallet är den äldre aviseringen Totals (Alla objekt) inte längre tillgänglig och kommer att migreras till den senare, enklare versionen. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Top 1000 Items </p> <p> </p> </td> 
   <td colname="col2"> <p>Skapa aviseringar för de 1 000 främsta objekten i en rapport. </p> </td> 
   <td colname="col3"> <p>Inte längre tillgänglig i den nya aviseringshanteraren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tidsbaserade aviseringar om unika besökare (varje dag, varje vecka, varje månad osv. Unika besökare) </p> <p> </p> </td> 
   <td colname="col2"> <p>Skapa aviseringar för unika besöksrapporter varje timme, dag, vecka och månad. </p> </td> 
   <td colname="col3"> <p>I den nya Varningshanteraren stöds inte längre vissa tidsbaserade unika besökarvarningar. Om du till exempel tidigare kunde ange en veckoavisering för unika besökare varje dag, kan du ange en daglig, veckovis avisering. varning om att de unika besökarnas mått går ut. (Analysis Workspace har stöd för ett unikt besöksmått, men inte för varje dag/vecka/månad/osv.) Unika besökarvärden.) </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sök </p> </td> 
   <td colname="col2"> <p>Skapa aviseringar för en dimensionsrapport med en sökning tillämpad. Gäller endast för"Summor" ("Alla objekt") eller"Top 1000 Items". </p> <p> </p> </td> 
   <td colname="col3"> <p>Inte längre tillgänglig i den nya aviseringshanteraren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Rapporter som är specifika för rapporter och analyser </p> </td> 
   <td colname="col2"> <p>Skapa aviseringar för flera rapporter som finns i Rapporter och analyser och som inte motsvarar någon Analysis Workspace-rapport, till exempel 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">Sökvägslängd </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">Robotar </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">Tidszoner </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">Domäner på översta nivån </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>Inte längre tillgänglig i den nya aviseringshanteraren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Varningar med en ASI-plats som rapportsserie </p> </td> 
   <td colname="col2"> <p>Du kan inte längre skapa eller redigera ASI-kortplatser och de är inte tillgängliga för användning i Analysis Workspace. De stöds därför inte av de nya aviseringarna. </p> <p> </p> </td> 
   <td colname="col3"> <p>Inte tillgängligt i den nya aviseringshanteraren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Notifieringar med hjälp av deltagarstatistik </p> </td> 
   <td colname="col2"> <p> <a href="https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-participation.html"  > Deltagandestatistik  </a> finns i Rapporter och analyser, men är för närvarande inte tillgängligt i det nya varningssystemet i Analysis Workspace. </p> <p> </p> </td> 
   <td colname="col3"> <p>Inte tillgängligt i den nya aviseringshanteraren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Månadsaviseringar för anpassade kalenderrapportsviter </p> </td> 
   <td colname="col2"> <p>Detta påverkar bara kunder med aviseringar som har ställts in för rapportsviter som har <a href="https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/data-requests/date-ranges/custom-calendar.html"  > anpassade månadsstartdatum </a> (National Retail Federation/NRF och Custom Calendar types). </p> <p>Det påverkar inte aviseringar om gregorianska eller ändrade gregorianska kalenderrapportsviter. Tidigare skickades dessa varningar den första dagen i den gregorianska månaden (t.ex. 1 januari, 1 februari osv.). Detta fungerar inte med den nya funktionen för avvikelseidentifiering som tar hänsyn till data från föregående månader när avvikelser upptäcks. I framtiden kommer vi att lägga till stöd i vårt schemaläggningssystem för anpassade kalendrar så att både aviseringar och schemalagda projekt kan schemaläggas att skickas den första dagen i den anpassade kalendermånaden i stället för bara den första dagen i den gregorianska månaden. </p> <p> </p> </td> 
   <td colname="col3"> <p>Inte tillgängligt ännu i den nya aviseringshanteraren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aviseringar som inte har körts sedan september 2015. </p> </td> 
   <td colname="col2"> <p>Det finns flera skäl till att varningar inte skulle ha kunnat utföras sedan september 2015, bland annat: </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">Du klickade på Inaktivera i varningshanteraren. </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">Varningen stöter på fel och slutförs aldrig korrekt. </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> Dessa aviseringar migreras inte till det nya systemet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Varningar som markerats som"inaktiverade" </td> 
   <td colname="col2"> Det finns för närvarande inget sätt att inaktivera/återaktivera aviseringar i det nya användargränssnittet, men det finns planer på att lägga till den här funktionen. <p> </p> </td> 
   <td colname="col3"> Dessa aviseringar migreras inte till det nya systemet. </td> 
  </tr> 
 </tbody> 
</table>

