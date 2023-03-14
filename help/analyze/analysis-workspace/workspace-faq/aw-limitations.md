---
description: Förteckning över kända begränsningar i Adobe Analysis Workspace och dess tillhörande komponenter
title: Kända begränsningar i Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 520e970b-1387-4f70-985b-bfe397f4a21b
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Kända begränsningar i Analysis Workspace

Här är en lista över kända begränsningar i Analysis Workspace och dess komponenter:

## Tabeller

* Datumjämförelsekolumner kan inte läggas till när datumintervall eller mätvärden används som rader i en tabell.
* Skapa mätvärden från markering är inaktiverat när segment används som rader i en tabell. Dessutom ska Skapa mätvärden från markering inte tillämpas på datumjusterade kolumner.
* Villkorsstyrd formatering för uppdelningsrader kan inte använda anpassade intervall.
* Tabellsummeringsrader kan inte trendas när inställningen för att beräkna summor har tillämpats (används vanligtvis för statiska radobjekt).
* [!UICONTROL Contribution Analysis] kan köras på [!UICONTROL daily] granularitet _endast_. Den kan inte köras mot [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualiseringar

* Visualiseringar som utnyttjar segmentering, som [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort]och [!UICONTROL Histogram], kan inte acceptera beräknade värden som indata.
* [!UICONTROL Flow]: Ingångs-/avslutningsdimensioner, t.ex. [!UICONTROL Entry page], kan inte användas i Flow.
* [!UICONTROL Cohort]: Icke-heltal kan inte användas som kohortvillkor.

## Paneler

* Segmentjämförelse: The [!UICONTROL Everyone Else] segmentet skapas inte om en segmentmall används i den inledande släppzonen.

## Komponenter > Segment

* Vissa mått och mått kan inte segmenteras, t.ex. [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], osv.
* Adhoc-segment skapade i [panelens dropzon](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) visas inte i den vänstra listen i Workspace eller i Segment-komponenthanteraren, såvida de inte är offentliga. Detta kan du göra genom att redigera segmentet och markera **[!UICONTROL Make this segment public]**.

## Komponenter > Beräknade mått

* Beräknade mått kan inte användas i vissa visualiseringar. Se Visualiseringar ovan.
* Beräknade mått kan inte användas i [!UICONTROL Attribution] eftersom beräknade värden i sig kan innehålla separata attribueringsmodeller.
* Vissa komponenter och operatorer är inte tillgängliga om ett beräknat mått skapas från arbetsytan (till skillnad från om de skapas från [!UICONTROL Components > Segments]). Exempel, [!UICONTROL IP Address].

## Komponenter > Datumintervall

* Anpassade datumintervall stöds inte [!UICONTROL This day last year], [!UICONTROL This day last month], osv.

## Komponenter > Virtuella rapportsviter

* När rapporttidsbearbetning är aktiverat stöds inte vissa komponenter. En fullständig lista finns på [Bearbetning av rapporttid](/help/components/vrs/vrs-report-time-processing.md).

## Komponenter > Alla komponenter > Rapportinställningar

* Vissa av inställningarna på [!UICONTROL Report Settings] sidan gäller inte. Analysis Workspace använder bara [!UICONTROL Language/Currency/Encoding] inställningarna längst ned: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding]och [!UICONTROL CSV Separator Character].

## Attribution IQ

* En delmängd av mätvärden stöds inte i [!UICONTROL Attribution IQ]. En fullständig lista finns i [Vanliga frågor om Attribution IQ](../attribution/faq.md).
