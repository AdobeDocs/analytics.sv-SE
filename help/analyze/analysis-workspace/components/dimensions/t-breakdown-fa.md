---
description: Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.
keywords: Analysis Workspace
title: Dela upp dimensioner
feature: Dimensions
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 8%

---

# Dela upp dimensioner

Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.

Analysera data på obegränsade sätt efter just era behov och bygg frågor med hjälp av relevanta mätvärden, mått, segment, tidslinjer och andra analysvärden.

1. [Skapa ett projekt](/help/analyze/analysis-workspace/home.md) med en datatabell.
1. Högerklicka på ett radobjekt i datatabellen och välj **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Stegresultat](assets/fa_data_table_actions.png)

   Du kan dela upp mätvärden efter dimensionsobjekt eller målgruppssegment under valda tidsperioder. Du kan även gå ned mer i detalj.

   >[!NOTE]
   >
   >Antalet uppdelningar i tabellen är begränsat till 200. Den här gränsen kommer att öka för export av uppdelningar.

## Tillämpa attribueringsmodeller på uppdelningar

Alla uppdelningar i en tabell kan också ha en attribueringsmodell. Den här attribueringsmodellen kan vara densamma eller en annan än den överordnade kolumnen. Du kan till exempel analysera linjära beställningar i dimensionen marknadsföringskanaler, men använda U-formade beställningar på specifika spårningskoder i en kanal. Om du vill redigera attribueringsmodellen som används för en uppdelning håller du muspekaren över nedbrytningsmodellen och klickar på **[!UICONTROL Edit]**:

![Brytningsinställningar](assets/breakdown_settings.png)

Detta är det förväntade beteendet när du tillämpar attribueringsmodeller på uppdelningar eller redigerar dem:

* Om du tillämpar en attribuering när det inte finns några andra attribut gäller attribueringen för hela kolumnträdet.

* Om du lägger till en uppdelning efter att en attribuering har tillämpats, används standardvärdet för den angivna uppdelning som lades till, om den dimensionen har ett standardvärde. I annat fall används den uppdelning som görs från den överordnade kolumnen. Vissa dimensioner har en standardallokering.  Exempel: [!UICONTROL Time] dimensioner och [!UICONTROL Referrer] använd [!UICONTROL Same Touch]. Dimensionen [!UICONTROL Product] använder [!UICONTROL Last Touch]. Andra dimensioner saknar standardvärde och använder den överordnade kolumnallokeringen.

* Om det redan finns attribut i kolumnträdet påverkas bara den du redigerar om du ändrar attributet.

## Videor


>[!BEGINSHADEBOX]

En demonstrationsvideo finns i ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Lägga till mått och mätvärden i ditt projekt i Analysis Workspace](https://video.tv.adobe.com/v/30606?quality=12&learn=on){target="_blank"} .

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Arbeta med dimensioner i en frihandstabell](https://video.tv.adobe.com/v/40179?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [dimensionsuppdelningar efter position](https://video.tv.adobe.com/v/24033?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

