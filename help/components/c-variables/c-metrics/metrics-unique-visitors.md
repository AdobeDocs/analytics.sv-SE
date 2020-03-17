---
description: I version 14 avser en unik besökare en besökare som besöker en plats för första gången inom en viss tidsperiod. Den unika besökaren kan till exempel besöka en webbplats tio gånger i veckan, men om tidsperioden är vecka räknas en unik besökare bara en gång för den veckan. Efter den veckan kan den unika besökaren räknas igen för en annan tidsperiod.
title: Unika besökare
topic: Metrics
uuid: ae210698-99f9-485e-a640-c7520807adc7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Unika besökare

I version 14 avser en unik besökare en besökare som besöker en plats för första gången inom en viss tidsperiod. Den unika besökaren kan till exempel besöka en webbplats tio gånger i veckan, men om tidsperioden är vecka räknas en unik besökare bara en gång för den veckan. Efter den veckan kan den unika besökaren räknas igen för en annan tidsperiod.

## Skillnader mellan version 14 och 15

Version 14 tar inte bort dubbletter [!UICONTROL Visits] och [!UICONTROL Unique Visitors] mått från klassificeringsbaserade rapporter. Om till exempel två videoklipp har samma klassificering genereras två [!UICONTROL Visits] och [!UICONTROL Unique Visitors] i den klassificeringsbaserade rapporten av en enskild besökare som visade båda klippen.

Version 15 tar bort dubbletter [!UICONTROL Visits] och [!UICONTROL Unique Visitors] dubbletter från den klassificeringsbaserade rapporten. Detta är ett exaktare mått på [!UICONTROL Visits] och [!UICONTROL Visitors]men resulterar vanligtvis i en minskning av dina [!UICONTROL Visits] - och [!UICONTROL Unique Visitors] mätvärden för klassificeringsbaserade rapporter, jämfört med data som samlats in före uppgraderingen.

| Användningsområden | Beskrivning |
|---|---|
| Trafik | En besökare är en person som kommer till er webbplats. Kräver ingen beständig cookie. |
| Konvertering | En besökare är en person som kommer till er webbplats. Räknas när en konverteringsrelaterad händelse eller åtgärd inträffar. |
| Ad hoc-analys | En besökare är en person som kommer till er webbplats. Kräver ingen beständig cookie. |

Se [Unik besökarrapport - version 15 och ad hoc-analys](/help/components/c-variables/dimensionslist/reports-unique-visitors-v15-dsc.md).

>[!MORELIKETHIS]
>
>* [Dagliga unika besökare](/help/components/c-variables/c-metrics/metrics-daily-unique-visitors.md)

