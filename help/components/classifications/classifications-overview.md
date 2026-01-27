---
title: Klassificeringsöversikt
description: Anpassa grupperingen av dimensionsobjekt.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 1e209d4313c3d9d67f15a0c3a0939ceeb7a1ed31
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 0%

---

# Klassificeringsöversikt

En klassificering är ett sätt att kategorisera Analytics-variabeldata och sedan visa data på olika sätt när du genererar rapporter. Du upprättar en relation mellan ett variabelvärde och metadata som är relaterade till det värdet. Klassificeringar kan användas på de flesta anpassade dimensioner, till exempel [Spårningskod](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) och [eVars](/help/components/dimensions/evar.md).

* **Klassificeringsuppsättningar** är de primära komponenterna för att klassificera data. [Klassificeringsuppsättningar](/help/components/classifications/sets/overview.md) gör att du kan skapa och hantera klassificeringar i ett enda, förenklat gränssnitt.

* **Äldre klassificeringar** dokumenterar de äldre klassificeringsmetoderna för att klassificera data. Dessa metoder är föråldrade och kommer inte att vara tillgängliga efter den 31 augusti 2026.

   * [Klassificeringsregler](/help/components/classifications/crb/classification-rule-builder.md): Skapa regler som tilldelar ett givet dimensionsobjekt till ett klassificeringsdimensionsobjekt. Den här metoden för att klassificera data är bäst när en dimension ofta stöter på nya unika värden eller där manuella klassificeringar är vanliga och betungande.
   * [Klassificeringsimportör](/help/components/classifications/importer/c-working-with-saint.md): Exportera ett mallkalkylblad med dimensionsobjekt på varje rad. Kolumner representerar varje klassificering för en dimension. Den här metoden för att klassificera data är bäst när alla dimensionsobjekt är kända och kräver ingen frekvent uppdatering.

En enda dimension kan ha flera klassificeringsdimensioner. Du kan till exempel klassificera [!UICONTROL Product IDs] med ytterligare produktattribut, som produktnamn, färg, storlek, beskrivning och SKU. Var och en av dessa attribut skulle vara en separat klassificeringsdimension som tillhör samma överordnade dimension. Genom att förbättra dina rapporter med dessa attribut får du djupare och mer komplexa rapporteringsmöjligheter. När en dimension innehåller klassificeringsdata är klassificeringsdimensionen tillgänglig i rapporter som endast innehåller klassificeringsdimensionsobjekt. Alla överordnade dimensionsobjekt som inte innehåller något klassificeringsvärde grupperas under [Ospecificerade](/help/technotes/unspecified.md)
