---
description: Jämför Ad Hoc Analysis terminologi och uppgifter med Analysis Workspace.
title: Analysis Workspace jämfört med Ad Hoc Analysis
uuid: e4b3e40f-2b08-49a0-95f1-384d85c1640d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 2%

---


# Analysis Workspace jämfört med Ad Hoc Analysis

>[!IMPORTANT]
>
>Adobe flyttar Ad Hoc Analysis till livets slut den 1 mars 2021. [Läs mer](https://adobe.ly/discoverworkspace)

Jämför Ad Hoc Analysis terminologi och uppgifter med Analysis Workspace.

Analysis Workspace lägger in mycket av funktionaliteten i Ad Hoc Analysis i webbläsararbetsflödet. Även om vissa termer och funktioner fortfarande är desamma mellan produkterna finns det vissa nya termer och analysmetoder som introduceras i Analysis Workspace.

En teknisk jämförelse av viktiga funktioner och systemkrav mellan dessa två produkter finns [här](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/analytics-product-comparison.html).

## Jämförelse av nyckelterminologi {#section_6109406B83B043A18E46D38F130B1D2E}

| Ad Hoc Analysis | Analysis Workspace |
|--- |--- |
| Projekt | Arbetsyta eller projekt |
| Arbetsyta | Panel |
| Rapport | Frihandstabell |
| Diagram/diagram | Visualisering |
| Hierarki: Projekt > Arbetsytor > Rapporter | Hierarki: Projekt > Paneler > Tabeller |
| Mallar för rankade, trender och summor för rapporter | Visualisering av frihandstabell |
| Flödesmall | Flödesvisualisering |
| Utfall | Utfallsvisualisering |

## Jämförelse av viktiga uppgifter {#section_F31446F1DFA742D794A30D713E223440}

<table id="table_90D4461F04F34D70844C5E3FBB0BBE44"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col2" class="entry"> Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lägga till dimensioner och segment i måttkolumner </p> </td> 
   <td colname="col2"> <p>Du kan infoga dimensionella objekt eller segment som kolumnrubriker för att enkelt skapa jämförande vyer av mätvärden. <a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/metrics/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html"  > Video: Lägga till Dimensioner och statistik i ditt projekt i Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använd segment </p> </td> 
   <td colname="col2"> <p>Segment är tillgängliga under komponentmenyn Segment och kan användas på tre platser i Analysis Workspace: </p> 
    <ol id="ol_800D81FE2C84459B94B085C51E140330"> 
     <li id="li_F2E050902F9A4831BBA57F466E07DEAE">På <b>panelnivå</b>, som gäller för många visualiseringar i panelen. Det liknar att använda ett segment på en arbetsyta i Ad Hoc. </li> 
     <li id="li_2D88E43E0161485C95B08DC3C593EFD9">Som <b>rader i en tabell</b>. Det här liknar att lägga till segment i avsnittet Rader/uppdelningar i tabellbyggaren i Ad Hoc. </li> 
     <li id="li_102E1A1DAA9247C08FC46C5AB3D78113">Som <b>kolumner i en tabell</b>. Det här liknar att lägga till segment i avsnittet Kolumner i tabellverktyget i Ad Hoc Analysis eller att använda ett segment på rapportnivå i Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/applying-segments-to-your-analysis-workspace-project.html"  > Video: Använda segment i arbetsytan</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/panel-level-segments.html"  > Video: Använda segment på en panel</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skapa tillfälliga ("ad hoc") segment </p> </td> 
   <td colname="col2"> <p>Du kan <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > skapa tillfälliga ("ad hoc") segment</a> i Analysis Workspace genom att dra dimensionsobjekt till segmentsläppzonen högst upp på panelen. Dessutom kan du lägga till listrutefilter i panelens listruta för att skapa flera tillfälliga segment samtidigt, vilket möjliggör styrd projektinteraktion. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/ad-hoc-temporary-segments.html"  > Video: Ad hoc-segment i Analysis Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-drop-down-filters.html"  > Video: Listrutefilter i Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Välj datumintervall och kornighet </p> </td> 
   <td colname="col2"> <p>Datumintervall och detaljer finns på komponentmenyn Tid och kan användas på tre sätt: </p> 
    <ol id="ol_8B57C8A840694A879B22B809C58E7482"> 
     <li id="li_58FAE6A87B494A5C9007CD35BB101608">Datumintervall kan användas på kolumner/rader och åsidosätta det markerade paneldatumintervallet. Det liknar datumintervall på rapportnivå. </li> 
     <li id="li_85BB89EFF9C8466A992815BB7804EA37">Med Använd används ett datumintervall för alla visualiseringar inom en panel. Detta liknar datumintervallet för arbetsytan i Ad Hoc Analysis. </li> 
     <li id="li_BC18564A8FBB48F4A522BCAC60838759">Med Använd för alla paneler används ett datumintervall för alla paneler i ett Workspace-projekt. Detta liknar ett datumintervall för projekt i Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html"  > Video: Arbeta med datum i Analysis Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/creating-custom-date-ranges-in-analysis-workspace.html"  > Video: Anpassade datumintervall</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använd utrullnings- och konverteringsfunktioner </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  > Utfallsvisualiseringar </a> finns i Analysis Workspace på menyn Visualisering-komponent. Liknar Ad Hoc Analysis: </p> 
    <ol id="ol_625FF45AED4E403DBEE1A906282E8531"> 
     <li id="li_7B6C5F2682774641B82D2021786AE5C4">Utskicket kan omfatta ett besök eller en besökare och"Alla besök" kan också ingå. Utfall kan snabbt dras via högerklicksmenyn. </li> 
     <li id="li_CFBDDAB8E96A445DB0624640AEB25994">Dimensionsobjekt kan anslutas av en OR-operator (liknande grupper) och händelser kan användas i tratten. </li> 
     <li id="li_6638E6A62C744A27B2C066E5F9EC62C0">Nästa steg för genomgång och utfall kan också återges via högerklicksmenyn. </li> 
    </ol> <p>Dessutom tillåter Utfall i Analysis Workspace att <a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md"  > blandade dimensioner</a> inom steg blir en förbättring jämfört med Ad Hoc Analysis. Blandade dimensioner inom steg hanteras med operatorn AND. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization.html"  > Video: Utfallsvisualisering</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/multi-dimensional-fallout.html"  > Video: Använda flera bortfallsDimensioner</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/comparing-segments-in-fallout.html"  > Video: Jämföra segment i utfall</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Undersök flöde (bana) </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  > Flödesvisualiseringar </a> finns i Analysis Workspace på menyn Visualiseringskomponent. Liknar Ad Hoc Analysis: </p> 
    <ul id="ul_42D259310823496499F7D1474E1639AF"> 
     <li id="li_5DE6980EF66A49E58B8946A0422BC02C">Flödet kan omfatta ett besök eller en besökare. </li> 
     <li id="li_70A692266D32416BA3D70C1F8999F837">Nyckelstatistik visas i % sökvägsvyer. </li> 
    </ul> <p>Dessutom tillåter Flow <a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  > blandade dimensioner</a> och möjlighet att högerklicka och skapa ett segment, vilket är en förbättring jämfört med Ad Hoc Analysis. </p> <p>För närvarande kan inte Flow i Analysis Workspace <b>låta användare välja en success-händelse.</b> </li> 
    </ul> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization.html"  > Video: Översikt över Flödesvisualisering</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/text-wrapping-and-multi-dimensional-flow.html"  > Video: Flerdimensionellt flöde</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/expanding-on-flow-visualization.html"  > Video: Skapa segment från flöde</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utför oändliga uppdelningar </p> </td> 
   <td colname="col2"> <p>Med Analysis Workspace kan du gå ned till oändliga nivåer i webbläsaren. Segment och dimensioner kan blandas. Flera dimensionsobjekt kan brytas ned samtidigt genom att markera flera och sedan dra i en detaljdimension </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/dimension-breakdown-by-position.html"  > Video: Förbättrade uppdelningar</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skapa trenddata snabbt </p> </td> 
   <td colname="col2"> <p>Du kan snabbt visualisera data genom att klicka på diagramikonen i rapportraden. Dessutom länkas dessa snabba visualiseringar till källtabellen så att du kan klicka från ett värde till nästa i tabellen och se diagramuppdateringen automatiskt. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/dimension-graph-live-linking.html"  > Video: Dimension-Graph Live Linking</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Välj rapportsviter </p> </td> 
   <td colname="col2"> <p>Flera rapportsviter kan läggas till i ett enda projekt i Analysis Workspace.  </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/multiple-report-suites-in-analysis-workspace.html"  > Video: Flera rapportsviter på arbetsytan</a> </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribution IQ </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/attribution/overview.md"  > Med Attribution </a> IQin Analysis Workspace kan du lägga till många nya typer av attribueringsmodeller i frihandsritningar, visualiseringar och beräknade värden. Det innehåller över 10 regelbaserade och algoritmiska modeller. </p>  <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-attribution-iq-in-freeform-tables.html"  > Video: Attribution IQ i frihandstabeller</a> </p> </td> 
  </tr>  
 </tbody> 
</table>

