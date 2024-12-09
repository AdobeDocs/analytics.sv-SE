---
title: Klassificeringsöversikt
description: Anpassa grupperingen av dimensionsobjekt.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 0f5890679ea73c1bbea9f5d2939e89c6775c85da
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---

# Klassificeringsöversikt

En klassificering är ett sätt att kategorisera Analytics-variabeldata och sedan visa data på olika sätt när du genererar rapporter. Du upprättar en relation mellan ett variabelvärde och metadata som är relaterade till det värdet. Klassificeringar kan användas på de flesta anpassade dimensioner, till exempel [Spårningskod](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) och [eVars](/help/components/dimensions/evar.md).

Adobe erbjuder flera sätt att klassificera data. Alla klassificeringsdata fungerar på samma sätt vid rapportering, och du kan kombinera alla dessa metoder som passar din organisation bäst. Adobe rekommenderar att du använder **klassificeringsuppsättningar**.

* **Klassificeringsuppsättningar**: Skapa och hantera klassificeringar och deras regler i ett enda, förenklat gränssnitt.
* **Klassificeringsregler**: Skapa regler som tilldelar ett givet dimensionsobjekt till ett klassificeringsdimensionsobjekt. Den här metoden för att klassificera data är bäst när en dimension ofta stöter på nya unika värden eller där manuella klassificeringar är vanliga och betungande.
* **Klassificeringsimportör**: Exportera ett mallkalkylblad med dimensionsobjekt på varje rad. Kolumner representerar varje klassificering för en dimension. Den här metoden för att klassificera data är bäst när alla dimensionsobjekt är kända och kräver ingen frekvent uppdatering.

En enda dimension kan ha flera klassificeringsdimensioner. Du kan till exempel klassificera [!UICONTROL Product IDs] med ytterligare produktattribut, som produktnamn, färg, storlek, beskrivning och SKU. Var och en av dessa attribut skulle vara en separat klassificeringsdimension som tillhör samma överordnade dimension. Genom att förbättra dina rapporter med dessa attribut får du djupare och mer komplexa rapporteringsmöjligheter. När en dimension innehåller klassificeringsdata är klassificeringsdimensionen tillgänglig i rapporter som endast innehåller klassificeringsdimensionsobjekt. Alla överordnade dimensionsobjekt som inte innehåller något klassificeringsvärde grupperas under [Ospecificerade](/help/technotes/unspecified.md)
