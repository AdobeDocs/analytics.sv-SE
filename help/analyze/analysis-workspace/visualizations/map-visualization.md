---
description: Använd kartvisualisering i ett Workspace-projekt.
title: Karta
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 2%

---

# Karta {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="Karta"
>abstract="Den här visualiseringen representerar mätvärden genom att täcka över dem på en karta. Detta är användbart när du vill identifiera data i olika geografiska regioner."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_bubbles"
>title="Bubblor"
>abstract="Rita händelser med bubblor."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_heatmap"
>title="Heatmap"
>abstract="Rita händelser med hjälp av en värmekarta."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_I den här artikeln beskrivs kartvisualiseringen i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Det finns för närvarande ingen kartvisualisering i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

## Översikt {#section_19F740FAF08D47B1AF1EF239A74FC75C}

The Map Visualization in Analysis Workspace

* Gör att du kan skapa en visuell karta över alla mått (inklusive beräknade värden).
* Är användbart för att identifiera och jämföra mätdata för olika geografiska regioner.
* Kan hantera två datakällor: latitud/longitud från mobilanvändning eller geografisk dimension för webbanvändning.
* Stöd för export till PDF.
* Använder WebGL för bildvisning. Om grafikdrivrutinerna inte har stöd för WebGL-återgivning kan du behöva uppdatera drivrutinerna.

Här är en videoöversikt:

>[!VIDEO](https://video.tv.adobe.com/v/23559/?quality=12)

## Skapa en kartvisualisering {#section_61BBFA3A7BFD48DA8D305A69D9416299}

1. Dra **[!UICONTROL Map]** från listan med visualiseringar till en friformspanel:

   ![](assets/map-viz1.png)

1. Dra ett mätvärde från listan med mätvärden (inklusive beräknade värden).
1. Ange den datakälla som du vill rita från. (Den här dialogrutan visas bara om du har platsspårning aktiverad för mobilappsdata.)

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Mobile Lat/Long] | Det här alternativet representerar mobilappsdata. Det här alternativet visas bara om du har aktiverat det för din rapportserie i [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Report Suites] > (välj rapportserie) > [!UICONTROL Edit Settings] > [!UICONTROL Mobile Management] > [!UICONTROL Enable Location Tracking]. Det här är standardinställningen (om platsspårning är aktiverat). |
| [!UICONTROL Geographic Dimension] | Det här alternativet representerar geosegmenteringsdata om besökarens plats baserat på besökarens IP-adress. Dessa data omvandlas till [!UICONTROL Country], [!UICONTROL Region] och [!UICONTROL City]. Observera att det inte går till DMA- eller Zip-kodnivån. Nästan alla rapportsviter har den här dimensionen aktiverad. Om du inte har det kontaktar du Adobe kundtjänst för att aktivera geografiska rapporter. |

1. Klicka på **[!UICONTROL Build]**.

   Den första vyn som du ser är en World View med en bubbelkarta som liknar den här.

   ![](assets/bubble-world-view.png)

1. Nu kan du

   * **Zooma** in på kartan om du vill förstora vissa områden genom att dubbelklicka på kartan eller använda rullningshjulet. Kartan zoomas enligt var du har placerat markören. Genom zoominteraktion uppdateras den nödvändiga dimensionen (land > stat > stad) automatiskt utifrån zoomnivån.
   * **Jämför** två eller flera mappningsvisualiseringar i samma projekt genom att placera dem sida vid sida.
   * **Visa jämförelser mellan period och period (till exempel år över år)**:

      * Visa negativa tal: Om du till exempel ritar ett årligt mått kan kartan visa -33 % över New York.
      * Med mätvärden av typen procent beräknar klustring det genomsnittliga procentvärdet.
      * Ett grönt/rött färgschema: positiv/negativ

   * **Rotera** kartan i 2D eller 3D genom att hålla ned tangenten [!UICONTROL Ctrl] och flytta kartan.

   * **Växla** till en annan vy, till exempel värmekartan, med [inställningarna](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) som beskrivs nedan. Observera att bubbelvyn är standardinställningen.

1. **Spara** projektet om du vill spara alla kartinställningar (koordinater, zoomning, rotation).
1. Tabellen på frihand, nedanför visualiseringen, kan fyllas med genom att du drar i platsdimensioner och mått från den vänstra listen:

   ![](assets/location-dimensions.png)

## Inställningar för kartvisualisering {#section_5F89C620A6AA42BC8E0955478B3A427E}

Det finns två uppsättningar inställningar för kartan:

Ikonen **skiftnyckel** längst upp till höger visar den inledande dialogrutan där du kan ändra måttet och datakällan:

![](assets/map-wrench.png)

Om du klickar på **kugghjulsikonen** visas följande visualiseringsinställningar:

| Inställning | Beskrivning |
|--- |--- |
| Bubblor | Ritar händelser med bubblor. Ett bubbeldiagram är ett diagram med flera variabler och som är ett kors mellan ett punktdiagram och ett proportionellt ytdiagram. Det här är standardvyn. |
| Heatmap | Ritar händelser med hjälp av en heatmap. En heatmap är en grafisk representation av data där de enskilda värdena i en matris representeras som färger. |
| Stilar: Färgtema | Visar färgschemat för värmekartan och bubblorna. Du kan välja mellan Coral, Reds, Green eller Blues. Standardvärdet är Koral. |
| Format: Kartstil | Du kan välja mellan Basic, Streets, Bright, Light, Dark och Satellite. |
| Klusterradie | Grupperar datapunkter som ligger inom det angivna antalet pixlar. Standardvärdet är 50. |
| Anpassat maxvärde | Gör att du kan ändra tröskelvärdet för det högsta värdet för kartan. Om du justerar det här värdet justeras skalan för värdena för bubblor/heatmap (färg och storlek) i förhållande till det anpassade maxvärdet. |

## Skapa en heatmap med tidsdelning

Här är en video om ämnet:

>[!VIDEO](https://video.tv.adobe.com/v/26991/?quality=12)
