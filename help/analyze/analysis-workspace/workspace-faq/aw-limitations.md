---
description: Förteckning över kända begränsningar i Adobe Analysis Workspace och dess tillhörande komponenter
title: Kända begränsningar i Analysis Workspace
translation-type: tm+mt
source-git-commit: 00f36d8583ec9224337404cfd7fa020502d89c2d
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 1%

---


# Kända begränsningar i Analysis Workspace

Här är en lista över kända begränsningar i Analysis Workspace och dess komponenter:

## Tabeller

* Datumjämförelsekolumner kan inte läggas till när datumintervall eller mätvärden används som rader i en tabell.
* Skapa mätvärden från markering är inaktiverat när segment används som rader i en tabell. Dessutom ska Skapa mätvärden från markering inte tillämpas på datumjusterade kolumner.
* Villkorsstyrd formatering för uppdelningsrader kan inte använda anpassade intervall.
* Tabellsummeringsrader kan inte trendas när inställningen för att beräkna summor har tillämpats (används vanligtvis för statiska radobjekt).
* [!UICONTROL Contribution Analysis] kan köras med [!UICONTROL daily] granularitet _endast_. Den kan inte köras mot [!UICONTROL hourly], [!UICONTROL weekly]osv., data.

## Visualiseringar

* Visualiseringar som utnyttjar segmentering, som [!UICONTROL Fallout], [!UICONTROL Flow]och [!UICONTROL Cohort][!UICONTROL Histogram], kan inte acceptera beräknade värden som indata.
* [!UICONTROL Flow]: Ingångs-/avslutningsdimensioner, t.ex. [!UICONTROL Entry page], kan inte användas i Flow.
* [!UICONTROL Cohort]: Icke-heltal kan inte användas som kohortvillkor.

## Paneler

* Segmentjämförelse: Segmentet skapas inte om [!UICONTROL Everyone Else] en segmentmall används i den inledande släppzonen.

## Komponenter > Segment

* Vissa mätvärden och dimensioner kan inte segmenteras, t.ex. [!UICONTROL Occurrences][!UICONTROL Unique Visitors].
* De ad hoc-segment som skapas i [panelens dropzone](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html) visas inte i den vänstra listen i Workspace eller segmentkomponenthanteraren, såvida de inte publiceras. Detta kan du göra genom att redigera segmentet och markera **[!UICONTROL Make this segment public]**.

## Komponenter > Beräknade mått

* Beräknade mått kan inte användas i vissa visualiseringar. Se Visualiseringar ovan.
* Beräknade mått kan inte användas på [!UICONTROL Attribution] panelen eftersom beräknade värden i sig kan innehålla separata attribueringsmodeller.
* Vissa komponenter och operatorer är inte tillgängliga om ett beräknat mått skapas från arbetsytan (till skillnad från att skapas från [!UICONTROL Components > Segments]). Exempel, [!UICONTROL IP Address].

## Komponenter > Datumintervall

* Anpassade datumintervall har inte stöd för [!UICONTROL This day last year], [!UICONTROL This day last month]osv.

## Komponenter > Virtuella rapportsviter

* När rapporttidsbearbetning är aktiverat stöds inte vissa komponenter. En fullständig lista finns i [Rapporttidsbearbetning](/help/components/vrs/vrs-report-time-processing.md).

## Komponenter > Rapportinställningar

* Vissa av inställningarna på [!UICONTROL Report Settings] sidan gäller inte. Analysis Workspace använder bara inställningarna [!UICONTROL Language/Currency/Encoding] längst ned: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding]och [!UICONTROL CSV Separator Character].

## Attribution IQ

* En delmängd av mätvärden stöds inte i [!UICONTROL Attribution IQ]. En fullständig lista finns i Vanliga frågor om [Attribution IQ](../attribution/faq.md).
