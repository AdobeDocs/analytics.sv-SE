---
title: Använd attribut på analysarbetsytan
description: Lär dig var i Adobe Analytics ni kan använda attribuering.
translation-type: tm+mt
source-git-commit: 509f86a0346e909b62d237deea71c67b7ee950af

---


# Använd attribut på analysarbetsytan

Med attribuerings-IQ i Analysis Workspace kan ni jämföra alla attribueringsmodeller som stöds med varandra, visualisera viktiga marknadsföringssekvenser som leder till konvertering med avancerade bortfalls- och flödesvisualiseringar, enkelt trenda valfri marknadsföringskanal eller kampanj för att se resultatet över tid och hitta statistiska avvikelser i kanalens/kampanjens prestanda, varnas när resultatet faller eller ökar.

## Använd attribuering i frihandstabeller {#section_F2F72AE840EB4EA781302A559726E6F4}

Analysis Workspace Freeform Tables stöder attribueringsmodeller som kan användas på nästan alla mätvärden. Attributionsmodeller kan anges för kolumnmåtten Frihandstabell i Kolumninställningar:

1. Klicka på ikonen Inställningar (kugghjulet) i en kolumn i frihandstabellen.

   ![](assets/Column_Settings.png)

1. Under **[!UICONTROL Data Settings]**, kolla **[!UICONTROL Use non-default attribution model]**. Mer information om de olika attribueringsmodellerna finns i [Attribution IQ Overview](attribution.md).

   ![](assets/Attribution_Model_Selection.png)

## Tillämpa attribueringsmodeller på uppdelningar {#section_ED1E7532CF084B5AB0942BD80B4770C9}

Alla uppdelningar i en friformstabell kan också ha en attribueringsmodell som kan vara densamma eller en annan än den överordnade kolumnen. Du kan till exempel analysera linjära beställningar i dimensionen marknadsföringskanaler, men använda U-formade beställningar på specifika spårningskoder i en kanal. Om du vill redigera attribueringsmodellen som används för en uppdelning håller du bara muspekaren över nedbrytningsmodellen och klickar på Redigera:

![](assets/breakdown_settings.png)

## Jämför en attribueringsmodell med en annan {#section_1D74C09549CC4EC8A952A7392C76D375}

Om du snabbt och enkelt vill jämföra en attribueringsmodell med en annan högerklickar du på ett mätresultat och väljer **[!UICONTROL Add comparative attribution model]**:

![](assets/Comparative_Attribution_Model.png)

På så sätt kan du snabbt och enkelt jämföra en attribueringsmodell med en annan utan att behöva dra i ett mätresultat och konfigurera den två gånger.

## Panelen Attribution och visualiseringar {#section_6B02F28182F14ECC9FC5020F224726E6}

attribueringspanelen är ett enkelt sätt att skapa en analys som jämför olika attribueringsmodeller. För att komma åt panelen Attribution,

1. Klicka på panelikonen längst till vänster.
1. Dra panelen Attribution till analysarbetsyteprojektet.

   ![](assets/Attribution_Panel_1.png)

1. Lägg till ett framgångsmått som du vill attribuera och lägga till valfri kanaldimension till attribut mot (t.ex. marknadsföringskanaler eller interna kampanjer).

   ![](assets/attribution_panel2.png)

1. Välj de [attribueringsmodeller](attribution.md) du vill jämföra och uppslagsfönstret.

   Attribution Panel returnerar en mängd data och visualiseringar som hjälper er att bättre förstå hur era marknadsföringskanaler (eller andra dimensioner) fungerar tillsammans:

   ![](assets/attr_panel_vizs.png)

   Här följer en beskrivning av varje visualisering:

| Visualisering | Beskrivning |
|--- |--- |
| Totalt mått | Det totala antalet konverteringar som inträffade under rapporttidsperioden. Detta är de konverteringar som tilldelas för den dimension som du har valt. |
| Diagram över jämförelsetabell för måttattribut | Gör att du kan jämföra de tilldelade konverteringarna visuellt för var och en av dimensionsobjekten från den valda dimensionen. Varje stapelfärg representerar en unik attribueringsmodell som har valts. |
| Freeform-tabell för måttattribut | Visar samma data som stapeldiagrammet. Om du markerar olika kolumner eller rader i tabellen filtreras stapeldiagrammet samt flera andra visualiseringar i panelen. Den här tabellen fungerar på samma sätt som andra frihandstabeller i arbetsytan, vilket gör att du kan lägga till mått, segment, uppdelningar osv. |
| Dimensionsöverlappningsdiagram | Ett Venndiagram som visar de tre viktigaste måttposterna (t.ex. kanaler) och hur ofta de deltar tillsammans i en konvertering. Storleken på bubbelöverlappningen anger till exempel hur ofta konverteringar inträffade när en besökare exponerades för båda dimensionsobjekten (t.ex. kanaler). Om du väljer andra rader i friformstabellen uppdateras visualiseringen så att den återspeglar din markering. |
| Marknadsföringspunkter per resa | Ett histogram som anger antalet marknadsföringskontaktytor (eller någon dimension) som besökaren hade i rapportdatumintervallet. Det här är användbart om du vill se hur effektfull multitouch-attribuering är för din datauppsättning. Om nästan alla besökare bara har en enda kontaktyta kommer olika attribueringsmodeller inte att skilja sig något från varandra i resultaten. |
| Prestandainformation för marknadsföringskanal | Gör att du kan jämföra upp till tre attribueringsmodeller visuellt med en punktdiagram. |
| Marknadsföringskanalflöde | Gör att du kan se vilka kanaler som interagerar med de flesta, och i vilken ordning, på en besökares resa. |
