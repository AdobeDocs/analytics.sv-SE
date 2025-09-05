---
description: Beskriver de tre alternativen för produktkompatibilitet.
title: Mätkompatibilitet
feature: Calculated Metrics
exl-id: 936d8139-7bbc-4de4-9e30-60ef5e12be08
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Mätkompatibilitet {#metrics-compatibility}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Produktkompatibilitet"
>abstract="Ett litet antal tillgängliga mätkriterier är inte kompatibla med alla Adobe Analytics-verktyg. Verktyg som är kompatibla med mätvärdena visas i den här listan. Om du vill att ett mätresultat ska vara kompatibelt med alla Adobe Analytics-verktyg kan du prova att redigera villkoret."

I den här artikeln förklaras de tre alternativen för produktkompatibilitet.

När du skapar beräknade mått i verktyget för beräknade mätvärden visas mätvärdena som kompatibla med ett eller flera verktyg i Adobe Analytics.


| Kompatibel med | Beskrivning |
| --- | --- |
| **[!UICONTROL Current Data]** | Med alternativet [!UICONTROL Include Current Data] i Adobe Analytics kan du visa de senaste Analytics-data, ofta innan alla data har bearbetats och slutförts. [!UICONTROL Current Data] visar de flesta mätvärden på några minuter och tillhandahåller åtgärdbara data för snabbt beslutsfattande. [!UICONTROL Current Data] stöder endast beräknade värden (de som innehåller multiplikation, division, addition och subtraktion.) [!UICONTROL Current Data] stöder inte avancerade beräknade värden (som innehåller segment eller funktioner). |
| **[!UICONTROL Fully Processed Data]** | Data som är fullständigt bearbetade och innehåller segment och klassificeringar. Om du hellre vill visa alla mätvärden efter att data har bearbetats fullständigt kan du inaktivera [!UICONTROL Current Data] genom att ta bort användare från gruppen Aktuella dataanvändare. |
| **[!UICONTROL Marketing Channel Reports]** | Mätvärden med första-touch-allokering är bara kompatibla med Marketing Channel-rapporter. |
