---
title: Översikt över klassificeringar
description: Anpassa grupperingen av dimensionsobjekt.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 496b4891d447ed9dd091a6498a792146a2d5aceb
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# Översikt över klassificeringar

En klassificering är ett sätt att kategorisera Analytics-variabeldata och sedan visa data på olika sätt när du genererar rapporter. Du upprättar en relation mellan ett variabelvärde och metadata som är relaterade till det värdet. Klassificeringar kan användas för de flesta anpassade dimensioner, som spårningskod, props och eVars.

Adobe erbjuder flera sätt att klassificera data. Alla klassificeringsdata fungerar på samma sätt vid rapportering, och du kan kombinera alla dessa metoder som passar din organisation bäst. Adobe rekommenderar att du använder **Klassificeringsuppsättningar**.

* **Klassificeringsuppsättningar**: Skapa och hantera klassificeringar och deras regler i ett enda, förenklat gränssnitt.
* **Klassificeringsregler**: Skapa regler som tilldelar en given dimensionsuppgift till en klassificeringsdimensionsuppgift. Den här metoden för att klassificera data är bäst när en dimension ofta stöter på nya unika värden eller där manuell klassificering skulle vara frekvent och betungande.
* **Klassificeringsimportör**: Exportera ett mallkalkylblad med dimensionsobjekt på varje rad. Kolumner representerar varje klassificering för en dimension. Den här metoden för att klassificera data är bäst när alla dimensionsobjekt är kända och kräver ingen frekvent uppdatering.

När en dimension innehåller klassificeringsdata är en ny dimension tillgänglig i rapporter som bara innehåller klassificeringsdimensionsobjekt. Du kan till exempel klassificera [!UICONTROL Product IDs] med ytterligare produktattribut som produktnamn, färg, storlek, beskrivning och SKU. Förstärkning av rapporterings- och analysdata med ytterligare attribut ger djupare och mer komplexa rapporteringsmöjligheter.

En enda dimension kan ha flera klassificeringsdimensioner. Du kan till exempel klassificera spårningskod med sökmotor, nyckelord och kampanjkanal.

>[!VIDEO](https://video.tv.adobe.com/v/16853/?quality=12)
