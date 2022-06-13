---
title: Antal upprepande instanser
description: Anger om upprepade instanser räknas i rapporter.
feature: Metrics
exl-id: e80544c0-f030-44e7-84c5-0902cd18d467
source-git-commit: c728df537c543eb171ba74e72b158f4200f1e828
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 0%

---

# Antal upprepande instanser

[!UICONTROL Count repeat instances] Anger om upprepade instanser räknas i rapporter eller projekt. När den här inställningen är aktiverad behandlas flera på varandra följande sidvyer till samma sida som flera sidvyer. När inställningen är Av räknas dessa sidvyer som en enda sidvy. Den här inställningen påverkar bara vissa mått, till exempel [!UICONTROL Single Page Visit].

I Rapporter och analyser går det inte att konfigurera den här inställningen. Upprepa instanser inkluderas som standard.
I arbetsytan kan du välja att [include/exclude repeat-instanser](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) under **[!UICONTROL Project]** > **[!UICONTROL Project info and settings]**. De inkluderas som standard.

>[!NOTE]
>Den här inställningen gäller inte för [!UICONTROL Flow] eller [!UICONTROL Fallout] visualiseringar. I arbetsytan [!UICONTROL Flow] har sin egen [inställning](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) för att ta bort upprepningar. I Rapporter och analyser har flödesrapporten alltid tagit bort upprepade instanser som standard.
