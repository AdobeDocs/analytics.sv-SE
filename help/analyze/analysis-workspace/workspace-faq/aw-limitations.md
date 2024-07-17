---
description: Förteckning över kända begränsningar i Adobe Analysis Workspace och dess tillhörande komponenter
title: Kända begränsningar i Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 520e970b-1387-4f70-985b-bfe397f4a21b
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# Kända begränsningar i Analysis Workspace

Här är en lista över kända begränsningar i Analysis Workspace och dess komponenter:

## Tabeller

* Datumjämförelsekolumner kan inte läggas till när datumintervall eller mätvärden används som rader i en tabell.
* Skapa mätvärden från markering är inaktiverat när segment används som rader i en tabell. Dessutom ska Skapa mätvärden från markering inte tillämpas på datumjusterade kolumner.
* Villkorsstyrd formatering för uppdelningsrader kan inte använda anpassade intervall.
* Tabellsummeringsrader kan inte trendas när inställningen för att beräkna summor har tillämpats (används vanligtvis för statiska radobjekt).
* [!UICONTROL Contribution Analysis] kan bara köras vid [!UICONTROL daily] granularitet _endast_. Det kan inte köras mot [!UICONTROL hourly], [!UICONTROL weekly] osv., data.

## Visualiseringar

* Visualiseringar som utnyttjar segmentering, som [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort] och [!UICONTROL Histogram], kan inte acceptera beräknade värden som indata.
* [!UICONTROL Flow]: Det går inte att använda in-/avslutningsdimensioner, t.ex. [!UICONTROL Entry page], i Flow.
* [!UICONTROL Cohort]: Icke-heltal kan inte användas som kohortvillkor.

## Panel

* Segmentjämförelse: Segmentet [!UICONTROL Everyone Else] skapas inte om en segmentmall används i den inledande släppzonen.

## Komponenter > Segment

* Vissa mått och mått kan inte segmenteras, som [!UICONTROL Occurrences], [!UICONTROL Unique Visitors] osv.
* Adhoc-segment som skapas i [panelens dropzone](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) är en typ av snabbfilter. De visas inte i den vänstra listen i Workspace eller segmentkomponenthanteraren, såvida de inte är offentliga. Mer information finns i [Snabbsegment](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

## Komponenter > Beräknade mått

* Beräknade mått kan inte användas i vissa visualiseringar. Se Visualiseringar ovan.
* Beräknade mått kan inte användas på panelen [!UICONTROL Attribution] eftersom beräknade mått i sig kan innehålla separata attribueringsmodeller.
* Vissa komponenter och operatorer är inte tillgängliga om ett beräknat mått skapas från Workspace (till skillnad från när det skapas från [!UICONTROL Components > Segments]). Exempel: [!UICONTROL IP Address].

## Komponenter > Datumintervall

* Anpassade datumintervall stöder inte [!UICONTROL This day last year], [!UICONTROL This day last month] osv.

## Komponenter > Virtuella rapportsviter

* När rapporttidsbearbetning är aktiverat stöds inte vissa komponenter. En fullständig lista finns i [Rapporttidsbearbetning](/help/components/vrs/vrs-report-time-processing.md).

## Komponenter > Alla komponenter > Rapportinställningar

* Vissa av inställningarna på sidan [!UICONTROL Report Settings] gäller inte. Analysis Workspace använder bara inställningarna [!UICONTROL Language/Currency/Encoding] längst ned: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding] och [!UICONTROL CSV Separator Character].

## Tillskrivning

* En delmängd av mätvärden stöds inte i [!UICONTROL Attribution]. En fullständig lista finns i [Vanliga frågor om attribuering](/help/analyze/analysis-workspace/attribution/faq.md).
