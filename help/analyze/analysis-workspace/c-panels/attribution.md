---
title: Attributionspanelen
description: Använda och tolka attribueringspanelen i Analysis Workspace.
feature: Attribution
role: User, Admin
exl-id: 96ce3cb9-7753-4ec0-b551-e70a1508e3b7
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Attributionspanelen

Panelen [!UICONTROL Attribution] är ett enkelt sätt att skapa en analys som jämför olika attribueringsmodeller. Det är en funktion i [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) som ger dig en dedikerad arbetsyta att använda och jämföra attribueringsmodeller.

>[!VIDEO](https://video.tv.adobe.com/v/23139/?quality=12)

## Skapa en attribueringspanel

1. Klicka på panelikonen till vänster.
1. Dra panelen [!UICONTROL Attribution] till ditt Analysis Workspace-projekt.

   ![Ny attribueringspanel](assets/Attribution_Panel_1.png)

1. Lägg till ett mätvärde som du vill attributera och lägg till en dimension till attributet mot. Exempel är marknadskanaler eller anpassade dimensioner, som interna kampanjer.

   ![Välj dimension och mått](assets/attribution_panel2.png)

1. Välj de [attribueringsmodeller och det uppslagsfönster](../attribution/models.md) som du vill jämföra.

1. Attributionspanelen returnerar en mängd data och visualiseringar som jämför attribuering för den valda dimensionen och det valda måttet.

   ![Attributvisualiseringar](assets/attr_panel_vizs.png)

## Attributvisualiseringar

* **Totalt mått**: Det totala antalet konverteringar som inträffade under rapporttidsperioden. Detta är de konverteringar som tilldelas för den dimension som du har valt.
* **Attribution Comparison Bar**: Jämför de tilldelade konverteringarna visuellt för alla dimensionsobjekt från den valda dimensionen. Varje stapelfärg representerar en distinkt attribueringsmodell.
* **Attributjämförelsetabell**: Visar samma data som stapeldiagrammet, representerat som en tabell. Om du markerar olika kolumner eller rader i den här tabellen filtreras stapeldiagrammet och flera andra visualiseringar i panelen. Den här tabellen fungerar på ungefär samma sätt som andra frihandstabeller i Workspace, vilket gör att du kan lägga till komponenter som mått, segment och uppdelningar.
* **Överlappningsdiagram**: Ett Venndiagram som visar de tre viktigaste dimensionsobjekten och hur ofta de deltar tillsammans i en konvertering. Storleken på bubbelöverlappningen anger till exempel hur ofta konverteringar inträffade när en besökare exponerades för båda dimensionsobjekten. Om du markerar andra rader i den angränsande friformstabellen uppdateras visualiseringen så att den återspeglar din markering.
* **Prestandainformation**: Gör att du kan jämföra upp till tre attribueringsmodeller visuellt med en punktdiagram.
* **Trended Performance**: Visar som standard trenden för konverteringsprestanda per attribueringsmodell för den första dimensionen som listas i den intilliggande frihandstabellen. Du kan välja olika dimensionsrader i frihandstabellen för att visa trenden för de valda dimensionerna (till exempel Total intäkt för varje attribueringsmodell för sociala kampanjer och betald sökning). Alternativt kan du markera celler i kolumnerna för alla kombination av mått och attribueringstyp i friformstabellen för att se hur prestanda efter dimensionsvärde har utvecklats för de angivna attribueringsmodellerna (t.ex. Total intäkt per marknadsföringskanal med hjälp av Last Touch- och First Touch-attribuering).
* **Flöde**: Gör att du kan se vilka kanaler som interagerar med de flesta, och i vilken ordning, under en besökares resa.
