---
title: Översikt över klassificeringar
description: Anpassa grupperingen av dimensionsobjekt.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 0%

---

# Översikt över klassificeringar

En klassificering är ett sätt att kategorisera Analytics-variabeldata och sedan visa data på olika sätt när du genererar rapporter.

Videoöversikt över [Analysklassificeringar](https://video.tv.adobe.com/v/16853/).

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > *`<Traffic or Conversion>`*

När du klassificerar etablerar du en relation mellan variabeln och de metadata som är relaterade till den variabeln. Klassificeringar används oftast i kampanjer. Data som samlas in med hjälp av variabelinformation (eVars, props och events) kan sammanställas genom att metadata tillämpas på de värden som samlas in i variablerna.

![Steginformation](assets/sub_class_create.png)

När de har klassificerats kan alla rapporter som du kan generera med nyckelvariabeln också genereras med de associerade attributen. Du kan till exempel klassificera [!UICONTROL Product IDs] med ytterligare produktattribut som produktnamn, färg, storlek, beskrivning och SKU. Förstärkning av rapporterings- och analysdata med ytterligare attribut ger djupare och mer komplexa rapporteringsmöjligheter.

När du har skapat klassificeringarna kan du använda de nya dataattributen i hela Adobe Analytics.

Här är en översiktsvideo om Adobe Analytics klassificeringar:

>[!VIDEO](https://video.tv.adobe.com/v/16853/?quality=12)

## Exempel på spårningskoder

Anta att ni i stället för att bara visa kampanjer med spårningskod vill se kampanjresultaten med sökmotorn, nyckelordet och kampanjkanalen. I stället för att avrunda konverteringsvariablerna för var och en av dem kan du skapa tre klassificeringar av kampanjvariabeln som representerar sökmotorn, nyckelordet och kampanjkanalen. Med den här strategin kan du se webbplatsens framgångshändelser med alla fyra variablerna, utan ytterligare taggning.

Rapportering och analys innehåller fördefinierade klassificeringar för spårningskodvariabeln, som erbjuder klassificeringsbaserade rapporter som kallas Creative Elements och Campaigns. Du måste konfigurera klassificeringar manuellt för alla andra konverterings- och trafikvariabler.

Se [Trafikklassificeringar](/help/admin/admin/c-traffic-variables/traffic-classifications.md) och [Konverteringsklassificeringar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html).

I följande tabell beskrivs de olika typer av klassificeringar som är tillgängliga och de variabeltyper som stöder dem. Granska informationen i [Allmän filstruktur](/help/components/classifications/importer/c-saint-data-files.md) innan datafiler överförs.

<table id="table_279728C28D9C40EE832ACC9F211B5F17"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>TYP </p> </th> 
   <th colname="col2" class="entry"> <p>TILLGÄNGLIGHET </p> </th> 
   <th colname="col3" class="entry"> <p>BESKRIVNING </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Text</span> </p> </td> 
   <td colname="col2"> <p>Konvertering och trafikvariabler </p> </td> 
   <td colname="col3"> <p>Textklassificeringar definierar en kategori där du kan gruppera variabeldata för rapportering. </p> <p>Om du till exempel säljer skjortor kanske du vill kategorisera skjortförsäljningen (konverteringar) efter färg, storlek och stil så att du kan generera rapporter som visar skjortförsäljningen ordnade efter dessa kategorier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Text aktiverad den</span> </p> <p>Obs! I underhållsutgåvan av Analytics Maintenance, 10 maj 2018, började Adobe begränsa funktionaliteten för datumaktiverade klassificeringar. Dessa klassificeringstyper har tagits bort från gränssnitten Admin och Klassificeringsimporter. Inga nya datumaktiverade klassificeringar kan läggas till. Befintliga klassificeringar kan fortfarande hanteras (överföras till, tas bort) via standardarbetsflödet för klassificering, och kommer även i fortsättningen att vara tillgängliga vid rapportering. </p> </td> 
   <td colname="col2"> <p>Konverteringsvariabler </p> </td> 
   <td colname="col3"> <p>Med en datumaktiverad textklassificering kan du tilldela datumintervall till en textklassificering. Detta används vanligtvis med kampanjklassificeringar så att du kan dra nytta av Gantt-diagramvyn i <span class="wintitle"> Kampanjer</span> rapport. </p> <p>Du kan inkludera faktiska kampanjdatum i den datafil som fyller i klassificeringsdata. </p> <p>Rapporter och analyser samlar in kampanjspårningskoder även om kampanjens slutdatum redan har passerats, men kampanjdata som samlas in efter kampanjens slutdatum är inte associerade med kampanjen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Numeriskt</span> <p>Obs! I underhållsutgåvan av Analytics Maintenance, 10 maj 2018, började Adobe begränsa funktionaliteten för numeriska klassificeringar. Dessa klassificeringstyper har tagits bort från gränssnitten Admin och Klassificeringsimporter. Inga nya numeriska klassificeringar kan läggas till. Befintliga klassificeringar kan fortfarande hanteras (överföras till, tas bort) via standardarbetsflödet för klassificering, och kommer även i fortsättningen att vara tillgängliga vid rapportering. </p> </p> </td> 
   <td colname="col2"> <p>Konverteringsvariabler </p> </td> 
   <td colname="col3"> <p>Med numeriska klassificeringar kan du använda fasta numeriska värden på <span class="wintitle"> Konvertering</span> rapporter. Dessa klassificeringar visas som mått i rapporter. </p> <p>När du funderar på om du ska lägga till en <span class="wintitle"> Numeriskt</span> måste det numeriska värdet vara fast och oföränderligt över tiden. </p> </td> 
  </tr> 
 </tbody> 
</table>
