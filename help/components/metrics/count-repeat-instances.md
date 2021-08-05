---
title: Antal upprepande instanser
description: Anger om upprepade instanser räknas i rapporter.
source-git-commit: e2b38b5b12290ca7da78d00be7b5733303115a03
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 0%

---


# Antal upprepande instanser

[!UICONTROL Count repeat instances] Anger om upprepade instanser räknas i rapporter eller projekt. När den här inställningen är aktiverad behandlas flera på varandra följande sidvyer till samma sida som flera sidvyer. När inställningen är Av räknas dessa sidvyer som en enda sidvy. Den här inställningen påverkar bara vissa mått, till exempel [!UICONTROL Single Page Visit].

I Rapporter och analyser går det inte att konfigurera den här inställningen. Upprepa instanser inkluderas som standard.
I arbetsytan kan du välja att [inkludera/exkludera upprepande instanser](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) under **[!UICONTROL Project]** > **[!UICONTROL Project info and settings]**. De inkluderas som standard.

>[!NOTE]
>Den här inställningen gäller inte för visualiseringar av typen [!UICONTROL Flow] eller [!UICONTROL Fallout]. I arbetsytan har [!UICONTROL Flow] en egen [inställning](/help/analyze/analysis-workspace/visualizations/c-flow/flow-settings.md) för att ta bort upprepningar. I Rapporter och analyser har flödesrapporten alltid tagit bort upprepade instanser som standard.
