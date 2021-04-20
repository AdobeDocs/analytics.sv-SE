---
description: Förteckning över kända begränsningar i Adobe Analysis Workspace och dess tillhörande komponenter
title: Kända begränsningar i Analysis Workspace
feature: Workspace Basics
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---


# Kända begränsningar i Analysis Workspace

Här är en lista över kända begränsningar i Analysis Workspace och dess komponenter:

## Tabeller

* Datumjämförelsekolumner kan inte läggas till när datumintervall eller mätvärden används som rader i en tabell.
* Skapa mätvärden från markering är inaktiverat när segment används som rader i en tabell. Dessutom ska Skapa mätvärden från markering inte tillämpas på datumjusterade kolumner.
* Villkorsstyrd formatering för uppdelningsrader kan inte använda anpassade intervall.
* Tabellsummeringsrader kan inte trendas när inställningen för att beräkna summor har tillämpats (används vanligtvis för statiska radobjekt).
* [!UICONTROL Contribution Analysis] kan köras med  [!UICONTROL daily] granularitet  _endast_. Det kan inte köras mot [!UICONTROL hourly], [!UICONTROL weekly], osv., data.

## Visualiseringar

* Visualiseringar som utnyttjar segmentering, t.ex. [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort] och [!UICONTROL Histogram], kan inte acceptera beräknade värden som indata.
* [!UICONTROL Flow]: Ingångs-/avslutningsdimensioner, t.ex.  [!UICONTROL Entry page], kan inte användas i Flow.
* [!UICONTROL Cohort]: Icke-heltal kan inte användas som kohortvillkor.

## Paneler

* Segmentjämförelse: Segmentet [!UICONTROL Everyone Else] skapas inte om en segmentmall används i den inledande släppzonen.

## Komponenter > Segment

* Vissa mått och mått kan inte segmenteras, t.ex. [!UICONTROL Occurrences], [!UICONTROL Unique Visitors].
* De ad hoc-segment som skapas i [panelens dropzone](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html) visas inte i den vänstra listen i Workspace eller segmentkomponenthanteraren, såvida de inte är offentliga. Detta kan du göra genom att redigera segmentet och välja **[!UICONTROL Make this segment public]**.

## Komponenter > Beräknade mått

* Beräknade mått kan inte användas i vissa visualiseringar. Se Visualiseringar ovan.
* Beräknade mått kan inte användas i panelen [!UICONTROL Attribution] eftersom beräknade värden i sig kan innehålla separata attribueringsmodeller.
* Vissa komponenter och operatorer är inte tillgängliga om ett beräknat mått skapas från arbetsytan (till skillnad från när det skapas från [!UICONTROL Components > Segments]). Exempel, [!UICONTROL IP Address].

## Komponenter > Datumintervall

* Anpassade datumintervall stöder inte [!UICONTROL This day last year], [!UICONTROL This day last month] osv.

## Komponenter > Virtuella rapportsviter

* När rapporttidsbearbetning är aktiverat stöds inte vissa komponenter. En fullständig lista finns i [Rapporttidsbearbetning](/help/components/vrs/vrs-report-time-processing.md).

## Komponenter > Rapportinställningar

* Vissa inställningar på [!UICONTROL Report Settings]-sidan gäller inte. Analysis Workspace använder bara [!UICONTROL Language/Currency/Encoding]-inställningarna längst ned: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding] och [!UICONTROL CSV Separator Character].

## Attribution IQ

* En delmängd av mätvärden stöds inte i [!UICONTROL Attribution IQ]. En fullständig lista finns i [Vanliga frågor om Attribution IQ](../attribution/faq.md).
